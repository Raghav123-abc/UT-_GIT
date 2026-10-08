# Claude Project Rules

Rules for maintaining the TVM Project Repository.

1. **Document every requirement.** Add an entry in `Documentation/03_Requirements/`.
2. **Document every metadata change.** Add a record in `Documentation/04_Change_Records/`.
3. **Maintain before/after values.** Every change record states the value before and after the change.
4. **Record the Salesforce org alias.** Every change record and deployment note names the org alias it applies to.
5. **Maintain deployment notes.** Add an entry in `Documentation/06_Deployment/` for every deployment.
6. **Maintain conflict logs.** Log every conflict and its resolution in `Documentation/05_Conflicts/`.
7. **Update technical documents automatically.** When metadata changes, update the matching folder in `Documentation/07_Technical_Documents/` in the same commit.
8. **Organize entries by date.** Name entries `YYYY-MM-DD_<short-name>.md`.
9. **Create meaningful commit messages.** Say what changed and why, e.g. `Add Test_Address__c field on Contact (REQ: address capture)`.
10. **Never overwrite historical records.** Add new entries or append to existing ones; never edit or delete past entries.
11. **Log every Salesforce change in the master change log.** Add one new row per change to `Documentation/04_Change_Records/Change_Log.xlsx`, commit it, show the changes for review, and push to GitHub only after confirmation. Never edit or delete existing rows.
