# 🗺️ VISUAL DEPENDENCY TREE

Login
  ↓
Auth Protection
  ↓
Admin Layout
  ↓
Navigation
  ↓
Dashboard (Leads Overview)
  ↓
Leads Feature
  ↓
Other CRUD Features
  ↓
Polish
  ↓
Release


# Frontend Roadmap – 

## Lifecycle Stage
Action Code – Implementation (Guided)

---

## Goal
Build a secure, scalable admin dashboard starting from authentication.

---

## Phase 1: Authentication Entry
- Admin login page
- Session-based auth
- Redirect logic

Status: Planned / In Progress

---

## Phase 2: Route Protection
Objective:
- Block unauthenticated access to admin routes

Includes:
- Protected route rules
- Redirect unauthenticated users to login
- Redirect authenticated users away from login

---

## Phase 3: Admin Layout Shell
Objective:
- Create a persistent admin container

Includes:
- Sidebar region
- Header region
- Content outlet

Out of scope:
- Styling polish
- Feature logic

---

## Phase 4: Admin Navigation UX
Objective:
- Make navigation predictable and usable

Includes:
- Sidebar links
- Active state logic
- Logout placement
- Navigation order by usage

---

## Phase 5: Dashboard Home (Leads First)
Objective:
- Show what needs attention immediately

Includes:
- New leads indicator
- Recruiter priority signals
- Quick actions (view leads, add project)

---

## Phase 6: Leads Viewer
Objective:
- View and manage incoming leads

Includes:
- Leads list
- Role-based priority (Recruiter vs Other)
- Read/unread state

---

## Phase 7: Content Management
Includes:
1. Profile management
2. Projects management
3. Timeline management
4. Resume management

Shared patterns:
- List + edit
- Confirmation for destructive actions

---

## Phase 8: Polish & Consistency
Includes:
- Empty states
- Error states
- UX consistency
- Minor visual refinement

---

## Phase 9: Release
- Merge develop → main
- Tag stable version
