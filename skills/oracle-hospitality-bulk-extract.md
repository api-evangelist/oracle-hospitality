---
name: Extract data in bulk from OPERA Cloud
description: Use the asynchronous job APIs, the Export Configuration API and the Reporting & Analytics GraphQL Data APIs to pull large volumes without hurting the transactional platform.
api: openapi/oracle-hospitality-property-v1-rsvasync.json
operations:
  - startReservationsDailySummaryProcess
  - getReservationsProcessStatus
  - getReservationsDailySummary
  - headMassUpdateProcessStatus
  - getMassUpdateProcessSummary
  - getExportsAvailable
  - getExportsGenerated
  - postExportSchedules
generated: '2026-07-28'
method: generated
source: openapi/oracle-hospitality-property-v1-rsvasync.json, openapi/oracle-hospitality-property-v1-expcfg.json, graphql/
---

# Bulk extraction

Three published routes out of OPERA Cloud, in increasing order of volume.

## 1. Asynchronous APIs — a large slice of transactional data

Seven specs carry the `/async/v1` pattern: `blkasync`, `crmasync`, `cshasync`, `invasync`, `parasync`,
`rsvasync`, `rtpasync`. The documented example is thirty days of reservations.

The four-step contract:

1. `POST` the start operation — for example `startReservationsDailySummaryProcess`
   (`openapi/oracle-hospitality-property-v1-rsvasync.json`). The response returns a `Location` header.
2. `HEAD` the `Location` to poll status (`headMassUpdateProcessStatus` is the mass-update equivalent).
3. When complete, the `HEAD` response's `Location` header carries the results URL.
4. `GET` that URL — `getReservationsDailySummary` / `getMassUpdateProcessSummary`.

**Results are single-use.** After the final `GET`, the same `summaryId` returns `404`; restart from step 1
to get the data again.

Budget: 100 POST/minute per gateway (250/minute per environment-application), 300 HEAD/minute,
300 GET/minute. Identical async requests must be at least **30 minutes** apart;
`startBlockAllocationSummaryProcess` with date filters at least **3 hours** apart.

## 2. Export Configuration API — scheduled file exports

`openapi/oracle-hospitality-property-v1-expcfg.json` (22 operations): `getExportsAvailable`,
`getExportsGenerated`, `postExportSchedules`, `getExportSchedules`, `changeExportSchedules`,
`getExportActivityLog`. Oracle's own framing: "the
exports feature in OPERA Cloud provides the ability to create and export data files, such as back office
data, to third-party interfaces and receiving systems."

## 3. Reporting & Analytics GraphQL Data APIs — the high-volume path

75 read-only subject areas under `graphql/`, queried at `<gateway URL>/rna/v1/graphql/`. Oracle's stated
purpose: "allow bulk data to be queried from Reporting & Analytics to avoid any performance impact on the
transactional OPERA Cloud platform."

- One root query field per subject area (`bookingsReservation`, `financialGuestLedger`,
  `profilesIndividuals`, `inventoryRooms`, `ratesCodes`, …).
- Filter inputs are typed comparison objects — `_eq`, `_ne`, `_in`, `_nin`, `_gt`, `_lt`, `_gte`, `_lte`,
  `_btn`, `_isNull` — on `Date` (`YYYY-MM-DD`), `DateTime` (`YYYY-MM-DD HH24:MI:SS`), String and numeric
  scalars.
- Send `Accept: multipart/mixed; deferSpec=20220824, application/json` alongside the usual
  `Authorization`, `x-app-key` and `x-request-id` headers.
- Several subject areas exist **only** here — aging reports, forecast and pace statistics, manager's
  report, budget vs forecast, change log. See `mcp/oracle-hospitality-tool-crosswalk.yml`.

## Rules

- Do not simulate bulk extraction by looping a transactional GET. The gateway budget is shared across
  every consumer on the property's gateway, and long GETs hit the documented query-parameter limit
  (`414`).
- Configuration is not covered by any of these. There is no operation that exports the OPERA configuration
  model — rate plans, room types, chain and hotel setup — as a portable migration package. A "Portable
  Export of your Application Details" is available by support ticket only.
