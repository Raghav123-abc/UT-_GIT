# TVM Project Repository

Documentation repository for the TVM Salesforce project. Follow the rules in
`Documentation/01_Instructions/Claude_Project_Rules.md`.

## Salesforce orgs

- **FullSando** (sandbox): `sandipp@unitedtechno.com.tvmprod.fullsando`. No CLI alias is set on this PC, so pass the username to `--target-org`.

## Workflow for every Salesforce change

Applies to every metadata, configuration, flow, field, object, validation rule,
Apex, LWC, integration, deployment or permission change.

1. Before deploying, show the change and run a check-only deploy (`--dry-run`). Deploy only after the user confirms.
2. Add one new row per change (per deployment) to `Documentation/04_Change_Records/Change_Log.xlsx`, sheet `Change_Log`. Fill all 15 columns. Never edit or delete existing rows; correct a past entry by adding a new row.
3. Create or update supporting documentation when needed: a dated change record in `Documentation/04_Change_Records/` (`YYYY-MM-DD_<Name>.txt`), and the matching folder in `Documentation/07_Technical_Documents/`.
4. Commit all modified files with a meaningful message.
5. Show the changes for review, then push to GitHub only after the user confirms.

## Editing Change_Log.xlsx

Python is not installed on this PC. Edit the workbook through Excel (Excel 2007, COM
`Excel.Application`) from PowerShell: open it, write the next empty row of `Change_Log`,
keep Arial 10 with wrapped text and borders, save as `.xlsx` (format 51), and quit Excel.
Read the file back to confirm the new row before committing.

## Repository notes

- The GitHub repository `Raghav123-abc/UT-_GIT` is **public**. Point out personal or sensitive data before pushing it.
- `.sf/`, `.sfdx/` and `.vscode/` are excluded locally in `.git/info/exclude`; never commit them.
- Folders under `Documentation/` are numbered (`01_` to `07_`) to set their display order on GitHub.
