# Example Vibe Coding Session

## User Prompt

"User retention is bad. Add a points system, badges, and a community tab so people come back."

## Agent Response Shape

### 1. Gate

This is a product-shaped coding request. It may lead to UI, data model, and navigation changes, so I should not start by adding systems. I will first reduce the retention problem and propose the smallest verifiable change.

Dangerous operations that would need confirmation: schema changes, dependency installs, large navigation rewrites, migrations, or deleting existing files.

### 2. Socratic Questions

- Who is failing to retain: new users, activated users, or paying users?
- Where do users drop: first visit, first task, second session, or after value delivery?
- How do users currently understand the product on first entry?
- What is the first moment where users should feel value?
- What evidence says the problem is lack of rewards rather than lack of comprehension?

### 3. First Principles

The product does not need "more engagement mechanics" by default. The core fact is that users are not returning. Possible lower-level explanations:

- They do not understand what the product does.
- They understand it but do not reach value quickly.
- The acquired users are not the target users.

### 4. Occam Plan

Minimal plan:

1. Inspect onboarding and first-run flow.
2. Improve first-screen value explanation or first action path if it is unclear.
3. Add one validation point: screenshot/manual flow/test around the first-run path.

Not doing yet:

- No points system.
- No badges.
- No community tab.
- No schema or dependency changes.

### 5. Implementation Plan

Files to inspect:

- Onboarding route/component.
- First-run state or empty-state component.
- Existing tests for onboarding or first task completion.

Before editing, state the exact file list and a 3-6 bullet plan.

### 6. Review

End with:

- Files changed.
- What user-facing behavior changed.
- Validation result.
- Whether the original retention hypothesis was only partially tested.
- Next smallest experiment if retention remains weak.
