# ADR-002: Project Model Design

## Status
Accepted

---

## Context

Projects represent individual pieces of work that demonstrate technical skill,
problem-solving ability, and ownership.

Each Project corresponds to a real or buildable product that can be showcased
to recruiters, founders, and technical reviewers.

Project data is stored in the database so it can be centrally managed,
dynamically rendered on the portfolio website, and reordered or hidden without
requiring code changes.

The Project model is intentionally separated from employment history and resume
content to allow flexible presentation across different user interfaces.

---

## Decision

We will create a Project model to represent portfolio work items.

The Project model will:
- Store structured project-related data such as title, description, technologies, and links
- Be managed exclusively via authenticated admin APIs
- Support ordering and visibility control for UI presentation
- Be exposed to the public only through read-only APIs

This approach ensures clarity, security, and long-term flexibility.

---

## Data Fields

- `title` (required)  
  Reason: Primary identifier and headline for the project.

- `description` (required)  
  Reason: Explains the problem solved and the value of the project.

- `techStack` (required, array of strings)  
  Reason: Allows clear visibility of technologies and future filtering.

- `githubUrl` (optional)  
  Reason: Provides access to source code when available.

- `liveUrl` (optional)  
  Reason: Allows reviewers to see a running version of the project.

- `coverImage` (optional)  
  Reason: Improves visual presentation without being mandatory.

- `isVisible` (required, boolean)  
  Reason: Enables hiding projects without deleting historical data.

- `order` (required, number)  
  Reason: Controls display order without frontend sorting logic.

---

## Rules & Constraints

- Multiple Project documents are expected.
- Projects are ordered using the `order` field.
- Hidden projects (`isVisible = false`) remain in the database.
- Only authenticated admin users may create, update, or delete projects.
- Public access is strictly read-only.

---


## Collection Naming Convention

- The Project model follows **standard Mongoose pluralization rules**.
- The collection name will be automatically derived as `projects`.
- No explicit collection name override is used.

Reason:
- Aligns with industry conventions and tooling expectations.
- Avoids unnecessary configuration and surprises for future maintainers.
- Singleton behavior (only one Project document) is enforced at the **controller level**, not via schema or collection naming.

---

## Non-Goals

The Project model will NOT contain:
- Employment or company history
- Job titles or employment dates
- Resume content
- Blog or long-form markdown content

These concerns are handled by separate models.

---

## Consequences

### Positive
- Clean separation of concerns
- Easy UI control without code changes
- Scalable and future-proof design
- Predictable API behavior

### Trade-offs
- Ordering must be managed intentionally by the admin
- Slightly more fields than a minimal demo model

---

## Future Considerations

- Tag-based categorization
- Featured projects flag
- Analytics or engagement metrics
