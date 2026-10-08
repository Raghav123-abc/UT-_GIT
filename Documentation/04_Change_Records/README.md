# Change Records

One record per metadata change, with before/after values and the Salesforce org alias. Organized by date.

## Master change log

[Change_Log.csv](Change_Log.csv) has one row per Salesforce change, for audit. GitHub shows it as a table.

1. Add one new row at the bottom for every Salesforce change: metadata, configuration, flow, field, object, validation rule, Apex, LWC, integration, deployment or permission.
2. Never edit or delete existing rows. To correct a past entry, add a new row that says which entry it corrects.
3. Write dates as YYYY-MM-DD.
4. Fill in every column. Write "Not stated" or "Not tested" rather than leaving a cell blank.
5. Before Change Details and After Change Details give the actual values, not just a description.
6. Keep the file UTF-8, with every value in double quotes.

Supporting change records are kept in this folder as dated files.
