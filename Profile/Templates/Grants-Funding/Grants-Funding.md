---
title: Grants & Funding
type: index
---

# Grants & Funding

> *Parent: [[Templates]]*

Templates for tracking your grant track record — funded and completed grants as profile entries. This folder is for **outcomes**, not active applications (those live in `Applications/Grants/`).

## Structure

```
Grants-Funding/
├── Grants-Funding.md                     # Overview + Dataview tables
└── Grant-YYYY-Funder-Title.md            # One note per funded grant
```

## Naming Convention

`Grant-YYYY-Funder-Title` (e.g., `Grant-2024-FWF-AIMonitoring`, `Grant-2022-Horizon-ClimateData`)

## Relationship to Applications

- **Applications/Grants/** — where you prepare and track grant *applications* (context, strategy, outputs).
- **Grants-Funding/** — where you record *funded* grants as part of your track record.
- When a grant application succeeds, create a note here and link it back to the original application.

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Grant title |
| `type` | string | Always `grant` |
| `funder` | string | Funding organization |
| `program` | string | Funding program/scheme |
| `role` | string | `PI`, `Co-PI`, `researcher`, `consultant` |
| `amount` | number | Total funding amount |
| `currency` | string | Currency code (e.g., `EUR`, `USD`) |
| `start_date` | date | Project start |
| `end_date` | date | Project end |
| `domain` | list | `academic`, `technical`, `consulting` |
| `partners` | list | Consortium partners (if applicable) |
| `application` | string | Wikilink to original application in Applications/Grants/ |
| `related` | list | Wikilinks to related publications, projects, experience |
| `status` | string | `active`, `completed` |
| `tags` | list | Additional tags for filtering |

## Rules

1. **Only funded grants go here** — rejected or pending applications stay in `Applications/Grants/`.
2. **One note per grant** — keep it flat, no subfolders.
3. **Link to the application** — if the grant was prepared via Applications/Grants/, link to it.
4. **Link to outputs** — connect to publications, projects, and experience that resulted from this funding.
5. **Track record is key** — this folder feeds directly into grant applications and CVs.
6. **Never delete** — set `status: completed` when the grant ends.

## Dashboard Queries

### All Grants

```
dataview
TABLE funder AS "Funder", role AS "Role", amount AS "Amount", currency AS "Currency", status AS "Status"
FROM "Grants-Funding"
WHERE type = "grant"
SORT start_date DESC
```

### Active Grants

```
dataview
TABLE funder AS "Funder", role AS "Role", amount AS "Amount", end_date AS "Ends"
FROM "Grants-Funding"
WHERE type = "grant" AND status = "active"
SORT end_date ASC
```

### Total Funding by Role

```
dataview
TABLE role AS "Role", sum(amount) AS "Total"
FROM "Grants-Funding"
WHERE type = "grant"
GROUP BY role
```

## Template

- [[Grant-YYYY-Funder-Title]] — Template for a single grant entry

