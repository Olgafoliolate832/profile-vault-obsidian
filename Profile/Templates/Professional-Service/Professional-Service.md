---
title: Professional Service
type: index
---

# Professional Service

> *Parent: [[Templates]]*

Templates for tracking peer reviewing, mentoring/supervision, and organizing activities. Flat list — use the `service_type` frontmatter field to distinguish types.

## Structure

```
Professional-Service/
├── Professional-Service.md               # Overview + Dataview tables
└── Service-Type-Organization.md          # One note per entry
```

## Naming Convention

`Service-Type-Organization` (e.g., `Service-Reviewer-NeurIPS`, `Service-Mentor-UniversitySalzburg`, `Service-Organizer-ICML-Workshop`)

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Descriptive title of the service role |
| `type` | string | Always `service` |
| `service_type` | string | `reviewing`, `mentoring`, `organizing` |
| `organization` | string | Journal, conference, institution, or event |
| `role` | string | Specific role (e.g., `reviewer`, `PC member`, `PhD mentor`, `workshop chair`) |
| `domain` | list | `academic`, `technical`, `consulting` |
| `start_date` | date | When the service started |
| `end_date` | date | When it ended (leave blank if ongoing) |
| `frequency` | string | `one-time`, `recurring`, `ongoing` |
| `related` | list | Wikilinks to related experience, publications, etc. |
| `status` | string | `active`, `completed`, `inactive` |
| `tags` | list | Additional tags for filtering |

## Service Types

### Reviewing
Peer reviewing for journals and conferences. Track the venue, your role (reviewer, PC member, senior PC), and frequency.

### Mentoring
Mentoring and supervision of students, junior researchers, or colleagues. Track who, when, and the outcome.

### Organizing
Organizing conferences, workshops, events, or sessions. Track your role (chair, co-chair, local organizer) and the event.

## Rules

1. **One note per service role** — if you review for the same journal yearly, one note is enough. Update it over time.
2. **Use `service_type`** to distinguish — this enables filtered Dataview queries.
3. **Track ongoing service** — leave `end_date` blank and set `status: active` for continuing roles.
4. **Quantify where possible** — note number of papers reviewed, students mentored, etc.
5. **Link to related work** — connect service to publications, experience, or projects where relevant.
6. **Never delete** — set `status: inactive` or `status: completed` instead.

## Dashboard Queries

### All Professional Service

```
dataview
TABLE service_type AS "Type", organization AS "Organization", role AS "Role", status AS "Status"
FROM "Professional-Service"
WHERE type = "service"
SORT service_type ASC, start_date DESC
```

### Active Service

```
dataview
TABLE service_type AS "Type", organization AS "Organization", role AS "Role", start_date AS "Since"
FROM "Professional-Service"
WHERE type = "service" AND status = "active"
SORT service_type ASC
```

### Reviewing Activity

```
dataview
TABLE organization AS "Venue", role AS "Role", frequency AS "Frequency", status AS "Status"
FROM "Professional-Service"
WHERE type = "service" AND service_type = "reviewing"
SORT start_date DESC
```

## Template

- [[Service-Type-Organization]] — Template for a single service entry

