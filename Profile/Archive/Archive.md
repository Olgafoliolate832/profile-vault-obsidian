---
title: Archive
type: dashboard
---

# Archive

> *Parent: [[Profile]]*

Holding area for retired, outdated, or superseded content. Mirrors the vault's folder structure. See `Templates/Archive/` for documentation and rules.

## How to Archive

1. Move the note (or folder) into the matching subfolder here.
2. Add `archived_date`, `archived_reason`, and `archived_from` to the note's frontmatter.
3. Update or remove any wikilinks from active notes that pointed to the archived content.

## Archived Content

```dataview
TABLE archived_from AS "From", archived_reason AS "Reason", archived_date AS "Archived"
FROM "Archive" AND -"Templates"
WHERE archived_date
SORT archived_date DESC
```

## Subfolders

Create these on demand as you archive content:

- `Archive/Applications/`
- `Archive/Experience/`
- `Archive/Education/`
- `Archive/Skills/`
- `Archive/Publications/`
- `Archive/Projects/`
- `Archive/Grants-Funding/`
- `Archive/Awards-Honors/`
- `Archive/Talks-Workshops/`
- `Archive/Professional-Service/`
- `Archive/References/`
- `Archive/Identity/`

