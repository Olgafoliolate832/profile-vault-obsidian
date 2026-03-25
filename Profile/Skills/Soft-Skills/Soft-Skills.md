---
title: Soft Skills
type: index
category: soft-skills
---

# Soft Skills

> *Parent: [[Skills]]*

Project management, communication, coordination, leadership, teamwork, and other interpersonal and organizational skills.

```dataview
TABLE proficiency AS "Proficiency", years_experience AS "Years", status AS "Status"
FROM "Skills/Soft-Skills" AND -"Templates"
WHERE type = "skill"
SORT proficiency DESC
```

