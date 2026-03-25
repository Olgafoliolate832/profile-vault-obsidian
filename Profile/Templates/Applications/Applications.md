---
title: Application Templates
type: index
---

# Application Templates

> *Parent: [[Templates]]*

Templates for tracking and managing all types of applications — from job searches to conference submissions. Each application type follows the same internal structure but with type-specific content.

## Application Types

- [[Jobs]] — Job and position applications
- [[Grants]] — Research funding and grant proposals
- [[Fellowships]] — Fellowship and scholarship applications
- [[PhDs]] — Doctoral program applications
- [[Conferences]] — Conference talk and paper submissions

## Universal Rules

1. **One folder per application** — each application gets its own folder under the relevant type in `Applications/`.
2. **Naming convention**: `YYYY-MM-Organization-ShortTitle` (e.g., `2026-03-Google-SeniorMLE`).
3. **Copy the template folder** from here into the corresponding type folder under `Applications/`, then rename.
4. **Status tracking** — every application's `Index.md` must have a `status` field in frontmatter. Valid statuses: `researching`, `drafting`, `submitted`, `interview`, `offered`, `accepted`, `rejected`, `withdrawn`.
5. **Priority levels**: `high`, `medium`, `low`.
6. **Never delete applications** — change status to `rejected` or `withdrawn` instead. Move to `Archive/` only after review.
7. **Deadlines** — always use ISO format (`YYYY-MM-DD`) in frontmatter.
8. **Cross-references** — link to relevant Experience, Skills, Publications, and Projects notes from other vault folders when filling in Strategy/Mapping.
9. **Applications overview** — `Applications/Applications.md` is the dashboard that queries all `Index.md` files with `type: application` to show a unified overview.
10. **Folder-level files** — every folder gets an overview file named to match the folder (e.g., `Jobs/Jobs.md`), except per-application entry points which use `Index.md`.
11. **Plural naming** — template type folders use plural names (Jobs, Grants, Fellowships, PhDs, Conferences) to match the knowledge-base folder names.

## Internal Structure (per application)

Every application follows this structure:

| Folder/File | Purpose |
|-------------|---------|
| `Index.md` | Entry point. Frontmatter holds metadata (status, deadline, priority). Links to all sub-documents. |
| `Context/` | **Their information.** What they published, require, and who they are. |
| `Strategy/` | **Your analysis.** How your profile maps to their needs, gaps, and angle. |
| `Outputs/` | **Deliverables.** The actual documents you submit (CV, cover letter, etc.). |

## Workflow

1. **Research** — fill in `Context/` (Description, Requirements, Research).
2. **Strategize** — fill in `Strategy/Mapping.md`, linking evidence to your profile notes.
3. **Draft** — generate outputs in `Outputs/` using context and strategy as input.
4. **Review & submit** — update `Index.md` status and timeline.

---

## Dashboard Template

The `Applications/Applications.md` file in the knowledge-base should use the following Dataview queries for a live overview. Copy these when setting up the real file.

### All Active Applications

```
dataview
TABLE organization AS "Organization", role AS "Role", deadline AS "Deadline", priority AS "Priority", status AS "Status"
FROM "Applications" AND -"Templates"
WHERE type = "application" AND status != "rejected" AND status != "withdrawn" AND status != "accepted"
SORT deadline ASC
```

### By Priority

```
dataview
TABLE organization AS "Organization", app_type AS "Type", deadline AS "Deadline", status AS "Status"
FROM "Applications" AND -"Templates"
WHERE type = "application" AND status != "rejected" AND status != "withdrawn" AND status != "accepted"
SORT priority ASC
```

### Recently Completed

```
dataview
TABLE organization AS "Organization", app_type AS "Type", status AS "Status", date_applied AS "Applied"
FROM "Applications" AND -"Templates"
WHERE type = "application" AND (status = "accepted" OR status = "rejected" OR status = "withdrawn")
SORT date_applied DESC
LIMIT 10
```

### Statistics

- **Total active**: count of applications with active statuses
- **By type**: breakdown across Jobs, Grants, Fellowships, PhDs, Conferences
- **By status**: breakdown across all statuses
- **Upcoming deadlines**: applications with deadlines in the next 30 days

