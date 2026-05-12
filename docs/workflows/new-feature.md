# Workflow: New Feature

Use this when implementing a new feature from scratch or a significant addition to an existing codebase.

## Flow

```
/mp-grill-with-docs   → challenge your plan against the domain model
/speckit-specify      → write the feature spec
/speckit-clarify      → resolve ambiguities (optional)
/speckit-plan         → design artifacts (architecture, data model)
/speckit-tasks        → generate ordered task list
/speckit-analyze      → cross-check consistency (optional)
/speckit-implement    → execute tasks one by one
/claude-review        → review after each story
/runtime-fix-review   → verify fixes are actually implemented
```

## When to use which review

| Situation | Skill |
|---|---|
| After a story is done | `/claude-review` |
| Suspicious of a "claimed fix" | `/runtime-fix-review` |
| Security-sensitive change | `/security-review` (built-in) |
| Code feels bloated after the task | `/simplify` (built-in) |

## Tips

- Run `/speckit-clarify` before planning if the spec has open questions — saves rework later.
- Use `/mp-tdd` inside `/speckit-implement` for individual tasks when logic is complex.
- After implementing, run `/gemini-review` or `/codex-review` for a second opinion at $0 cost.
