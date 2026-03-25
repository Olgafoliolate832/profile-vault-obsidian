---
title: Languages
type: index
category: languages
---

# Languages

> *Parent: [[Skills]]*

Spoken and written languages with proficiency levels.

## Proficiency Scale

Use CEFR levels or equivalent:

| Level | CEFR | Description |
|-------|------|-------------|
| `native` | — | Native speaker |
| `expert` | C2 | Mastery / near-native |
| `advanced` | C1 | Effective operational proficiency |
| `intermediate` | B1–B2 | Independent user |
| `beginner` | A1–A2 | Basic user |

## Skills

```
dataview
TABLE proficiency AS "Proficiency", status AS "Status"
FROM "Skills/Languages"
WHERE type = "skill"
SORT proficiency DESC
```

