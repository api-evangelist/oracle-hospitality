---
name: Drive housekeeping room status
description: Read the housekeeping board, set room conditions, manage out-of-order/out-of-service rooms and work task sheets.
api: openapi/oracle-hospitality-property-v1-hsk.json
operations:
  - getHousekeepingOverview
  - getHousekeepingDiscrepancies
  - getRoomConditions
  - setRoomCondition
  - putRoomRelatedStatus
  - getOutOfOrderRooms
  - postOutOfOrderRooms
  - completeOutOfOrderRooms
  - getOutOfServiceRooms
  - postOutOfServiceRooms
  - completeOutOfServiceRooms
  - getHouseKeepingTasks
  - autoGenerateTaskSheets
  - startServicingTaskRoom
  - completeServicingTaskRoom
  - completeTaskSheet
generated: '2026-07-28'
method: generated
source: openapi/oracle-hospitality-property-v1-hsk.json
---

# Housekeeping room status

The OPERA Cloud Housekeeping Service API (`/hsk/v1`, 60 operations) is what a housekeeping app, a
robotics/IoT integration or a room-status agent drives. Hotel-scoped — send `x-hotelid`.

Authenticate first — see `oracle-hospitality-authenticate.md`.

## Steps

1. **Read the board** — `getHousekeepingOverview` for the property's room-status picture;
   `getHousekeepingDiscrepancies` for rooms where the front-desk status and the housekeeping status
   disagree.

2. **Set a room's condition** — `getRoomConditions` then `setRoomCondition`. Use `putRoomRelatedStatus`
   for the combined status change and `setRoomCleaningPriority` / `putRoomCleaningPriority` to reorder
   the queue.

3. **Take a room out of service** — `postOutOfOrderRooms` (revenue-impacting) or
   `postOutOfServiceRooms` (not revenue-impacting); close them with `completeOutOfOrderRooms` /
   `completeOutOfServiceRooms`. Read the current sets with `getOutOfOrderRooms` / `getOutOfServiceRooms`.

4. **Maintenance** — `postRoomMaintenance`, `getRoomMaintenance`, `putRoomMaintenance`, then
   `resolveRoomMaintenance` (or `unResolveRoomMaintenance`) and `deleteRoomMaintenance`.

5. **Task sheets** — `autoGenerateTaskSheets` builds the day's sheets;
   `postHousekeepingAttendantSchedule` and `getHousekeepingAttendantsSchedule` handle attendants;
   `getHouseKeepingTasks` lists the work. Drive a room through
   `startServicingTaskRoom` → `completeServicingTaskRoom` (or `skipServicingTaskRoom` /
   `cancelServicingTaskRoom`), then `completeTaskSheet` / `completeTaskSheetSet`. `reopenTaskSheet`
   reverses it. `moveTaskRooms` reassigns rooms between sheets.

6. **Guest-facing housekeeping** — `setGuestHousekeepingServiceRequest` records a do-not-disturb or
   service request; `getReservationHousekeepingSchedule` and `postReservationHousekeepingTasks` manage
   per-reservation service schedules.

## Rules

- Room status changes are visible to the front desk immediately and affect what can be sold — treat
  `setRoomCondition` and `postOutOfOrderRooms` as consequential writes, not idempotent toggles.
- Room condition values are hotel-configured; resolve them through
  `openapi/oracle-hospitality-property-v1-lov.json` rather than hard-coding strings, or expect `400`.
- To react to housekeeping changes instead of polling, subscribe to Business Events — see
  `oracle-hospitality-business-events.md`.
