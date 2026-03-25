---
title: Grant Applications
type: index
app_type: grant
---

# Grant Applications

> *Parent: [[Applications]]*

Research funding and grant proposal applications. See `Templates/Applications/` for documentation and templates.

```dataview
TABLE funder AS "Funder", program AS "Program", deadline AS "Deadline", priority AS "Priority", status AS "Status"
FROM "Applications/Grants" AND -"Templates"
WHERE type = "application" AND app_type = "grant"
SORT deadline ASC
```

