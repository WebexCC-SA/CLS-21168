# Riverside Unified School District

## Design at a glance

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

## Important Riverside boundaries

- Office assistants are not described as a formal queue team, so Customer Assist and Call Queue capabilities are not automatically required.
- Dial by Name and Dial by Extension provide directory access; they do not determine whether a teacher should answer during instruction.
- Teacher voicemail should remain personal, while school-office and attendance voicemail should remain team-owned.
- A separate Spanish Auto Attendant provides clearer system prompts and parallel routing than one bilingual greeting.
- A Hunt Group is appropriate for simple office call distribution. A Call Queue requires a new requirement such as caller waiting, capacity management, callback, or queue reporting.

## Useful Riverside discovery questions

- Should Dial by Name search the entire district or only the selected school?
- Which staff members should be included in the public directory?
- Should teacher calls ring a classroom device, Webex App, or go directly to voicemail during instruction?
- Should each main office ring simultaneously or in a specific order?
- Who maintains the English and Spanish menus?
- Who may activate a district-wide or school-specific delay or closure?
