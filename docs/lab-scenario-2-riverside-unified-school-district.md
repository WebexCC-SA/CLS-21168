# Lab Scenario 2 - Riverside Unified School District

Public K-12 school district | PAIN: Too many transfers + inconsistent call handling | OUTCOME: Families reach the right school or staff member

| **CUSTOMER VOICE**  We are a small public school district with an elementary school, a middle school, and a high school. Families often call the district number when they really need a school office, attendance, transportation, or a teacher. We want a simple menu, a staff directory, and direct extension dialing so callers can reach the right person without a chain of transfers. Our office assistants answer regular calls; they are not a formal customer-service team. We also need shared attendance voicemail, English and Spanish call paths, and consistent messages for holidays, delayed openings, and closures. |
| --- |

| **DESIGN INSTRUCTION**  Do not start with a feature list. Translate the numbered requirements into the smallest design that creates the stated outcome. Use the cheat sheet and, if available, optional read-only Control Hub browsing as references; no system changes are part of this activity. |
| --- |

### Current environment

* The district is replacing a legacy PBX while keeping one district main number and one published number for each of its three schools.
* Approximately 240 staff members have four-digit extensions. Most teachers cannot take unscheduled calls during instruction, but callers should be able to find them by name or extension and leave personal voicemail.
* Each school main office has three administrative assistants who answer calls as part of their normal duties. There is no queue sign-in process, callback service, or dedicated call supervisor.
* Attendance messages belong to each school office, not to one employee. English and Spanish are the most common languages, and the district needs separate behavior for school days, after hours, holidays, delayed openings, and closures.

### Specific customer requirements

**RS-1 District main number as a clear front door**

**Customer requirement:** The district number must offer simple choices for the three schools, enrollment, transportation, the staff directory, and an operator, with explicit no-input and invalid-input behavior.

**Success looks like:** A family reaches a school or district department in one selection without first relying on a receptionist to transfer the call.

**RS-2 A local front door for each school**

**Customer requirement:** Each school must keep its published number and play a school-specific greeting with choices for the main office, attendance, nurse, and staff directory.

**Success looks like:** Callers who dial a school directly hear the correct school name and reach local destinations; the district menu can transfer to the same school entry point.

**RS-3 Find teachers and staff by name or extension**

**Customer requirement:** A caller must be able to use the Auto Attendant to search for a teacher or staff member by name or enter a known four-digit extension.

**Success looks like:** The design names the Dial by name and Dial by extension menu actions, defines the intended directory scope, and identifies how naming data will be kept usable.

**RS-4 Teacher voicemail without a transfer chain**

**Customer requirement:** When a teacher does not answer, the call must reach that teacher's voicemail instead of returning to the main office. The teacher needs an email notification or audio copy according to district policy.

**Success looks like:** The caller can leave a message for the selected teacher, and the design distinguishes a notification from an attached recording while preserving an owned personal mailbox.

**RS-5 Main office coverage without a formal queue**

**Customer requirement:** Calls for a school main office should ring its three administrative assistants in a predictable pattern and then reach the school's shared main-office voicemail if nobody answers.

**Success looks like:** The design identifies a Hunt Group, members, routing pattern, ring or advance behavior, and a final owned destination without inventing queue states or callback service.

**RS-6 Attendance messages owned by each school**

**Customer requirement:** A caller choosing attendance must be able to leave a message in that school's attendance mailbox, and the recording must be delivered to the shared attendance email address.

**Success looks like:** Each school has a team-owned Voicemail Group or equivalent shared mailbox with a clear greeting, access owners, storage decision, and email audio-copy behavior.

**RS-7 English and Spanish caller paths**

**Customer requirement:** The district and school menus must offer an understandable Spanish path while routing families to the same schools, offices, directories, and mailboxes as the English path.

**Success looks like:** The design uses a Spanish-language Auto Attendant or a clearly justified bilingual greeting strategy, and identifies how paired menus and destinations will stay aligned.

**RS-8 School-day, after-hours, delay, and closure routing**

**Customer requirement:** District and school numbers must play the right message and follow the right route for school days, after hours, holidays, delayed openings, and closures. Authorized district staff must be able to switch and restore an exception.

**Success looks like:** Scheduled behavior changes automatically, and authorized staff can activate and restore a district-wide or school-specific delay or closure without rebuilding menus.

### Known constraints

* Do not assume Customer Assist or a Call Queue: office assistants have no queue states, callback promise, or dedicated supervisor workflow in the stated requirements.
* Dial by name and dial by extension provide directory access; they do not decide whether a teacher should answer during instruction. That remains a district policy and per-user call-handling decision.
* An Auto Attendant uses one selected language for its default prompts. A separate Spanish Auto Attendant is usually the cleaner way to provide Spanish system prompts and a parallel menu.

### Your design challenge

1. **Prioritize:** Identify the three requirements that most directly protect customer experience or operations.
2. **Map:** Name the Webex Calling feature or design decision that addresses each numbered requirement.
3. **Detail:** Describe the important route, identity, schedule, membership, role, desktop, or policy choices at a conceptual level.
4. **Explain:** State why this choice fits the business better than a plausible alternative.
5. **Discover:** Ask at least three questions whose answers could change the design.
6. **Walk through:** Explain the normal customer experience and at least one relevant after-hours, invalid-input, no-answer, unavailable-team, full-queue, callback, or closure path in words.
7. **Present:** Prepare a three-minute recommendation using requirement IDs so the customer can trace every choice.

### Discussion checkpoints

* Can the team explain the normal caller or user experience without relying on feature names alone?
* Can the team identify assumptions that would change the recommendation?
* Can the team distinguish required capabilities from optional enhancements?

| **OPTIONAL ROUND-TWO TWIST**  During enrollment week, calls for enrollment and transportation spike. Add temporary office coverage and clearer menu routing without assuming a formal queue. If you recommend a Call Queue, state the new waiting, capacity, or callback requirement that justifies it. |
| --- |
