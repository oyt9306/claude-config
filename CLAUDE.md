\# CLAUDE.md



Onboarding document for AI coding agents.

Read this file before performing any actions.



\---



\## WHAT — Project Structure



AI/ML research repository. Key layout:



```

src/

&#x20; models/      # model architectures

&#x20; datasets/    # dataset loaders

&#x20; training/    # training pipelines

&#x20; evaluation/  # metrics and benchmarks

&#x20; utils/       # shared utilities

configs/       # experiment configurations

scripts/       # run scripts

experiments/   # experiment outputs

notebooks/     # analysis notebooks

```



\---



\## WHY — Design Principles



\*\*Reproducibility first.\*\* All results in this repository must remain reproducible.



\- Do not silently change random seeds, experiment defaults, or logged outputs

\- Document any modification that affects training behavior



\*\*Stability.\*\* Preserve compatibility with existing experiments, baselines, and benchmark implementations.



\---



\## HOW — Agent Operating Rules



1\. \*\*Understand before editing\*\*: Read relevant files, identify dependencies and side effects before making changes

2\. \*\*Minimal edits\*\*: Prefer small targeted patches. Do not rewrite entire subsystems

3\. \*\*Protected artifacts (never modify automatically)\*\*: dataset files, saved checkpoints, experiment results, benchmark outputs, archived configs

4\. \*\*When uncertain\*\*: Do not proceed — explain the uncertainty and request clarification

5\. \*\*Adding dependencies\*\*: Confirm necessity → check compatibility → update dependency files



\---



\## HOW — Claude Behavior Principles



\### 1. Plan Mode Default

\- Enter plan mode for ANY non-trivial task (3+ steps or architecture)

\- Define BOTH execution + verification steps

\- If something breaks → STOP and re-plan

\- Write detailed specs to remove ambiguity



\### 2. Subagent Strategy

\- Use subagents aggressively for complex problems

\- Split tasks: research, execution, analysis — one task per agent

\- Parallelize thinking, not just execution



\### 3. Self-Improvement Loop

\- After ANY mistake → log it in gotchas.md

\- Convert mistakes into rules

\- Review past lessons before starting



\### 4. Verification Before Done

\- Never mark done without proof

\- Run tests, check logs, simulate real usage

\- Compare expected vs actual behavior

\- Ask: "Would a senior engineer approve this?"



\### 5. Demand Elegance

\- Ask: "Is there a simpler / cleaner way?"

\- Avoid hacky or temporary fixes

\- Optimize for long-term maintainability

\- Skip overengineering for small fixes



\### 6. Autonomous Bug Fixing

\- Bugs → fix immediately (no hand-holding)

\- Trace logs, errors, failing tests

\- Find root cause, not symptoms

\- Fix CI failures proactively



\### 7. Skills = System Layer

\- Skills are NOT just markdown files — they include code, scripts, data, workflows

\- Use skills for: verification, automation, data analysis, scaffolding



\### 8. File System = Context Engine

\- Use folders for: references/, scripts/, templates/

\- Structure improves reasoning quality



\### 9. Avoid Over-Constraining AI

\- Provide context, not micromanagement

\- Let AI adapt to the problem

\- Flexibility > strict instructions



\### Task Management

1\. Plan first → write tasks with checklist

2\. Verify before execution

3\. Track progress continuously

4\. Explain changes at each step

5\. Document results clearly

6\. Capture lessons after completion



\### 10. Code Modification Policy

\- When modifying existing code, do NOT over-encapsulate or over-abstract the original logic

\- Improving overall readability and refactoring for clarity is encouraged

\- But avoid introducing unnecessary abstraction layers, wrapper classes, or indirection that obscures the original intent

\- Rule of thumb: if the abstraction only serves one call site, it's probably not needed



\### Core Principles

\- Simplicity First → minimal, clean solutions

\- Systems > Prompts

\- Verification > Generation

\- Iteration > Perfection

\- No Lazy Fixes → solve root cause



\---



\## Execution Environment



\- Python ≥ 3.10, CUDA GPU (do not assume GPU availability unless explicitly required)

\- Core frameworks: PyTorch, HuggingFace, NumPy, SciPy, Matplotlib



\---



\## Detailed Guides



Read the following documents when relevant:



\- `agent\_docs/experiment\_workflow.md` — pipeline from data preprocessing to evaluation

\- `agent\_docs/logging\_and\_testing.md` — logging requirements and testing expectations



