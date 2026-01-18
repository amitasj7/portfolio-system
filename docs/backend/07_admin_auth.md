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


