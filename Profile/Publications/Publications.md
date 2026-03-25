---
title: Publications
type: dashboard
---

# Publications

> *Parent: [[Profile]]*

Overview of all publications. See `Templates/Publications/` for documentation and templates.

## All Publications

```dataview
TABLE pub_type AS "Type", venue AS "Venue", year AS "Year", status AS "Status"
FROM "Publications" AND -"Templates"
WHERE type = "publication"
SORT year DESC
```

## Peer-Reviewed

```dataview
TABLE pub_type AS "Type", venue AS "Venue", year AS "Year", citations AS "Citations"
FROM "Publications" AND -"Templates"
WHERE type = "publication" AND peer_reviewed = true
SORT year DESC
```

## In Review / Upcoming

```dataview
TABLE pub_type AS "Type", venue AS "Venue", status AS "Status"
FROM "Publications" AND -"Templates"
WHERE type = "publication" AND (status = "in-review" OR status = "accepted" OR status = "draft")
SORT status ASC
```

