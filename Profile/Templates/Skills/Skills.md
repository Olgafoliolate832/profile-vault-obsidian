---
title: Skills
type: index
---

# Skills

> *Parent: [[Templates]]*

Templates for tracking skills across six categories. Each category has a folder with an overview file and individual skill notes.

## Structure

```
Skills/
├── Skills.md                         # Overview + Dataview tables
├── Technical/
│   ├── Technical.md                  # Category overview
│   └── Skill-Name.md                # Individual skill notes
├── Research/
│   ├── Research.md
│   └── Skill-Name.md
├── Consulting/
│   ├── Consulting.md
│   └── Skill-Name.md
├── Languages/
│   ├── Languages.md
│   └── Skill-Name.md
├── Software-Tools/
│   ├── Software-Tools.md
│   └── Skill-Name.md
└── Soft-Skills/
    ├── Soft-Skills.md
    └── Skill-Name.md
```

## Categories

- [[Technical]] — Programming languages, frameworks, platforms, infrastructure
- [[Research]] — Research methods, frameworks, domains, methodologies
- [[Consulting]] — Strategy, analysis, client management, business development
- [[Languages]] — Spoken and written languages with proficiency levels
- [[Software-Tools]] — Specific software and tools with proficiency levels
- [[Soft-Skills]] — Project management, communication, coordination, leadership, teamwork

## Naming Convention

`Skill-Name` (e.g., `Skill-Python`, `Skill-MachineLearning`, `Skill-German`, `Skill-ProjectManagement`)

## Proficiency Levels

Use a consistent scale across all categories:

| Level | Meaning |
|-------|---------|
| `beginner` | Basic understanding, limited practical experience |
| `intermediate` | Can work independently, solid practical experience |
| `advanced` | Deep expertise, can mentor others |
| `expert` | Industry-recognized, can lead and innovate |

For languages, additionally use standard frameworks (CEFR: A1–C2, or native).

## Frontmatter Fields (Individual Skill Notes)

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Name of the skill |
| `type` | string | Always `skill` |
| `category` | string | `technical`, `research`, `consulting`, `languages`, `software-tools`, `soft-skills` |
| `proficiency` | string | `beginner`, `intermediate`, `advanced`, `expert` |
| `years_experience` | number | Approximate years of experience |
| `last_used` | date | When you last actively used this skill |
| `domain` | list | `academic`, `technical`, `consulting` |
| `related` | list | Wikilinks to related experience, projects, certifications |
| `status` | string | `active`, `rusty`, `learning` |
| `tags` | list | Additional tags for filtering |

## Rules

1. **One note per skill** — each distinct skill gets its own note inside its category folder.
2. **Be specific** — prefer `Skill-PyTorch` over a generic `Skill-DeepLearning` when both exist.
3. **Proficiency must be honest** — this drives CV generation. Overstating hurts you in interviews.
4. **Link to evidence** — connect skills to the experience, projects, and certifications where you used them.
5. **Update `last_used`** — a skill unused for years should be marked `status: rusty`.
6. **Category overviews** summarize the folder and can list skills that don't warrant their own note.
7. **Never delete** — set `status: rusty` or move to `Archive/`.

## Dashboard Queries

### All Skills by Category

```
dataview
TABLE category AS "Category", proficiency AS "Proficiency", years_experience AS "Years", status AS "Status"
FROM "Skills"
WHERE type = "skill"
SORT category ASC, proficiency DESC
```

### Expert-Level Skills

```
dataview
TABLE category AS "Category", years_experience AS "Years"
FROM "Skills"
WHERE type = "skill" AND proficiency = "expert"
SORT category ASC
```

### Skills Currently Being Learned

```
dataview
TABLE category AS "Category", proficiency AS "Proficiency"
FROM "Skills"
WHERE type = "skill" AND status = "learning"
SORT category ASC
```

## Templates

- [[Skill-Name]] — Generic template for any individual skill note

