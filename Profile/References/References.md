---
title: References
type: dashboard
---

# References

> *Parent: [[Profile]]*

Overview of all referees. See `Templates/References/` for documentation and templates.

## All Active Referees

```dataview
TABLE affiliation AS "Affiliation", relationship AS "Relationship", can_speak_to AS "Can Speak To", last_contacted AS "Last Contacted"
FROM "References" AND -"Templates"
WHERE type = "reference" AND status = "active"
SORT last_contacted ASC
```

## By Domain

```dataview
TABLE affiliation AS "Affiliation", relationship AS "Relationship", domain AS "Domain"
FROM "References" AND -"Templates"
WHERE type = "reference" AND status = "active"
SORT domain ASC
```

## Usage History

```dataview
TABLE affiliation AS "Affiliation", used_for AS "Used For"
FROM "References" AND -"Templates"
WHERE type = "reference" AND length(used_for) > 0
SORT last_contacted DESC
```

