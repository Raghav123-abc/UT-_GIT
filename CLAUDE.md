# TVM Project Repository

Documentation repository for the TVM Salesforce project. Follow the rules in
`Documentation/01_Instructions/Claude_Project_Rules.md`.

## Salesforce orgs

- **FullSando** (sandbox): `sandipp@unitedtechno.com.tvmprod.fullsando`. No CLI alias is set on this PC, so pass the username to `--target-org`.

## Workflow for every Salesforce change

Applies to every metadata, configuration, flow, field, object, validation rule,
Apex, LWC, integration, deployment or permission change.

1. Before deploying, show the change and run a check-only deploy (`--dry-run`). Deploy only after the user confirms.
2. Add one new row per change (per deployment) to `Documentation/04_Change_Records/Change_Log.csv`. Fill all 14 columns (there is no Changed By column; it was removed at the user's request). Never edit or delete existing rows; correct a past entry by adding a new row.
3. Create or update supporting documentation when needed: a dated change record in `Documentation/04_Change_Records/` (`YYYY-MM-DD_<Name>.txt`), and the matching folder in `Documentation/07_Technical_Documents/`.
4. Commit all modified files with a meaningful message.
5. Show the changes for review, then push to GitHub only after the user confirms.

## Editing Change_Log.csv

The log is a CSV (not Excel) so the user can read it directly on GitHub. Append rows
only; never rewrite the file. Keep it UTF-8 without a BOM, LF line endings, every value
in double quotes (double any `"` inside a value), and the 14-column header order:
Date, Environment, Org Alias, Component Type, Component Name, API Name, Reason,
Before Change Details, After Change Details, Change Summary, Deployment Details,
Rollback Details, Testing Details, Salesforce Link.
Read it back with `Import-Csv` to confirm the new row before committing.

## Repository notes

- The GitHub repository `Raghav123-abc/UT-_GIT` is **public**. Point out personal or sensitive data before pushing it.
- `.sf/`, `.sfdx/` and `.vscode/` are excluded locally in `.git/info/exclude`; never commit them.
- Folders under `Documentation/` are numbered (`01_` to `07_`) to set their display order on GitHub.
