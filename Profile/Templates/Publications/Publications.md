---
title: Publications
type: index
---

# Publications

> *Parent: [[Templates]]*

Templates for tracking all types of publications. Flat list — use the `pub_type` frontmatter field to distinguish types. Designed to be Zotero-compatible when integration is added later.

## Structure

```
Publications/
├── Publications.md                       # Overview + Dataview tables
└── Pub-YYYY-Venue-Title.md               # One note per publication
```

## Naming Convention

`Pub-YYYY-Venue-Title` (e.g., `Pub-2024-NeurIPS-GraphOptimization`, `Pub-2023-Springer-ChapterAI`, `Pub-2025-ArXiv-TransformerSurvey`)

For types without a venue, use the publisher or platform:
- Blog: `Pub-2025-Medium-MLPipelines`
- Software: `Pub-2024-GitHub-DataToolkit`
- Thesis: `Pub-2023-UniSalzburg-MScThesis`

## Publication Types

| `pub_type` | Description |
|------------|-------------|
| `journal` | Peer-reviewed journal article |
| `conference` | Conference paper (full, short, workshop) |
| `book-chapter` | Chapter in an edited book |
| `book` | Authored or edited book |
| `report` | Technical report, white paper |
| `preprint` | Preprint (ArXiv, SSRN, etc.) |
| `thesis` | PhD, MSc, or BSc thesis |
| `software` | Software package, library, tool |
| `article` | Magazine article, non-academic article |
| `blog` | Blog post |

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Publication title |
| `type` | string | Always `publication` |
| `pub_type` | string | See table above |
| `authors` | list | All authors in order |
| `venue` | string | Journal, conference, publisher, or platform |
| `year` | number | Year published |
| `date` | date | Exact publication date |
| `doi` | string | DOI if available |
| `url` | string | Link to publication |
| `zotero_key` | string | Zotero item key (for future integration) |
| `domain` | list | `academic`, `technical`, `consulting` |
| `abstract` | string | Brief abstract or summary |
| `status` | string | `published`, `accepted`, `in-review`, `preprint`, `draft`, `in-progress` |
| `peer_reviewed` | boolean | Whether peer-reviewed |
| `open_access` | boolean | Whether openly accessible |
| `citations` | number | Citation count (update periodically) |
| `related` | list | Wikilinks to related grants, projects, experience |
| `tags` | list | Additional tags for filtering |

## Rules

1. **One note per publication** — keep it flat, no subfolders.
2. **Include everything** — journal papers, blog posts, software packages. Use `pub_type` and `peer_reviewed` to filter for CVs.
3. **Authors list must be complete and ordered** — this is used for CV generation.
4. **Track status honestly** — distinguish between published, accepted, in-review, and draft.
5. **Link to related work** — connect publications to the grants that funded them, projects they belong to, and experience where the work was done.
6. **Zotero readiness** — include `zotero_key` when Zotero integration is set up. Leave blank for now.
7. **Update citations periodically** — useful for track record in grant applications.
8. **Never delete** — even retracted or withdrawn publications should be noted, not deleted.

## Dashboard Queries

### All Publications

```
dataview
TABLE pub_type AS "Type", venue AS "Venue", year AS "Year", status AS "Status"
FROM "Publications"
WHERE type = "publication"
SORT year DESC
```

### Peer-Reviewed Only

```
dataview
TABLE pub_type AS "Type", venue AS "Venue", year AS "Year", citations AS "Citations"
FROM "Publications"
WHERE type = "publication" AND peer_reviewed = true
SORT year DESC
```

### By Type

```
dataview
TABLE venue AS "Venue", year AS "Year", status AS "Status"
FROM "Publications"
WHERE type = "publication"
SORT pub_type ASC, year DESC
```

### In Review / Upcoming

```
dataview
TABLE pub_type AS "Type", venue AS "Venue", status AS "Status"
FROM "Publications"
WHERE type = "publication" AND (status = "in-review" OR status = "accepted" OR status = "draft")
SORT status ASC
```

### Most Cited

```
dataview
TABLE venue AS "Venue", year AS "Year", citations AS "Citations"
FROM "Publications"
WHERE type = "publication" AND citations > 0
SORT citations DESC
LIMIT 10
```

## Template

- [[Pub-YYYY-Venue-Title]] — Template for a single publication note

