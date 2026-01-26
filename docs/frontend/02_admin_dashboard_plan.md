# Admin Dashboard Plan – Portfolio System

## 1. Purpose
- Provide a UI for the admin to manage portfolio content
- Consume admin backend APIs
- Replace manual Postman usage

## 2. Entry Point
- URL: /admin/login
- First page user sees when unauthenticated

## 3. Authentication Flow
- Admin logs in using email + password
- Backend creates session (cookie)
- Frontend relies on cookie-based auth
- Unauthorized users are redirected to login

## 4. Dashboard Layout
- Sidebar navigation
- Main content area
- Header with logout action

## 5. Pages (v1)

### 5.1 Login
- Route: /admin/login
- API: POST /admin/auth/login

### 5.2 Dashboard Home
- Route: /admin
- Simple overview / welcome screen

### 5.3 Profile Management
- Route: /admin/profile
- APIs:
  - GET /admin/profile
  - PUT /admin/profile

### 5.4 Projects Management
- Route: /admin/projects
- APIs:
  - GET /admin/projects
  - POST /admin/projects
  - PUT /admin/projects/:id
  - DELETE /admin/projects/:id

### 5.5 Timeline Management
- Route: /admin/timeline
- APIs:
  - GET /admin/timeline
  - POST /admin/timeline
  - PUT /admin/timeline/:id
  - DELETE /admin/timeline/:id

### 5.6 Resume Management
- Route: /admin/resume
- APIs:
  - GET /admin/resume
  - PUT /admin/resume
  - POST /admin/resume/upload

### 5.7 Leads Viewer
- Route: /admin/leads
- APIs:
  - GET /admin/leads
  - GET /admin/leads/:id
  - DELETE /admin/leads/:id

## 6. Navigation Rules
- Sidebar visible only after login
- Logout clears session and redirects to login

## 7. Access Control
- All routes except /admin/login are protected
- Auth check runs on page load

## 8. Non-Goals (v1)
- Role-based access
- Multi-admin support
- Public portfolio pages

## 9. Definition of Done
- Admin can manage all portfolio data via UI
- No need to use Postman for daily work
