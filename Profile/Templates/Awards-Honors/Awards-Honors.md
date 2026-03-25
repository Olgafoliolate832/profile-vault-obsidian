---
title: Awards & Honors
type: index
---

# Awards & Honors

> *Parent: [[Templates]]*

Templates for tracking awards, prizes, honors, distinctions, scholarships, and nominations. Each entry gets a single note with structured frontmatter — no subfolders needed.

## Structure

```
Awards-Honors/
├── Awards-Honors.md                    # Overview + Dataview table
└── Award-YYYY-ShortName.md             # One note per entry
```

## Naming Convention

`Award-YYYY-ShortName` (e.g., `Award-2024-BestPaper-NeurIPS`, `Award-2023-Fulbright-Scholarship`)

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Name of the award |
| `type` | string | Always `award` |
| `award_type` | string | `award`, `honor`, `scholarship`, `nomination` |
| `organization` | string | Who granted it |
| `year` | number | Year received |
| `date` | date | Exact date if known |
| `domain` | list | `academic`, `technical`, `consulting` |
| `for` | string | What it was awarded for (brief description) |
| `value` | number | Monetary value (if applicable) |
| `currency` | string | Currency code (e.g., `EUR`, `USD`) |
| `related` | list | Wikilinks to related publications, projects, etc. |
| `status` | string | `received`, `nominated`, `declined` |
| `tags` | list | Additional tags for filtering |

## Rules

1. **One note per entry** — keep it flat, no subfolders.
2. **Include all types** — awards, honors, scholarships, and nominations all go here.
3. **Track nominations too** — even unsuccessful nominations show recognition. Use `status: nominated`.
4. **Link to related work** — connect awards to the publications, projects, or experience that earned them.
5. **Never delete** — set `status: declined` if you turned one down. Move truly outdated entries to `Archive/`.

## Dashboard Queries

### All Awards & Honors

```
dataview
TABLE organization AS "Organization", award_type AS "Type", year AS "Year", for AS "For"
FROM "Awards-Honors"
WHERE type = "award"
SORT year DESC
```

### By Type

```
dataview
TABLE organization AS "Organization", year AS "Year", for AS "For"
FROM "Awards-Honors"
WHERE type = "award"
SORT award_type ASC, year DESC
```

### With Monetary Value

```
dataview
TABLE organization AS "Organization", year AS "Year", value AS "Value", currency AS "Currency"
FROM "Awards-Honors"
WHERE type = "award" AND value > 0
SORT year DESC
```

## Template

- [[Award-YYYY-ShortName]] — Template for a single award/honor note

