# Frontend Overview – Portfolio System

## 1. Purpose
Describe why this frontend exists.
- Admin dashboard to manage portfolio content
- Uses existing backend APIs
- Session-based authentication

## 2. Scope
What this frontend WILL include:
- Admin login
- Profile management
- Projects management
- Timeline management
- Resume management
- Leads viewer

What this frontend will NOT include (v1):
- Public portfolio pages
- SEO optimization
- Mobile app

## 3. Users
- Single Admin (owner)
- No multi-user support

## 4. Authentication Model
- Session-based auth (cookies)
- Backend manages session
- Frontend does not store tokens
- Protected routes enforced

## 5. API Interaction
- REST APIs
- Base URL via environment variable
- Cookies sent automatically

## 6. Non-Goals (Important)
Explicitly list what is intentionally excluded to avoid scope creep.

## 7. Success Criteria
Define when frontend v1 is considered “done”.
