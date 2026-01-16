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

Reasoning:
- Simple to understand
- Easy to maintain
- Safe for frontend compatibility
