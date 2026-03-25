---
title: Templates
type: index
---

# Templates

> *Parent: [[Profile]]*

This folder contains the canonical folder structures, file templates, and documentation for all knowledge entries in this vault. Templates serve as blueprints — when creating a new entry, copy the relevant template folder and rename it.

## Template Categories

- [[Profile-Template]] — Template for the root-level vault overview
- [[Templates/Applications/Applications|Applications]] — Job, Grant, Fellowship, PhD, and Conference application templates
- [[Templates/Experience/Experience|Experience]] — Academic, industry, and freelance role templates
- [[Templates/Education/Education|Education]] — Degrees, certifications, and courses templates
- [[Templates/Skills/Skills|Skills]] — Technical, research, consulting, languages, software, and soft skills templates
- [[Templates/Publications/Publications|Publications]] — All publication types including Zotero integration templates
- [[Templates/Projects/Projects|Projects]] — Notable project templates
- [[Templates/Grants-Funding/Grants-Funding|Grants & Funding]] — Funded grant track record templates
- [[Templates/Awards-Honors/Awards-Honors|Awards & Honors]] — Awards, prizes, scholarships, and nominations templates
- [[Templates/Talks-Workshops/Talks-Workshops|Talks & Workshops]] — Talks, presentations, workshops, panels, and posters templates
- [[Templates/Professional-Service/Professional-Service|Professional Service]] — Reviewing, mentoring, and organizing templates
- [[Templates/References/References|References]] — Referee tracking templates
- [[Templates/Identity/Identity|Identity]] — Personal info, bios, research statement, and professional summaries
- [[Templates/Archive/Archive|Archive]] — Rules for archiving retired content

## Vault-Wide Conventions

### Root Overview

The vault has a root-level `Profile.md` that links to every top-level folder. Its template is stored here as `Templates/Profile-Template.md`.

### Folder-Level Overview Files

Each top-level folder has a matching `.md` file that serves as its overview/dashboard. These files:
- Are named to match their folder (e.g., `Applications/Applications.md`, `Skills/Skills.md`)
- Link back to `Profile.md` as their parent
- Link down to their contents
- May include Dataview queries for dynamic overviews

| Folder | Overview File |
|--------|--------------|
| `Profile/` | `Profile.md` |
| `Applications/` | `Applications.md` |
| `Experience/` | `Experience.md` |
| `Education/` | `Education.md` |
| `Skills/` | `Skills.md` |
| `Publications/` | `Publications.md` |
| `Projects/` | `Projects.md` |
| `Grants-Funding/` | `Grants-Funding.md` |
| `Awards-Honors/` | `Awards-Honors.md` |
| `Talks-Workshops/` | `Talks-Workshops.md` |
| `Professional-Service/` | `Professional-Service.md` |
| `References/` | `References.md` |
| `Identity/` | `Identity.md` |
| `Archive/` | `Archive.md` |
| `Templates/` | `Templates.md` |

The **only exception** is the per-application entry point, which uses `Index.md` (since the folder name already identifies the application).

### General Rules

1. **Never edit templates directly for real data** — always copy first, then fill in the copy.
2. **Template files use empty fields** — frontmatter values are left blank as placeholders.
3. **When updating templates**, ensure all existing entries still align with the new structure.
4. **Naming convention for copies**: replace the placeholder name with the actual name following the naming pattern defined in each type.
5. **Every folder gets an overview file** named to match the folder, linking to its contents.
6. **Use wikilinks** (`[[Note Name]]`) for all internal cross-references.
7. **Use ISO dates** (`YYYY-MM-DD`) everywhere in frontmatter.
8. **Never delete content** — move to `Archive/` instead.
9. **Template application folders use plural names** (Jobs, Grants, Fellowships, PhDs, Conferences) to match the knowledge-base folder names.

