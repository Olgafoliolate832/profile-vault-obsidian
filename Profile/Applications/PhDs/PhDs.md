---
title: PhD Applications
type: index
app_type: phd
---

# PhD Applications

> *Parent: [[Applications]]*

Doctoral program and PhD position applications. See `Templates/Applications/` for documentation and templates.

```dataview
TABLE university AS "University", department AS "Department", deadline AS "Deadline", priority AS "Priority", status AS "Status"
FROM "Applications/PhDs" AND -"Templates"
WHERE type = "application" AND app_type = "phd"
SORT deadline ASC
```

