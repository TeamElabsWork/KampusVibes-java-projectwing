# Backend — CampusExplore

This directory will contain the **Spring Boot** backend application for CampusExplore.

> **Status: Not yet implemented.** No source code, Maven configuration (`pom.xml`), or project structure exists here yet. This README documents what is planned.

---

## Planned Technology

| Technology | Role |
|---|---|
| Java | Primary backend language |
| Spring Boot | Application framework; REST API, dependency injection, lifecycle management |
| Spring Data JPA / Hibernate | ORM layer for database interaction |
| MySQL | Relational database (running locally or on a server) |
| JUnit | Unit and integration testing |
| Maven | Build tool and dependency management |

---

## Planned Responsibilities

The backend will be responsible for:

- Exposing a REST API consumed by the frontend.
- Implementing business logic including the recommendation engine.
- Integrating external services (LLM API for the AI chatbot; Maps API for location data) on the server side to keep API keys out of the browser.
- Handling user authentication and session management.
- Performing database operations through the repository layer.

---

## Prerequisites (for when implementation begins)

The following software will be required to run the backend locally. Exact versions will be confirmed when the Spring Boot version is selected and documented here.

- **JDK** — A version compatible with the chosen Spring Boot release.
- **Maven** — Or use the Maven wrapper (`./mvnw`) that will be generated during project initialization.
- **MySQL Server** — A locally running instance with a database created for development.

---

## Getting Started (future)

Build and run instructions, environment configuration steps, and database setup will be added to this file once the Spring Boot project has been initialized. Do not attempt to run the backend from this directory yet.

---

## Structure (planned)

Once initialized, the backend will follow the standard Spring Boot Maven project layout:

```
backend/
├── pom.xml
└── src/
    ├── main/
    │   ├── java/
    │   │   └── com/campusexplore/
    │   │       ├── controller/
    │   │       ├── service/
    │   │       ├── repository/
    │   │       ├── model/
    │   │       └── CampusExploreApplication.java
    │   └── resources/
    │       ├── application.properties
    │       └── application-local.properties  (gitignored)
    └── test/
        └── java/
            └── com/campusexplore/
```

This structure has not been created yet.
