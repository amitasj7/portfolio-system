2️⃣ CRUD ORDER (IMPORTANT — DO NOT RANDOMIZE)
Profile (singleton)
Projects (collection)
Timeline (collection)
Resume (singleton + upload)
Leads (read-only + delete)


2️⃣ CRUD ORDER (IMPORTANT — DO NOT RANDOMIZE)

🔹 Profile (SINGLE document)
GET    /admin/profile
PUT    /admin/profile
Rules:
No POST
PUT = create or update
Always one document

🔹 Projects (MULTIPLE) 
GET    /admin/projects
POST   /admin/projects
PUT    /admin/projects/:id
DELETE /admin/projects/:id
Rules:
Admin sees ALL (visible + hidden)
isVisible controlled here


4️⃣ DIRECTORY STRUCTURE (ADMIN CRUD) -
backend/src/
├── controllers/
│   └── admin/
│       ├── profile.controller.ts
│       ├── projects.controller.ts
│       ├── timeline.controller.ts
│       ├── resume.controller.ts
│       └── leads.controller.ts
│
├── routes/
│   └── admin/
│       ├── auth.route.ts
│       ├── profile.route.ts
│       ├── projects.route.ts
│       ├── timeline.route.ts
│       ├── resume.route.ts
│       ├── leads.route.ts
│       └── index.ts


5️⃣ EXECUTION STRATEGY (HOW YOU BUILD FAST)

For each resource:

1️⃣ Create controller file (admin)
2️⃣ Add CRUD functions
3️⃣ Create route file
4️⃣ Mount in routes/admin/index.ts
5️⃣ Test in Postman
6️⃣ Commit
7️⃣ Move on

👉 One resource at a time. No mixing.

