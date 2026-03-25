---
title: Academic Experience
type: index
domain: academic
---

# Academic Experience

> *Parent: [[Experience]]*

University positions, research roles, postdocs, and teaching.

```dataview
TABLE organization AS "Organization", start_date AS "Start", end_date AS "End", status AS "Status"
FROM "Experience/Academic" AND -"Templates"
WHERE type = "experience"
SORT start_date DESC
```

