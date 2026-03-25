---
title: Grants & Funding
type: dashboard
---

# Grants & Funding

> *Parent: [[Profile]]*

Track record of funded grants. For active grant applications, see [[Applications]]. See `Templates/Grants-Funding/` for documentation and templates.

## All Grants

```dataview
TABLE funder AS "Funder", role AS "Role", amount AS "Amount", currency AS "Currency", status AS "Status"
FROM "Grants-Funding" AND -"Templates"
WHERE type = "grant"
SORT start_date DESC
```

## Active Grants

```dataview
TABLE funder AS "Funder", role AS "Role", amount AS "Amount", end_date AS "Ends"
FROM "Grants-Funding" AND -"Templates"
WHERE type = "grant" AND status = "active"
SORT end_date ASC
```

