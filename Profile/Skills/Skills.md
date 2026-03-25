---
title: Skills
type: dashboard
---

# Skills

> *Parent: [[Profile]]*

Overview of all skills across six categories. See `Templates/Skills/` for documentation and templates.

## Categories

- [[Technical]] — Programming, frameworks, platforms, infrastructure
- [[Research]] — Methods, frameworks, domains, methodologies
- [[Consulting]] — Strategy, analysis, client management
- [[Languages]] — Spoken and written languages
- [[Software-Tools]] — Specific software and tools
- [[Soft-Skills]] — Project management, communication, leadership

## All Skills

```dataview
TABLE category AS "Category", proficiency AS "Proficiency", years_experience AS "Years", status AS "Status"
FROM "Skills" AND -"Templates"
WHERE type = "skill"
SORT category ASC, proficiency DESC
```

## Expert-Level Skills

```dataview
TABLE category AS "Category", years_experience AS "Years"
FROM "Skills" AND -"Templates"
WHERE type = "skill" AND proficiency = "expert"
SORT category ASC
```

