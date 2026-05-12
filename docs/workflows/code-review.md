# Workflow: Code Review

Use this to review a branch, PR, or set of commits before merging.

## Standard review (any branch)

```
/claude-review [N commits | SHA | range]   → Claude Opus, classifies P1/P2/P3
```

## Cross-model review (second opinion, $0)

Run two independent reviews and compare findings:

```
/gemini-review [N | SHA | range]   → Gemini CLI (Google OAuth, free)
/codex-review  [N | SHA | range]   → OpenAI Codex CLI
```

## Security-focused review

```
/security-review   → built-in, focused on OWASP, secrets, injection, auth
```

## Post-fix verification

```
/runtime-fix-review   → after applying review findings, confirm each fix is real
```

## Priority guide

| Priority | What it means | Action |
|---|---|---|
| P1 | Logic error, security issue, data corruption | Block merge, fix now |
| P2 | Performance, maintainability, missing error handling | Fix before merge |
| P3 | Style, naming, minor suggestions | Fix or defer to next PR |

## Tips

- For diffs > 30KB, pass a commit range (`HEAD~3..HEAD`) to avoid context limits.
- Running two models (e.g. Claude + Gemini) catches different classes of issues.
- Use `/simplify` (built-in) separately when code feels over-engineered after review.
