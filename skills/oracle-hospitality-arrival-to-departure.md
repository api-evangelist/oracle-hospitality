---
name: Run a guest from arrival to departure
description: Pre-check-in, room assignment, check-in, in-stay folio charges and check-out in OPERA Cloud.
api: openapi/oracle-hospitality-property-v1-fof.json
operations:
  - getReservationSummaries
  - postPreCheckInReservation
  - verifyCheckinReservation
  - autoAssignRoom
  - assignRoomsAI
  - postCheckIn
  - postAdvanceCheckIn
  - deleteCheckin
  - postChargesAndPayments
  - getCheckDetails
  - postCheckOut
  - reinstateCheckOut
generated: '2026-07-28'
method: generated
source: openapi/oracle-hospitality-property-v1-fof.json, openapi/oracle-hospitality-property-v1-rsv.json, openapi/oracle-hospitality-property-v1-csh.json
---

# Arrival to departure

The front-desk lifecycle across three OPERA Cloud APIs: Front Desk Operations (`/fof/v1`), Reservation
(`/rsv/v1`) and Cashiering (`/csh/v1`). All hotel-scoped — send `x-hotelid`.

Authenticate first — see `oracle-hospitality-authenticate.md`.

## Steps

1. **Read the arrivals board** — `getReservationSummaries`
   (`openapi/oracle-hospitality-property-v1-fof.json`) for the day's expected arrivals, in-house and
   departures. `getReservationStatusStatistics` gives the counts.

2. **Pre-check-in (optional, digital flows)** — `postPreCheckInReservation`
   (`openapi/oracle-hospitality-property-v1-rsv.json`). Reverse with `deletePreCheckInReservation`.

3. **Assign a room** — `autoAssignRoom`, or `assignRoomsAI` where the property has AI room assignment
   enabled. Check the room is releasable first: `getRoomConditions` and `getOutOfOrderRooms`
   (`openapi/oracle-hospitality-property-v1-hsk.json`).

4. **Verify then check in** — `verifyCheckinReservation` validates the reservation is checkable, then
   `postCheckIn`. Use `postAdvanceCheckIn` for advance check-in and `postMassCheckIn` /
   `postMassAdvanceCheckIn` for a group arrival. `deleteCheckin` reverses a mistaken check-in.

5. **Post charges during the stay** — `postChargesAndPayments`
   (`openapi/oracle-hospitality-property-v1-csh.json`); read the folio back with `getCheckDetails` and
   adjust with `putBillingCharges`. Never handle raw card data: use Oracle Payment Interface —
   `postEcommTokenization` (`openapi/oracle-hospitality-property-v1-ecommtokenization.json`) and
   `openPaymentTokenExchange` (`openapi/oracle-hospitality-property-v1-tokenexchange.json`).

6. **Check out** — `postCheckOut`. `reinstateCheckOut` reverses it. `postAutoCheckoutReservations` runs
   the automated departure batch.

## Rules

- Payment operations are irreversible in effect even when a reversal operation exists — never retry a
  posting after a timeout without first reading the folio with `getCheckDetails`. OHIP has no
  idempotency key.
- `openPaymentTokenExchange` accepts a 2MB body; the default limit elsewhere is 100KB.
- A `404 OPICS-NOT_FOUND` from the token exchange means Oracle Payment Interface Cloud Service is not
  provisioned on that environment (product ID 14308 with Token Exchange Service selected) — an
  environment problem, not a request problem.
- A `403` on a front-desk call is usually the integration user's OPERA roles or a mismatched `x-hotelid`,
  not the token.
