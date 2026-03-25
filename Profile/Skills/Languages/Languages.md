---
title: Languages
type: index
category: languages
---

# Languages

> *Parent: [[Skills]]*

Spoken and written languages with proficiency levels.

```dataview
TABLE proficiency AS "Proficiency", status AS "Status"
FROM "Skills/Languages" AND -"Templates"
WHERE type = "skill"
SORT proficiency DESC
```

