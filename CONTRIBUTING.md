# Contributing

## Adding a skill

1. Create `skills/your-skill-name/SKILL.md`
2. Use this frontmatter:

```yaml
---
name: your-skill-name
description: One sentence — what it does and when to trigger it.
---
```

3. Write the body in markdown: phases, steps, rules. Keep it tight — skills are loaded into context on every use.
4. Add an entry to the relevant table in `README.md`.
5. Open a PR.

## Skill quality checklist

- [ ] Trigger condition is explicit (when to use / not use)
- [ ] Steps are numbered and actionable
- [ ] No filler — every sentence is load-bearing
- [ ] Tested on at least one real task before submitting

## File structure

```
skills/
└── your-skill-name/
    ├── SKILL.md          # Required
    ├── REFERENCE.md      # Optional — extended docs
    └── scripts/          # Optional — helper scripts
```

## Reporting issues

Open a GitHub issue describing: what skill, what you tried, what happened, what you expected.
