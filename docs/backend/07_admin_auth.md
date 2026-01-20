🧭 ADMIN ROADMAP (LOCK THIS ORDER)

We will build admin in 4 clear phases:

Phase A — Auth (first, mandatory)
Admin login
Session-based auth (cookies)
Protect admin routes

Phase B — Admin APIs (CRUD)
Manage profile
Manage projects
Manage timeline
Manage resume
View leads

Phase C — Middleware
requireAdmin guard
Session validation

Phase D — Admin UI (later)
Dashboard (frontend)

👉 We start with Phase A only.

# Admin Authentication

## Scope
- Single admin user (portfolio owner)
- No public signup
- Credentials stored securely

## Auth Strategy
- Session-based authentication
- HTTP-only cookies
- Server-managed sessions

## Admin Capabilities
- Login
- Logout
- Access protected admin APIs

## Non-goals
- No OAuth
- No multiple roles
- No password reset (v1)

## Security Rules
- Admin routes are protected
- Public APIs remain unaffected
- Sessions expire automatically

## Failure Handling
- Invalid credentials → 401
- No session → 401

## We’ll design this in 4 small blocks so it’s easy to implement

### 1️⃣ ADMIN AUTH FLOW (MENTAL MODEL)
Admin Login
   ↓
Credentials Verified
   ↓
Session Created (cookie) 
   ↓
Protected Admin APIs Accessible

Logout = session destroyed.

### 2️⃣ AUTH METHOD (LOCKED)
Session-based authentication
Cookie-based
HTTP-only
Server-managed session

Reason:
Single admin
Browser dashboard
Simple & secure


### 3️⃣ DIRECTORY STRUCTURE (ADMIN AUTH)
backend/src/
├── auth/
│   ├── admin.credentials.ts     # admin email/password config
│   └── password.util.ts         # hash / compare helpers
│
├── middlewares/
│   └── requireAdmin.ts          # session guard
│
├── controllers/
│   └── admin/
│       └── auth.controller.ts   # login / logout
│
├── routes/
│   └── admin/
│       └── auth.route.ts        # /admin/login, /admin/logout
│
└── config/
    └── session.ts               # express-session setup


### 4️⃣ ADMIN CREDENTIAL STRATEGY (IMPORTANT)
Since it’s single admin:

Stored in:
.env (hashed password)
NOT in database (v1)

Example (conceptual):
ADMIN_EMAIL
ADMIN_PASSWORD_HASH

Why?
No signup
No user table needed
Simple & secure

### 5️⃣ ROUTES DESIGN
POST /admin/login
POST /admin/logout
GET  /admin/me    (optional)

### Rules

Public APIs → untouched
Admin APIs → protected by middleware

### 6️⃣ SESSION RULES
- Cookie: httpOnly
- Secure: true (in production)
- Session expires automatically
- Logout destroys session

### 7️⃣ SECURITY GUARANTEES
❌ No JWT
❌ No tokens in frontend
❌ No password in client storage
✅ Cookies auto-sent
✅ Server controls auth

### 8️⃣ FAILURE CASES (DEFINED)
| Case              | Response |
| ----------------- | -------- |
| Wrong credentials | 401      |
| No session        | 401      |
| Session expired   | 401      |
| Logout success    | 200      |





# what i do -
🧩 STEP 1: Session Configuration (FOUNDATION)
   - backend/src/config/session.ts

🧩 STEP 2: Admin Credentials Helper
backend/src/auth/admin.credentials.ts
backend/src/auth/password.util.ts

🧩 STEP 3: Admin Auth Controller
backend/src/controllers/admin/auth.controller.ts

🧩 STEP 4: Admin Auth Routes
backend/src/routes/admin/auth.route.ts

🧩 STEP 5: Admin Guard Middleware
backend/src/middlewares/requireAdmin.ts

🧩 STEP 6: Wire Session & Admin Routes
backend/src/app.ts



## FULL, INDUSTRY-LEVEL Admin API list,
===============================
ADMIN API – FULL LIST (v1)
===============================

Base prefix:
 /admin

--------------------------------
AUTH (ADMIN)
--------------------------------

POST   /admin/auth/login
- Login admin (creates session)

POST   /admin/auth/logout
- Logout admin (destroys session)

GET    /admin/auth/me
- Check current admin session (auth verify)


--------------------------------
PROFILE (SINGLE DOCUMENT)
--------------------------------

GET    /admin/profile
- Get profile data (admin view)

PUT    /admin/profile
- Create or update profile data


--------------------------------
PROJECTS (MULTIPLE)
--------------------------------

GET    /admin/projects
- Get all projects (including hidden)

POST   /admin/projects
- Create a new project

PUT    /admin/projects/:id
- Update a project

DELETE /admin/projects/:id
- Delete a project


--------------------------------
TIMELINE (EDUCATION + EXPERIENCE)
--------------------------------

GET    /admin/timeline
- Get all timeline entries

POST   /admin/timeline
- Create timeline entry

PUT    /admin/timeline/:id
- Update timeline entry

DELETE /admin/timeline/:id
- Delete timeline entry


--------------------------------
RESUME (SINGLE DOCUMENT)
--------------------------------

GET    /admin/resume
- Get resume data (admin)

PUT    /admin/resume
- Create or update resume

POST   /admin/resume/upload
- Upload resume file (PDF)


--------------------------------
LEADS / CONTACT
--------------------------------

GET    /admin/leads
- View all contact form submissions

GET    /admin/leads/:id
- View single lead

DELETE /admin/leads/:id
- Delete a lead


--------------------------------
SYSTEM / META (OPTIONAL)
--------------------------------

GET    /admin/health
- Admin-only system health

--------------------------------
SECURITY RULE
--------------------------------

ALL /admin/* routes:
- Require session (requireAdmin middleware)
- Public users cannot access any admin route


===============================
ADMIN API – FULL LIST (v1)
===============================

Base prefix:
 /admin

--------------------------------
AUTH (ADMIN)
--------------------------------

POST   /admin/auth/login
- Login admin (creates session)

POST   /admin/auth/logout
- Logout admin (destroys session)

GET    /admin/auth/me
- Check current admin session (auth verify)


--------------------------------
PROFILE (SINGLE DOCUMENT)
--------------------------------

GET    /admin/profile
- Get profile data (admin view)

PUT    /admin/profile   
- Create or update profile data


--------------------------------
PROJECTS (MULTIPLE)
--------------------------------

GET    /admin/projects
- Get all projects (including hidden)

POST   /admin/projects
- Create a new project

PUT    /admin/projects/:id
- Update a project

DELETE /admin/projects/:id
- Delete a project


--------------------------------
TIMELINE (EDUCATION + EXPERIENCE)
--------------------------------

GET    /admin/timeline
- Get all timeline entries

POST   /admin/timeline
- Create timeline entry

PUT    /admin/timeline/:id
- Update timeline entry

DELETE /admin/timeline/:id
- Delete timeline entry


--------------------------------
RESUME (SINGLE DOCUMENT)
--------------------------------

GET    /admin/resume
- Get resume data (admin)

PUT    /admin/resume
- Create or update resume

POST   /admin/resume/upload
- Upload resume file (PDF)


--------------------------------
LEADS / CONTACT
--------------------------------

GET    /admin/leads
- View all contact form submissions

GET    /admin/leads/:id
- View single lead

DELETE /admin/leads/:id
- Delete a lead


--------------------------------
SYSTEM / META (OPTIONAL)
--------------------------------

GET    /admin/health
- Admin-only system health

--------------------------------
SECURITY RULE
--------------------------------

ALL /admin/* routes:
- Require session (requireAdmin middleware)
- Public users cannot access any admin route


app.ts
 └── mounts /admin
      └── routes/admin/index.ts
           ├── auth.route.ts     → /admin/auth/
           ├── profile.route.ts  → /admin/profile
           ├── projects.route.ts → /admin/projects


routes/admin/index.ts
- mounts auth routes at /admin/auth
- mounts profile routes at /admin/profile
- mounts project routes at /admin/projects


backend/src/routes/admin/
│
├── index.ts
│   ├─ mounts all admin routes
│   └─ applies requireAdmin middleware
│
├── auth.route.ts
│   ├─ POST /admin/auth/login
│   ├─ POST /admin/auth/logout
│   └─ GET  /admin/auth/me
│
├── profile.route.ts
│   ├─ GET /admin/profile
│   └─ PUT /admin/profile
│
├── projects.route.ts
│   ├─ GET    /admin/projects
│   ├─ POST   /admin/projects
│   ├─ PUT    /admin/projects/:id
│   └─ DELETE /admin/projects/:id
│
├── timeline.route.ts
│   ├─ GET    /admin/timeline
│   ├─ POST   /admin/timeline
│   ├─ PUT    /admin/timeline/:id
│   └─ DELETE /admin/timeline/:id
│
├── resume.route.ts
│   ├─ GET  /admin/resume
│   ├─ PUT  /admin/resume
│   └─ POST /admin/resume/upload
│
└── leads.route.ts
    ├─ GET    /admin/leads
    ├─ GET    /admin/leads/:id
    └─ DELETE /admin/leads/:id


STEP 4️⃣ Test Protected Admin Route (Auth Guard)

If you already have a protected route like:
GET /admin/auth/me
(or any admin-only route)

Request
GET {{baseUrl}}/admin/auth/me

Expected
✅ If logged in:

Status 200

Admin data returned

❌ If NOT logged in:

Status 401

Message: Unauthorized

👉 This proves session-based auth is working.

🔁 FULL REQUEST FLOW (ADMIN) ---

Client (Postman / Admin UI)
   ↓
Route (/admin/...)
   ↓
requireAdmin middleware
   ↓
Controller (business logic)
   ↓
Model (MongoDB)
   ↓
Response (JSON)


