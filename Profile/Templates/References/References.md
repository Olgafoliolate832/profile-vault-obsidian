---
title: References
type: index
---

# References

> *Parent: [[Templates]]*

Templates for managing referees and reference letters. Each referee gets a single note with structured frontmatter — no subfolders needed.

## Structure

```
References/
├── References.md                    # Overview + Dataview table
└── Ref-FirstnameLastname.md         # One note per referee
```

## Naming Convention

`Ref-FirstnameLastname` (e.g., `Ref-MariaSchmidt`, `Ref-JohnDoe`)

## Frontmatter Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Full name of the referee |
| `type` | string | Always `reference` |
| `relationship` | string | `supervisor`, `manager`, `collaborator`, `mentor`, `colleague`, `client` |
| `domain` | list | `academic`, `technical`, `consulting` |
| `affiliation` | string | Current organization |
| `position` | string | Their current title/role |
| `email` | string | Contact email |
| `phone` | string | Contact phone (optional) |
| `can_speak_to` | list | What they can vouch for (e.g., `research`, `teaching`, `leadership`, `technical`, `teamwork`) |
| `used_for` | list | Wikilinks to applications where this referee was used |
| `last_contacted` | date | When you last reached out |
| `status` | string | `active`, `inactive`, `prefer-not` |
| `tags` | list | Additional tags for filtering |

## Rules

1. **One note per referee** — keep it flat, no subfolders.
2. **Keep contact details current** — update affiliation and email when they change.
3. **Track usage** — add a wikilink to `used_for` every time you list this referee in an application.
4. **Ask before using** — always contact referees before listing them. Update `last_contacted` when you do.
5. **Never delete** — set `status: inactive` or `status: prefer-not` instead.
6. **Sensitive data** — this folder contains personal contact info. Handle with care.

## Dashboard Queries

### All Active Referees

```
dataview
TABLE affiliation AS "Affiliation", relationship AS "Relationship", can_speak_to AS "Can Speak To", last_contacted AS "Last Contacted"
FROM "References"
WHERE type = "reference" AND status = "active"
SORT last_contacted ASC
```

### Referees by Domain

```
dataview
TABLE affiliation AS "Affiliation", relationship AS "Relationship", domain AS "Domain"
FROM "References"
WHERE type = "reference" AND status = "active"
SORT domain ASC
```

### Usage History

```
dataview
TABLE affiliation AS "Affiliation", used_for AS "Used For"
FROM "References"
WHERE type = "reference" AND length(used_for) > 0
SORT last_contacted DESC
```

## Template

- [[Ref-Name]] — Template for a single referee note

