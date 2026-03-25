---
title: Applications
type: dashboard
---

# Applications

> *Parent: [[Profile]]*

Overview of all applications across all types. See `Templates/Applications/` for documentation and templates.

## Application Types

- [[Jobs]]
- [[Grants]]
- [[Fellowships]]
- [[PhDs]]
- [[Conferences]]

## All Active Applications

```dataview
TABLE organization AS "Organization", role AS "Role", deadline AS "Deadline", priority AS "Priority", status AS "Status"
FROM "Applications" AND -"Templates"
WHERE type = "application" AND status != "rejected" AND status != "withdrawn" AND status != "accepted"
SORT deadline ASC
```

## Recently Completed

```dataview
TABLE organization AS "Organization", app_type AS "Type", status AS "Status", date_applied AS "Applied"
FROM "Applications" AND -"Templates"
WHERE type = "application" AND (status = "accepted" OR status = "rejected" OR status = "withdrawn")
SORT date_applied DESC
LIMIT 10
```

