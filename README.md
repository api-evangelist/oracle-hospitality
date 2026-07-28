# Oracle Hospitality (oracle-hospitality)

Oracle Hospitality is Oracle Corporation's hotel and food-and-beverage technology line, built on the 2014 acquisition of MICROS Systems and anchored by OPERA Cloud, the property management system that runs the front desk, reservations, housekeeping, cashiering and event sales for a large share of the world's branded hotel rooms, alongside OPERA Cloud Distribution, Simphony point of sale and Nor1 upsell. Home market is the United States. It sits in the middle of the hotel distribution chain rather than at either end: it is the system of record a property runs on, and the switch through which that property's availability, rates and inventory reach GDS, OTA and web channels and through which reservations come back. Its API posture is unusually open at the specification layer and firmly gated at the credential layer - Oracle publishes 59 Swagger 2.0 specifications covering roughly 3,500 operations to a public GitHub repository under the Universal Permissive License, and publishes the full Oracle Hospitality Integration Platform (OHIP) developer guide openly, but there is no self-serve signup: partners must purchase Oracle Hospitality Integration Cloud Service through the Oracle Store or a CPQ form, production access requires an Oracle Partner Network reference number, and distribution channel partners additionally need an Oracle-issued global Channel Code and an Oracle Cloud Marketplace listing.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/oracle-hospitality/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/oracle-hospitality/refs/heads/main/apis.yml)

## Tags

- Travel
- United States
- Hospitality
- Hotels
- Property Management
- Distribution
- Channel Management
- Booking
- Reservations
- Point of Sale

## Timestamps

- **Created:** 2026-07-28
- **Modified:** 2026-07-28

## APIs

### OPERA Cloud Distribution ARI Publication

Oracle Hospitality Distribution ARI publication message specification for distribution partners to receive in real time property restrictions/availability, rate, and inventory schedules updates, also known as ARI. Partner receives this message will respond with success or error/warning so that property/CRS user can see the status of message delivery in OPERA. A channel code identifier is required in Oracle Hospitality Distribution to receive those messages. Compatible with OPERA Cloud release 26.2.0.0. 3 operation(s) documented; base path /aripublication/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/outbound/aripublication.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/outbound/aripublication.json)

#### Tags

- ARI Publication
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-outbound-aripublication.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Outbound Lookup

Oracle Hospitality Distribution External Lookup is to get rate plan and room types from external channel partners. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /lookup/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/outbound/lookup.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/outbound/lookup.json)

#### Tags

- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-outbound-lookup.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Content Notification

Oracle Hospitality Distribution Content notification message specification for distribution partners to receive in real time property content, channel room and rate updates. Partner receives this message will respond with success or error/warning so that property/CRS user can see the status of message delivery in OPERA. A channel code identifier is required in Oracle Hospitality Distribution to receive those messages. Compatible with OPERA Cloud release 26.2.0.0. 1 operation(s) documented; base path /notification/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/outbound/notification.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/outbound/notification.json)

#### Tags

- Content Notification
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-outbound-notification.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Book

OPERA Cloud Distribution Reservations API allows authorized channel partners to create and update reservations for any active property in Oracle Hospitality Distribution (regardless if the property is using OPERA Cloud, OPERA V5 / Suite8 / on-premise PMS Versions). Regardless of how the reservation is created, either directly in Oracle Hospitality Distribution API (reservation request operations) or already created and committed in another external system (reservation notification operations) the same API can be used. Compatible with OPERA Cloud release 26.2.0.0. 5 operation(s) documented; base path /book/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/book.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/book.json)

#### Tags

- Reservation Request
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-book.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Content

Oracle Hospitality Distribution Content is for distribution partners to retrieve property Channel content information. Compatible with OPERA Cloud release 26.2.0.0. 5 operation(s) documented; base path /content/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/content.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/content.json)

#### Tags

- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-content.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Property Controls

Oracle Hospitality Distribution Property Controls specification for distribution partners to retrieve property controls and settings. Compatible with OPERA Cloud release 26.2.0.0. 1 operation(s) documented; base path /controls/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/controls.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/controls.json)

#### Tags

- Distribution Controls
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-controls.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Reservation Service

The OPERA Cloud Distribution Reservation API enables authorized channel partners to create, update, fetch and cancel reservations for properties managed through OPERA Cloud Foundation or OPERA Cloud Central, leveraging Oracle Hospitality Identity Management for secure access. Each request must include a valid channel code in the x-channelCode header. When a hotel maps its hotel, room type, and rate codes to channel-specific values, the API will return those mapped channel codes; otherwise, it will return the native OPERA Cloud codes. Compatible with OPERA Cloud release 26.2.0.0. 4 operation(s) documented; base path /distribution/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/distribution.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/distribution.json)

#### Tags

- Reservation
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-distribution.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Authentication API

API to obtain the access token (in the JWT format) that matches the provided credentials issued by the Oracle Hospitality Distribution administrator for a specific Distribution channel partner. The token will then be used by API users to access OPERA Cloud Distribution APIS. Once a token is created, it can be used in multiple subsequent calls until it expires as defined in this API response. Username for a channel partner Distribution API account is provisioned by an Oracle administrator at the channel level. It is not an OPERA Cloud (PMS) user and not created or approved by the hotelier. Additionally, for each property, the hotelier will need to enable the channel so that it can access data for their specific hotel in the reservation context. More information on how to request a username and temporary password for a registered channel for Distribution APIs: Channel partners registered via OHIP receive credential(s) from the Oracle Hospitality Distribution administrator during the channel registration. Compatible with OPERA Cloud release 26.2.0.0. 1 operation(s) documented; base path /hdpba/oauth2/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/hdpbaoauth2.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/hdpbaoauth2.json)

#### Tags

- Authentication
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-hdpbaoauth2.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Onboarding

Oracle Hospitality Distribution Onboarding specification for distribution partners to retrieve property status with its attributes and update property status. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /onboard/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/onboard.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/onboard.json)

#### Tags

- Onboarding
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-onboard.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Reservation Notification

OPERA Cloud Distribution Reservation Notifications API allows authorized channel partners to create and update reservations for any active property in Oracle Hospitality Distribution (regardless if the property is using OPERA Cloud / OPERA V5 / on-premise PMS Versions). This API is meant to transmit reservations already created and committed in the channel external system and does not perform any Pricing and Availability validation. Compatible with OPERA Cloud release 26.2.0.0. 4 operation(s) documented; base path /resnotif/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/resnotif.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/resnotif.json)

#### Tags

- Reservation Notification
- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-resnotif.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### OPERA Cloud Distribution Shop

Oracle Hospitality Distribution Shop is for distribution partners to find properties availability, room-rates offers for a single property or a specific room-rate offer detail.. Compatible with OPERA Cloud release 26.2.0.0. 6 operation(s) documented; base path /shop/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/shop.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/distribution/v1/shop.json)

#### Tags

- Distribution
- Channel Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-distribution-v1-shop.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_distribution_apis.htm)

### Nor1 Integrated Upsell API

An upsell service that can be consumed to display upgrade offers to a hotel guest prior to arrival. Pre-arrival upsells are becoming increasingly important due to the adoption of mobile and kiosk check-in which reduces the opportunity for front-desk upselling. Upgrade offers are based on PRiME(R) AI/ML decision intelligence and OPERA real-time inventory. The service allows instant fulfillment of the upgrade offer. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /ohcgep/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/nor1/v1/upselloffers.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/nor1/v1/upselloffers.json)

#### Tags

- Nor1 Integrated Upsell API
- Upsell
- Merchandising

#### Properties

- [OpenAPI](openapi/oracle-hospitality-nor1-v1-upselloffers.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oracle_hospitality_nor1_integrated_upsell_apis.htm)

### OPERA Cloud Customer Relationship Management Outbound API

APIs to cater for Customer Relationship Management external (outbound) functionality with OPERA. These APIs facilitate various operations related to getting data from an external system, and inserting it into OPERA. Compatible with OPERA Cloud release 26.2.0.0. 12 operation(s) documented; base path /crm/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/outbound/crmoutbound.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/outbound/crmoutbound.json)

#### Tags

- Profile
- ProfileExternal
- ProfileMembership
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-outbound-crmoutbound.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Cashiering Outbound API

APIs to cater for Cashiering related external (outbound) functionality with OPERA. These APIs facilitate various operations related to getting data from an external system, and inserting it into OPERA. Compatible with OPERA Cloud release 26.2.0.0. 7 operation(s) documented; base path /csh/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/outbound/cshoutbound.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/outbound/cshoutbound.json)

#### Tags

- Cashiering
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-outbound-cshoutbound.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Front Desk Operations Outbound API

APIs to cater for Front Desk related external (outbound) functionality with OPERA Cloud. These APIs facilitate various operations related to getting data from an external system, and inserting it into OPERA Cloud. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /fof/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/outbound/fofoutbound.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/outbound/fofoutbound.json)

#### Tags

- FrontOfficeExternal
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-outbound-fofoutbound.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Activity API

APIs to cater for Sales Activity functionality in OPERA Cloud. Activities provide you with an account management tool for managing daily tasks such as appointments, sales calls, contact follow-up, and so on. Compatible with OPERA Cloud release 26.2.0.0. 23 operation(s) documented; base path /act/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/act.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/act.json)

#### Tags

- Activity
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-act.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Activity Management API

APIs to cater for Activity Configuration functionality in OPERA Cloud. In this module you can retrieve, create, update Activity configuration codes, for example create a new Activity Type. Compatible with OPERA Cloud release 26.2.0.0. 25 operation(s) documented; base path /act/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/actcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/actcfg.json)

#### Tags

- ActivityManagement
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-actcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Accounts Receivables API

APIs to cater for Accounts Receivables functionality in OPERA Cloud. 60 operation(s) documented; base path /ars/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/ars.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/ars.json)

#### Tags

- AccountsReceivables
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-ars.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Block API

APIs to cater for Business Block functionality in OPERA Cloud. A block is a group of rooms held for guests who are attending an event, meeting, or function. You can create blocks for family reunions, business conferences, weddings, and so on. You can also set aside rooms for the event (block). Compatible with OPERA Cloud release 26.2.0.0. 93 operation(s) documented; base path /blk/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/blk.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/blk.json)

#### Tags

- BlockExternal
- Block
- BlockStats
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-blk.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Block Reservation Asynchronous API

APIs to cater Block Reservation related asynchronous functionality in OPERA. Compatible with OPERA Cloud release 26.2.0.0. 14 operation(s) documented; base path /blk/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/blkasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/blkasync.json)

#### Tags

- BlockAsync
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-blkasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Block Configuration API

APIs for Block configuration, such as creating, updating, fetching and removing codes related to blocks. 57 operation(s) documented; base path /blk/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/blkcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/blkcfg.json)

#### Tags

- ChainConfig
- BlockConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-blkcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Back Office Operations API

APIs to cater for Back Office Operations functionality in OPERA Cloud. A common BackOffice industry term is End of Day. This closes and balances each day's business activities. It reconciles guest folios and processes credit card transactions. The End of Day routine rolls the business date forward and prints final reports. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /bof/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/bof.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/bof.json)

#### Tags

- BackOfficeOperations
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-bof.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Channel Configuration API

APIs to cater for Channel Management functionality in OPERA Cloud. Channel Management allows a property to configure and administer channels such as OTAs, and web channels, covering functionality such as channel configuration, availability, inventory and restrictions. Compatible with OPERA Cloud release 26.2.0.0. 138 operation(s) documented; base path /chl/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/chl.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/chl.json)

#### Tags

- Availability
- Inventory
- Channel
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-chl.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud API for Customer Management Service

This API deals with the different aspect of the CustomerManagement. Compatible with OPERA Cloud release 26.2.0.0. 6 operation(s) documented; base path /cms/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/cms.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/cms.json)

#### Tags

- CustomerManagement
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-cms.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Customer Relationship Management API

APIs to cater for Customer Relationship Management (profile) functionality in OPERA Cloud. There are different types of profiles in OPERA Cloud, including Guest, Company, Travel Agent, Source, Group, and Contact profile types. A profile can store and display a wide range of information about the guest, company, travel agent etc., depending upon the type of profile. For example, a guest profile can store the guest name, address, contact information, details on billing, membership benefits, preferences and much more. All profiles in OPERA when created are assigned a ProfileID. This ID will be used throughout the CRM APIs. Compatible with OPERA Cloud release 26.2.0.0. 165 operation(s) documented; base path /crm/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/crm.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/crm.json)

#### Tags

- Profile
- ProfileExternal
- ProfileLOV
- ProfileMembership
- ProfileStatistics
- SuspendedStay
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-crm.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud CRM Asynchronous API

APIs to insert Stay Records related asynchronous functionality in OPERA. Compatible with OPERA Cloud release 26.2.0.0. 4 operation(s) documented; base path /crm/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/crmasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/crmasync.json)

#### Tags

- CRMAsync
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-crmasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud CRM Configuration API

APIs for Customer Relationship Management (profile) configuration, such as creating preferences, or address types. It also includes Membership Configuration, where you can retrieve membership levels that are configured for a property, or create new membership enrollment codes . Compatible with OPERA Cloud release 26.2.0.0. 310 operation(s) documented; base path /crm/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/crmcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/crmcfg.json)

#### Tags

- ProfileConfiguration
- MembershipConfig
- ChainConfig
- HotelConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-crmcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Cashiering API

APIs to cater for Cashiering related functionality in OPERA Cloud. Cashiering provides access to a guest folio, posting journals, receipt histories, currency calculations, credit card settlements, and check a guest out. Compatible with OPERA Cloud release 26.2.0.0. 195 operation(s) documented; base path /csh/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/csh.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/csh.json)

#### Tags

- Cashiering
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-csh.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Cashiering Asynchronous API

APIs to cater for Cashiering related asynchronous functionality in OPERA Cloud. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /csh/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/cshasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/cshasync.json)

#### Tags

- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-cshasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud DataValueMapping Service API

APIs which offer external systems to config and use values different than what are configured in opera Compatible with OPERA Cloud release 26.2.0.0. 10 operation(s) documented; base path /dvm/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/dvm.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/dvm.json)

#### Tags

- DataValueMapping
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-dvm.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### Cloud OPI Tokenization ECommerce API

ECommerce Tokenization API This API allows you to process credit card tokenization via e-commerce token form. Compatible with OPERA Cloud release 25.3.0.0. 2 operation(s) documented; base path /eComm/eToken/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/ecommtokenization.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/ecommtokenization.json)

#### Tags

- Hotels
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-ecommtokenization.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Enterprise Configuration API

APIs to cater for Enterprise Configuration functionality in OPERA Cloud. 246 operation(s) documented; base path /ent/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/entcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/entcfg.json)

#### Tags

- ChainConfig
- ExternalConfig
- HotelConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-entcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Sales Event Management API

APIs to cater for Event Management functionality in OPERA Cloud. The Events feature in OPERA Cloud is designed to manage any kind of catering activity. Events can be as simple as a one-hour reception or more complex, such as a three-day business meeting with meals, breaks, and specific meeting functionSpaceDetails with setupCode and resource requirements. Any group function can be an Event. Compatible with OPERA Cloud release 26.2.0.0. 45 operation(s) documented; base path /evm/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/evm.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/evm.json)

#### Tags

- EventManagement
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-evm.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Event Configuration API

This API caters for Event Configuration in OPERA Cloud. 137 operation(s) documented; base path /evm/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/evmcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/evmcfg.json)

#### Tags

- ResourceConfig
- ChainConfig
- HotelConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-evmcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Export Configuration API

APIs catering to the managing export master data configuration. 22 operation(s) documented; base path /exp/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/expcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/expcfg.json)

#### Tags

- Export
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-expcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Front Desk Operations Service

APIs to cater for Front Desk Operations and Front Desk Statistic functionality in OPERA Cloud. Front Desk features some of the most commonly used operations in OPERA Cloud, such as managing guest arrivals, managing in-house guests, and managing guest departures. Some additional tasks you can complete from the Front Desk menu are room searches, room assignments, and quick check outs as well as opening folios, creating registration cards, setting wake up calls, and sending messages to guests. Compatible with OPERA Cloud release 26.2.0.0. 91 operation(s) documented; base path /fof/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/fof.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/fof.json)

#### Tags

- FOFStats
- FrontDeskOperations
- Commissions
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-fof.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Front Desk Configuration API

APIs to cater for Front Desk Configuration in OPERA Cloud. Here you can find operations to get, post, put and delete front desk codes such as commission codes, transaction groups, codes & subgroups, articles, payment methods and credit card types. Compatible with OPERA Cloud release 26.2.0.0. 363 operation(s) documented; base path /fof/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/fofcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/fofcfg.json)

#### Tags

- AccountsReceivablesConfig
- CashieringConfig
- CreditCard
- CommissionConfig
- EndOfDayConfig
- ChainConfig
- HotelConfig
- Property Management

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-fofcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Housekeeping Service API

APIs to cater for Housekeeping functionality in OPERA Cloud. Housekeeping enables you to schedule daily room cleaning, maintenance, and housekeeping staff activities. It provides information on room status, out of order/out of service rooms, and forecasting. Compatible with OPERA Cloud release 26.2.0.0. 60 operation(s) documented; base path /hsk/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/hsk.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/hsk.json)

#### Tags

- Housekeeping
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-hsk.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Integration Processor API

APIs to get Business Events generated in OPERA Cloud. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /int/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/int.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/int.json)

#### Tags

- IntegrationProcessor
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-int.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Integration Configuration API

APIs catering to Integration Configuration in OPERA Cloud. Operations such as get Hotel Interface Types, or get UDF mappings can be found in this module. Compatible with OPERA Cloud release 26.2.0.0. 50 operation(s) documented; base path /int/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/intcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/intcfg.json)

#### Tags

- BEProcessor
- ExternalSystemsConfig
- ChainConfig
- OEDSConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-intcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Inventory API

APIs to cater for Inventory functionality in OPERA Cloud. This includes sell limits for date ranges, viewing and updating the properties inventory, as well as item inventory (such as rollaways, microwaves etc.). Compatible with OPERA Cloud release 26.2.0.0. 13 operation(s) documented; base path /inv/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/inv.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/inv.json)

#### Tags

- Inventory
- INVStats
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-inv.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### Opera Cloud Inventory Asynchronous API

APIs to cater for Inventory related asynchronous functionality in OPERA Cloud. This includes viewing inventory data along with its revenue and updating inventory&apos;s sell limits for date ranges. This API follows an async pattern where You make an initial request, which returns a Location header You poll HEAD on the Location header returned to obtain the status of the process Once the process completes HEAD will return in the Location header the URL that must be called to obtain the results of the process You call the URL to obtain the results of the process Compatible with OPERA Cloud release 26.2.0.0. 6 operation(s) documented; base path /inv/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/invasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/invasync.json)

#### Tags

- InventoryAsync
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-invasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Leisure Management API

APIs to cater for external Leisure Management functionality integrated with OPERA Cloud. Compatible with OPERA Cloud release 26.2.0.0. 26 operation(s) documented; base path /lms/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/lms.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/lms.json)

#### Tags

- LeisureManagement
- LeisureManagementConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-lms.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud List of Values Management API

APIs to cater for List of Value functionality in OPERA Cloud. A List of Values in the OPERA Application can be configured by a property. Then by using these APIs you can retrieve all configured codes. As an example, Titles is a configurable ListOfValues. A hotel can specify what titles they wish to use, and thus fetching the LOV for title, you can view the codes that are configured for a property. Compatible with OPERA Cloud release 26.2.0.0. 453 operation(s) documented; base path /lov/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/lov.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/lov.json)

#### Tags

- LOV
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-lov.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Content Service

Opera Content Service offers capability to manage large content such as images and files. Compatible with OPERA Cloud release 26.2.0.0. 11 operation(s) documented; base path /med/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/medcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/medcfg.json)

#### Tags

- OperaContent
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-medcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### oAuth API for OHIP

REST API to obtain an OAuth token from the Oracle Hospitality Integration Platform. For authenticating to Distribution APIs please use the Early Release OPERA Cloud Distribution Authentication API. Compatible with OPERA Cloud release 21.5.0.0. 1 operation(s) documented; base path /oauth/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 21.5.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/oauth.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/oauth.json)

#### Tags

- Authentication
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-oauth.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Provisioning Service API

APIs to cater to provisioning and deprovisioning of new properties and chains in OPERA. Compatible with OPERA Cloud release 26.2.0.0. 1 operation(s) documented; base path /ops/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/ops.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/ops.json)

#### Tags

- Provisioning
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-ops.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Price Availability Rate API

APIs to cater for Price and Rate Availability functionality in OPERA Cloud. Availability enables you to manage your room inventory by providing a detailed view of all available and sold rooms at a property. Some of the tasks you can perform include defining conditions for stay restrictions, setting room sell limits, and searching for and viewing room availability. Compatible with OPERA Cloud release 26.2.0.0. 28 operation(s) documented; base path /par/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/par.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/par.json)

#### Tags

- Availability
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-par.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Price Availability Rate Async API

APIs to cater for Price and Rate Availability Asynchronous functionality in OPERA Cloud. Compatible with OPERA Cloud release 26.2.0.0. 2 operation(s) documented; base path /par/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/parasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/parasync.json)

#### Tags

- AvailabilityAsync
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-parasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Report Master Data Management API

APIs for adding, updating, and deleting stationery reports in OPERA Cloud. Compatible with OPERA Cloud release 26.2.0.0. 12 operation(s) documented; base path /rep/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/repcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/repcfg.json)

#### Tags

- Report
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-repcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Room Configuration API

APIs to cater for room configuration, such as configuring room types, room Classes, creating new room features, or updating housekeeping room maintenance reasons. Compatible with OPERA Cloud release 26.2.0.0. 170 operation(s) documented; base path /rm/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rmcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rmcfg.json)

#### Tags

- ChainConfig
- HotelConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rmcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Room Rotation Service API

APIs to facilitate Room Rotation functionality in OPERA Cloud. Api provides capability to handle Room Rotation in OPERA Cloud. Room Rotation provides room ownership options for automatic inventory rotation and prioritization for owner rooms assignment and occupancy. Compatible with OPERA Cloud release 26.2.0.0. 10 operation(s) documented; base path /rmr/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rmr.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rmr.json)

#### Tags

- RoomRotation
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rmr.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Room Rotation Configuration Service API

APIs to cater for Room Rotation Configuration functionality in OPERA Cloud. Api provides capability to handle Room Rotation in OPERA Cloud. Room Rotation provides room ownership options for automatic inventory rotation and prioritization for owner rooms assignment and occupancy. Compatible with OPERA Cloud release 26.2.0.0. 30 operation(s) documented; base path /rmr/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rmrcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rmrcfg.json)

#### Tags

- RoomRotationConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rmrcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Reservation API

APIs to cater for Reservation functionality in OPERA Cloud. OPERA Cloud Reservations provides a complete set of capabilities for creating and updating reservations. Reservations are a central feature of OPERA Cloud. As a key source of information, the reservation specifies a guest's arrival date, departure date, room type, rate, packages, and many other details. It is also a gateway to dozens of other functions that contribute to the guest's experience. All reservations in OPERA Cloud require a guest profile. You can create profiles while booking a reservation. If a profile already exists, you can look it up (using getProfiles in CRM module) and attach it to the reservation during the reservation booking process using the Profile ID. Compatible with OPERA Cloud release 26.2.0.0. 184 operation(s) documented; base path /rsv/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rsv.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rsv.json)

#### Tags

- ReservationExternal
- Reservation
- RSVStats
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rsv.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Reservation Asynchronous API

APIs to cater for Reservation Asynchronous functionality in OPERA Cloud. This includes viewing reservation data along with its revenue. This API follows an async pattern where You make an initial request, which returns a Location header You poll HEAD on the Location header returned to obtain the status of the process Once the process completes HEAD will return in the Location header the URL that must be called to obtain the results of the process You call the URL to obtain the results of the process Compatible with OPERA Cloud release 26.2.0.0. 15 operation(s) documented; base path /rsv/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rsvasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rsvasync.json)

#### Tags

- ReservationAsync
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rsvasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Reservation Master Data Management API

APIs to cater for Reservation Configuration in OPERA Cloud. In this module you can retrieve, create, modify or delete configuration related to Reservations, Blocks and Leisure Management. Compatible with OPERA Cloud release 26.2.0.0. 215 operation(s) documented; base path /rsv/config/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rsvcfg.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rsvcfg.json)

#### Tags

- ReservationConfig
- ChainConfig
- HotelConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rsvcfg.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPERA Cloud Rate API

APIs to cater for Rate Availability functionality in OPERA Cloud. Rate Management provides all the tools you need to effectively define and manage the rate structures for a property in OPERA Cloud. Some of the things you can do include creating and managing rate codes, rate classes, rate categories, display sets, rate strategies, as well as managing promotion groups and codes. Compatible with OPERA Cloud release 26.2.0.0. 144 operation(s) documented; base path /rtp/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rtp.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rtp.json)

#### Tags

- Availability
- RatePlan
- ChainConfig
- HotelConfig
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rtp.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### Opera Cloud Rate Plan Asynchronous Service API

APIs catering to the Rate Plan asynchronous related functionality in a hotel. This includes adding/updating daily rates&apos; pricing schedules and best available rates by day or length of stay. This API follows an async pattern where You make an initial request, which returns a Location header You poll HEAD on the Location header returned to obtain the status of the process Once the process completes HEAD will return in the Location header the URL that must be called to obtain the results of the process You call the URL to obtain the results of the process Compatible with OPERA Cloud release 26.2.0.0. 18 operation(s) documented; base path /rtp/async/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 26.2.0.0).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rtpasync.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/rtpasync.json)

#### Tags

- RatePlanAsync
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-rtpasync.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

### OPI Token Exchange Service API

Oracle Token Exchange Service Specification Compatible with OPERA Cloud release 1.0.1. 1 operation(s) documented; base path /tokenExchange/v1. Harvested verbatim from Oracle's public hospitality-api-docs repository (Swagger 2.0, release 1.0.1).

- **Human URL:** [https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/tokenexchange.json](https://github.com/oracle/hospitality-api-docs/blob/main/rest-api-specs/property/v1/tokenexchange.json)

#### Tags

- Hotels
- Property Management
- OPERA Cloud

#### Properties

- [OpenAPI](openapi/oracle-hospitality-property-v1-tokenexchange.json) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_property_apis.htm)

## Common Properties

- [Website](https://www.oracle.com/hospitality/)
- [Portal](https://www.oracle.com/hospitality/integration-platform/)
- [Documentation](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/)
- [Documentation](https://docs.oracle.com/en/industries/hospitality/index.html)
- [Git Hub Organization](https://github.com/oracle)
- [Git Hub Repository](https://github.com/oracle/hospitality-api-docs)
- [Postman Workspace](https://www.postman.com/hospitalityapis/oracle-hospitality-apis/overview)
- [Linked In](https://www.linkedin.com/showcase/oracle-hospitality/)
- [Terms Of Service](https://www.oracle.com/legal/terms.html)
- [License](https://oss.oracle.com/licenses/upl)
- [Authentication](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_oauth_token_api.htm)
- [Rate Limits](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_limits.htm)
- [Versioning](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_versioning.htm)
- [Support](https://docs.oracle.com/cd/F29336_01/doc.201/f27480/c_getting_help_and_contacting_support.htm)

## Maintainers

**FN:** Kin Lane
**Email:** kin@apievangelist.com
