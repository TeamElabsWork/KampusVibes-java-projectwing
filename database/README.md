# Database — CampusExplore

This directory will contain **SQL schema migrations, seed data, and database documentation** for CampusExplore.

> **Status: Not yet implemented.** No schema files, migration scripts, or seed data exist here yet. This README documents what is planned.

---

## Planned Technology

| Technology | Role |
|---|---|
| MySQL | Primary relational database for all application data |
| Spring Data JPA / Hibernate | ORM layer; manages entity-to-table mapping from the backend |
| SQL migration tool (TBD) | Managing schema versioning (e.g., Flyway or Liquibase, to be decided) |

---

## Planned Data Model (high-level)

The following entities are expected. Their exact structure, relationships, and constraints will be designed and documented when implementation begins.

| Entity | Description |
|---|---|
| `User` | Registered application users |
| `Venue` | Cafés, food outlets, study spaces, parks, and hangout spots |
| `Category` | Venue categories (e.g., café, park, study space) |
| `Review` | User-submitted reviews and star ratings for venues |
| `Favourite` | Saved venues per user |
| `UserPreference` | Budget, distance, and category preferences per user |

---

## Prerequisites (for when implementation begins)

- **MySQL Server** — A locally running instance.
- **A MySQL client** — MySQL Workbench, DBeaver, or the MySQL command-line client.
- A local database created for development (name and credentials to be documented once agreed).

---

## Getting Started (future)

Schema creation and migration instructions will be added here once the schema has been designed and the migration tool selected. Connection details will be provided through a local configuration file that is excluded from Git.

---

## Structure (planned)

```
database/
├── migrations/     ← Versioned schema migration scripts
└── seeds/          ← Optional sample data for local development
```

This structure has not been created yet.
