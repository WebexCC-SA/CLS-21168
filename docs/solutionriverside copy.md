# Lakeshore Community Health Network

## Design at a glance

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

## Important Lakeshore boundaries

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

## Common Lakeshore red flags

| Participant response | Why it is incomplete or incorrect |
|---|---|
| “The phone number finds the patient automatically.” | Caller ID is a hint, not authentication. Duplicate, shared, blocked, and unknown numbers require an approved verification workflow. |
| “Use one shared employee account for every treatment room.” | This mixes personal identities and history and undermines privacy. Use a supported Workspace device with a defined Hot Desking lifecycle. |
| “Use DECT because it is wireless Wi-Fi.” | DECT and Wi-Fi wireless phones use different deployment models, coverage assumptions,solu devices, and support decisions. |
| “Forward every provider to the on-call nurse’s personal mobile.” | This exposes personal identity and does not define authorization, hours, no-answer behavior, caller ID, or restoration. |
| “Send every voicemail recording to a personal email inbox.” | Patient-related audio may require controlled storage and delivery. Notification, attached audio, transcription, and access are different choices. |
| “The Auto Attendant handles the busy patient-access period.” | An Auto Attendant routes choices but does not hold callers, offer callback, manage agent state, or provide queue analytics. |
| “Put patient names on the shared phone screen.” | Shared and mobile endpoints can expose PHI to the wrong person. Minimize call context and keep record access in the authorized workflow. |

## Reusable design reminders

- Start with the customer journey, not a feature list.
- Explain the normal path and at least one exception path.
- Identify who owns every mailbox, queue, number, and exception.
- State assumptions that could change the design.
- Choose the simplest feature that meets the stated requirement.
- Explain why a plausible alternative does not fit as well.