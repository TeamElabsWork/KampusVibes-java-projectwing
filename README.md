# CampusExplore

> **A collaborative student-focused campus discovery web application.**

---

## Table of Contents

1. [Introduction](#1-introduction)
2. [Project Objectives](#2-project-objectives)
3. [Planned Features](#3-planned-features)
4. [Technology Stack](#4-technology-stack)
5. [Planned Architecture](#5-planned-architecture)
6. [Repository Structure](#6-repository-structure)
7. [Current Development Status](#7-current-development-status)
8. [Prerequisites](#8-prerequisites)
9. [Development Setup](#9-development-setup)
10. [Git and GitHub Collaboration Workflow](#10-git-and-github-collaboration-workflow)
11. [Branch and Commit Conventions](#11-branch-and-commit-conventions)
12. [GitHub Issues and Project Board](#12-github-issues-and-project-board)
13. [Code Review Expectations](#13-code-review-expectations)
14. [Configuration and Secrets](#14-configuration-and-secrets)
15. [Testing Strategy](#15-testing-strategy)
16. [Milestones and Development Roadmap](#16-milestones-and-development-roadmap)
17. [Contribution Guidelines](#17-contribution-guidelines)
18. [Troubleshooting and Support](#18-troubleshooting-and-support)
19. [License](#19-license)
20. [Acknowledgements and Project Ownership](#20-acknowledgements-and-project-ownership)

---

## 1. Introduction

**CampusExplore** is a collaborative web application designed to help students discover and explore places around their campus — including cafés, food outlets, parks, study spaces, libraries, and hangout spots. Students often struggle to find suitable venues that match their budget, available time, and personal preferences, particularly when new to an area or looking for something different. CampusExplore aims to solve this by providing a single, student-centred platform that aggregates local venue information, supports filtering and comparison, and offers intelligent recommendations driven by a Java-based recommendation engine and an AI-powered chatbot.

The intended users are university and college students. The expected value is a faster, more personalized, and socially informed way to choose where to go — whether for a quick meal between lectures, a focused study session, or a full day out with friends.

---

## 2. Project Objectives

The primary objectives of CampusExplore are:

- **Simplify campus-area discovery** by providing a curated, searchable directory of nearby venues organized by category.
- **Enable informed comparison** by surfacing price ranges, distances, ratings, and user reviews alongside each venue.
- **Deliver personalized recommendations** by learning from user preferences and incorporating budget and distance constraints.
- **Support AI-assisted venue discovery** through a natural-language chatbot that understands contextual requests such as *"a quiet place to study within 10 minutes' walk that costs under ₹100."*
- **Help users plan multi-stop outings** through a Plan My Day feature that sequences venue visits into a coherent itinerary.

---

## 3. Planned Features

All features listed below are **planned** and have not yet been implemented.

### Core MVP

- Place listings with name, category, description, and location.
- Keyword search across venue names and descriptions.
- Category filtering (e.g., café, food outlet, study space, park, hangout).
- Venue detail pages with price range, ratings summary, and basic information.
- Simple distance-based or proximity display.

### User Features

- User registration, login, and authentication.
- User-submitted reviews and star ratings.
- Favorites / saved places list.
- Personal preference settings (budget, preferred categories, distance tolerance).

### Location Features

- Interactive map view of nearby venues.
- Distance calculation from a user-defined or device-detected starting point.
- Navigation link or directions integration.

### Smart Features

- **Recommendation engine** — Java-based logic that suggests venues based on user preferences, history, and contextual filters.
- **AI chatbot** — natural-language interface for venue queries, integrated through the backend via an LLM API.
- **Plan My Day** — multi-stop outing planner that generates an ordered itinerary from selected or recommended venues.

### Administrative Features

- Venue management interface (add, edit, deactivate listings).
- Review moderation.
- Basic usage and content reporting.

---

## 4. Technology Stack

The following technologies are **planned** for use in this project. No integrations or dependencies have been configured yet.

| Layer | Technology | Intended Role |
|---|---|---|
| Frontend | HTML5, CSS3 | Page structure and styling |
| Frontend | Bootstrap 5 | Responsive UI components and layout |
| Frontend | JavaScript (Vanilla) | Client-side interactivity |
| Backend | Java | Primary application language |
| Backend | Spring Boot | REST API framework, dependency injection, application lifecycle |
| Database | MySQL | Relational data storage for venues, users, reviews, and preferences |
| Persistence | Spring Data JPA / Hibernate | ORM layer for database interaction |
| Maps | Google Maps API or Mapbox (TBD) | Interactive maps, location search, and distance calculation |
| AI Integration | LLM API (provider TBD) | Powering the AI chatbot via the Java backend |
| Testing | JUnit | Unit and integration tests for backend logic |
| Testing | API testing tool (TBD) | REST endpoint testing |
| Version Control | Git | Source control |
| Collaboration | GitHub | Repository hosting, Issues, pull requests, and project board |

> **Note:** The map provider and AI API provider have not yet been finalized. These decisions will be documented when confirmed.

---

## 5. Planned Architecture

The intended high-level architecture follows a layered approach:

```
Browser / Frontend (HTML, CSS, Bootstrap, JS)
        │
        │  HTTP / REST API calls
        ▼
Spring Boot REST Controllers
        │
        │  Business logic delegation
        ▼
Service Layer (business logic, recommendation engine, AI integration)
        │
        │  Data access
        ▼
Repository Layer (Spring Data JPA / Hibernate)
        │
        │  SQL
        ▼
MySQL Database

External Services (Google Maps / Mapbox, LLM API)
  integrated through the Service Layer
```

**Layer responsibilities (planned):**

| Layer | Responsibility |
|---|---|
| Frontend | User interface, form handling, map rendering, chatbot UI |
| Controllers | Accept and validate HTTP requests; delegate to services; return responses |
| Service Layer | Business logic, recommendation engine, orchestration of AI and map calls |
| Repository Layer | Database queries and persistence via JPA/Hibernate |
| Database | Persistent storage for all application data |
| External Services | Maps and AI APIs, called from the backend to keep API keys server-side |

None of these layers have been implemented. This section documents the intended design only.

---

## 6. Repository Structure

The following structure reflects the **actual state** of the repository after initial setup. No application source code, configuration files, or schemas exist yet.

```
CampusExplore/
├── README.md              ← This file. Main project documentation.
├── .gitignore             ← Git ignore rules for Java, Spring Boot, IDE, OS, and frontend artefacts.
├── .editorconfig          ← Editor settings for consistent formatting across contributors.
├── CONTRIBUTING.md        ← Collaboration workflow, branch conventions, and PR checklist.
├── docs/
│   └── .gitkeep           ← Preserves the docs/ directory until documentation is added.
├── backend/
│   └── README.md          ← Describes the planned Spring Boot backend. No code yet.
├── frontend/
│   └── README.md          ← Describes the planned frontend. No code yet.
└── database/
    └── README.md          ← Describes the planned MySQL database. No schema yet.
```

**Directory and file purposes:**

| Path | Purpose |
|---|---|
| `README.md` | Top-level project documentation (this file) |
| `.gitignore` | Prevents build artefacts, IDE files, secrets, and OS files from being committed |
| `.editorconfig` | Enforces consistent indentation, line endings, and encoding for all contributors |
| `CONTRIBUTING.md` | Step-by-step collaboration guide including the PR checklist |
| `docs/` | Reserved for architecture notes, API documentation, and design decisions |
| `backend/` | Will contain the Spring Boot application once implementation begins |
| `frontend/` | Will contain HTML, CSS, JS, and Bootstrap assets once implementation begins |
| `database/` | Will contain SQL schema migrations and seed scripts once implementation begins |

---

## 7. Current Development Status

> **The repository is in its initial setup stage.**

| Area | Status |
|---|---|
| Repository configuration | ✅ Initialized (`.gitignore`, `.editorconfig`) |
| Project documentation | ✅ Initialized (`README.md`, `CONTRIBUTING.md`, directory READMEs) |
| Backend (Spring Boot, Java) | ⏳ Not yet implemented |
| Frontend (HTML, CSS, Bootstrap, JS) | ⏳ Not yet implemented |
| Database schema and migrations | ⏳ Not yet implemented |
| Maps integration | ⏳ Not yet implemented |
| AI chatbot integration | ⏳ Not yet implemented |
| Recommendation engine | ⏳ Not yet implemented |
| Authentication | ⏳ Not yet implemented |
| Testing setup | ⏳ Not yet implemented |
| Deployment configuration | ⏳ Not yet planned |

The project will evolve incrementally through GitHub Issues and reviewed pull requests. Each piece of work is expected to be tracked, reviewed, and merged before being considered done.

---

## 8. Prerequisites

The following software will be required when implementation begins. No application can be run from this repository at present.

| Software | Purpose | Notes |
|---|---|---|
| Git | Version control and collaboration | Required immediately |
| JDK | Compiling and running the Java backend | Version to be confirmed when Spring Boot version is selected |
| Maven | Backend build and dependency management | Or use the Maven wrapper (`mvnw`) once the backend is initialized |
| MySQL Server | Running the local database | Version to be confirmed with schema design |
| MySQL client (e.g., MySQL Workbench, DBeaver) | Inspecting and managing the local database | Any compatible client |
| IDE (e.g., VS Code, IntelliJ IDEA) | Writing and debugging code | VS Code with Java Extension Pack is sufficient; IntelliJ IDEA Community Edition is also suitable |
| Modern web browser | Viewing the frontend | Chrome, Firefox, or Edge recommended |
| Node.js | Frontend tooling | Only required if a build tool (e.g., Webpack, Vite) is adopted; the initial frontend is planned with plain HTML, CSS, Bootstrap, and JavaScript |

Specific version requirements will be documented in `backend/README.md` and `frontend/README.md` once the implementation setup is complete.

---

## 9. Development Setup

### Cloning the Repository

Replace `<repository-url>` with the actual URL of the organization repository on GitHub, and `<repository-directory>` with the resulting local folder name.

```bash
git clone <repository-url>
cd <repository-directory>
```

### Before Starting Work

1. Read this README in full to understand the project context and current status.
2. Review `CONTRIBUTING.md` for the collaboration workflow and branch conventions.
3. Identify or create the GitHub Issue that corresponds to your assigned task.
4. Confirm the scope of the issue with your team before writing any code.

### Build and Run Instructions

Complete build and run instructions will be added to `backend/README.md` and `frontend/README.md` once the respective configurations have been initialized. Do not attempt to build or run the application from this repository yet.

---

## 10. Git and GitHub Collaboration Workflow

All contributors must follow this workflow for every piece of work.

### Step-by-Step

1. **Review the assigned GitHub Issue.** Understand the acceptance criteria and scope before starting.
2. **Synchronize your local `main` branch** to ensure you are working from the latest state.
3. **Create a feature branch** from `main` using the naming conventions in [Section 11](#11-branch-and-commit-conventions).
4. **Implement only the agreed scope** described in the issue.
5. **Test your changes** against the acceptance criteria.
6. **Commit with a meaningful message** following the conventions in [Section 11](#11-branch-and-commit-conventions).
7. **Push your feature branch** to the remote repository.
8. **Open a pull request** targeting `main` on GitHub.
9. **Link the related Issue** in the pull request description (e.g., `Closes #12`).
10. **Address review feedback** promptly and merge according to the repository's branch protection rules.

### Commands

```bash
# Synchronize main
git switch main
git pull origin main

# Create a feature branch
git switch -c feature/short-description

# Check what has changed
git status

# Stage only relevant files
git add <relevant-files>

# Commit with a meaningful message
git commit -m "feat: describe the change"

# Push the branch and set upstream tracking
git push -u origin feature/short-description
```

> Refer to `CONTRIBUTING.md` for the branch naming conventions and the pull request checklist.

> Exact merge permissions and approval requirements depend on the settings configured for this organization repository. Check the repository settings or ask the repository maintainer.

---

## 11. Branch and Commit Conventions

### Branch Naming

Use one of the following prefixes followed by a short, hyphenated description:

| Prefix | When to Use |
|---|---|
| `feature/` | Adding new functionality |
| `fix/` | Correcting a bug or broken behavior |
| `docs/` | Documentation-only changes |
| `test/` | Adding or updating tests |
| `refactor/` | Code restructuring without behavior change |

**Examples:**

```
feature/place-listing-api
feature/ai-chatbot-ui
fix/review-submission-validation
docs/update-development-setup
test/recommendation-service-unit-tests
refactor/venue-service-cleanup
```

### Commit Messages

Follow the [Conventional Commits](https://www.conventionalcommits.org/) style:

```
<type>: <short imperative description>
```

**Examples:**

```
feat: add place listing API endpoint
feat: implement category filter on venue search
fix: validate review submission form inputs
docs: update development setup instructions
test: add unit tests for recommendation service
refactor: extract venue scoring into separate helper
```

> These are conventions for future work. The branches and features named in the examples above do not yet exist.

---

## 12. GitHub Issues and Project Board

### Creating Issues

Every piece of work — features, fixes, documentation updates, and research tasks — should be tracked as a GitHub Issue before work begins. Each issue should include:

- **Title:** Concise and descriptive (e.g., *"Implement venue search by category"*).
- **Description:** Context, motivation, or problem being solved.
- **Scope and expected outcome:** What will be done and what will not be done.
- **Acceptance criteria:** A clear, checkable list of conditions that define when the issue is complete.
- **Dependencies:** Any other issues that must be completed first.
- **Labels:** Use labels such as `feature`, `bug`, `documentation`, `enhancement`, `question`.
- **Assignee:** The contributor responsible.
- **Milestone:** The project milestone this issue belongs to.

### Project Board Statuses

| Status | Meaning |
|---|---|
| **Backlog** | Identified and documented, not yet ready to start |
| **Ready** | Sufficiently defined and unblocked; available to be picked up |
| **In Progress** | Actively being worked on |
| **In Review** | A pull request has been opened and is awaiting review |
| **Done** | Accepted, merged, and verified |

### Definition of Done

An issue is **Done** when:
- All acceptance criteria have been met.
- The pull request has been reviewed and approved.
- The branch has been merged into `main`.
- Any relevant documentation has been updated.

---

## 13. Code Review Expectations

- **Keep pull requests focused.** Each pull request should address one issue or a closely related set of changes. Do not bundle unrelated changes.
- **Describe the change.** Explain what was done, why, and how it was tested in the pull request description.
- **Tests must pass.** Ensure all existing and new tests pass before requesting review.
- **Reviewers should check for:**
  - Correctness and adherence to the acceptance criteria.
  - Readability and maintainability.
  - Security considerations (especially for authentication, data access, and external API calls).
  - Integration compatibility with existing and planned components.
- **Resolve merge conflicts** before requesting a merge. Do not ask reviewers to resolve your conflicts.
- **Respond to feedback** constructively and in a timely manner. Mark conversations as resolved once addressed.

---

## 14. Configuration and Secrets

**Never commit credentials, API keys, tokens, or any sensitive configuration to this repository.**

This applies to:
- Database usernames and passwords.
- AI API keys (OpenAI, Gemini, or any other provider).
- Map API keys (Google Maps, Mapbox).
- Any other service credentials or tokens.

Local environment configuration (e.g., `.env` files or `application-local.properties`) must be excluded from Git. Refer to `.gitignore` for the patterns already in place.

Once the backend configuration requirements are known, a placeholder template (e.g., `.env.example` or `application.properties.example`) containing only variable names and no real values will be added to the repository. Contributors will copy this template and populate it locally.

Production and local configurations must be kept separate. Production secrets will never be stored in the repository.

---

## 15. Testing Strategy

The following testing approach is **planned** and has not yet been implemented.

| Test Type | Scope | Tooling |
|---|---|---|
| Unit tests | Backend service and business logic | JUnit |
| API integration tests | REST endpoint correctness | API testing tool (TBD) |
| Database integration tests | Repository layer and query correctness | JUnit with an in-memory or test database |
| Frontend checks | UI correctness and usability | Manual review initially; automated tooling TBD |
| End-to-end tests | Critical user journeys (e.g., search → view → review) | Tooling TBD once application is integrated |

Testing patterns, conventions, and instructions for running tests will be documented when the testing setup is established.

---

## 16. Milestones and Development Roadmap

The following milestones represent the **proposed** development progression. These are not confirmed dates or completed deliverables.

| # | Milestone | Description |
|---|---|---|
| 1 | Repository and architecture setup | Initialize repository structure, documentation, tooling, and agree on architecture decisions |
| 2 | Backend foundation and database design | Initialize Spring Boot project, design MySQL schema, configure JPA |
| 3 | Place management and discovery | Implement venue listings, search, and category filtering |
| 4 | Reviews, ratings, and favorites | Implement user-submitted content and saved places |
| 5 | Maps and location | Integrate map provider, display distances, link navigation |
| 6 | Recommendation engine | Build Java-based recommendation logic using user preferences |
| 7 | AI chatbot | Integrate LLM API; build natural-language venue discovery interface |
| 8 | Plan My Day | Build multi-stop outing planning and itinerary sequencing |
| 9 | Testing, deployment, and expo preparation | Harden test coverage, prepare deployment, polish UI |

---

## 17. Contribution Guidelines

A summary of what is expected from every contributor:

- **Work against an assigned or agreed GitHub Issue.** Do not start work without a tracked issue.
- **Ask questions before making major architectural changes.** Discuss changes that affect multiple layers or contributors before implementing them.
- **Follow the shared coding and naming conventions** once they are established. Conventions will be documented in `CONTRIBUTING.md` and this README.
- **Keep commits and pull requests focused.** One issue, one pull request.
- **Update documentation when behavior or setup changes.** A pull request that changes how something works must also update the relevant documentation.
- **Never commit secrets.** See [Configuration and Secrets](#14-configuration-and-secrets).
- **Communicate blockers early.** If you are stuck or blocked, raise it in the relevant Issue or team channel rather than waiting.

For the detailed collaboration workflow, branch naming, and pull request checklist, see [`CONTRIBUTING.md`](./CONTRIBUTING.md).

---

## 18. Troubleshooting and Support

If you encounter a problem during setup or development:

1. **Check the relevant documentation** in this README, `CONTRIBUTING.md`, and the appropriate directory README.
2. **Search existing GitHub Issues** — the problem may already be tracked or resolved.
3. **Prepare a clear description** before asking for help:
   - Steps to reproduce the problem.
   - The exact error message or unexpected behavior observed.
   - Your operating system, software versions, and any relevant environment details.
4. **Do not include credentials, API keys, or any sensitive data** in issue descriptions, comments, or chat messages.
5. **Create a new GitHub Issue** if the problem is not already tracked, using the format described in [Section 12](#12-github-issues-and-project-board).

---

## 19. License

The project license is **pending**. No open-source license has been formally selected or approved for this repository. Usage, modification, and redistribution terms have not yet been declared.

A `LICENSE` file will be added to the repository once the licensing decision has been made by the project owners.

---

## 20. Acknowledgements and Project Ownership

CampusExplore is a collaborative team project developed under a shared GitHub organization. It is a student initiative and does not represent any institution, company, or external organization.

Contributor names, organizational affiliations, and external endorsements will be documented here when formally agreed upon by the team.
