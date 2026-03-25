---
title: Freelance Experience
type: index
domain: freelance
---

# Freelance Experience

> *Parent: [[Experience]]*

Contract work, consulting engagements, and self-employed projects.

```
dataview
TABLE organization AS "Client", start_date AS "Start", end_date AS "End", status AS "Status"
FROM "Experience/Freelance"
WHERE type = "experience"
SORT start_date DESC
```

