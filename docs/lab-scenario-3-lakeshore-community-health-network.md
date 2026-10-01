# Bonus Scenario - Lakeshore Community Health Network

**INDUSTRY:** Outpatient healthcare network | **PAIN:** Private patient access across mobile and shared clinical spaces

!!! quote "Customer Voice"

    Patients and caregivers often have to repeat their information to different staff members when calls are transferred between our four clinics. Staff also need a consistent way to reach colleagues who move among desks, treatment rooms, and mobile assignments. We need a simpler front door, dependable coverage, and a design that does not expose patient information through shared devices or casual voicemail forwarding.

**DESIGN INSTRUCTION**

* Do not start with a feature list. Translate the numbered requirements into the smallest design that creates the stated outcome.
* Use the cheat sheet, each other, your own Collaboration Control Hub for reference, the instructor-provided Control Hub demo login, and/or help.webex.com.
* We are not configuring anything in Collaboration Control Hub.
* There may be more than one way to meet the requirements.

## **Current environment**

* Lakeshore Community Health Network operates four neighborhood clinics and a centralized patient access team. The organization is replacing a legacy phone system while keeping one published patient access number and a direct number for each clinic.
* Twelve patient access representatives handle appointment requests, referrals, and general questions. They need a real waiting experience and callback during busy periods, but the electronic health record is not currently integrated with Webex Calling.
* Nurses and care coordinators move between work areas and sometimes work from mobile assignments. Some staff use Webex App on managed smartphones; the organization is evaluating Cisco Wireless Phones 840 and 860 for teams that need a managed Wi-Fi phone.
* The largest clinic has treatment rooms, rehabilitation space, and a lab area where staff need portable handsets. The network team is considering a Cisco DECT deployment for predictable building coverage rather than treating DECT as a replacement for Wi-Fi.
* Several check-in counters and treatment spaces use shared phones. Staff must be able to sign in to a supported shared phone for a shift or assignment, use their own calling identity, and sign out without leaving personal call history or account information behind. The underlying Workspace must still have a clear identity and defined behavior when no user is signed in. Clinic hours, holidays, weather closures, and after-hours nurse coverage do not follow one schedule.

## **Requirements**

**HC-1 One patient access front door**

**Customer requirement:** The published patient access number must greet callers and offer clear choices for appointments, nurse or care coordination, billing and records, clinic locations, and after-hours help. No-input and invalid-input callers need an intentional destination.

**Success looks like:** A caller reaches the right service in one or two choices, and the design explains what happens when the caller does not make a valid selection.

**HC-2 A local front door for each clinic**

**Customer requirement:** Each clinic must keep its direct number and present a clinic-specific greeting and route for the local front desk, check-in questions, referrals, and a clinic-owned final destination when the local team is unavailable.

**Success looks like:** A caller who dials a clinic directly receives the correct clinic identity and does not fall into a generic district-wide transfer loop.

**HC-3 Patient access calls need a real waiting experience**

**Customer requirement:** Appointment, referral, and general patient-access calls must reach the right representatives, hear useful wait treatment, and be offered callback during sustained demand. The design must define overflow, no-answer, and unavailable-team behavior.

**Success looks like:** The design names a Call Queue or a justified alternative, members, routing, callback treatment, ownership, and the final destination for calls that cannot be answered.

**HC-4 Caller context must not become patient disclosure**

**Customer requirement:** Staff need a practical way to use the incoming number as a search hint, but Webex Calling must not be treated as proof of patient identity or authorization. Shared phones, mobile lock screens, voicemail, and any desktop workflow must avoid exposing protected health information to the wrong person.

**Success looks like:** The design separates caller-number context from identity verification and explains the secure workflow for known, duplicate, shared, and unknown numbers.

**HC-5 Shared clinical spaces need controlled Hot Desking**

**Customer requirement:** Staff who move between check-in counters, treatment areas, and other shared clinical spaces need to sign in to a supported shared phone for a shift or assignment, use their own calling identity, and sign out without leaving personal call history or account information on the device. The base Workspace must still have a clear identity and defined behavior when no user is signed in.

**Success looks like:** The design identifies the Workspace and Hot Desking device, eligible users, sign-in or booking method, expiration and sign-out behavior, privacy cleanup, and incoming-call or emergency behavior before sign-in and after sign-out.

**HC-6 Mobile care teams need a managed business identity**

**Customer requirement:** Nurses and care coordinators must place and receive routine administrative calls while moving between locations without exposing personal cellular numbers. The design must distinguish a managed Webex App or Cisco Wireless Phone experience from emergency clinical dispatch.

**Success looks like:** A patient sees an approved Lakeshore identity, staff can be reached on the managed device or app, and the design states which workflows require a managed desktop or Wi-Fi phone.

**HC-7 Portable coverage must fit the building**

**Customer requirement:** The largest clinic needs portable handsets for authorized staff in treatment, rehabilitation, and lab areas. The design must address coverage, base stations, handset assignment, and what happens when a handset or base is unavailable.

**Success looks like:** The team distinguishes a DECT Network from Wi-Fi mobile calling and describes a deployment and fallback that match the building and operational risk.

**HC-8 Away providers and closures need owned exception paths**

**Customer requirement:** Providers and care coordinators need a scheduled away experience for routine calls, while the patient access and after-hours routes need separate behavior for holidays, weather closures, and unexpected clinic shutdowns. Messages must land in an owned mailbox without sending protected audio to an uncontrolled personal inbox.

**Success looks like:** The design explains when Personal Call Routing is appropriate for an individual, when Operating Modes or schedules control a shared service, who can activate and restore an exception, and how the final voicemail path protects ownership and privacy.

## **Design challenge**

1. **Prioritize:** Identify the three requirements that most directly protect patient experience, staff safety, or privacy.
2. **Map:** Name the Webex Calling feature or design decision that addresses each numbered requirement.
3. **Detail:** Describe the important route, identity, schedule, device, role, privacy, or policy choice at a conceptual level.
4. **Explain:** State why this choice fits the network better than a plausible alternative.
5. **Discover:** Ask at least three questions whose answers could change the design.
6. **Present: Prepare a two-minute recommendation using requirement IDs so the customer can trace every choice.**

## **Discussion checkpoints**

* Can the team explain the patient or staff experience without relying on feature names alone?
* Can the team identify where identity verification and protected-health-information controls actually live?
* Can the team distinguish an individual away workflow from shared-service coverage and emergency operations?
* Can the team explain why Hot Desking, a Workspace, a DECT Network, a Wi-Fi phone, a queue, or a voicemail design is appropriate for the stated space or role?

