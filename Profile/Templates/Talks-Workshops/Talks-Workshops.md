---
title: Talks & Workshops
type: index
---

# Talks & Workshops

> *Parent: [[Templates]]*

Templates for tracking conference talks, invited lectures, workshops, panels, and poster presentations. Flat list — use the `talk_type` frontmatter field to distinguish types.

## Structure

```
Talks-Workshops/
├── Talks-Workshops.md                    # Overview + Dataview tables
└── Talk-YYYY-Venue-Topic.md              # One note per entry
```

## Naming Convention

`Talk-YYYY-Venue-Topic` (e.g., `Talk-2024-NeurIPS-GraphOptimization`, `Talk-2025-TU-Wien-AIforClimate`)

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Title of the talk/presentation |
| `type` | string | Always `talk` |
| `talk_type` | string | `conference`, `invited`, `workshop`, `panel`, `poster` |
| `event` | string | Name of the conference/event |
| `venue` | string | Hosting organization or location name |
| `location` | string | City, country |
| `date` | date | Date of the presentation |
| `url` | string | Link to event page or recording |
| `slides_url` | string | Link to slides (if shared) |
| `recording_url` | string | Link to video/recording (if available) |
| `domain` | list | `academic`, `technical`, `consulting` |
| `audience` | string | Brief description of the audience |
| `invited_by` | string | Who invited you (for invited talks) |
| `related` | list | Wikilinks to related publications, projects, etc. |
| `status` | string | `delivered`, `upcoming`, `cancelled`, `declined` |
| `tags` | list | Additional tags for filtering |

## Rules

1. **One note per entry** — keep it flat, no subfolders.
2. **Track all types** — conference talks, invited lectures, workshops given, panels, and posters all go here.
3. **Use `talk_type`** to distinguish — this enables filtered Dataview queries by type.
4. **Link to related work** — connect talks to the publications, projects, or grants they stem from.
5. **Store slides and recordings** — link to external URLs or store files in an `Assets/` subfolder if needed.
6. **Track upcoming talks** — use `status: upcoming` for scheduled presentations.
7. **Never delete** — set `status: cancelled` or `status: declined` instead.

## Dashboard Queries

### All Talks & Workshops

```
dataview
TABLE talk_type AS "Type", event AS "Event", location AS "Location", date AS "Date"
FROM "Talks-Workshops"
WHERE type = "talk"
SORT date DESC
```

### By Type

```
dataview
TABLE event AS "Event", location AS "Location", date AS "Date"
FROM "Talks-Workshops"
WHERE type = "talk"
SORT talk_type ASC, date DESC
```

### Upcoming

```
dataview
TABLE talk_type AS "Type", event AS "Event", location AS "Location", date AS "Date"
FROM "Talks-Workshops"
WHERE type = "talk" AND status = "upcoming"
SORT date ASC
```

### Invited Talks

```
dataview
TABLE event AS "Event", invited_by AS "Invited By", location AS "Location", date AS "Date"
FROM "Talks-Workshops"
WHERE type = "talk" AND talk_type = "invited"
SORT date DESC
```

## Template

- [[Talk-YYYY-Venue-Topic]] — Template for a single talk/workshop note

