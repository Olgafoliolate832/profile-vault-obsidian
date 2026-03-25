---
title: Talks & Workshops
type: dashboard
---

# Talks & Workshops

> *Parent: [[Profile]]*

Overview of all talks, presentations, workshops, panels, and posters. See `Templates/Talks-Workshops/` for documentation and templates.

## All Talks & Workshops

```dataview
TABLE talk_type AS "Type", event AS "Event", location AS "Location", date AS "Date"
FROM "Talks-Workshops" AND -"Templates"
WHERE type = "talk"
SORT date DESC
```

## Upcoming

```dataview
TABLE talk_type AS "Type", event AS "Event", location AS "Location", date AS "Date"
FROM "Talks-Workshops" AND -"Templates"
WHERE type = "talk" AND status = "upcoming"
SORT date ASC
```

## Invited Talks

```dataview
TABLE event AS "Event", invited_by AS "Invited By", location AS "Location", date AS "Date"
FROM "Talks-Workshops" AND -"Templates"
WHERE type = "talk" AND talk_type = "invited"
SORT date DESC
```

