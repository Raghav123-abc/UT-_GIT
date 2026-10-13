# Omni-Channel Presence Statuses

| | |
|---|---|
| **Extraction date** | 2026-10-13 |
| **Environment** | Sandbox |
| **Org alias** | FullSando |
| **Source** | Setup > Omni-Channel > Presence Statuses, read through the Salesforce API (ServicePresenceStatus metadata and SetupEntityAccess) |
| **Total statuses** | 7 |

## Presence statuses

A status with no channels is a **Busy** status: agents in it receive no work.

| Status name | API name | Type | Case | Messaging | Phone | Created | Last modified | Record ID |
|---|---|---|:-:|:-:|:-:|---|---|---|
| Available for All Support | `Available_for_All_Support` | Online | ✓ | ✓ | ✓ | 2025-03-17 | 2025-03-17 | 0N5Vb00000003cDKAQ |
| Ready for Cases Only | `Available_for_Cases_Only` | Online | ✓ | ✓ | | 2025-03-17 | 2026-09-18 | 0N5Vb00000003dpKAA |
| Ready for Voice Only | `AvailableforVoice` | Online | | | ✓ | 2023-06-20 | 2025-03-17 | 0N55f000000XmTFCA0 |
| Available for back up | `Available_for_back_up` | Online | | | ✓ | 2026-06-29 | 2026-07-13 | 0N5Va00000010NlKAI |
| Available for high priority | `Available_for_high_priority` | Online | | | ✓ | 2026-06-29 | 2026-07-13 | 0N5Va00000010M9KAI |
| Voice Call Available | `Voice_Call_Available` | Online | | | ✓ | 2023-06-27 | 2026-07-14 | 0N55f000000XmTKCA0 |
| Voice Call Busy | `Voice_Call_Busy` | Busy | | | | 2023-06-27 | 2023-06-27 | 0N55f000000XmTPCA0 |

Service channel API names: Case = `Case`, Messaging = `sfdc_livemessage`, Phone = `sfdc_phone`.

## Access by profile and permission set

Agents can only select a presence status that their profile or one of their permission sets gives them access to.

| Granted through | All Support | Cases Only | Voice Only | Back up | High priority | Voice Call Available | Voice Call Busy |
|---|:-:|:-:|:-:|:-:|:-:|:-:|:-:|
| **Profile:** System Administrator | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Profile:** Director of Support | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Profile:** Foundation System Administrator | ✓ | ✓ | ✓ | | | | |
| **Profile:** Apollo API | ✓ | ✓ | ✓ | | | | |
| **Profile:** General Support | | | ✓ | | | | |
| **Permission set:** Omni Users Access | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Permission set:** Omni Case-Voice Access | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ | ✓ |
| **Permission set:** General Service | ✓ | ✓ | ✓ | | | | ✓ |
| **Permission set:** General Support | ✓ | ✓ | ✓ | | | | ✓ |
| **Permission set:** Partner Telephony Permission Set | | | ✓ | | | | |
| **Permission set:** Service Cloud Voice Permission Set | | | ✓ | | | | |

## Notes

1. **Labels and API names differ for two statuses.** "Ready for Cases Only" has the API name `Available_for_Cases_Only`, and "Ready for Voice Only" has the API name `AvailableforVoice`. Use the API names when deploying or referencing these statuses.
2. **"Available for high priority" and "Available for back up" are Phone only.** Their names suggest they are meant for case work (for example the High Priority Case Queue), but an agent in either status receives no cases. Add the Case channel if they are meant for cases.
3. **"Ready for Cases Only" also includes Messaging,** not only Case.
4. **"Voice Call Busy" is a Busy status.** It has no channels, so agents in it receive no work. This is expected for agents on a call.
5. **"Voice Call Available" is not in the General Service or General Support permission sets,** although "Voice Call Busy" is. Agents who rely only on those permission sets can't select it.
6. **Omni Configurations and Queues deployment.** All 7 statuses are listed in the TVM Omni Configurations and Queues deployment as "Deployed / Active in Prod". In the deployment document, "Available for back up" is spelled "Available for backup".
