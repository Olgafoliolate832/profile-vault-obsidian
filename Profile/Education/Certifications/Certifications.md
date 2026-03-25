---
title: Certifications
type: index
---

# Certifications

> *Parent: [[Education]]*

Professional certifications.

```dataview
TABLE issuer AS "Issuer", date_obtained AS "Obtained", expiry_date AS "Expires", status AS "Status"
FROM "Education/Certifications" AND -"Templates"
WHERE type = "education" AND edu_type = "certification"
SORT date_obtained DESC
```

