---
title: Experience
type: dashboard
---

# Experience

> *Parent: [[Profile]]*

Overview of all professional roles and positions. See `Templates/Experience/` for documentation and templates.

## Categories

- [[Academic]] — University, research, postdoc, teaching
- [[Industry]] — Company positions
- [[Freelance]] — Contract and consulting work

## All Experience

```dataview
TABLE organization AS "Organization", domain AS "Domain", start_date AS "Start", end_date AS "End", status AS "Status"
FROM "Experience" AND -"Templates"
WHERE type = "experience"
SORT start_date DESC
```

## Current Roles

```dataview
TABLE organization AS "Organization", domain AS "Domain", start_date AS "Since"
FROM "Experience" AND -"Templates"
WHERE type = "experience" AND status = "current"
SORT start_date DESC
```

