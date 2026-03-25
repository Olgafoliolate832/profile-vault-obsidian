---
title: Industry Experience
type: index
domain: industry
---

# Industry Experience

> *Parent: [[Experience]]*

Full-time and part-time positions at companies, startups, and organizations.

```
dataview
TABLE organization AS "Organization", start_date AS "Start", end_date AS "End", status AS "Status"
FROM "Experience/Industry"
WHERE type = "experience"
SORT start_date DESC
```

