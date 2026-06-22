# Kastle Elevator Specification Letter — Type DD (Destination Dispatch)
## Template & Agent Behavior Rules

---

## AGENT INSTRUCTIONS: TYPE DD

### When to Use This Template
Use this template when `letter_type` equals `"DD"`. The Type DD system is a **Destination Dispatch** configuration in which the building's elevator system uses a destination dispatch controller — tenants enter their destination floor at a kiosk or keypad in the lobby, and the dispatch system assigns them to a specific elevator car. The Kastle system integrates directly with the destination dispatch controller via the method specified in `integration_method`. This is the most complex letter type and requires close coordination between Kastle, the building owner, the elevator contractor, and the dispatch system manufacturer.

### Type DD Required Fields
In addition to all shared required fields, Type DD requires:
- `dispatch_system_manufacturer` — name of the destination dispatch system manufacturer
- `dispatch_system_model` — model name or number of the dispatch system
- `integration_method` — how Kastle integrates with the dispatch system (e.g., "API/software integration", "dry contact input", "Wiegand output to dispatch controller")
- `dispatch_zones` — array of zone objects, each with:
  - `zone_label` — name or identifier for the zone (e.g., "Zone A – Low Rise", "Zone B – High Rise")
  - `floors_served` — array of floor labels served by this zone
  - `access_level` — credential access level required for this zone
  - `notes` — any zone-specific notes (optional)

---

## LETTER TEMPLATE

---

**KASTLE SYSTEMS**
11400 Commerce Park Drive
Reston, VA 20191
(703) 234-3800

---

{{date}}

{{recipient.name}}
{{recipient.title}}
{{recipient.company}}
{{recipient.address.street}}
{{recipient.address.city}}, {{recipient.address.state}} {{recipient.address.zip}}

**RE: Elevator Access Control Specification – Type DD (Destination Dispatch)**
**Property: {{property.name}}**
**{{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}**

Dear {{recipient.name}},

Kastle Systems is pleased to provide the following elevator access control specifications for the {{elevator_bank}} at {{property.name}}, located at {{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}. This letter describes the Type DD Destination Dispatch system, which requires integration between the Kastle access control system and the building's {{dispatch_system_manufacturer}} {{dispatch_system_model}} destination dispatch controller. This integration requires coordinated effort among Kastle Systems, the building ownership, the elevator contractor, and the dispatch system manufacturer or their authorized representative. Please review these specifications carefully prior to scheduling any installation or integration work.

---

**System Overview**

The Kastle Type DD elevator access control system integrates with the building's {{dispatch_system_manufacturer}} {{dispatch_system_model}} destination dispatch controller via {{integration_method}}. During {{access_hours}}, the Kastle system will validate tenant credentials at the designated Kastle reader locations and communicate authorized floor destinations to the destination dispatch controller. The dispatch controller will then assign the tenant to the appropriate elevator car based on their authorized destination and the dispatch system's car assignment algorithm. Tenants who do not present a valid Kastle credential will not be permitted to enter a destination floor into the dispatch system for secured zones. At the appropriate time each morning, Kastle will return the elevator system to normal unrestricted daytime operation in coordination with the dispatch controller.

---

**Tenant Operation**

To use the elevator system during {{access_hours}}, a building tenant approaches the Kastle credential reader located at the destination dispatch kiosk or entry point and presents their Kastle credential. Upon successful authentication, the Kastle system communicates the tenant's authorized destination floors to the dispatch controller. The dispatch system will prompt the tenant to select or confirm their destination floor and will assign them to a specific elevator car. The tenant proceeds to the assigned elevator car, which will be dispatched to their destination floor. Tenants are authorized only for the destination floors configured in the Kastle system. Tenants who require access to additional floors or after-hours access must be reconfigured in the Kastle system by the building manager.

---

**Elevator Contractor & Integration Specifications**

The building ownership and management will be responsible for contracting with both the elevator maintenance company and the {{dispatch_system_manufacturer}} authorized representative to perform the integration work described in this letter. If required by local building codes or authority having jurisdiction (AHJ), the contractor must obtain the appropriate permits before commencing work.

A pre-installation coordination meeting between Kastle Systems, the elevator contractor, and the dispatch system manufacturer's representative is strongly recommended prior to commencing any integration work. The dispatch system manufacturer must provide Kastle Systems with the applicable integration documentation, API specifications, or wiring diagrams required to complete the integration via {{integration_method}} prior to the scheduled installation date.

Some work performed by the elevator contractor and dispatch system integrator — including system testing prior to Kastle certification — may need to be performed outside of regular business hours. Kastle recommends that provisions for overtime work be included in all contractor agreements. Kastle Systems will not be liable for payment of any elevator contractor or integrator overtime charges incurred in connection with this project.

Upon completion of all integration work, all parties must notify Kastle Systems to schedule the system commissioning and certification visit. The system will not be placed into service until Kastle has completed its final inspection and integration testing with the dispatch controller.

---

**Wiring Requirements**

Kastle will install the Kastle Elevator Control (KEC) panel at {{kec_location}}. The specific wiring and signal interface between the Kastle KEC panel and the {{dispatch_system_manufacturer}} {{dispatch_system_model}} dispatch controller will be completed via {{integration_method}}. Detailed wiring diagrams will be provided to the elevator contractor and dispatch system integrator by Kastle Systems prior to installation commencement.

All wiring must be run in accordance with all applicable electrical codes and elevator safety standards. All wiring must be properly labeled at both ends and documented in the as-built drawings provided to the building owner upon project completion.

The following table identifies the dispatch zones, the floors served within each zone, and the Kastle access level required for each zone:

---

**Destination Dispatch Zone Assignment Table**

| Zone | Floors Served | Required Access Level | Notes |
|---|---|---|---|
{{#each dispatch_zones}}
| {{zone_label}} | {{floors_served}} | {{access_level}} | {{#if notes}}{{notes}}{{else}}—{{/if}} |
{{/each}}

**Elevator Cars in Scope**

| Elevator Car | Notes |
|---|---|
{{#each cars}}
| {{id}} | {{#if notes}}{{notes}}{{else}}—{{/if}} |
{{/each}}

*All zone assignments and car dispatch logic are subject to review and confirmation by the {{dispatch_system_manufacturer}} authorized representative. Kastle Systems and the dispatch system manufacturer must jointly verify integration functionality prior to certification testing.*

---

**Important Notes**

1. All work performed by the elevator contractor must comply with ASME A17.1 Safety Code for Elevators and Escalators, applicable local building codes, and the requirements of the authority having jurisdiction (AHJ).
2. Kastle Systems is not responsible for any damage to the elevator or dispatch system resulting from improper installation or integration by the elevator contractor or dispatch system integrator.
3. The dispatch system manufacturer must confirm in writing that the {{dispatch_system_model}} system supports integration via {{integration_method}} prior to commencement of any integration work.
4. Any changes to the dispatch zone configuration, access levels, or floors served after system installation must be coordinated between Kastle Systems and the dispatch system manufacturer and approved in writing before implementation.
5. Any changes to the scope of work described in this letter must be approved in writing by Kastle Systems prior to implementation.
6. This specification letter is valid for ninety (90) days from the date of issuance. If work has not commenced within that period, please contact your Kastle project representative for reconfirmation.

---

**Acknowledgment**

By signing below, the recipient acknowledges receipt of this elevator access control specification letter and confirms their agreement to coordinate the required elevator contractor and dispatch system integration work in accordance with the specifications provided herein.

Signature: ___________________________________________     Date: ___________________

Printed Name: ________________________________________

Title: _______________________________________________

Company: ___________________________________________

---

Please return a signed copy of this letter to your Kastle Systems project representative. If you have any questions regarding these specifications, please do not hesitate to contact us.

Sincerely,

{{kastle_rep.name}}
{{kastle_rep.title}}
Kastle Systems
{{kastle_rep.phone}}
{{kastle_rep.email}}

---

*Kastle Systems – Confidential. This document contains proprietary technical specifications intended solely for the use of the named recipient and their designated elevator contractor.*