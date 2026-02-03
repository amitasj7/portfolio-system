

# GLOBAL RULES (NON-NEGOTIABLE)

1. Never jump directly to a fix.
2. Always restate the problem in your own words first.
3. Separate symptoms from root causes.
4. Do not mix multiple hypotheses at once.
5. Apply the smallest possible change.
6. Every action must have a clear reason.
7. Prefer clarity over cleverness.
8. If something works, explain WHY it works.
9. If something fails, explain WHY it failed.
10. Assume this work will be audited later.

--------------------------------------------------------------------

PROBLEM-SOLVING PHASES (MANDATORY ORDER)

PHASE 0 — STABILITY
- Pause.
- Remove urgency.
- Treat the problem as data, not failure.

PHASE 1 — PROBLEM DEFINITION
- What exactly is failing?
- When does it fail (dev, build, runtime)?
- What is the exact error message?
- What changed before this started?
- Is the issue reproducible?

PHASE 2 — SYSTEM BOUNDARY IDENTIFICATION
- Which layer is involved?
  (UI, framework, build tool, runtime, dependency, OS)
- Who owns this layer? (our code vs third-party)
- Where is the interface between systems?

PHASE 3 — FACT COLLECTION
- Relevant files
- Versions (framework, libraries, runtime)
- Configuration involved
- Environment details
NO assumptions allowed.

PHASE 4 — HYPOTHESIS GENERATION
- List possible causes.
- Rank them by likelihood.
- Each hypothesis must be testable.

PHASE 5 — HYPOTHESIS ELIMINATION
- Test ONE hypothesis at a time.
- Use evidence, not intuition.
- Eliminate fast and move on.

PHASE 6 — INTENTIONAL FIX
- Apply the smallest valid fix.
- Avoid shotgun changes.
- Keep rollback simple.

PHASE 7 — VERIFICATION
- Restart from a clean state if needed.
- Confirm the issue is gone.
- Ensure no new warnings/errors appear.

PHASE 8 — ROOT CAUSE ANALYSIS
- Why did this happen?
- Why now?
- Why was it not caught earlier?

PHASE 9 — SYSTEM HARDENING
- How do we prevent this?
- What guardrail was missing?
- Do we need documentation, constraints, or checks?

PHASE 10 — KNOWLEDGE ENCODING
- Document what we learned.
- Update project notes.
- Convert the fix into a reusable mental model.

--------------------------------------------------------------------

DOCUMENTATION RULES (FOR FRONTEND WORK)

When writing what we did, always use this structure:

1. Context
2. Problem Statement
3. System Layers Involved
4. Root Cause
5. Fix Applied
6. Why This Fix Works
7. What We Learned
8. How We Prevent This in Future

Formatting rules:
- Clear headings
- Consistent indentation
- No vague language
- No skipped steps

--------------------------------------------------------------------

QUALITY BAR

Ask yourself before finalizing:
- Would a Staff / Principal Engineer approve this?
- Would this make sense 6 months later?
- Can another engineer reproduce my reasoning?

If the answer is NO, refine the work.

--------------------------------------------------------------------

FINAL PRINCIPLE

"I do not fix bugs.
I fix the systems that create bugs."

Proceed only when the reasoning is sound.
