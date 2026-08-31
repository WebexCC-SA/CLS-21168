# Lab 3 Webex Calling: Feature Cheat Sheet

**Popular features and design building blocks**

*Use this sheet to identify possible features and design questions. Availability, licensing, providers, supported devices, limits, and regional requirements can vary.*

### Administration features

#### 1. Call Routing & Reception

* **Auto Attendant (AA):** The digital receptionist. Uses greetings, keypress menus, business and holiday schedules, and defined no-input and invalid-input routes. It routes callers but does not hold them for an agent.
* **Operating Modes:** Routes a managed feature differently by schedule or by an authorized manual mode change. Modes can control forwarding for Auto Attendants, Hunt Groups, Call Queues, and Customer Assist queues.
* **Call Queue:** The waiting room. Holds callers until an agent is available and can include routing patterns, announcements, music, callback, overflow, bounced-call and stranded-call handling, forced forwarding, agent states, analytics, and reports.
* **Customer Assist:** Adds contact-center capabilities to Webex Calling queues, including screen pop, wrap-up, real-time queue views, and richer agent and supervisor analytics in Webex App. Some experiences require the desktop app.
* **Hunt Group:** Distributes calls among members without putting callers in a queue. Routing patterns include Top Down, Circular, Longest Idle, Weighted, and Simultaneous, with a defined busy or no-answer destination.
* **Paging Group:** A live, one-way audio broadcast to eligible phones. Originators and target devices are defined so only authorized users can start a page.
* **Call Pickup Group:** Allows a group member to answer a call ringing another member's supported phone or Webex App without sharing credentials or changing the called number.
* **External and Queue Caller ID:** Controls the business number presented by a user, workspace, virtual line, or queue. A permitted queue identity can keep service callbacks recognizable and returnable; PSTN provider and CNAM rules still apply.
* **Virtual Lines:** Additional cloud-based lines that are not tied to a dedicated user. They can support shared line appearances, service identities, call routing, recording policies, or shared voicemail designs.

#### 2. Mobility & Flexible Work

* **Webex App:** The primary interface for calling, messaging, and meetings on desktop and mobile. Webex Calling presents the approved business identity instead of a personal mobile number.
* **Webex Go:** Mobile operator integration that adds a Webex Calling business number to a supported phone's native dialer. Carrier, country, device, and entitlement support must be confirmed.
* **Hot Desking:** Lets an eligible user book and sign in to a supported shared workspace phone so the device loads the user's line and permitted personal calling information for the booking period.
* **Hot Desking Pre-booking / Workspace Booking:** Allows a shared workspace or device to be reserved before arrival through an approved calendar, Cisco Spaces, or supported third-party booking service. The user confirms identity when claiming the resource.
* **Hot Desking Sign-out and Privacy:** Removes the user's line, calendar, call history, contacts, and other personal data at manual or automatic sign-out. An active call delays automatic sign-out until the call ends.
* **Call Forwarding:** Redirects incoming calls to another number, user, or voicemail. Common choices include Forward All, Busy, No Answer, and Selective Forwarding.
* **Network-Disconnect Forwarding:** Forwards calls for an eligible user or workspace when its primary calling devices are unreachable because the office loses connectivity. It addresses a different failure point than PSTN or gateway resiliency.

#### 3. Productivity, Integrations & Compliance

* **Call Recording:** Captures call audio under an assigned policy for users, workspaces, virtual lines, or queues. Design decisions include provider, Always or On-Demand behavior, pause or resume, announcements, access, storage, and retention.
* **Voicemail Group / Shared Voicemail:** Provides a shared mailbox for a department or call-routing feature. A voicemail group or virtual-line mailbox can have a common greeting, controlled access, notifications, and an optional transfer-to-zero destination.
* **Email a Copy of Message:** Sends the voicemail audio recording to a designated email address. This is different from a new-message notification; internal versus external storage choices affect in-app access and transcription.
* **Voicemail Transcription:** Converts supported voicemail messages to text and can deliver the transcript with the audio by email when the organization and mailbox settings allow it.
* **Customer Assist screen pop:** Customer Assist screen pop can open a supported URL or search workflow for inbound calls; define how known, duplicate, and unknown numbers are handled. Can be used to provide information about customers from CRM’s such as Salesforce.
* **Webex Calling Detailed Call History / CDR:** Organizational call metadata such as parties, time, direction, duration, and routing. Detailed Call History reports or the CDR API support analysis and export; CDR is not conversation audio.
* **Compliance, eDiscovery, and Legal Hold:** Allows an authorized compliance officer to search and export eligible Webex Calling CDR and call-recording content and preserve covered data under legal hold. Availability, retention, licensing, geography, and provider storage must be confirmed.
* **Queue Analytics, Reports, and Supervisor Views:** Provides live and historical queue and agent information, including answered and abandoned calls, wait and handle measures, agent state, and service-level trends. The exact experience depends on Call Queue or Customer Assist licensing.
* **Call Park:** Places a call on a park extension so another authorized user can retrieve it from a supported phone or app.
* **Privacy / Do Not Disturb:** Helps a user control interruptions and visibility. Do Not Disturb changes how calls alert the user; caller-ID privacy controls whether an outbound number is presented.

#### 4. Connectivity, PSTN & Resiliency

* **Cisco Calling Plan:** Cisco supplies supported phone numbers and PSTN connectivity for eligible locations, simplifying cloud calling ownership where available.
* **Cloud Connected PSTN (CCP):** Uses a supported cloud PSTN provider for the selected country and location without customer-managed on-premises PSTN hardware.
* **Premises-based PSTN / Local Gateway (LGW):** Connects Webex Calling to an on-premises PSTN provider or PBX through a supported session border controller. It adds dial-plan, security, resiliency, monitoring, and support-owner responsibilities.
* **Trunks, Route Groups, and Dial Plans:** A trunk connects Webex Calling to the premises; a route group combines trunks for distribution or redundancy; a dial plan routes matching enterprise numbers to a trunk or route group.
* **PSTN Migration and Number Porting:** Coordinates number ownership, port orders, main and location numbers, caller ID, coexistence, cutover, rollback, and support ownership when moving public calling to Webex Calling.
* **Emergency Calling and Location Addressing:** Aligns emergency-service requirements, location and address information, endpoint movement, notifications, and provider obligations with the selected PSTN design and operating regions.

#### 5. Shared Spaces, Devices & Meetings

* **Cisco Board, Desk, and Room Series:** Collaboration devices selected according to room size, seating, camera sight lines, microphone pickup, speakers, displays, controls, accessibility, and support needs.
* **RoomOS Content Sharing and Meeting Interoperability:** Supports wired or wireless content sharing and Webex or supported external meeting join workflows. Available methods and layouts depend on the device, RoomOS version, displays, and meeting service.
* **Room and Bandwidth Design:** Matches media quality and display layout to the network and room. Bandwidth is shared dynamically across audio, main video, content, screens, and layouts, so room-specific discovery matters.

### Lab Webex User Hub: The End-User Control Center

#### 1. Call Handling (Flexibility on the Go)

* **Call Forwarding:** Users can manage permitted Forward All, Busy, No Answer, Selective, and network-disconnect options. Organization or workspace policy can affect which settings are available.
* **Simultaneous Ring:** Rings multiple destinations at the same time so the user can answer from the most convenient device.
* **Sequential Ring:** Rings a defined series of destinations in order before following the final no-answer treatment.
* **Do Not Disturb (DND):** Suppresses normal call alerting so the user can avoid interruptions; final call treatment follows the applicable calling settings.
* **Operating Mode Management:** An authorized user can view and switch assigned operating modes for managed calling features, including scheduled and exception routing.

#### 2. Voicemail Management (The "Set it and Forget it" Features)

* **Voicemail Greeting:** Users can record and manage their personal professional greetings when allowed by policy.
* **Voicemail-to-Email:** Users can select an email address for an audio copy when that option is enabled; this is different from notification-only email.
* **Voicemail PIN:** Users can reset their own PIN without a help-desk request when self-service is available.
* **Transcription:** Users can receive supported voicemail transcripts when transcription is enabled for the organization and mailbox.

#### 3. Privacy & Personalization

* **Block Caller ID:** Users can suppress their number for eligible outbound calls when the organization and PSTN service allow it.
* **Call Logs:** Users can view their own recent incoming, outgoing, and missed calls. Personal call history is not an organizational CDR or compliance archive.
* **Profile Settings:** Users can manage permitted profile preferences such as display name, time zone, and language.

#### 4. Device Management

* **Devices and App Downloads:** Users can see devices associated with their account and download Webex App for supported desktop and mobile platforms.
