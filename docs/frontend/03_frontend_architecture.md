# Frontend Architecture – Portfolio Admin

## 1. Framework Choice
- Framework: (Next.js / React + Vite) [to be locked]
- Reason for choice:
    ✅ Why Next.js + App Router (Locked)
        Industry standard
        Clean layouts (perfect for admin dashboards)
        Middleware for protected routes
        Recruiter-approved stack

## 2. Application Type
- SPA with client-side routing
- Admin-only frontend

## 3. Routing Strategy
- Public route:
  - /admin/login
- Protected routes:
  - /admin
  - /admin/profile
  - /admin/projects
  - /admin/timeline
  - /admin/resume
  - /admin/leads

## 4. Auth Protection Strategy
- Session-based authentication
- Auth check on app load
- Redirect unauthenticated users to /admin/login
- Logout clears session and redirects

## 5. 📁 Folder Structure (Admin-First, Scalable)

portfolio-frontend/
│
├── app/
│   ├── (auth)/
│   │   └── admin/
│   │       └── login/
│   │           └── page.tsx
│   │
│   ├── (protected)/
│   │   └── admin/
│   │       ├── layout.tsx
│   │       ├── page.tsx              # dashboard home
│   │       ├── profile/
│   │       ├── projects/
│   │       ├── timeline/
│   │       ├── resume/
│   │       └── leads/
│   │
│   ├── layout.tsx                    # root layout
│   └── globals.css
│
├── components/
│   ├── ui/                           # buttons, inputs, modals
│   ├── layout/                       # sidebar, header
│   └── common/                       # loaders, empty states
│
├── lib/
│   ├── api.ts                        # axios / fetch wrapper
│   ├── auth.ts                       # auth helpers (client-safe)
│   └── constants.ts
│
├── hooks/
│   ├── useAuth.ts
│   └── useFetch.ts
│
├── middleware.ts                    # route protection
│
├── public/
│
├── .env.local
├── next.config.js
├── tsconfig.json
└── package.json

## 6. API Layer Design
- Centralized API client
- Base URL from environment variable
- Cookies included automatically
- Error handling in one place

## 7. State Management
- Local component state for forms
- Minimal global state (auth status only)
- No heavy state library in v1

## 8. Error Handling Strategy
- API error → user-friendly message
- Auth error → redirect to login
- Network error → retry / message

## 9. Non-Goals (v1)
- SSR optimization
- Mobile-first design
- Offline support

## 10. Definition of Done
- Architecture supports all admin features
- Easy to extend
- No duplicated API logic
