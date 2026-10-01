# Possible Scenario Designs

These are possible designs for each scenario. Other designs may also be valid if they meet the customer requirements, explain the tradeoffs, and identify important assumptions.

## Urban Bean Coffee Roasters

### Design at a glance

Auto Attendant → mobile Webex Calling identities → Wholesale Customer Assist queue with callback and CRM context → Wholesale caller ID → Paging Group → Schedules, Operating Modes, and shared voicemail

| Requirement | Possible design | Important considerations |
|---|---|---|
| **UB-1: One professional front door** | Use an Auto Attendant on the published main number. | Provide choices for the storefront, wholesale service, deliveries, and hours or directions. Define no-input, invalid-input, operator, voicemail, and after-hours behavior. |
| **UB-2: Mobile business identity** | Use Webex App mobile or Webex Go with a Webex Calling business identity. | Employees remain reachable without exposing personal numbers. Confirm the users, numbers, outbound identity, mobile experience, and return-call path. |
| **UB-3: Wholesale callers wait for the right team** | Use a Customer Assist queue with the four wholesale coordinators. | Define routing, queue capacity, announcements, music, callback eligibility, overflow, unavailable-team behavior, and final ownership. |
| **UB-4: Salesforce context at answer** | Use a Customer Assist screen pop with a supported Salesforce search or record URL. | Define the CRM objects, fields, search pattern, inbound call data, authentication, and desktop assumptions. Include duplicate and unknown-number handling. |
| **UB-5: Recognizable wholesale callback identity** | Present the approved wholesale service number on outbound callbacks. | Confirm who may use the number and verify that calling it returns to the staffed wholesale route. |
| **UB-6: Warehouse delivery broadcast** | Use a Paging Group for the supported warehouse phones. | Define authorized originators, eligible targets, and supported primary devices. Paging is a live, one-way broadcast. |
| **UB-7: Hours, closures, and owned voicemail** | Use schedules and Operating Modes for normal hours, holidays, and unexpected closures. Use a shared mailbox or Voicemail Group for unanswered wholesale calls. | Define who can activate and restore a closure, who owns the mailbox, and where an audio copy is sent. |

### Important Urban Bean boundaries

- Customer Assist screen pop is a desktop workflow; it does not replace mobile calling.
- Caller-number matching does not guarantee one unique CRM record.
- Webex Go requires confirmation of provider, plan, device or eSIM, and entitlement.
- A Hunt Group is not a substitute for a queue that needs waiting treatment, callback, or Customer Assist capabilities.
- Shared wholesale voicemail should belong to the team, not one coordinator.

### Useful Urban Bean discovery questions

- What are the wholesale peak volumes, acceptable wait time, callback threshold, and final destination when no coordinator is available?
- Which CRM objects and fields should open for a known caller?
- How should duplicate and unknown phone numbers be handled?
- Which employees need Webex App mobile, and is a native mobile dialer required?
- Who may declare a closure, and who owns the shared wholesale mailbox?
