# Lab Scenario 1 - The Urban Bean Coffee Roasters

Retail + wholesale food service | PAIN: Mobile work + fragmented wholesale service | OUTCOME: Professional reachability + account-aware support

| **CUSTOMER VOICE**  We have one storefront, a roastery, and a warehouse, but our wholesale business now serves cafes, hotels, and restaurants across the region. Store and operations employees are rarely at desks, and they must not expose personal mobile numbers. Wholesale customers call about orders, deliveries, and equipment support, and our service coordinators use a CRM to manage those accounts. We want one professional phone experience that routes callers correctly, gives the wholesale team useful account context, and still lets warehouse staff hear delivery announcements. |
| --- |

| **DESIGN INSTRUCTION**  Do not start with a feature list. Translate the numbered requirements into the smallest design that creates the stated outcome. Use the cheat sheet and, if available, optional read-only Control Hub browsing as references; no system changes are part of this activity. |
| --- |

### Current environment

* The company is replacing a legacy key system while retaining one published main number and a separate wholesale number used on invoices.
* Ten storefront, roastery, and warehouse employees work away from desks. Some carry personal phones and some use company-owned phones.
* Four wholesale service coordinators answer order, delivery, and equipment questions from Webex App desktop. A CRM stores business accounts, contacts, and cases.
* Retail hours, wholesale service hours, holidays, and weather closures differ. The warehouse has four supported desk phones used by receiving, roasting, packing, and the supervisor.

### Specific customer requirements

**UB-1 One professional front door**

**Customer requirement:** The published main number must greet callers and offer clear choices for the storefront, wholesale service, deliveries, and hours or directions, with a defined result for no input or invalid input.

**Success looks like:** A caller reaches the intended destination in one selection, and the business does not recreate every legacy line appearance.

**UB-2 Mobile business identity**

**Customer requirement:** Store and operations employees must place and receive business calls on smartphones while keeping personal cellular numbers private.

**Success looks like:** Customers see and call back an approved Urban Bean number while employees remain reachable away from desks.

**UB-3 Wholesale callers wait for the right team**

**Customer requirement:** Wholesale calls must wait for an available service coordinator, hear useful announcements or music, and be offered callback during sustained busy periods rather than ringing an unowned phone.

**Success looks like:** The design identifies a wholesale Customer Assist queue, membership, routing pattern, wait treatment, callback rules, and an owned overflow or unavailable-team destination.

**UB-4 Relevant customer information at answer**

**Customer requirement:** When a coordinator answers a known wholesale caller, the desktop workflow should open useful CRM account or case context. Shared business numbers, duplicate records, and unknown callers need a defined search path.

**Success looks like:** The supported CRM page or search opens with useful call data, and the coordinator can resolve ambiguous or unknown numbers without assuming a perfect match.

**UB-5 Recognizable wholesale callback identity**

**Customer requirement:** When a coordinator calls a wholesale customer back, the wholesale service number must be presented so the return call reaches the same service path instead of an individual employee.

**Success looks like:** The customer recognizes the number and calling it back returns to the staffed wholesale route.

**UB-6 Warehouse delivery broadcast**

**Customer requirement:** Authorized storefront and receiving staff need one number that broadcasts a live, one-way delivery announcement to the intended warehouse phones.

**Success looks like:** Eligible idle targets hear the same announcement, and only approved originators can initiate it.

**UB-7 Hours, closures, and owned voicemail**

**Customer requirement:** Retail and wholesale schedules must route differently after hours and on holidays. A manager must be able to activate an unexpected-closure route, and unanswered wholesale calls must reach a team-owned mailbox with an audio copy sent to the wholesale email address.

**Success looks like:** Scheduled changes occur automatically, an authorized manager can switch and restore a closure, and messages remain owned by the wholesale team rather than one employee.

### Known constraints

* Customer Assist screen pop is a desktop workflow; it does not replace the mobile calling experience needed by storefront and warehouse employees.
* Caller-number matching supplies context but does not guarantee that one phone number identifies one Salesforce record or one person.
* Webex Go is an option only after confirming the supported provider, plan, device or eSIM, and entitlement; Webex App mobile remains a valid app-based design.

### Your design challenge

1. **Prioritize:** Identify the three requirements that most directly protect customer experience or operations.
2. **Map:** Name the Webex Calling feature or design decision that addresses each numbered requirement.
3. **Detail:** Describe the important route, identity, schedule, membership, role, desktop, or policy at a conceptual level.
4. **Explain:** State why this choice fits the business better than a plausible alternative.
5. **Discover:** Ask at least three questions whose answers could change the design.
6. **Walk through:** Explain the normal customer experience and at least one relevant after-hours, invalid-input, no-answer, unavailable-team, full-queue, callback, or closure path in words.
7. **Present:** Prepare a three-minute recommendation using requirement IDs so the customer can trace every choice.

### Discussion checkpoints

* Can the team explain the normal caller or user experience without relying on feature names alone?
* Can the team identify assumptions that would change the recommendation?
* Can the team distinguish required capabilities from optional enhancements?

| **OPTIONAL ROUND-TWO TWIST**  Holiday wholesale volume doubles for six weeks and one coordinator is unavailable. Revise temporary queue membership, callback, overflow ownership, and caller identity without adding another published number or exposing personal mobile numbers. |
| --- |
