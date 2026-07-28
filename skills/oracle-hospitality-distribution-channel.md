---
name: Connect a distribution channel to OPERA Cloud
description: Onboard a property to a channel, shop and book through OPERA Cloud Distribution, and receive ARI notifications as a channel partner.
api: openapi/oracle-hospitality-distribution-v1-shop.json
operations:
  - getPropertyStatus
  - putPropertyStatus
  - getPropertyControls
  - getPropertiesSummary
  - getPropertyInfo
  - getRoomTypesInfo
  - getRatePlansInfo
  - getProperties
  - getPropertyOffers
  - getPropertyCalendar
  - postReservation
  - putReservation
  - getReservation
  - postCancelReservation
  - postReservationNotif
  - postInventory
  - postRates
  - postRestrictions
  - postContent
generated: '2026-07-28'
method: generated
source: openapi/oracle-hospitality-distribution-v1-*.json, openapi/oracle-hospitality-distribution-outbound-*.json
---

# Connect a distribution channel

OPERA Cloud Distribution is the ARI switch between a property and its channels. As a channel partner you
sit on **both sides** of the contract: you call Oracle's Distribution APIs, and you implement the outbound
endpoints Oracle calls on you.

## Before you start

Distribution access has a hard gate the Property APIs do not: you need an Oracle-issued **global Channel
Code**, requested from `hgbu_distribution_partner_rqs_grp@oracle.com` (five business day acknowledgement),
plus Oracle Partner Network membership and an Oracle Cloud Marketplace listing before you can touch a
customer's production environment. The code is issued once per partner and reused for every property that
connects to your channel. Send it on `x-channelCode`.

Authenticate with `getToken`
(`openapi/oracle-hospitality-distribution-v1-hdpbaoauth2.json`) — Distribution has its own OAuth path
(`/hdpba/oauth2/v1`) separate from the Property `/oauth/v1` path.

## Steps

1. **Confirm the property is live on your channel** — `getPropertyStatus`
   (`openapi/oracle-hospitality-distribution-v1-onboard.json`); `putPropertyStatus` updates it.
   `getPropertyControls` (`...-controls.json`) returns the property's distribution settings.

2. **Pull content** — `getPropertiesSummary`, `getPropertyInfo`, `getRoomTypesInfo`, `getRatePlansInfo`,
   `getRateRooms` (`openapi/oracle-hospitality-distribution-v1-content.json`). Where the hotel has mapped
   its hotel, room type and rate codes to channel-specific values the API returns your mapped codes;
   otherwise it returns native OPERA codes.

3. **Shop** — `getProperties`, `getPropertyOffers`, `getPropertyOffer`, `getPropertyAddons`,
   `getPropertyCalendar`, `getPropertyAlternateOffers`
   (`openapi/oracle-hospitality-distribution-v1-shop.json`).

4. **Book** — `postReservation` (`openapi/oracle-hospitality-distribution-v1-book.json`), or
   `postOnHoldReservation` to hold. `putReservation` modifies, `getReservation` reads,
   `postCancelReservation` cancels. If the reservation was already created and committed in your own
   system, use the notification path instead: `postReservationNotif`, `putReservationNotif`,
   `postCancelReservationNotif` (`openapi/oracle-hospitality-distribution-v1-resnotif.json`).

5. **Receive ARI.** Implement the outbound contracts Oracle calls on you —
   `postInventory`, `postRates`, `postRestrictions`
   (`openapi/oracle-hospitality-distribution-outbound-aripublication.json`, OpenTravel
   `OTA_HotelInvCountNotifRQ` / `OTA_HotelRateAmountNotifRQ` / `OTA_HotelRestrictionsNotifRQ` payloads) and
   `postContent` (`...-outbound-notification.json`). Respond success or error/warning — the property sees
   your response as the delivery status in OPERA. Oracle may also call **you**:
   `getExternalRoomTypes` and `getExternalRatePlans` (`...-outbound-lookup.json`).
   Full event surface: `asyncapi/oracle-hospitality-outbound-asyncapi.yml`.

6. **Manage the mapping from the hotel side** (if you also drive the property) — the Channel Configuration
   API (`openapi/oracle-hospitality-property-v1-chl.json`, 138 operations): `getChannels`, `postChannels`,
   `getChannelAccounts`, `postAmenitiesMapping`, `publishChannelAvailability`.

## Rules

- The 50 requests/second gateway budget is shared with every other integration on that property's gateway.
  ARI bursts compete with the hotel's own systems.
- Distribution reservations are not idempotent. On a timeout, `getReservation` before re-posting.
- OpenTravel shapes only survive on the ARI publication edge. Everything else — the shop, book and content
  payloads — is Oracle's proprietary model.
