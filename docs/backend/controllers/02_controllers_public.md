⚙️ HOW TO IMPLEMENT EACH CONTROLLER (SAME PATTERN)
✅ COMMON RULES (apply to ALL)

Export named functions (not default)
One main handler per controller file
Async functions
try/catch always
No routing logic
No process.env
No mutations (GET only)


1️⃣ profile.controller.ts
Implement this logic ONLY:

Fetch single Profile (findOne)
Shape public response
Return:
200 + data if exists
200 + null or 404 if not (your choice, be consistent)

2️⃣ projects.controller.ts
Implement this logic ONLY:

Fetch projects (find)
Filter isVisible: true
Sort (order or createdAt)
Always return array

3️⃣ timeline.controller.ts
Implement this logic ONLY:

Fetch timeline items (find)
Filter isVisible: true
Sort (order or date)
Always return array

4️⃣ resume.controller.ts
Implement this logic ONLY:

Fetch single resume
Check isPublic
If false → return 404
If true → return data


