---
title: Professional Service
type: dashboard
---

# Professional Service

> *Parent: [[Profile]]*

Overview of all professional service activities — reviewing, mentoring, and organizing. See `Templates/Professional-Service/` for documentation and templates.

## All Professional Service

```dataview
TABLE service_type AS "Type", organization AS "Organization", role AS "Role", status AS "Status"
FROM "Professional-Service" AND -"Templates"
WHERE type = "service"
SORT service_type ASC, start_date DESC
```

## Active Service

```dataview
TABLE service_type AS "Type", organization AS "Organization", role AS "Role", start_date AS "Since"
FROM "Professional-Service" AND -"Templates"
WHERE type = "service" AND status = "active"
SORT service_type ASC
```

