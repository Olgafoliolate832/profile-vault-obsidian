---
title: Archive
type: index
---

# Archive

> *Parent: [[Templates]]*

Templates for the archive — a holding area for retired, outdated, or superseded content. The archive mirrors the vault's folder structure so content can be traced back to its origin.

## Structure

```
Archive/
├── Archive.md                    # Overview
├── Applications/                 # Archived applications
├── Experience/                   # Archived experience entries
├── Education/                    # Archived education entries
├── Skills/                       # Archived skill entries
├── Publications/                 # Archived publications
├── Projects/                     # Archived projects
├── Grants-Funding/               # Archived grants
├── Awards-Honors/                # Archived awards
├── Talks-Workshops/              # Archived talks
├── Professional-Service/         # Archived service entries
├── References/                   # Archived references
└── Identity/                     # Archived bios, statements, etc.
```

## Rules

1. **Mirror the vault structure** — when archiving a note, move it into the matching subfolder (e.g., an old experience note goes to `Archive/Experience/`).
2. **Create subfolders on demand** — only create an archive subfolder when you first need it.
3. **Never truly delete** — archive is the last stop before deletion. Only delete from archive if you're absolutely sure.
4. **Add archive metadata** — when archiving, add `archived_date` and `archived_reason` to the note's frontmatter.
5. **Don't break links** — when you move a note to Archive, wikilinks from other notes will break. Update or remove those links.
6. **Archive entire application folders** — for applications, move the entire folder (with Context, Strategy, Outputs) intact.
7. **Review periodically** — check the archive quarterly and delete anything truly useless.

## Frontmatter Fields to Add When Archiving

Add these fields to the existing frontmatter of any note being archived:

| Field | Type | Description |
|-------|------|-------------|
| `archived_date` | date | When the note was archived |
| `archived_reason` | string | Why it was archived (e.g., `superseded`, `outdated`, `rejected`, `no longer relevant`) |
| `archived_from` | string | Original folder path |

