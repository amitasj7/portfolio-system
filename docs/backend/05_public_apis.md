# Public Read-Only APIs

## Rules
- GET only
- No auth
- No mutation
- No sensitive fields

## APIs

### GET /api/v1/profile
- Purpose
- Response shape

### GET /api/v1/projects
- Purpose
- Sorting rules

### GET /api/v1/timeline
- Purpose
- Order rules

### GET /api/v1/resume
- Purpose


## API Versioning Strategy

- API versioning is handled via URL path.
- Current active version: v1
- All public APIs are exposed under /api/v1/*
- Future breaking changes will be introduced in /api/v2/*

- API URLs use major version only (v1, v2).
- Minor and patch versions are managed internally via code releases.

### 🧩 How app.ts will mount routes (concept)

/app.ts
app.use('/api/v1', v1Router)

Inside v1Router:
/profile
/projects
/timeline
/resume


Reasoning:
- Simple to understand
- Easy to maintain
- Safe for frontend compatibility



Public Read-Only APIs (v1)
Global Rules

Method: GET only
Auth: None
Access: Public
Versioning: /api/v1/
No mutations
No sensitive/internal fields
isVisible = true filters applied where applicable


GET /api/v1/profile

Purpose
Return public profile data for portfolio header / about section.

Data Source
Profile model (singleton)

Behavior
Fetch single profile document

If not found → return null
Exclude internal fields (_id, __v, timestamps)
Response Shape


GET /api/v1/projects

Purpose
Return all visible projects for portfolio showcase.

Data Source
Project model

Behavior
Filter: isVisible = true

Sort: order ASC or createdAt DESC
Return array (can be empty)
Response Shape


GET /api/v1/timeline

Purpose
Return education + experience timeline.

Data Source
Timeline model

Behavior
Filter: isVisible = true

Sort: order ASC
Mixed types allowed (education, experience)
Response Shape


GET /api/v1/resume

Purpose
Return resume content or resume metadata.

Data Source
Resume model (singleton)

Behavior
If isPublic = false → return 404

No file streaming here (only metadata / HTML)
Response Shape


Error Handling (All APIs)

200 → success
404 → resource not found / not public
500 → unexpected server error
No custom error objects in v1.


Versioning Note

/api/v1 is stable
Breaking changes → /api/v2
Minor changes handled internally

## follow this directory structure
routes/
    │   ├── index.ts                # Root router (mounts /api, /health)
    │   ├── health.route.ts         # GET /health
    │   │
    │   └── api/
    │       ├── index.ts            # Mounts versions (/v1, future /v2)
    │       │
    │       └── v1/
    │           ├── index.ts        # Mounts v1 routes
    │           │
    │           ├── profile.route.ts    # GET /api/v1/profile
    │           ├── projects.route.ts   # GET /api/v1/projects
    │           ├── timeline.route.ts   # GET /api/v1/timeline
    │           └── resume.route.ts     # GET /api/v1/resume
    │

### 🧩 ROUTE MAPPING (MENTAL MODEL) -
app.ts
 ├── /health
 └── /api
      └── /v1
           ├── /profile
           ├── /projects
           ├── /timeline
           └── /resume

