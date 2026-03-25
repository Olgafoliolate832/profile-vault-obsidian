---
title: Projects
type: dashboard
---

# Projects

> *Parent: [[Profile]]*

Overview of all notable projects. See `Templates/Projects/` for documentation and templates.

## All Projects

```dataview
TABLE domain AS "Domain", role AS "Role", client AS "Client", status AS "Status"
FROM "Projects" AND -"Templates"
WHERE type = "project"
SORT start_date DESC
```

## Active Projects

```dataview
TABLE domain AS "Domain", role AS "Role", client AS "Client", start_date AS "Started"
FROM "Projects" AND -"Templates"
WHERE type = "project" AND status = "active"
SORT start_date DESC
```

