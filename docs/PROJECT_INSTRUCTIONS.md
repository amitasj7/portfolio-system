📘 Project Instructions – Portfolio Backend


1. Branch Strategy

develop
→ Stable integration branch
→ No direct coding here

feature/<task-name>
→ Used for exactly ONE task
→ Example:

feature/backend-env-config
feature/backend-db-config
feature/backend-app-bootstrap


2. Standard Workflow (MANDATORY)

For every new task, follow this order:
1. Create feature branch from develop
2. Write planning (docs / comments)
3. Implement code
4. Manually check logic + git status
5. Commit with correct prefix
6. Merge into develop
7. Delete or leave feature branch
8. Move to next task


3. Commit Message Rules
Type	When to use
feat	New functionality
chore	Setup / config / infra
docs	Documentation only
refactor	Rename / restructure (no behavior change)

❌ Never mix multiple concerns in one commit.


4. Planning Rules

High-level decisions → docs/
File-specific intent → comments at top of file
Do NOT mix planning + random code


5. Safety Rules

.env is never committed
process.env is used only in env.ts
Database connection must happen before server start
app.ts never calls app.listen()


6. Completion Rule (IMPORTANT)

A task is considered DONE only when:
Code is committed
Branch is merged into develop
git status is clean
Next task starts on a new branch

🔒 One-line philosophy (remember this)
“Finish one thing cleanly before starting the next.”