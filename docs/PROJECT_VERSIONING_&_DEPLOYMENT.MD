INDUSTRY-LEVEL PROJECT VERSIONING & DEPLOYMENT PLAYBOOK
(From v1 Completion to Production)

================================================================

PHASE 1 — V1 COMPLETION CHECK (FREEZE THE BASELINE)

├─ Define what "v1" means
│  ├─ Core features complete
│  ├─ No experimental features
│  ├─ Known limitations documented
│  └─ Scope explicitly frozen
│
├─ Code hygiene
│  ├─ Remove dead code
│  ├─ Remove console/debug logs
│  ├─ Ensure consistent formatting
│  └─ Linting passes
│
├─ Documentation baseline
│  ├─ README updated
│  ├─ Setup instructions verified
│  ├─ Environment variables listed
│  └─ Known issues documented
│
└─ Final v1 sanity check
   ├─ App runs locally from clean install
   ├─ No critical warnings
   └─ Core user flow works end-to-end

Senior mindset:
"v1 is not perfect. It is stable."

================================================================

PHASE 2 — VERSIONING STRATEGY (NON-NEGOTIABLE)

├─ Use Semantic Versioning (industry standard)
│
│  Version format:
│  MAJOR.MINOR.PATCH
│
│  ├─ MAJOR → breaking changes
│  ├─ MINOR → new features (backward compatible)
│  └─ PATCH → bug fixes only
│
├─ Initial release
│  └─ v1.0.0
│
├─ Examples
│  ├─ v1.0.1 → small bug fix
│  ├─ v1.1.0 → new feature added
│  └─ v2.0.0 → breaking change
│
└─ Rule
   └─ Never change versions casually

Senior mindset:
"Versions communicate risk."

================================================================

PHASE 3 — GIT & RELEASE DISCIPLINE

├─ Branch strategy (simple & clean)
│
│  main
│   └─ develop
│       └─ feature/*
│
├─ Before deployment
│  ├─ Merge feature branches into develop
│  ├─ Test develop branch
│  └─ Merge develop → main
│
├─ Tag the release
│  ├─ Create git tag: v1.0.0
│  └─ Push tag to origin
│
└─ Release notes
   ├─ What shipped
   ├─ Known issues
   └─ What’s next

Senior mindset:
"main should always be deployable."

================================================================

PHASE 4 — PRE-DEPLOYMENT CHECKLIST (CRITICAL)

├─ Environment configuration
│  ├─ Production env vars set
│  ├─ Secrets NOT in code
│  ├─ Correct API keys
│  └─ Correct database URLs
│
├─ Build verification
│  ├─ Production build passes
│  ├─ No build-time errors
│  └─ Reasonable bundle size
│
├─ Security basics
│  ├─ Auth flows verified 
│  ├─ Rate limits (if applicable)
│  ├─ Input validation
│  └─ Dependency audit
│
└─ Performance sanity
   ├─ Page load acceptable
   ├─ API response times OK
   └─ No obvious bottlenecks

Senior mindset:
"Most failures happen before deploy, not after."

================================================================

PHASE 5 — DEPLOYMENT (CONTROLLED, NOT RUSHED)

├─ Choose deployment type
│  ├─ Web app → Vercel / Netlify / Cloud
│  ├─ Backend → Cloud VM / Container / PaaS
│  └─ Database → Managed service
│
├─ First deployment
│  ├─ Deploy v1.0.0
│  ├─ Verify live URL
│  └─ Smoke test core flows
│
├─ Logging & visibility
│  ├─ Enable logs
│  ├─ Check error monitoring
│  └─ Confirm metrics are flowing
│
└─ Rollback readiness
   ├─ Previous build available
   └─ Rollback process known

Senior mindset:
"Deployment without rollback is gambling."

================================================================

PHASE 6 — POST-DEPLOYMENT VALIDATION

├─ Functional verification
│  ├─ Login / auth
│  ├─ Core features
│  └─ Edge cases
│
├─ Real-world checks
│  ├─ Different devices
│  ├─ Different browsers
│  └─ Network variability
│
├─ Monitoring
│  ├─ Error rates
│  ├─ Performance
│  └─ Resource usage
│
└─ Fix fast if needed
   └─ Patch → v1.0.1

Senior mindset:
"Shipping is the start, not the end."

================================================================

PHASE 7 — COMMUNICATION & VISIBILITY

├─ Update portfolio
│  ├─ Live URL
│  ├─ Version shown (v1.0.0)
│  └─ Case study linked
│
├─ Demo readiness
│  ├─ Stable demo flow
│  └─ Backup plan if live fails
│
├─ Optional announcements
│  ├─ LinkedIn
│  ├─ README release notes
│  └─ Changelog
│
└─ Capture feedback
   ├─ Bugs
   ├─ UX issues
   └─ Feature requests

Senior mindset:
"Visibility creates opportunity."

================================================================

PHASE 8 — POST-V1 MAINTENANCE MODE

├─ Maintenance rules
│  ├─ Only bug fixes in PATCH releases
│  ├─ No feature creep in v1.x
│  └─ Keep main stable
│
├─ Planning v1.1 / v2
│  ├─ Gather feedback
│  ├─ Identify breaking changes
│  └─ Decide upgrade path
│
├─ Technical debt tracking
│  ├─ Known shortcuts
│  └─ Refactor candidates
│
└─ Decide lifespan
   ├─ Iterate
   └─ Or archive gracefully

Senior mindset:
"Not every project needs infinite life."

================================================================

FINAL INDUSTRY TRUTHS (MEMORIZE)

├─ Versioning is communication
├─ Deployment is a process, not a button
├─ Stability beats speed after v1
├─ Documentation is part of the product
└─ A calm deploy is a successful deploy

================================================================

## DEMO MODE (Local Tunnel via ngrok)

If you need to demo the project to a client from your local machine, use the integrated Demo Mode:

1. **Start ngrok tunnels**:
   - Backend: `ngrok http 5000`
   - Frontend: `ngrok http 3000`

2. **Run Demo Setup**:
   Use the helper script in the root directory to sync the tunnels:
   ```bash
   npm run demo:setup <backend_ngrok_url> <frontend_ngrok_url>
   ```

 Backend:  https://5cbe-110-235-234-45.ngrok-free.app -> http://localhost:5000
 Frontend: https://646c-110-235-234-45.ngrok-free.app -> http://localhost:3000

3. **Launch Apps**:
   - `npm run backend:dev`
   - `npm run frontend:dev`

This ensures the frontend talks to the correct backend tunnel and handles CORS correctly.

================================================================

Failed to fetch
src/lib/api.ts (23:28) @ apiRequest


  21 |     }
  22 |
> 23 |     const response = await fetch(`${API_URL}${endpoint}`, config);
     |                            ^
  24 |
  25 |     if (!response.ok) {
  26 |         const errorData = await response.json().catch(() => ({}));
Call Stack
50

Show 46 ignore-listed frame(s)
apiRequest
src/lib/api.ts (23:28)
Object.getProjects
src/services/public.service.ts (146:26)

> **Troubleshooting:** This error occurs because the development servers have not been restarted to load the new environment variables. Please restart both servers (`npm run dev`) to fix it.


present: 
   app working is fine in normal mode.
   when i try to open in incognito mode it is not working.
   
   console log:
      
Access to fetch at 'https://5cbe-110-235-234-45.ngrok-free.app/api/v1/settings' from origin 'https://646c-110-235-234-45.ngrok-free.app' has been blocked by CORS policy: The value of the 'Access-Control-Allow-Origin' header in the response must not be the wildcard '*' when the request's credentials mode is 'include'.Understand this error
api.ts:23  GET https://5cbe-110-235-234-45.ngrok-free.app/api/v1/settings net::ERR_FAILED 200 (OK)
      
### [UX Improvement] Auto-Scroll Interaction

**Changelog:**
- **Loading State:** The site now shows a dedicated "Initializing Experience" loading screen until all profile data is fetched and assets are ready (minimum 2 seconds).
- **Auto-Scroll:** Once loaded, the page automatically smooth-scrolls to the Hero Card (lock phase) over 2 seconds.
- **Interaction Lock:** User scrolling is disabled (`overflow: hidden`) during the loading and auto-scroll phases to ensure the cinematic entry is not interrupted.
- **Result:** This solves the issue of the empty 3D space appearing broken before the user manually scrolls.

**Status:** `[COMPLETED]`

