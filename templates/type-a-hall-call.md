# Kastle Elevator Specification Letter — Type A (Hall Call)
## Template & Agent Behavior Rules

---

## AGENT INSTRUCTIONS: TYPE A

### When to Use This Template
Use this template when `letter_type` equals `"A"`. The Type A system is a **Hall Call** configuration in which a Kastle reader is installed at the elevator lobby (hall call station) on each secured floor. When a tenant presents a valid credential at the hall call reader, the Kastle system sends a signal to the elevator controller allowing the elevator to be called to that floor. Without a valid credential, the elevator cannot be summoned to secured floors during access control hours.

### Type A Required Fields
In addition to all shared required fields, Type A requires the following per car:
- `cars[n].reader_location` — physical location of the hall call reader for that car
- `cars[n].hall_call_bypass_terminal` — terminal designation in the elevator controller for the hall call bypass contact

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

**RE: Elevator Access Control Specification – Type A (Hall Call)**
**Property: {{property.name}}**
**{{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}**

Dear {{recipient.name}},

Kastle Systems is pleased to provide the following elevator access control specifications for the {{elevator_bank}} at {{property.name}}, located at {{property.address.street}}, {{property.address.city}}, {{property.address.state}} {{property.address.zip}}. This letter describes the Type A Hall Call system, which requires the elevator contractor to provide wiring connections at the elevator controller as detailed below. Please review these specifications carefully and coordinate with your elevator maintenance contractor prior to scheduling installation.

---

**System Overview**

The Kastle Type A elevator access control system utilizes Kastle-installed card readers positioned at the hall call station on each secured floor. During {{access_hours}}, the Kastle system will restrict the ability to call the elevator to secured floors. When a building tenant or authorized user presents a valid Kastle credential — such as an access card, key fob, or mobile credential — at the Kastle hall call reader on their floor, the Kastle Elevator Control (KEC) panel will send a signal to the elevator controller, enabling the elevator to respond to that floor call. Without a valid credential presentation, the elevator will not respond to calls from secured floors during access control hours. At the appropriate time each morning, Kastle will return the elevators to normal unrestricted daytime operation by deactivating the access control system.

---

**Tenant Operation**

To call the elevator to a secured floor during {{access_hours}}, a building tenant presents their Kastle credential at the Kastle hall call reader located at the elevator lobby on their floor. Upon successful authentication, the Kastle system enables the elevator call for a preset dwell time, during which the tenant may press the hall call button to summon the elevator. If the button is not pressed within the dwell time, the system will re-secure and the tenant must re-present their credential. Each tenant's credential is programmed to permit hall call access only during their authorized hours and only on floors for which they are authorized. Tenants who require after-hours access must be configured in the Kastle system by the building manager.

---

**Elevator Contractor Specifications**

The building ownership and management will be responsible for contracting with the elevator maintenance company to make the necessary modifications to the building's elevator control system as described in this letter. If required by local building codes or authority having jurisdiction (AHJ), the contractor must obtain the appropriate permits before commencing work.

Some work performed by the elevator contractor — including system testing prior to Kastle certification — may need to be performed outside of regular business hours. Kastle recommends that provisions for overtime work be included in the contractor's agreement. Kastle Systems will not be liable for payment of any elevator contractor overtime charges incurred in connection with this project.

Upon completion of the elevator contractor's work, the contractor and building management must notify Kastle Systems to schedule the system commissioning and certification visit. The system will not be placed into service until Kastle has completed its final inspection and testing.

---

**Wiring Requirements**

Kastle will install the Kastle Elevator Control (KEC) panel at {{kec_location}}. Kastle will also install one (1) hall call reader per elevator car at the location specified per car below. The KEC panel provides one (1) dry contact output per elevator car. The elevator contractor must wire each dry contact output to the hall call security bypass contact terminals in the elevator controller for each respective car.

Wiegand signal wiring from each hall call reader to the KEC panel must be run in a dedicated conduit, separate from elevator power and control wiring, in accordance with all applicable electrical codes and elevator safety standards. All wiring must be properly labeled at both ends and documented in the as-built drawings provided to the building owner upon project completion.

The following table identifies each elevator car in scope, the reader location, and the corresponding KEC panel output and controller terminal assignments:

---

**Hall Call Reader & Wiring Assignment Table**

| Elevator Car | Reader Location | KEC Output | Hall Call Bypass Terminal | Notes |
|---|---|---|---|---|
{{#each cars}}
| {{id}} | {{reader_location}} | {{#if wire_pair}}{{wire_pair}}{{else}}TBD{{/if}} | {{#if hall_call_bypass_terminal}}{{hall_call_bypass_terminal}}{{else}}TBD{{/if}} | {{#if notes}}{{notes}}{{else}}—{{/if}} |
{{/each}}

*The elevator contractor shall verify hall call bypass terminal designations with the elevator controller manufacturer's wiring diagram prior to installation. If terminal designations differ from those specified above, the contractor must notify Kastle Systems before proceeding.*

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