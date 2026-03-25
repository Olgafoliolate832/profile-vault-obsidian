---
title: Education
type: index
---

# Education

> *Parent: [[Templates]]*

Templates for tracking formal education, certifications, and courses. Organized into three categories.

## Structure

```
Education/
├── Education.md                           # Overview + Dataview tables
├── Degrees/
│   ├── Degrees.md                         # Subfolder overview
│   └── Degree-Level-Field.md              # One note per degree
├── Certifications/
│   ├── Certifications.md                  # Subfolder overview
│   └── Cert-YYYY-Name.md                  # One note per certification
└── Courses/
    ├── Courses.md                         # Subfolder overview
    └── Course-YYYY-Name.md               # One note per course
```

## Categories

- [[Degrees]] — Formal academic degrees (PhD, MSc, BSc, etc.)
- [[Certifications]] — Professional certifications (AWS, PMP, etc.)
- [[Courses]] — Online courses, MOOCs, summer schools, bootcamps, professional training

## Naming Conventions

| Category | Pattern | Example |
|----------|---------|---------|
| Degrees | `Degree-Level-Field` | `Degree-MSc-ComputerScience` |
| Certifications | `Cert-YYYY-Name` | `Cert-2024-AWS-SolutionsArchitect` |
| Courses | `Course-YYYY-Name` | `Course-2025-DeepLearning-Coursera` |

## Rules

1. **One note per entry** — each degree, certification, or course gets its own note.
2. **Degrees are few and stable** — you'll rarely add new ones. Keep them detailed with thesis info, key courses, and outcomes.
3. **Certifications expire** — track expiry dates and renewal requirements.
4. **Courses are cumulative** — add every meaningful course. Use tags to make them queryable for CV generation.
5. **Link to related work** — connect education to Experience, Publications, or Projects where relevant.
6. **Never delete** — move outdated entries to `Archive/`.

## Dashboard Queries

### All Education

```
dataview
TABLE edu_type AS "Type", institution AS "Institution", year AS "Year", status AS "Status"
FROM "Education"
WHERE type = "education"
SORT year DESC
```

### Active Certifications

```
dataview
TABLE institution AS "Issuer", date_obtained AS "Obtained", expiry_date AS "Expires"
FROM "Education"
WHERE type = "education" AND edu_type = "certification" AND status = "active"
SORT expiry_date ASC
```

## Templates

- [[Degree-Level-Field]] — Template for a formal degree
- [[Cert-YYYY-Name]] — Template for a certification
- [[Course-YYYY-Name]] — Template for a course

