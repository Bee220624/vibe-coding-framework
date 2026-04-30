# Vibe Coding Framework Notes

## Table of Contents

1. Operating Model
2. Socratic Questioning
3. First Principles
4. Occam's Razor
5. Coding Phase Mapping
6. Dangerous Operation Policy
7. Trigger Examples
8. Anti-Patterns

## 1. Operating Model

This framework exists to stop AI agents from producing professional-looking but strategically empty answers. The agent should not mirror a vague prompt and immediately modify code. It should first turn the request into a smaller, testable, and implementation-ready problem.

The sequence is:

1. Socratic Questioning: clarify the problem.
2. First Principles: reduce the problem to facts, constraints, and value.
3. Occam's Razor: choose the smallest verifiable path.

The output is not a theory essay. It should become a task brief, implementation plan, or review checklist that helps the agent code with control.

## 2. Socratic Questioning

Purpose: stop answering too early. Convert vague big questions into judgeable small questions.

Core questions:

- Who exactly has this problem?
- What task are they trying to complete?
- Does the problem exist now, or is it a projection?
- What evidence supports the problem?
- How does the user solve the problem today?
- What is broken in the current workaround?
- What is the exact friction point?
- What would improve if this feature or change worked?
- What would prove that the feature is unnecessary?

Example: "Should we build this feature?"

Do not answer yes or no first. Decompose:

- Which user segment is it for?
- What job does it help them finish?
- What happens without it?
- Where does the current workflow fail?
- Is the cost of the failure high enough to justify code?

Expected output: a concise task brief and any blocking questions.

## 3. First Principles

Purpose: avoid copying habits, competitors, and industry defaults. Work from bottom-level facts.

Ask:

- What is the product or feature really selling?
- Is it a continuous tool or a one-time solution?
- Does value happen every day, repeatedly, or only at a key moment?
- How often does the user naturally need this?
- Is payment driven by daily necessity or by a single high-value moment?
- Which constraints are real: technical, user behavior, business, legal, time, team capacity?
- Which constraints are assumptions?
- Which proposed requirements exist only because another product does them?

Subscription example:

- Bad habit-based reasoning: most SaaS products use subscriptions, so this one should too.
- First-principles reasoning: if value is continuous and users return frequently, subscription may fit. If the product solves a rare or one-time problem, a subscription may create friction.

Expected output: a root analysis that separates facts, assumptions, habits, and constraints.

## 4. Occam's Razor

Purpose: prevent over-design before simple explanations have been tested.

Ask:

- What is the simplest explanation for the failure?
- What is the smallest change that can validate this explanation?
- Which solution has the fewest assumptions?
- Can this be tested without adding a new system?
- What should explicitly stay out of scope?

Retention example:

Do not jump directly to adding points, badges, communities, referral loops, or complex growth systems. First check:

- Comprehension: users may not understand what the product does in the first few seconds.
- Velocity: users may understand it but fail to feel value quickly.
- Alignment: acquisition may be attracting the wrong users.

Expected output: a minimal plan with validation and a clear "not doing" list.

## 5. Coding Phase Mapping

### Before Coding

Produce:

- Task brief.
- Assumptions.
- File or module areas likely to inspect.
- Minimal implementation plan.
- Validation plan.
- User confirmation request for dangerous operations.

### During Coding

Continuously check:

- Is the diff still serving the original problem?
- Has scope expanded?
- Did the agent discover a simpler fix?
- Is a dangerous operation now required?
- Are tests or validation still aligned with the actual behavior change?

### After Coding

Produce:

- Summary of what changed.
- Files changed.
- Validation run and result.
- Whether the original problem is addressed.
- Residual risks.
- Suggested next step only when it directly follows from the request.

## 6. Dangerous Operation Policy

Always ask for explicit confirmation before:

- Deleting files, directories, data, branches, or records.
- Bulk moving, renaming, or rewriting files.
- Large refactors or architecture changes.
- Public API, schema, migration, auth, security, or config changes.
- Installing packages or modifying dependency lockfiles.
- Running networked, production, deployment, or destructive git commands.
- Touching secrets, credentials, environment values, private keys, or live services.

If the user has not approved the operation, propose the minimal safe alternative.

## 7. Trigger Examples

Strong triggers:

- "Help me vibe code this feature."
- "Should we build this?"
- "Retention is bad; add a points system."
- "Users do not understand onboarding; make it better."
- "Maybe we should switch pricing to subscription."
- "Refactor this whole area so it is cleaner."
- "The AI keeps changing too much; help me control the coding process."
- "Review whether this implementation actually solves the problem."

Weak or no trigger:

- "Rename this button label."
- "Explain what this function does."
- "Run the test suite."
- "Fix this typo."
- "Format this file."

For weak triggers, use a lightweight check only if the task has hidden product or implementation risk.

## 8. Anti-Patterns

Avoid:

- Writing a long theory essay instead of a working plan.
- Asking many questions when reasonable assumptions are enough.
- Starting code edits before identifying the problem and file scope.
- Treating competitor behavior as proof.
- Treating retention problems as feature-count problems by default.
- Solving onboarding problems with gamification before checking comprehension.
- Adding infrastructure for a one-off change.
- Continuing after discovering a dangerous operation without asking the user.
