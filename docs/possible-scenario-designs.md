# Possible Scenario Designs

These are possible designs for each scenario. Other designs may also be valid if they meet the customer requirements, explain the tradeoffs, and identify important assumptions.

## Urban Bean Coffee Roasters

### Design at a glance

Auto Attendant → mobile Webex Calling identities → wholesale Customer Assist queue with callback and Salesforce context → wholesale caller ID → Paging Group → schedules, Operating Modes, and shared voicemail

| Requirement | Possible design | Important considerations |
|---|---|---|
| **UB-1: One professional front door** | Use an Auto Attendant on the published main number. | Provide choices for the storefront, wholesale service, deliveries, and hours or directions. Define no-input, invalid-input, operator, voicemail, and after-hours behavior. |
| **UB-2: Mobile business identity** | Use Webex App mobile or Webex Go with a Webex Calling business identity. | Employees remain reachable without exposing personal numbers. Confirm the users, numbers, outbound identity, mobile experience, and return-call path. |
| **UB-3: Wholesale callers wait for the right team** | Use a Customer Assist queue with the four wholesale coordinators. | Define routing, queue capacity, announcements, music, callback eligibility, overflow, unavailable-team behavior, and final ownership. |
| **UB-4: Salesforce context at answer** | Use a Customer Assist screen pop with a supported Salesforce search or record URL. | Define the Salesforce objects, fields, search pattern, inbound call data, authentication, and desktop assumptions. Include duplicate and unknown-number handling. |
| **UB-5: Recognizable wholesale callback identity** | Present the approved wholesale service number on outbound callbacks. | Confirm who may use the number and verify that calling it returns to the staffed wholesale route. |
| **UB-6: Warehouse delivery broadcast** | Use a Paging Group for the supported warehouse phones. | Define authorized originators, eligible targets, and supported primary devices. Paging is a live, one-way broadcast. |
| **UB-7: Hours, closures, and owned voicemail** | Use schedules and Operating Modes for normal hours, holidays, and unexpected closures. Use a shared mailbox or Voicemail Group for unanswered wholesale calls. | Define who can activate and restore a closure, who owns the mailbox, and where an audio copy is sent. |

### Important Urban Bean boundaries

- Customer Assist screen pop is a desktop workflow; it does not replace mobile calling.
- Caller-number matching does not guarantee one unique Salesforce record.
- Webex Go requires confirmation of provider, plan, device or eSIM, and entitlement.
- A Hunt Group is not a substitute for a queue that needs waiting treatment, callback, or Customer Assist capabilities.
- Shared wholesale voicemail should belong to the team, not one coordinator.

### Useful Urban Bean discovery questions

- What are the wholesale peak volumes, acceptable wait time, callback threshold, and final destination when no coordinator is available?
- Which Salesforce objects and fields should open for a known caller?
- How should duplicate and unknown phone numbers be handled?
- Which employees need Webex App mobile, and is a native mobile dialer required?
- Who may declare a closure, and who owns the shared wholesale mailbox?

## Riverside Unified School District

### Design at a glance

District Auto Attendant → school-specific Auto Attendants → Dial by Name and Dial by Extension → teacher voicemail → school-office Hunt Groups and attendance shared mailboxes → Spanish Auto Attendant → schedules and Operating Modes

| Requirement | Possible design | Important considerations |
|---|---|---|
| **RS-1: District main number** | Use a district Auto Attendant on the published district number. | Provide choices for schools, enrollment, transportation, the directory, and an operator. Define no-input, invalid-input, repeat, and after-hours behavior. |
| **RS-2: Local front door for each school** | Use a separate Auto Attendant for each school’s published number. | Include the school name, local greeting, office, attendance, nurse, and directory choices. |
| **RS-3: Find teachers and staff** | Use Dial by Name and Dial by Extension actions in the Auto Attendant. | Define the directory scope, four-digit extension plan, naming standards, and searchable staff. |
| **RS-4: Teacher voicemail** | Route unanswered teacher calls to the selected teacher’s personal Webex Calling voicemail. | Define no-answer behavior, ring duration, mailbox ownership, and whether the policy requires an email notification or an attached audio recording. |
| **RS-5: Main-office coverage** | Use a Hunt Group for each school’s three administrative assistants. | Choose simultaneous or ordered ringing, ring duration, busy behavior, and the shared main-office voicemail destination. |
| **RS-6: Attendance messages** | Use a separate shared mailbox or Voicemail Group for attendance at each school. | Define the greeting, access owners, storage, and shared attendance email address that receives the audio copy. |
| **RS-7: English and Spanish paths** | Use a Spanish-language Auto Attendant with parallel destinations. | Keep the English and Spanish menus aligned and assign an owner for maintaining both versions. |
| **RS-8: School-day, after-hours, delay, and closure routing** | Use schedules and Operating Modes for normal hours, holidays, delayed openings, and closures. | Define district-wide versus school-specific scope, messages, destinations, authorized users, and restoration procedures. |

### Important Riverside boundaries

- Office assistants are not described as a formal queue team, so Customer Assist and Call Queue capabilities are not automatically required.
- Dial by Name and Dial by Extension provide directory access; they do not determine whether a teacher should answer during instruction.
- Teacher voicemail should remain personal, while school-office and attendance voicemail should remain team-owned.
- A separate Spanish Auto Attendant provides clearer system prompts and parallel routing than one bilingual greeting.
- A Hunt Group is appropriate for simple office call distribution. A Call Queue requires a new requirement such as caller waiting, capacity management, callback, or queue reporting.

### Useful Riverside discovery questions

- Should Dial by Name search the entire district or only the selected school?
- Which staff members should be included in the public directory?
- Should teacher calls ring a classroom device, Webex App, or go directly to voicemail during instruction?
- Should each main office ring simultaneously or in a specific order?
- Who maintains the English and Spanish menus?
- Who may activate a district-wide or school-specific delay or closure?

## Reusable design reminders

- Start with the customer journey, not a feature list.
- Explain the normal path and at least one exception path.
- Identify who owns every mailbox, queue, number, and exception.
- State assumptions that could change the design.
- Choose the simplest feature that meets the stated requirement.
- Explain why a plausible alternative does not fit as well.
