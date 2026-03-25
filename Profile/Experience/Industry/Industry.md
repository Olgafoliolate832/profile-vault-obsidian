---
title: Industry Experience
type: index
domain: industry
---

# Industry Experience

> *Parent: [[Experience]]*

Full-time and part-time positions at companies and organizations.

```dataview
TABLE organization AS "Organization", start_date AS "Start", end_date AS "End", status AS "Status"
FROM "Experience/Industry" AND -"Templates"
WHERE type = "experience"
SORT start_date DESC
```

