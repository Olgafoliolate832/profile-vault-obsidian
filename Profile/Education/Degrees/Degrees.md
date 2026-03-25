---
title: Degrees
type: index
---

# Degrees

> *Parent: [[Education]]*

Formal academic degrees.

```dataview
TABLE field AS "Field", institution AS "Institution", year AS "Year"
FROM "Education/Degrees" AND -"Templates"
WHERE type = "education" AND edu_type = "degree"
SORT year DESC
```

