---
title: Conference Submissions
type: index
app_type: conference
---

# Conference Submissions

> *Parent: [[Applications]]*

Conference paper submissions, talk proposals, and workshop submissions. See `Templates/Applications/` for documentation and templates.

```dataview
TABLE conference AS "Conference", track AS "Track", deadline AS "Deadline", priority AS "Priority", status AS "Status"
FROM "Applications/Conferences" AND -"Templates"
WHERE type = "application" AND app_type = "conference"
SORT deadline ASC
```

