# ADR-005: Lead Model (Contact Submissions)

## Status
Accepted

---

## Context

The portfolio includes a contact form to allow recruiters, founders, and
collaborators to reach out.

Submitted contact data must be:
- Stored for follow-up
- Used to trigger notifications
- Accessible only to the admin

The Lead model exists to capture and manage these contact submissions in a
structured and auditable way.

---

## Decision

We will create a Lead model to represent contact form submissions.

The Lead model will:
- Store essential contact information and messages
- Be created via a public API endpoint
- Be readable and manageable only by authenticated admin users
- Serve as the trigger point for notification workflows

---

## Data Fields

- `name` (required)  
  Reason: Identifies the person submitting the message.

- `email` (required)  
  Reason: Primary method for responding to the lead.

- `message` (required)  
  Reason: Captures the intent or inquiry of the sender.

- `isRead` (required, boolean, default: false)  
  Reason: Tracks whether the lead has been reviewed by the admin.

- `createdAt` (auto)  
  Reason: Records submission time for auditing and follow-up.

---

## Rules & Constraints

- Multiple lead entries are expected.
- Leads are created via public API endpoints.
- Only admin users may read or manage leads.
- Leads are never edited after creation (read-status updates only).
- Timestamps are enabled.

---

## Non-Goals

The Lead model will NOT:
- Send notifications directly
- Handle authentication
- Store reply messages
- Perform spam filtering (future concern)

---

## Consequences

### Positive
- Clean separation of contact data from notification logic
- Reliable audit trail of incoming messages
- Simple and predictable API behavior

### Trade-offs
- Notification logic must be handled in services/controllers
