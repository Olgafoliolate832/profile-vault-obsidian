---
title: Education
type: dashboard
---

# Education

> *Parent: [[Profile]]*

Overview of all education — degrees, certifications, and courses. See `Templates/Education/` for documentation and templates.

## Categories

- [[Degrees]]
- [[Certifications]]
- [[Courses]]

## All Education

```dataview
TABLE edu_type AS "Type", institution AS "Institution", year AS "Year", status AS "Status"
FROM "Education" AND -"Templates"
WHERE type = "education"
SORT year DESC
```

## Active Certifications

```dataview
TABLE institution AS "Issuer", date_obtained AS "Obtained", expiry_date AS "Expires"
FROM "Education" AND -"Templates"
WHERE type = "education" AND edu_type = "certification" AND status = "active"
SORT expiry_date ASC
```

