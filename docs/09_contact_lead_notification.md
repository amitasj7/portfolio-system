1️⃣ What we’re building (scope)
Goal: When someone submits the contact form:

Save a Lead

Send a notification to admin (email first)

Public → Admin loop completed.


2️⃣ Public API (LOCK THIS)
POST /api/v1/contact


Public, no auth

Body (example):

{
  "name": "John Doe",
  "email": "john@email.com",
  "message": "Interested in working with you"
}

3️⃣ Flow (mental model)
Client
  ↓
POST /api/v1/contact
  ↓
contact.controller.ts
  ↓
Lead.model.ts (save)
  ↓
notification.service.ts
  ↓
Email sent to admin


4️⃣ Files & Directories
backend/src/
├── controllers/
│   └── public/
│       └── contact.controller.ts
│
├── routes/
│   └── api/v1/
│       └── contact.route.ts
│
├── services/
│   └── notification.service.ts
│
└── utils/
    └── email.util.ts   (optional helper)


5️⃣ Controller responsibilities
contact.controller.ts

Validate input

Create Lead

Call notification service

Return 201 (even if email fails)

6️⃣ Notification service (v1)
notification.service.ts

Send email to admin

Fire-and-forget (don’t block response)

No retries (v1)

Later (v2):

WhatsApp

Queue (BullMQ)

7️⃣ Postman tests (public)
POST /api/v1/contact
→ 201 Created
→ Lead saved
→ Email triggered


Edge cases:

Missing fields → 400

Invalid email → 400

8️⃣ Git plan

Branch

feature/public-contact-notification


Commits

feat: add public contact API
feat: add notification service
chore: wire contact route