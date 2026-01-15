# ADR-001: Profile Model Design

## Status
Accepted

## Context
The portfolio system requires a single, authoritative source of truth for
personal identity and presence-related information.

The Profile model is responsible for powering:
- Hero section (name, role, location)
- About section (short bio)
- Social and professional links
- Resume header metadata

This model is **read-heavy**, **admin-write-only**, and will have **exactly one document**
in the database.

The goal is to keep identity data centralized, minimal, and stable so that
frontend redesigns do not require backend refactoring.

---

## Decision
We will create a dedicated `Profile` model with **strict responsibility boundaries**.

The Profile model will:
- Contain only identity, presence, and external link data
- Exclude any project, resume, education, or experience data
- Be designed to store a single document only

All updates to this model will be **admin-only** via protected APIs.
Public access will be **read-only**.

---

## Data Fields

### Required Fields
- `name` (string, required)  
  Reason: Core identity field; cannot be optional for any professional portfolio.

- `role` (string, required)  
  Reason: Primary positioning statement for recruiters and founders.

### Optional Fields
- `bio` (string, optional)  
  Reason: Short professional summary; optional to allow minimal profiles.

- `location` (string, optional)  
  Reason: Useful for context and trust, but not mandatory.

- `photoUrl` (string, optional)  
  Reason: Stored as a URL to keep database storage simple and flexible.

- `socialLinks` (object, optional)  
  Reason: Links vary by platform and should remain extensible without schema changes.
  Example platforms include LinkedIn, GitHub, Twitter/X, personal blog.

---

## Non-Goals
The Profile model will NOT contain:
- Projects or case studies
- Resume content or files
- Education history
- Work experience
- Contact messages or leads

These concerns will be handled by separate models to enforce separation of concerns.

---

## Rules & Constraints
- Only one Profile document should exist in the database.
- Profile updates are restricted to authenticated admin users only.
- Public APIs may only read Profile data.
- No arrays or relational references are allowed in this model.
- The model should remain stable across UI redesigns.

## Collection Naming Convention

- The Profile model follows **standard Mongoose pluralization rules**.
- The collection name will be automatically derived as `profiles`.
- No explicit collection name override is used.

Reason:
- Aligns with industry conventions and tooling expectations.
- Avoids unnecessary configuration and surprises for future maintainers.
- Singleton behavior (only one Profile document) is enforced at the **controller level**, not via schema or collection naming.

---

## Consequences

### Positive
- Clean separation of identity vs content
- Easier frontend mapping and caching
- Minimal refactoring risk
- Clear ownership of responsibility

### Trade-offs
- Requires enforcing single-document logic at the controller level
- Slight duplication of data (e.g., name also appearing in resume) is intentional

---

## Future Considerations
If multi-profile support is ever required (e.g., SaaS expansion),
this decision can be revisited, but is intentionally out of scope for v1.
