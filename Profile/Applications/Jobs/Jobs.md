---
title: Job Applications
type: index
app_type: job
---

# Job Applications

> *Parent: [[Applications]]*

Job and position applications across academic, industry, and consulting roles. See `Templates/Applications/` for documentation and templates.

```dataview
TABLE organization AS "Organization", role AS "Role", deadline AS "Deadline", priority AS "Priority", status AS "Status"
FROM "Applications/Jobs" AND -"Templates"
WHERE type = "application" AND app_type = "job"
SORT deadline ASC
```

