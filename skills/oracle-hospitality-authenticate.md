---
name: Authenticate to the Oracle Hospitality Integration Platform
description: Obtain an OHIP OAuth token and assemble the header set every Oracle Hospitality API call requires.
api: openapi/oracle-hospitality-property-v1-oauth.json
operations:
  - getToken
generated: '2026-07-28'
method: generated
source: https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_authenticating_to_oracle_hospitality_property_apis_ocim.htm
---

# Authenticate to OHIP

Every Oracle Hospitality API call needs two credentials at once: an OAuth 2.0 bearer token **and** an
application key. Neither is self-serve — both come from the tenant-scoped OHIP Developer Portal after the
partner or hotelier has been onboarded.

## Before you start

Collect from the Developer Portal **Environments** page:

| Value | Where it comes from |
|---|---|
| Gateway URL | Environments page — per tenant, not published |
| `AppKey` | Application details, Developer Portal |
| `ClientId` / `ClientSecret` | Environments page |
| `Scope` | Environments page (`urn:opc:hgbu:ws:_myscopes_` for OCIM environments) |
| `EnterpriseId` | Supplied by the customer |
| `HotelId` | Supplied by the hotel — the OPERA property code |
| Integration user + password | SSD environments only; the user must hold the `WSACCESS` role |

## Steps

1. **Work out which authentication scheme the environment uses.** Environments migrated to OPERA Cloud
   Identity Management (OCIM) use the `client_credentials` grant. Older Self Service Deployment (SSD)
   environments use the Resource Owner Group scheme — the `password` grant with the OPERA integration
   user's credentials. Using pre-migration `clientId`/`clientSecret` values on a migrated environment is a
   documented cause of `403`.

2. **Call `getToken`** against `<gateway URL>/oauth/v1/tokens`.
   - `Authorization: Basic base64(clientId:clientSecret)`
   - `x-app-key: <AppKey>`
   - `Content-Type: application/x-www-form-urlencoded`
   - Body: `grant_type=client_credentials&scope=urn:opc:hgbu:ws:_myscopes_` (OCIM), or
     `grant_type=password&username=<integration user>&password=<password>` (SSD).

3. **Attach the token to every subsequent call**, together with the headers OHIP requires:
   - `Authorization: Bearer <token>`
   - `x-app-key: <AppKey>`
   - `x-hotelid: <HotelId>` on property-scoped operations
   - `x-channelCode: <ChannelCode>` on OPERA Cloud Distribution operations
   - `x-request-id: <GUID>` — optional but send it; it is what support asks for
   - `Accept: application/json` (the RnA GraphQL APIs want
     `multipart/mixed; deferSpec=20220824, application/json`)

4. **Keep total header size under 8KB.** That budget covers the token, the application key, the request id
   and everything else. Oversized headers are rejected.

## Failure modes

| Status | Meaning |
|---|---|
| `401`, no body | Token expired or invalid, or the application key is invalid |
| `402` `invalid_grant` | Wrong integration-user password (SSD) |
| `403` `Unauthorized to access the resource` | Integration user missing `WSACCESS`, unapproved user, or wrong `x-hotelid` |
| `403` `No Subscribed Plan or API found` | The application is not subscribed to the API being called |
| `403` `Forbidden` | IP allow listing is on and your source address is not listed |

Full catalogue: `errors/oracle-hospitality-problem-types.yml`.

## Rules

- **Do not retry blindly.** OHIP publishes no idempotency-key contract
  (`conventions/oracle-hospitality-conventions.yml`), so a retried write may duplicate.
- Respect the gateway budget: 50 requests/second sustained, 100 burst, **shared across every consumer on
  that gateway**. Over-burst returns `429`; sustained overage silently delays you.
- When a partner service is suspended and later resumed, the application key is **regenerated** — treat the
  key as rotatable configuration, never a constant.
