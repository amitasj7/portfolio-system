# Controllers Architecture
 ## Directory Structure -

 ├── controllers/
    │   ├── index.ts                    # optional barrel exports
    │   │
    │   ├── health/
    │   │   └── health.controller.ts    # health check logic
    │   │
    │   ├── public/                     # public (read-only) controllers
    │   │   ├── profile.controller.ts
    │   │   ├── projects.controller.ts
    │   │   ├── timeline.controller.ts
    │   │   └── resume.controller.ts
    │   │
    │   └── admin/                      # admin (protected) controllers
    │       ├── auth.controller.ts
    │       ├── profile.controller.ts
    │       ├── projects.controller.ts
    │       ├── timeline.controller.ts
    │       ├── resume.controller.ts
    │       └── leads.controller.ts

## Purpose

Controllers are responsible for handling request logic and coordinating
between routes and data models.

They contain:
- Request validation (basic)
- Data fetching / manipulation
- Response formatting

They do NOT contain:
- Routing logic
- Database connection setup
- Middleware configuration

---

## Controller Categories

Controllers are grouped by access level to enforce security boundaries.

### 1. Public Controllers
Path:


controllers/public/


Responsibilities:
- Handle public, read-only APIs
- No authentication
- No data mutation
- Safe for frontend consumption

Examples:
- profile.controller.ts
- projects.controller.ts
- timeline.controller.ts
- resume.controller.ts

---

### 2. Admin Controllers
Path:


controllers/admin/


Responsibilities:
- Handle protected APIs
- Full CRUD operations
- Authentication required
- Used by admin dashboard only

Examples:
- auth.controller.ts
- profile.controller.ts
- projects.controller.ts
- timeline.controller.ts
- resume.controller.ts
- leads.controller.ts

---

### 3. System Controllers
Path:

controllers/health/

Responsibilities:
- System-level endpoints
- No business logic
- No database dependency

Examples:
- health.controller.ts

---

## Controller Design Rules

- One controller file per resource
- Controllers must be stateless
- Controllers must not directly access `process.env`
- Controllers must not contain routing logic
- Controllers must handle errors explicitly

---

## Relationship with Routes

- Routes define URL paths and HTTP methods
- Controllers implement request handling logic
- Routes delegate work to controllers

Example:



Route → Controller → Model


---

## Relationship with Services (Future)

- Controllers may call services for complex logic
- Services will encapsulate business rules
- Controllers remain thin and readable

---

## Completion Criteria

A controller is considered complete when:
- It handles one clear responsibility
- It returns consistent response shapes
- It does not leak internal fields
