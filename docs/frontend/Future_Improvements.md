

## ✅  Protected Routes - TESTING NEEDED

**Problem Found:**
- The Express session cookie (`portfolio.sid`) was set on backend (port 5000)
- Next.js middleware runs on frontend (port 3000) - different origin
- Cookie was `httpOnly: true` so JavaScript couldn't read it
- Cookie was `sameSite: 'strict'` blocking cross-origin requests

**Fixes Applied:**
1. Changed `sameSite: 'strict'` to `'lax'` in development (backend session.ts)
2. Created `AuthGuard` component for client-side route protection
3. Added AuthGuard to admin layout and login page
4. Disabled middleware (can't read cross-origin httpOnly cookies)

**Test Now:**
- [ ] If user is not logged in, redirect to login page
- [ ] If user is logged in and tries to access /admin/login, redirect to dashboard  
- [ ] When user clicks logout, redirect to login page
- [ ] After logout, accessing admin pages redirects to login until correct credentials are entered



## profile section -
 - present : save changes button hightlight bright
 - future update: before update anything save change button not highlight or light. when we change anything then save changes button highlight or light.



## project section -

Project Links
├─ Live URL (MANDATORY)
│  ├─ Production deployment
│  └─ First impression for recruiters
│
├─ GitHub Repository (MANDATORY)
│  ├─ Code quality
│  ├─ Commit history
│  └─ Engineering maturity
│
├─ Case Study / Project Details (HIGH SIGNAL)
│  ├─ Problem statement
│  ├─ Architecture decisions
│  ├─ Trade-offs
│  ├─ Screenshots
│  └─ Learnings
│
├─ API / Technical Docs (OPTIONAL but STRONG)
│  ├─ API endpoints
│  ├─ Data flow
│  └─ System diagram
│
├─ Demo / Walkthrough (OPTIONAL)
│  ├─ Short video
│  ├─ Feature flow
│  └─ Edge cases
│
└─ Metrics / Impact (RARE but POWERFUL)
   ├─ Performance numbers
   ├─ Usage stats
   └─ Scalability notes

- we will take 4 points -
1. github url
2. live url
3. case study
4. demo / walkthrough
 
## Demo / Walkthrough (OPTIONAL)
- Short video
- Feature flow
- Edge cases

## What goes inside “Case Study” (mini tree)
Case Study
├─ Problem
├─ Why this solution
├─ Architecture
├─ Key decisions
├─ Challenges faced
├─ What I’d improve next
└─ Tech stack rationale

## Interaction Rules
├─ Live URL
│  └─ Primary button style
├─ GitHub URL
│  └─ Secondary button style
├─ Demo URL
│  └─ Text button / outline
└─ Case Study
   └─ Link-style or subtle button

## UI match with button -
┌────────────────────────────┐
│                            │
│   [  ▶ Live Demo  ]        │  ← BIG / primary
│                            │
│   [ GitHub ] [ Demo ] [ Case ]  ← small / equal
└────────────────────────────┘


## Projects/education section -

- Sort experience by date
- also take a tag of highest priority that show first if i check it.

## resume section - 
- /admin/resume/upload && /admin/upload/pdf : choose which is best ?
- when click to uplaod pdf: 
   - present: not showing anything like what happend
   - future update: show progress bar and success message and pdf icon in that box.


## leads section -
- present: it showing a list view of leads
- future update:  I'm also want a table view of leads and card view also

- - Role-based priority (Recruiter, founder vs Other)