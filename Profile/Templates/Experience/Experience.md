---
title: Experience
type: index
---

# Experience

> *Parent: [[Templates]]*

Templates for tracking professional roles and positions across three domains. Each role gets a single note with structured frontmatter.

## Structure

```
Experience/
├── Experience.md                              # Overview + Dataview tables
├── Academic/
│   ├── Academic.md                            # Category overview
│   └── Role-Organization-Title.md             # One note per role
├── Industry/
│   ├── Industry.md
│   └── Role-Organization-Title.md
└── Freelance/
    ├── Freelance.md
    └── Role-Organization-Title.md
```

## Categories

- [[Academic]] — University positions, research roles, postdocs, teaching
- [[Industry]] — Full-time and part-time positions at companies
- [[Freelance]] — Contract work, consulting engagements, self-employed projects

## Naming Convention

`Role-Organization-Title` (e.g., `Role-Google-SeniorEngineer`, `Role-TU-Wien-Postdoc`, `Role-ClientX-DataConsultant`)

## Relationship to Projects

- **Experience** tracks your roles/positions — where you worked and your title.
- **Projects** tracks specific notable work — what you built or delivered.
- One experience can contain many projects. One project can span multiple experiences.
- Link between them using wikilinks in the `related` field.

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Role title |
| `type` | string | Always `experience` |
| `domain` | string | `academic`, `industry`, `freelance` |
| `organization` | string | Employer or client |
| `department` | string | Team, department, or group |
| `location` | string | City, country |
| `start_date` | date | Role start date |
| `end_date` | date | Role end date (blank if current) |
| `employment_type` | string | `full-time`, `part-time`, `contract`, `internship` |
| `status` | string | `current`, `past` |
| `tags` | list | Skills, technologies, themes |
| `relevance` | list | What this role is relevant for (e.g., `data-science`, `cloud-architecture`) |
| `highlights` | list | 3-5 bullet-point achievements with quantified impact |
| `related` | list | Wikilinks to related projects, publications, grants |

## Rules

1. **One note per role** — each distinct position gets its own note in the appropriate category.
2. **Quantify achievements** — use numbers, percentages, and scale wherever possible in highlights.
3. **Highlights drive CV generation** — Claude pulls from these when building tailored CVs.
4. **Relevance tags matter** — these let Claude filter roles for specific application types.
5. **Link to projects** — every significant project done during this role should be linked.
6. **Current roles** — leave `end_date` blank and set `status: current`.
7. **Never delete** — set `status: past` when a role ends. Move truly outdated roles to `Archive/`.

## Dashboard Queries

### All Experience

```
dataview
TABLE organization AS "Organization", domain AS "Domain", start_date AS "Start", end_date AS "End", status AS "Status"
FROM "Experience"
WHERE type = "experience"
SORT start_date DESC
```

### Current Roles

```
dataview
TABLE organization AS "Organization", domain AS "Domain", start_date AS "Since"
FROM "Experience"
WHERE type = "experience" AND status = "current"
SORT start_date DESC
```

### By Domain

```
dataview
TABLE organization AS "Organization", start_date AS "Start", end_date AS "End"
FROM "Experience"
WHERE type = "experience"
SORT domain ASC, start_date DESC
```

## Template

- [[Role-Organization-Title]] — Template for a single experience entry

