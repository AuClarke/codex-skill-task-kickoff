---
name: codex-task-kickoff
description: Start complex Codex tasks with a compact goal/source/output/verification/boundary frame before execution. Use when the user asks for multi-step work, files, presentations, web research, browser operation, local app changes, Git-ready artifacts, or anything that could drift without clear acceptance criteria.
---

# Codex Task Kickoff

## Quick Frame

Before execution, establish these five fields. If the user already supplied enough context, infer them briefly and proceed.

```text
Goal:
Sources:
Output:
Verification:
Boundaries:
```

## Decision

- If the task is simple and low-risk, do the frame internally and answer directly.
- If the task changes global settings, installs dependencies, writes outside the workspace, deletes data, or affects security permissions, show the frame and wait for explicit approval.
- If the user explicitly says to continue or execute and the scope is safe, state the frame in one short update and proceed.

## Defaults For This User

- Use Chinese for updates and final summaries.
- Use the internet for current, source-dependent, or web/content tasks.
- Prefer real local state over assumptions.
- For deliverables, verify the artifact exists and can be inspected.
- For browser/social-media work, keep links and screenshots as evidence.

## Output Pattern

When reporting completion, include:

- What was produced
- Where it is saved
- What was checked
- Any remaining risk or user action needed
