# ADR-003: Resume Model Design

## Status
Accepted

---

## Context

The Resume represents the single, authoritative version of the candidate’s
professional summary presented on the portfolio website.

It powers both the rendered resume page and the downloadable PDF, while remaining
independent from projects, education, and experience models.

---

## Decision

We will create a Resume model designed as a singleton.

The Resume model will:
- Store structured resume content for rendering
- Optionally reference a downloadable PDF
- Be editable only via authenticated admin APIs
- Be publicly readable when enabled

---

## Data Fields

- `htmlContent` (required)  
  Reason: Renders the resume page consistently across UIs.

- `pdfUrl` (optional)  
  Reason: Allows resume download without storing files in the database.

- `isPublic` (required, boolean)  
  Reason: Enables hiding or showing the resume without deletion.

- `lastUpdated` (auto)  
  Reason: Tracks changes for admin clarity and auditing.

---

## Rules & Constraints

- Only one Resume document should exist.
- Public access is read-only.
- Admin access is required for updates.
- No relational data is stored in this model.
- Timestamps are enabled.

---

## Non-Goals

The Resume model will NOT contain:
- Project details
- Education or experience records
- Contact or lead data

---

## Consequences

### Positive
- Clear separation of concerns
- Simple rendering and downloads
- Minimal refactoring risk

### Trade-offs
- Singleton enforcement handled at controller level
