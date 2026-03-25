---
title: Awards & Honors
type: dashboard
---

# Awards & Honors

> *Parent: [[Profile]]*

Overview of all awards, prizes, honors, distinctions, scholarships, and nominations. See `Templates/Awards-Honors/` for documentation and templates.

## All Awards & Honors

```dataview
TABLE organization AS "Organization", award_type AS "Type", year AS "Year", for AS "For"
FROM "Awards-Honors" AND -"Templates"
WHERE type = "award"
SORT year DESC
```

## By Type

```dataview
TABLE organization AS "Organization", year AS "Year", for AS "For"
FROM "Awards-Honors" AND -"Templates"
WHERE type = "award"
SORT award_type ASC, year DESC
```

