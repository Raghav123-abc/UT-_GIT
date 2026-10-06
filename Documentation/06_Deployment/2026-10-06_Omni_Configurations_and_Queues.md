# Deployment Summary: Omni Configurations and Queues

| | |
|---|---|
| **Recorded on** | 2026-10-06 |
| **Source document** | [TVM - Deployment Document - Omni Configurations and Queues.pdf](Source_Documents/TVM%20-%20Deployment%20Document%20%20-%20Omni%20Configurations%20and%20Queues.pdf) |
| **Target org** | Production (per the source document) |
| **Salesforce org alias** | Not stated in the source document. To be confirmed. |
| **Deployment date** | Not stated in the source document. To be confirmed. |

## Overall status

Every component was **deployed** to production. A **partial rollback** followed:

- **Removed from prod:** Queues and Routing Configurations were deleted.
- **Deactivated in prod:** Service Channels, one Routing Configuration row (see note 1), and the Skill Based Routing Rules.
- **Still active in prod:** Presence Statuses, Skills, Service Resources (user skill assignments), Permission Sets, the Permission Set Group, the Supervisor Configuration and the Static Resource.

## Components

| # | Component type | Components | Deployment status | Rollback status |
|---|---|---|---|---|
| 1 | Queues | Cases: High Priority Case Queue, Medium Priority Case Queue, Low Priority Case Queue, Supervisors_Queue_for_dis, Enterprise_Queue, Supervisors_Queue. Voice: Voice Queue | Deployed | Deleted from prod |
| 2 | Routing Configurations | Cases: High Priority Case Routing Config, Low Priority Case Routing Config, Medium Priority Case Routing Config, Supervisors routing config. Voice: TVM Voice Routing Config | Deployed | Deleted from prod |
| 2a | Routing Configurations | No component named (see note 1) | Deployed | Deactivated from prod |
| 3 | Service Channels | Case | Deployed | Deactivated from prod |
| 4 | Service Channels | Messaging | Deployed | Deactivated from prod |
| 5 | Service Channels | Phone | Deployed | Deactivated from prod |
| 6 | Presence Statuses | Available for All Support, Available for backup, Available for high priority, Ready for Cases Only, Ready for Voice Only, Voice Call Available, Voice Call Busy | Deployed | Active in Prod |
| 7 | Skills | General, Inventory | Deployed | Active in Prod |
| 8 | User Assignments (Service Resources): General skill | 19 users (listed below) | Deployed | Active in Prod |
| 9 | User Assignments (Service Resources): Inventory skill | 11 users (listed below) | Deployed | Active in Prod |
| 10 | Skill Based Routing Rules | Skill based rules for cases | Deployed | Deactivated from prod |
| 11 | Permission Sets | Omnichannel Supervisor, Omni Users Access | Deployed | Active in Prod |
| 12 | Permission Set Groups | Omni Supervisor Access | Deployed | Active in Prod |
| 13 | Supervisor Configurations | General_Support, Primary_General_Support | Deployed | Active in Prod |
| 14 | Static Resources | silent | Deployed | Active in Prod |

## User assignments

### General skill (19 users)

1. Alan Flores
2. Jacob Moon
3. Jaime Ruiz
4. Jemma Sombrio
5. John Puglisi Clark
6. Joseph Cushmore
7. Nathan Corbitt
8. Rebecca Stuchetz
9. Alex Calacci
10. Ridesh Nair
11. Audry Sharpe
12. Robert Wilson
13. Emmanuel Lopez
14. Scott Vogelgesang
15. Jacob DiBiase
16. Erin Abad
17. Hayden West
18. Zyad Elmaghraby
19. Maria Mychaljuk

### Inventory skill (11 users)

1. Alvaro Lechuga
2. Francisco Alvidrez
3. Justin Dexter
4. Justin Schwartz
5. Maria Mychaljuk
6. Moses Cano
7. Marco Castillo
8. Nick Manuel
9. Ryan Franzen
10. Scott Vogelgesang
11. Alex Calacci

Three users have both skills: Alex Calacci, Maria Mychaljuk and Scott Vogelgesang.

## Notes and open questions

1. **Unnamed Routing Configuration row.** The source document has a second Routing Configuration row with no description, marked "Deployed / Deactivated from prod". It doesn't say which routing configuration this is.
2. **Rollback is incomplete.** Queues, routing configurations, channels and routing rules were rolled back. Skills, service resources, presence statuses, permission sets, the supervisor configuration and the static resource are still active in production. Confirm whether that is intended.
3. **Org alias and deployment date** are missing from the source document (project rule 4).
4. **Corrected spellings.** The source document spells two component types as "Superviosr Configuration" and "Skillls". They are written correctly above. Component and user names are copied exactly as they appear.
