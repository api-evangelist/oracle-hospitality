---
name: Shop availability and create a reservation
description: Search a property's availability and rates in OPERA Cloud, validate the rate, and create a reservation.
api: openapi/oracle-hospitality-property-v1-par.json
operations:
  - getHotelAvailability
  - searchHotelAvailability
  - getAlternateAvailability
  - getAvailabilityRatePlanInfo
  - validateRateInfo
  - getRateInfo
  - validatePolicies
  - postReservation
  - getHotelReservations
  - postCancelReservations
generated: '2026-07-28'
method: generated
source: openapi/oracle-hospitality-property-v1-par.json, openapi/oracle-hospitality-property-v1-rsv.json
---

# Shop availability and create a reservation (Property APIs)

The canonical guest-booking flow against OPERA Cloud through OHIP. Property APIs are hotel-scoped: every
call carries `x-hotelid`.

Authenticate first — see `oracle-hospitality-authenticate.md`.

## Steps

1. **Check availability** — `getHotelAvailability` (`openapi/oracle-hospitality-property-v1-par.json`) for
   the property, date range and occupancy. Use `searchHotelAvailability` when the criteria are too long for
   a GET (OHIP enforces a query-parameter limit and returns `414` when exceeded).

2. **If nothing is available, offer alternatives** — `getAlternateAvailability` /
   `searchAlternateAvailability` return alternate dates and room types.

3. **Pull the rate detail** — `getAvailabilityRatePlanInfo` for a single rate plan, or
   `getAvailabilityRatePlanInfoByMultipleRatePlans` to compare. Rate codes are hotel-specific
   configuration; resolve any code you do not recognise through the List of Values API
   (`openapi/oracle-hospitality-property-v1-lov.json`) rather than guessing.

4. **Validate before committing** — `validateRateInfo` and `getRateInfo`
   (`openapi/oracle-hospitality-property-v1-rsv.json`) confirm the rate is still sellable;
   `validatePolicies` checks deposit and cancellation policy applicability.

5. **Create the reservation** — `postReservation`
   (`openapi/oracle-hospitality-property-v1-rsv.json`). The response returns the created resource in a
   `Location` header. If the booking belongs to a group block, use `postReservationByBlock` instead.

6. **Confirm** — `getHotelReservations` to read it back, `getConfirmationLetters` /
   `postConfirmationLetters` to issue confirmation correspondence.

7. **Cancel when needed** — `postCancelReservations`, or `postCancelReservationByExtId` when you only hold
   your own external reference.

## Rules

- `postReservation` is **not idempotent** and OHIP has no idempotency key. On a timeout, search with
  `getHotelReservations` before retrying, or the guest gets two bookings.
- `400` responses name the offending fields; many values are constrained by that hotel's configured List
  of Values, so read the message and resolve the LOV rather than retrying the same payload.
- `postReservation` accepts a request body up to 2MB (the default elsewhere is 100KB).
- For anything bulk — thirty days of reservations, mass updates — switch to the asynchronous APIs
  (`openapi/oracle-hospitality-property-v1-rsvasync.json`); see
  `oracle-hospitality-bulk-extract.md`.
