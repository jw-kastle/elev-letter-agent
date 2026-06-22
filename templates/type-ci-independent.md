# Kastle Elevator Specification Letter — Type CI (Independent Floor Control)
## Template & Agent Behavior Rules

---

## AGENT INSTRUCTIONS: TYPE CI

### When to Use This Template
Use this template when `letter_type` equals `"CI"`. The Type CI system is an **Independent Floor Control** configuration. Like Type C, it provides per-floor relay output control from a Kastle in-cab reader. The key distinction of CI is that each secured floor operates independently — a tenant's credential unlocks only their specifically authorized floor relay and does not affect other floor relays in the same transaction. CI is typically used in buildings where tenants require strict isolation of floor access, such as multi-tenant professional or medical buildings. An additional KEC output expansion module may be required depending on the number of secured floors.

### Type CI Required Fields
In addition to all shared required fields, Type CI requires the following per car:
- `cars[n].secured_floors` — array of floor objects, each with:
  - `floor_label` — the floor designation (e.g., "Floor 3", "PH", "B2")
  - `relay_pair` — the relay output pair assigned to that floor in the KEC panel
  - `independent_lock` — confirmation that this floor operates in independent lock mode ("Yes" or description)

Type CI also accepts the following optional object:
- `output_module.required` — whether an expansion output module is required ("Yes" / "No")
- `output_module.location` — where the expansion module will be installed
- `output_module.notes` — any additional notes regarding the module

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

**RE: Elevator Access Control Specification – Type CI (Independent Floor Control)**
**Property: {{property.name}}**
**{{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}**

Dear {{recipient.name}},

Kastle Systems is pleased to provide the following elevator access control specifications for the {{elevator_bank}} at {{property.name}}, located at {{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}. This letter describes the Type CI Independent Floor Control system, which requires the elevator contractor to provide wiring connections at the elevator controller as detailed below. Please review these specifications carefully and coordinate with your elevator maintenance contractor prior to scheduling installation.

---

**System Overview**

The Kastle Type CI elevator access control system utilizes a Kastle-installed in-cab card reader inside each elevator car to provide independent per-floor access control. During {{access_hours}}, the Kastle system will restrict individual floor buttons on the elevator selector panel on a tenant-specific basis. When a building tenant or authorized user presents a valid Kastle credential — such as an access card, key fob, or mobile credential — at the Kastle in-cab reader, the Kastle Elevator Control (KEC) panel will independently activate only the relay output corresponding to that tenant's specifically authorized floor. Each floor relay operates independently, meaning that activation of one floor relay does not affect any other floor relay in the panel. Unauthorized floor buttons will remain inactive regardless of any credential presentation. Following a configurable dwell time, the activated floor button will return to its secured state. At the appropriate time each morning, Kastle will return the elevators to normal unrestricted daytime operation by deactivating the access control system.

---

**Tenant Operation**

To access a secured floor during {{access_hours}}, a building tenant enters the elevator cab and presents their Kastle credential at the Kastle in-cab reader. Upon successful authentication, the floor button corresponding to that tenant's authorized floor will become active independently for a preset dwell time. The tenant may then press their authorized floor button to proceed. Buttons for all other secured floors will remain inactive. If the floor button is not pressed within the dwell time, the relay will re-secure and the tenant must re-present their credential. Because each floor relay operates independently, a tenant authorized for multiple floors must present their credential once per floor selection. Tenants who require access to additional floors or after-hours access must be reconfigured in the Kastle system by the building manager.

---

**Elevator Contractor Specifications**

The building ownership and management will be responsible for contracting with the elevator maintenance company to make the necessary modifications to the building's elevator control system as described in this letter. If required by local building codes or authority having jurisdiction (AHJ), the contractor must obtain the appropriate permits before commencing work.

Some work performed by the elevator contractor — including system testing prior to Kastle certification — may need to be performed outside of regular business hours. Kastle recommends that provisions for overtime work be included in the contractor's agreement. Kastle Systems will not be liable for payment of any elevator contractor overtime charges incurred in connection with this project.

Upon completion of the elevator contractor's work, the contractor and building management must notify Kastle Systems to schedule the system commissioning and certification visit. The system will not be placed into service until Kastle has completed its final inspection and testing.

---

**Wiring Requirements**

Kastle will install the Kastle Elevator Control (KEC) panel at {{kec_location}}. The KEC panel provides one (1) independent dry contact relay output per secured floor per elevator car. The elevator contractor must wire each relay output to the corresponding floor button bypass contact terminal in the elevator controller cab wiring for each respective floor and car. Each relay circuit must be wired and verified independently prior to Kastle certification testing.

{{#if output_module.required}}
Due to the number of secured floors in this installation, a KEC output expansion module will be required. Kastle will install the expansion module at {{output_module.location}}. {{output_module.notes}}
{{/if}}

All wiring must be run in accordance with applicable electrical codes and elevator safety standards. Kastle recommends the use of a minimum 18 AWG stranded, shielded, twisted-pair cable for each relay pair run. All wiring must be properly labeled at both ends with the car ID, floor designation, and relay pair number, and documented in the as-built drawings provided to the building owner upon project completion.

The following table identifies each elevator car, each independently secured floor within that car, and the corresponding KEC relay output assignment:

---

**Independent Floor Control Relay Assignment Table**

{{#each cars}}
**Car {{id}}** {{#if notes}}— {{notes}}{{/if}}

| Floor | KEC Relay Output | Independent Lock | Notes |
|---|---|---|---|
{{#each secured_floors}}
| {{floor_label}} | {{#if relay_pair}}{{relay_pair}}{{else}}TBD{{/if}} | {{#if independent_lock}}{{independent_lock}}{{else}}Yes{{/if}} | — |
{{/each}}

{{/each}}

*The elevator contractor shall verify floor button bypass terminal designations with the elevator controller manufacturer's cab wiring diagram prior to installation. Each relay circuit must be tested independently. If terminal designations differ from those specified above, the contractor must notify Kastle Systems before proceeding.*

---

**Important Notes**

1. All work performed by the elevator contractor must comply with ASME A17.1 Safety Code for Elevators and Escalators, applicable local building codes, and the requirements of the authority having jurisdiction (AHJ).
2. Kastle Systems is not responsible for any damage to the elevator system resulting from improper installation by the elevator contractor.
3. Each floor relay in a Type CI system operates independently. The elevator contractor must verify independent relay operation for each floor prior to scheduling the Kastle certification visit.
4. The number of independently secured floors per car is limited by the relay output capacity of the installed KEC panel and any associated expansion module. Any changes to the secured floor list after installation must be approved in writing by Kastle Systems.
5. Any changes to the scope of work described in this letter must be approved in writing by Kastle Systems prior to implementation.
6. This specification letter is valid for ninety (90) days from the date of issuance. If work has not commenced within that period, please contact your Kastle project representative for reconfirmation.

---

**Acknowledgment**

By signing below, the recipient acknowledges receipt of this elevator access control specification letter and confirms their agreement to coordinate the required elevator contractor work in accordance with the specifications provided herein.

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