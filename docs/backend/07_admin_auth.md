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

