---
name: vibe-coding-framework
description: "Use when Codex or another AI coding agent needs a practical thinking framework before, during, or after vibe coding: unclear feature requests, questions like whether to build a feature, product/UX/retention/pricing decisions that may lead to code, rapid AI-assisted implementation, risky code changes, or post-change review. Helps turn vague requests into judgeable questions, first-principles analysis, a minimal verifiable plan, and a review checklist. Do not use for tiny explicit edits, simple code explanations, formatting-only changes, or already well-scoped low-risk tasks unless a light check is useful."
---

# Vibe Coding Framework

## Overview

Use this skill to keep AI-assisted coding deliberate. It is a thinking and control framework, not a replacement for normal repository reading, planning, editing, testing, and review.

Keep the process proportional. For vague or high-impact work, use the full flow. For narrow work, run only the relevant checks and proceed.

## Workflow

### 1. Gate the Task

- Identify the stage: before coding, during implementation, or after implementation.
- Decide whether the user asked for thinking only, planning, code changes, or review.
- If information is missing, ask at most 3 blocking questions. Otherwise state assumptions and continue.
- Before editing, identify the files or areas likely to change and state the plan in 3-6 bullets.

### 2. Clarify with Socratic Questions

Turn the vague request into smaller judgeable questions:

- Who has the problem?
- Does the problem really exist?
- How does the user solve it today without this change?
- Where is the current workflow failing?
- What result would prove the change worked?

### 3. Reduce with First Principles

Separate facts from habits:

- What is the bottom-level fact of the problem?
- Which assumptions come from competitors, industry norms, or team habit?
- What value is the product or feature actually delivering?
- Is the value continuous, repeated, or one-time?
- What user behavior, frequency, motivation, and technical constraints matter?

### 4. Simplify with Occam's Razor

Prefer the smallest explanation and the smallest verifiable plan:

- Check simple causes before complex fixes.
- Prefer a minimal change or experiment before adding new systems.
- Explicitly list what will not be changed.
- Define the fastest validation: test, screenshot, manual flow, metric, or code review.

For retention or onboarding problems, first test:

- Comprehension: users do not understand the product quickly enough.
- Velocity: time-to-value is too slow.
- Alignment: the attracted users are not the target users.

### 5. Implement with Guardrails

- Keep diffs small and reviewable.
- Follow existing repository style, architecture, helpers, and tests.
- Do not invent APIs, config keys, file paths, data schemas, or commands.
- Do not add analytics, telemetry, network calls, or dependencies unless the user asked.
- Run the fastest relevant validation after changes when feasible.

### 6. Review the Result

End with:

- What changed.
- Files changed.
- Validation performed and result.
- Whether the original problem was actually addressed.
- Residual risks or assumptions.

## Confirmation Rules

Ask for explicit user confirmation before:

- Deleting, overwriting, moving, or bulk-renaming files.
- Large refactors, public API changes, migrations, or schema changes.
- Modifying build config, package manager config, CI, deployment, auth, security, or environment handling.
- Installing dependencies or running commands that require network access.
- Touching production data, secrets, credentials, or live services.
- Running destructive git commands.

## Bundled Resources

- Read `references/framework-notes.md` when the request involves product reasoning, feature prioritization, retention, pricing, onboarding, vague strategy, or repeated uncertainty.
- Use `templates/task-brief-template.md` before coding when the request is ambiguous.
- Use `templates/implementation-plan-template.md` before edits or during implementation.
- Use `templates/review-checklist-template.md` after changes or during review.
- Use `examples/example-vibe-coding-session.md` as a compact model of the expected behavior.
