# Workflow: Debugging

Use this when something is broken, a test is failing, or you have a hard-to-reproduce regression.

## Flow by severity

### Quick bug (< 30 min expected)
```
/mp-diagnose   → disciplined reproduce → minimise → hypothesise → fix loop
```

### Hard bug (unknown root cause, long tail)
```
/debug-polya          → structured 4-phase Pólya framework
/mp-diagnose          → after framing, run the diagnosis loop
/runtime-fix-review   → after fixing, verify the fix is real
```

### Performance regression
```
/mp-zoom-out          → check if the regression is systemic or local
/mp-diagnose          → instrument and bisect
```

## Key principle

Both `/debug-polya` and `/mp-diagnose` enforce one rule: **build a fast, deterministic feedback loop first**. Without a reproducible signal, no tool will help. Spend the first 20% of your time on this.

## After the fix

Always run `/runtime-fix-review` before closing the ticket. It verifies:
- The fix is structurally correct
- The code path is actually reachable at runtime
- There are no obvious regressions introduced
