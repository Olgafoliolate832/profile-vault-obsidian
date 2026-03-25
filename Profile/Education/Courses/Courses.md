---
title: Courses
type: index
---

# Courses

> *Parent: [[Education]]*

Online courses, MOOCs, summer schools, bootcamps, and professional training.

```dataview
TABLE provider AS "Provider", course_type AS "Type", date_completed AS "Completed", status AS "Status"
FROM "Education/Courses" AND -"Templates"
WHERE type = "education" AND edu_type = "course"
SORT date_completed DESC
```

