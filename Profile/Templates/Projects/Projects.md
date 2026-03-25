---
title: Projects
type: index
---

# Projects

> *Parent: [[Templates]]*

Templates for tracking notable projects — specific pieces of work you delivered, built, or contributed to. Flat list with tags for domain and status.

## Structure

```
Projects/
├── Projects.md                           # Overview + Dataview tables
└── Proj-YYYY-ShortName.md                # One note per project
```

## Naming Convention

`Proj-YYYY-ShortName` (e.g., `Proj-2024-SmartCityPlatform`, `Proj-2023-ChurnPrediction`, `Proj-2022-ClimateDataPipeline`)

Use the year the project started.

## Relationship to Experience

- **Experience** tracks your roles/positions — where you worked.
- **Projects** tracks specific notable work — what you delivered.
- One experience can contain many projects. One project can span multiple experiences.
- Link between them using wikilinks in the `related` field.

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Project name |
| `type` | string | Always `project` |
| `domain` | list | `academic`, `technical`, `consulting` |
| `role` | string | Your role in the project (e.g., `lead`, `contributor`, `architect`) |
| `client` | string | Client or organization (if applicable) |
| `start_date` | date | Project start |
| `end_date` | date | Project end (blank if ongoing) |
| `budget` | number | Project budget (if applicable) |
| `currency` | string | Currency code |
| `status` | string | `active`, `completed`, `on-hold`, `cancelled` |
| `skills_used` | list | Skills applied in this project |
| `outcomes` | list | Key outcomes and deliverables |
| `related` | list | Wikilinks to related experience, grants, publications |
| `tags` | list | Additional tags for filtering |

## Rules

1. **One note per project** — keep it flat, no subfolders.
2. **Only notable projects** — not every task or assignment. Projects worth mentioning on a CV or in a proposal.
3. **Quantify outcomes** — use numbers, metrics, and scale wherever possible.
4. **Skills_used drives CV matching** — Claude uses this field to find relevant projects for applications.
5. **Link to experience** — connect each project to the role(s) where you did the work.
6. **Link to grants** — if the project was funded, link to the grant in Grants-Funding.
7. **Link to publications** — if the project produced papers, link them.
8. **Never delete** — set `status: completed`, `on-hold`, or `cancelled` instead.

## Dashboard Queries

### All Projects

```
dataview
TABLE domain AS "Domain", role AS "Role", client AS "Client", status AS "Status"
FROM "Projects"
WHERE type = "project"
SORT start_date DESC
```

### Active Projects

```
dataview
TABLE domain AS "Domain", role AS "Role", client AS "Client", start_date AS "Started"
FROM "Projects"
WHERE type = "project" AND status = "active"
SORT start_date DESC
```

### By Domain

```
dataview
TABLE role AS "Role", client AS "Client", start_date AS "Start", end_date AS "End"
FROM "Projects"
WHERE type = "project"
SORT domain ASC, start_date DESC
```

### By Skills Used

```
dataview
TABLE domain AS "Domain", skills_used AS "Skills", status AS "Status"
FROM "Projects"
WHERE type = "project"
SORT start_date DESC
```

## Template

- [[Proj-YYYY-ShortName]] — Template for a single project entry

