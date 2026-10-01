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

## Lakeshore Community Health Network

### Design at a glance

Patient access Auto Attendant → clinic-specific Auto Attendants → patient-access Call Queue with callback → privacy-aware caller context → Workspace Hot Desking → Webex App mobile or Cisco Wireless Phones 840/860 → DECT Network → Personal Call Routing, schedules, Operating Modes, and team-owned voicemail

| Requirement | Possible design | Important considerations |
|---|---|---|
| **HC-1: One patient access front door** | Use an Auto Attendant on the published patient access number. | Provide choices for appointments, nurse or care coordination, billing and records, clinic locations, and after-hours help. Define no-input, invalid-input, retry, operator, and final destinations. An Auto Attendant routes choices but does not create a waiting queue or verify patient identity. |
| **HC-2: A local front door for each clinic** | Use a separate Auto Attendant or direct feature path for each clinic number. | Preserve the clinic identity and route callers to the local front desk, check-in, referrals, and a clinic-owned no-answer destination. Define local schedules, holiday behavior, and how the district number reaches the local entry point without creating a transfer loop. |
| **HC-3: Patient access calls need a real waiting experience** | Use a Call Queue for appointments, referrals, and general patient access. | Define members, routing, announcements or music, callback eligibility, estimated-wait messaging, capacity, overflow, hours, no-answer behavior, and final ownership. Customer Assist may be considered when the desktop workflow or supervisor analytics require it, but it does not replace an EHR privacy workflow. |
| **HC-4: Caller context must not become patient disclosure** | Use the incoming number as a search hint only. If a screen pop or secure EHR landing page is proposed, require the organization’s authorization and verification process before displaying patient information. | Define the handling of duplicate household numbers, shared caregiver numbers, unknown or blocked callers, and wrong-number calls. The EHR or approved clinical workflow—not Webex Calling or a screen pop—must own matching, authentication, consent, audit, and PHI masking. |
| **HC-5: Shared clinical spaces need controlled Hot Desking** | Configure a supported shared phone in a Workspace with Hot Desking enabled. Eligible users sign in or book the phone for a shift or assignment; the device temporarily uses the user’s calling identity and clears personal data at sign-out. | Identify the supported device and eligible users. Define sign-in or booking, booking duration, automatic and manual sign-out, expiration, privacy cleanup, incoming-call behavior, emergency behavior before sign-in, and the callback or shared-location behavior after sign-out. Do not use a permanent shared employee account. |
| **HC-6: Mobile care teams need a managed business identity** | Use Webex App mobile and/or supported Cisco Wireless Phones 840/860 for appropriate users, with an approved clinic or care-coordination caller ID. | Confirm device ownership, Wi-Fi coverage, battery and loss procedures, callback routing, and which workflows require a desktop. Keep routine administrative mobility separate from emergency clinical dispatch, clinical policy, and identity verification. |
| **HC-7: Portable coverage must fit the building** | Use a Cisco DECT Network with a deliberate base-station and handset design, or document a justified alternative based on RF coverage and building layout. | Discuss single-cell or multicell design, base placement, handset assignment, roaming, access codes, battery and loss procedures, maintenance, and fallback if a base or handset is unavailable. DECT is a managed base-and-handset deployment, not a generic Wi-Fi network and not interchangeable with Cisco Wireless Phones without discovery. |
| **HC-8: Away providers and closures need owned exception paths** | Use Personal Call Routing for an individual provider or care coordinator who needs a scheduled away experience. Use schedules and Operating Modes for shared patient-access, after-hours, holiday, weather-closure, and unexpected-shutdown behavior. | Define who can activate and restore an exception, the coverage destination, dates, closure greeting, no-loop restoration, mailbox ownership, and whether email is notification-only or includes audio. Keep patient-related voicemail within the organization’s approved secure delivery policy. |

### Important Lakeshore boundaries

- Caller ID, Customer Assist context, and a screen pop are not patient identity, authentication, consent, or authorization.
- Workspaces provide the shared-device foundation for Hot Desking; Hot Desking temporarily loads a named user identity and clears personal data at sign-out.
- Hot Desking is not the same as using one shared employee account for every treatment room. The answer must define the sign-in, sign-out, expiration, privacy, and no-user lifecycle.
- DECT Network, Cisco Wireless Phones 840/860, and Webex App mobile are distinct endpoint and coverage choices.
- Personal Call Routing is an individual away experience. Shared on-call coverage belongs on a managed service route with an owner and restore rule.
- Voicemail notification, attached audio, transcription, and internal mailbox access are separate outcomes with different privacy implications.
- A Call Queue or Customer Assist queue can organize administrative callers; neither is a substitute for emergency clinical dispatch or an EHR privacy workflow.

### Useful Lakeshore discovery questions

- Which calls are administrative, which are nurse or care-coordination work, and which must immediately follow the approved emergency process?
- What identity and authorization checks are required before staff open a patient record, and which EHR workflow owns the audit trail?
- Are the four clinic schedules, after-hours nurse coverage, holidays, and weather closures managed centrally or independently?
- Do patient-access callers need estimated wait, callback, and queue analytics, or would a simpler Hunt Group meet the service promise?
- Which shared spaces need Hot Desking, which users are eligible, and what should happen before sign-in, after sign-out, or when a booking expires?
- What is the building layout, RF survey result, handset count, and failure fallback for the proposed DECT coverage?
- Does the privacy policy permit voicemail email notification, attached audio, transcription, or none of these for patient-related calls?
- Who can activate and restore a clinic closure or provider-away exception, and how will the change be communicated and audited?

### Common Lakeshore red flags

| Participant response | Why it is incomplete or incorrect |
|---|---|
| “The phone number finds the patient automatically.” | Caller ID is a hint, not authentication. Duplicate, shared, blocked, and unknown numbers require an approved verification workflow. |
| “Use one shared employee account for every treatment room.” | This mixes personal identities and history and undermines privacy. Use a supported Workspace device with a defined Hot Desking lifecycle. |
| “Use DECT because it is wireless Wi-Fi.” | DECT and Wi-Fi wireless phones use different deployment models, coverage assumptions, devices, and support decisions. |
| “Forward every provider to the on-call nurse’s personal mobile.” | This exposes personal identity and does not define authorization, hours, no-answer behavior, caller ID, or restoration. |
| “Send every voicemail recording to a personal email inbox.” | Patient-related audio may require controlled storage and delivery. Notification, attached audio, transcription, and access are different choices. |
| “The Auto Attendant handles the busy patient-access period.” | An Auto Attendant routes choices but does not hold callers, offer callback, manage agent state, or provide queue analytics. |
| “Put patient names on the shared phone screen.” | Shared and mobile endpoints can expose PHI to the wrong person. Minimize call context and keep record access in the authorized workflow. |

### Round-two twist debrief

**Customer change:** A satellite clinic opens in two weeks, and the privacy office rejects automatic patient-name display based on phone-number matching.

**Look for:** A new clinic entry point or route with its own schedule and owner; a Workspace and device plan for the new location; queue membership, capacity, and callback changes; an explicit secure EHR search and verification workflow; and a safe activation and restoration process.

**Do not reward:** A new menu branch with no staffing or hours, automatic patient selection from caller ID, or a personal mobile forward presented as the healthcare solution.

## Reusable design reminders

- Start with the customer journey, not a feature list.
- Explain the normal path and at least one exception path.
- Identify who owns every mailbox, queue, number, and exception.
- State assumptions that could change the design.
- Choose the simplest feature that meets the stated requirement.
- Explain why a plausible alternative does not fit as well.
