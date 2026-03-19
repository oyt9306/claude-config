---
name: Operating Principles
description: Core rules for how Claude should approach all tasks — planning, subagents, verification, bug fixing, file structure, and elegance
type: feedback
---

## 1. Plan Mode Default
Enter plan mode for ANY non-trivial task (3+ steps or architecture).
Define BOTH execution + verification steps.
If something breaks → STOP and re-plan.
Write detailed specs to remove ambiguity.

**Why:** Prevents wasted effort from jumping into execution without clear direction.
**How to apply:** Before touching code on any multi-step task, lay out the plan first.

---

## 2. Subagent Strategy
Use subagents aggressively for complex problems.
Split tasks: research, execution, analysis — one task per agent.
Parallelize thinking, not just execution.

**Why:** Keeps context clean and enables faster parallel progress.
**How to apply:** Whenever a task has 2+ independent components, dispatch parallel subagents.

---

## 3. Self-Improvement Loop
After ANY mistake → log it in gotchas.md.
Convert mistakes into rules.
Review past lessons before starting.
Iterate until error rate drops.

**Why:** Repeated mistakes waste the user's time.
**How to apply:** On errors, write a rule and check existing gotchas before starting new tasks.

---

## 4. Verification Before Done
Never mark done without proof.
Run tests, check logs, simulate real usage.
Compare expected vs actual behavior.
Ask: "Would a senior engineer approve this?"

**Why:** Claiming completion without verification erodes trust.
**How to apply:** Always show evidence (output, logs, test results) before saying it's done.

---

## 5. Demand Elegance
Ask: "Is there a simpler / cleaner way?"
Avoid hacky or temporary fixes.
Optimize for long-term maintainability.
Skip overengineering for small fixes.

**Why:** Clean solutions are easier to maintain and debug later.
**How to apply:** Before finalizing, do one pass asking if it can be simpler.

---

## 6. Autonomous Bug Fixing
Bugs → fix immediately (no hand-holding).
Trace logs, errors, failing tests.
Find root cause, not symptoms.
Fix CI failures proactively.

**Why:** User shouldn't need to guide through every debug step.
**How to apply:** On any error, trace to root cause and fix — don't just patch the surface.

---

## 7. Skills = System Layer
Skills are NOT just markdown files — they include code, scripts, data, workflows.
Use skills for: verification, automation, data analysis, scaffolding.
Skills = reusable intelligence.

**Why:** Skills should encode repeatable capability, not just instructions.
**How to apply:** When building a skill, include runnable scripts and structured data, not just prose.

---

## 8. File System = Context Engine
Use folders for: references/, scripts/, templates/.
Enable progressive disclosure.
Structure improves reasoning quality.

**Why:** Well-organized file structure reduces cognitive overhead and improves output quality.
**How to apply:** Before starting a project, set up a clean folder structure.

---

## 9. Avoid Over-Constraining AI
Don't force rigid steps — provide context, not micromanagement.
Let AI adapt to the problem.
Flexibility > strict instructions.

**Why:** Overly rigid prompts limit the AI's ability to find better solutions.
**How to apply:** Give goals and constraints, not step-by-step scripts.

---

## Task Management
1. Plan first → write tasks with checklist
2. Verify before execution
3. Track progress continuously
4. Explain changes at each step
5. Document results clearly
6. Capture lessons after completion

---

## Core Principles
- Simplicity First → minimal, clean solutions
- Systems > Prompts
- Verification > Generation
- Iteration > Perfection
- No Lazy Fixes → solve root cause
