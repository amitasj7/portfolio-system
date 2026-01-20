# Portfolio Backend Project – Complete Summary

## 1. Project Goal

Build a **professional, industry-grade portfolio backend** that:
- Serves public read-only APIs for frontend
- Supports a secure single-admin dashboard
- Is scalable, testable, and interview-ready
- Follows real backend engineering practices

---

## 2. Backend Architecture Overview

### Tech Stack
- Runtime: Node.js
- Framework: Express.js
- Language: TypeScript
- Database: MongoDB (Mongoose)
- Auth: Session-based (cookies)
- API Testing: Postman
- Versioning: URL-based (`/api/v1`)

---

## 3. Git Branching Strategy (LOCKED)

### Main Branches
- `develop` → integration & testing branch (production-ready code)
- `feature/*` → one feature per branch
- `chore/*` → docs, planning, config
- `sandbox/*` → experiments / accidental work (never merged)

### Golden Rules
- One task = one feature branch
- Only `develop` is tested in Postman
- `.env` is NEVER committed
- `.env.example` IS committed

---

## 4. Backend Core Files
backend/src/config/
├── env.ts # loads & validates env vars
├── db.ts # MongoDB connection
└── session.ts # express-session configuration
backend/src/config/
├── env.ts # loads & validates env vars
├── db.ts # MongoDB connection
└── session.ts # express-session configuration


GET /health
Purpose: verify backend process is running
(no DB checks, no auth)


---

## 5. API Versioning (Industry Standard)

- URL-based major version only
- No v1.1 / v1.2 in URLs

Example:

/api/v1/profile
/api/v1/projects



Minor/patch versions handled internally via code.

---

## 6. Routes Directory Structure (FINAL)

backend/src/routes/
├── index.ts # root router
├── api/
│   └── v1/
│       ├── index.ts # v1 router
│       ├── profile.route.ts
│       ├── projects.route.ts
│       ├── timeline.route.ts
│       ├── resume.route.ts
│       └── admin/
│           └── auth.route.ts
└── admin/
    └── auth.route.ts # legacy (optional)



Routes contain **NO business logic** — only wiring.

---

## 7. Controllers Architecture

Controllers handle **logic only**, not routing.

backend/src/controllers/
├── health/
│ └── health.controller.ts
├── public/
│ ├── profile.controller.ts
│ ├── projects.controller.ts
│ ├── timeline.controller.ts
│ └── resume.controller.ts
└── admin/
└── auth.controller.ts



Rules:
- Stateless
- try/catch always
- No `process.env`
- No DB connection setup
- Public vs Admin controllers separated

---

## 8. Public APIs (v1)

### Endpoints
GET /api/v1/profile
GET /api/v1/projects
GET /api/v1/timeline
GET /api/v1/resume



### Rules
- GET only
- No auth
- Read-only
- Safe for frontend & SEO
- Empty data is NOT an error

---

## 9. Admin Authentication Design

### Auth Method
- Session-based authentication
- HTTP-only cookies
- Single admin user

### Why sessions?
- Best for dashboards
- Simple logout
- No token handling in frontend
- JWT is overkill for single admin

### Admin Auth Files

backend/src/auth/
├── admin.credentials.ts
└── password.util.ts

backend/src/middlewares/
└── requireAdmin.ts

backend/src/controllers/admin/
└── auth.controller.ts

backend/src/routes/admin/
└── auth.route.ts


### Admin Routes
POST /admin/login
POST /admin/logout


---

## 10. What Goes in `.env`

### Allowed
```env
ADMIN_EMAIL=admin@example.com
ADMIN_PASSWORD_HASH=<bcrypt hash>
SESSION_SECRET=<random long string>
PORT=5000
NODE_ENV=development
MONGODB_URI=...

ot Allowed

Plain password

Tokens

Session IDs

Rule:

Passwords are never stored. Only hashes are stored.
11. Postman API Testing (Industry Way)
Collection
Portfolio Backend – Public APIs

Environment
Portfolio – Local
baseUrl = http://localhost:5000
Tests
Written in Post-response Script

Minimum per API:

Status code test

JSON response test

Why {{baseUrl}}?
Easy switch between local / staging / prod

No hardcoded URLs

Test ONLY from:
develop branch
12. OpenAPI & Postman Import
OpenAPI defines WHAT APIs exist

servers defines WHERE they run

VS Code Postman extension is unreliable

Use real Postman desktop app

13. Documentation Structure
docs/
├── PROJECT_INSTRUCTIONS.md
├── PROJECT_SUMMARY.md
└── backend/
    ├── 04_backend_config.md
    ├── 05_public_apis.md
    ├── 06_controllers.md
    └── 07_admin_auth.md
14. Current Project Status
Completed
Backend core setup

Health check

Public APIs (v1)

Controllers & routes

Postman testing

Admin auth design

Next Logical Steps
Admin auth implementation

Admin CRUD APIs

Notifications (leads → email/WhatsApp)

Frontend integration

Deployment

15. Core Engineering Principles Used
Separation of concerns

Versioned APIs

Secure auth design

Real Git workflow

Test-first mindset

Documentation-driven development