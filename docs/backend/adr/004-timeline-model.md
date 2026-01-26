# ADR-004: Education and Experience Timeline Model

## Status
Accepted

---

## Context

Education and professional experience are presented together as a chronological
timeline on the portfolio and resume.

Both education and experience share a common structure:
- Title
- Organization
- Duration
- Description
- Ordering and visibility

Separating them into different models would introduce unnecessary duplication
and complicate rendering and ordering logic.

---

## Decision

We will create a single Timeline model to represent both education and experience.

Each timeline entry will be differentiated using a `type` field with allowed
values:
- `education`
- `experience`

The Timeline model will:
- Store all education and experience records
- Support ordering and visibility control
- Be managed exclusively via authenticated admin APIs
- Be publicly readable through read-only APIs

---

## Data Fields

- `type` (required, enum: education | experience)  
  Reason: Distinguishes education entries from work experience.

- `title` (required)  
  Reason: Represents degree name or job title.

- `organization` (required)  
  Reason: Represents institution or company name.

- `location` (optional)  
  Reason: Provides additional context without being mandatory.

- `startDate` (required)  
  Reason: Required to establish chronological order.

- `endDate` (optional)  
  Reason: Allows representation of current or ongoing roles.

- `description` (optional)  
  Reason: Provides additional details without forcing verbosity.

- `order` (required, number)  
  Reason: Controls display order independent of date sorting.

- `isVisible` (required, boolean)  
  Reason: Allows hiding entries without deleting historical data.

---

## Rules & Constraints

- Multiple timeline entries are allowed.
- Timeline entries are ordered using the `order` field.
- Hidden entries remain stored in the database.
- Only admin users may create, update, or delete entries.
- Public access is strictly read-only.
- No relational references to other models.

---


## Collection Naming Convention

- The Timeline model follows **standard Mongoose pluralization rules**.
- The collection name will be automatically derived as `timelines`.
- No explicit collection name override is used.

Reason:
- Aligns with industry conventions and tooling expectations.
- Avoids unnecessary configuration and surprises for future maintainers.
- Singleton behavior (only one Timeline document) is enforced at the **controller level**, not via schema or collection naming.

---


## Non-Goals

The Timeline model will NOT:
- Store project data
- Store resume content
- Contain nested child records
- Handle analytics or engagement tracking

---

## Consequences

### Positive
- Unified and consistent timeline structure
- Simplified UI rendering
- Reduced schema duplication
- Easier maintenance and future extensions

### Trade-offs
- Requires clear use of the `type` field in frontend rendering
