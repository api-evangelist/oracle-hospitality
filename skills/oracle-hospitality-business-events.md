---
name: Consume OPERA Cloud Business Events
description: Subscribe to OPERA Cloud Business Events over the streaming WebSocket API, or poll them through the Integration Processor API.
api: openapi/oracle-hospitality-property-v1-int.json
operations:
  - getBusinessEvents
  - getBusinessEventsByExternalSystem
generated: '2026-07-28'
method: generated
source: https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_business_events.htm
---

# Consume Business Events

Business Events are OPERA Cloud resource changes — a reservation updated, a room status changed — each
carrying the **resource**, the **event name**, the **old value** and the **new value**. Two delivery
models exist. Oracle recommends streaming.

## Prerequisites

1. Create an **External System** and an **External Database** (one per chain or per property) in OPERA
   Cloud, and configure which Business Events are published for it.
2. Subscribe your application. The environment owner must approve a partner subscription in their own
   Developer Portal — except for a partner consuming from the partner sandbox or their own dedicated
   non-production environment, or a customer consuming from their own environment, where approval is
   automatic.
3. **Do not reuse an external system code between streaming and polling** — Oracle's documented warning is
   that events end up out of sequence.

## Streaming (push) — recommended

- GraphQL subscription over WebSocket against the per-tenant gateway. Schema:
  `graphql/oracle-hospitality-streaming-graphql-schema.json` (`Query`, `Mutation`, `Subscription`).
- Authorize the WebSocket, then send a `subscribe` message; the connection stays open.
- **Only one client** may consume a given chain, on a given gateway, with a given application key.
- Connect at least once every 24 hours. If you have been away longer, resume by supplying the `offset`
  parameter with the last offset you received.
- Leave at least 10,000 ms between sending a `complete` message and the next `subscribe`.
- Budget: 12 requests/minute sustained, 100 burst. Over-burst returns `429`.
- Use backpressure mode and the documented replay operations when you fall behind.

## Polling (pull) — fallback

- `getBusinessEvents` — `GET /int/v1/externalSystem/{extSystemCode}/hotels/{hotelId}/businessEvents`
- `getBusinessEventsByExternalSystem` — `GET /int/v1/externalSystem/{extSystemCode}/businessEvents`
- Maximum **20 events per call**, 300 requests/minute per gateway. That ceiling is why Oracle recommends
  streaming for anything busy.

## Rules

- Events are the change feed, not a query API. Read the changed resource back through the relevant
  Property API before acting on it.
- A hybrid split is legitimate and documented: stream the time-critical events (check-in) and poll the
  rest.
- There is no published AsyncAPI. The derived event and outbound-callback surface is captured in
  `asyncapi/oracle-hospitality-outbound-asyncapi.yml`.
