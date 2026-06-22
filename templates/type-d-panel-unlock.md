# Kastle Elevator Specification Letter — Type D (Standard Panel Unlock)
## Template & Agent Behavior Rules

---

## AGENT INSTRUCTIONS: TYPE D

### When to Use This Template
Use this template when `letter_type` equals `"D"`. The Type D system is a **Standard Panel Unlock** configuration in which a Kastle in-cab reader triggers a single dry contact output from the KEC panel, unlocking the entire elevator floor selector panel for a configurable dwell time. All floors become selectable upon a valid credential presentation. This is the simplest elevator letter type and serves as the baseline configuration.

### Type D Required Fields
Type D uses only the shared required fields. No additional type-specific fields are required beyond the base car `id`.

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

**RE: Elevator Access Control Specification – Type D (Standard Panel Unlock)**
**Property: {{property.name}}**
**{{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}**

Dear {{recipient.name}},

Kastle Systems is pleased to provide the following elevator access control specifications for the {{elevator_bank}} at {{property.name}}, located at {{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}. This letter describes the Type D Standard Panel Unlock system, which requires the elevator contractor to provide wiring connections at the elevator controller as detailed below. Please review these specifications carefully and coordinate with your elevator maintenance contractor prior to scheduling installation.

---

**System Overview**

The Kastle Type D elevator access control system utilizes a Kastle-installed in-cab card reader in each elevator car to interface with the building's elevator control panel. During {{access_hours}}, the Kastle system will restrict access to the elevator floor selector panel. When a building tenant or authorized user presents a valid Kastle credential — such as an access card, key fob, or mobile credential — at the Kastle reader inside the elevator cab, the Kastle Elevator Control (KEC) panel will send a momentary dry contact output signal to the elevator controller. This signal will temporarily unlock the floor selector panel, permitting the user to select their desired floor. Following a configurable dwell time sufficient for floor selection, the panel will automatically re-secure. At the appropriate time each morning, Kastle will return the elevators to normal unrestricted daytime operation by deactivating the access control system.

---

**Tenant Operation**

To operate the elevator during {{access_hours}}, a building tenant presents their Kastle credential at the Kastle reader installed inside the elevator cab. Upon successful authentication, the Kastle system sends a signal to unlock the elevator control panel for a preset dwell time, during which the tenant may select their desired floor. If no floor selection is made within the dwell time, the panel will re-lock and the tenant must re-present their credential. Each tenant's credential is programmed to permit access only during their authorized hours. Tenants who require after-hours access must be configured in the Kastle system by the building manager.

---

**Elevator Contractor Specifications**

The building ownership and management will be responsible for contracting with the elevator maintenance company to make the necessary modifications to the building's elevator control system as described in this letter. If required by local building codes or authority having jurisdiction (AHJ), the contractor must obtain the appropriate permits before commencing work.

Some work performed by the elevator contractor — including system testing prior to Kastle certification — may need to be performed outside of regular business hours. Kastle recommends that provisions for overtime work be included in the contractor's agreement. Kastle Systems will not be liable for payment of any elevator contractor overtime charges incurred in connection with this project.

Upon completion of the elevator contractor's work, the contractor and building management must notify Kastle Systems to schedule the system commissioning and certification visit. The system will not be placed into service until Kastle has completed its final inspection and testing.

---

**Wiring Requirements**

Kastle will install the Kastle Elevator Control (KEC) panel at {{kec_location}}. The KEC panel provides one (1) dry contact output per elevator car. The elevator contractor must wire each dry contact output to the NC (Normally Closed) and COM (Common) terminals of the floor selector security bypass contact located in the elevator controller for each respective car.

The dry contact wiring must be run in accordance with all applicable electrical codes and elevator safety standards. Kastle recommends the use of a minimum 18 AWG stranded, shielded, twisted-pair cable for each run. All wiring must be properly labeled at both ends and documented in the as-built drawings provided to the building owner upon project completion.

The following table identifies each elevator car in scope and the corresponding KEC panel dry contact output assignment:

---

**Wire Pair Assignment Table**

| Elevator Car | KEC Dry Contact Output | Terminal Connection | Notes |
|---|---|---|---|
{{#each cars}}
| {{id}} | {{#if wire_pair}}{{wire_pair}}{{else}}TBD{{/if}} | NC / COM – Floor Selector Bypass | {{#if notes}}{{notes}}{{else}}—{{/if}} |
{{/each}}

*The elevator contractor shall verify terminal designations with the elevator controller manufacturer's wiring diagram prior to installation. If terminal designations differ from those specified above, the contractor must notify Kastle Systems before proceeding.*

---

**Important Notes**

1. All work performed by the elevator contractor must comply with ASME A17.1 Safety Code for Elevators and Escalators, applicable local building codes, and the requirements of the authority having jurisdiction (AHJ).
2. Kastle Systems is not responsible for any damage to the elevator system resulting from improper installation by the elevator contractor.
3. Any changes to the scope of work described in this letter must be approved in writing by Kastle Systems prior to implementation.
4. This specification letter is valid for ninety (90) days from the date of issuance. If work has not commenced within that period, please contact your Kastle project representative for reconfirmation.

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