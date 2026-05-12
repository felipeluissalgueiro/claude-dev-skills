# claude-dev-skills

> 37 Claude Code skills for professional software development — code review, debugging, spec-driven development, TDD, architecture, and more.

A curated collection of battle-tested skills for [Claude Code](https://code.claude.com), organized to cover the full development lifecycle. Install once, use on any project.

**[🇧🇷 Versão em Português](README-pt.md)**

---

## Install

**macOS / Linux / WSL**

```bash
git clone https://github.com/Posicionamento-Digital/claude-dev-skills.git
cd claude-dev-skills
chmod +x install.sh && ./install.sh
```

**Windows (PowerShell)**

```powershell
git clone https://github.com/Posicionamento-Digital/claude-dev-skills.git
cd claude-dev-skills
.\install.ps1
```

Restart Claude Code after installing. Skills are placed in `~/.claude/skills/` and are available in all your projects immediately.

To overwrite existing skills: `./install.sh --force` / `.\install.ps1 -Force`

---

## Skills Catalog

### Code Review

| Skill | What it does |
|---|---|
| `/claude-review [N\|SHA\|range]` | Review via Claude Opus — classifies findings as P1/P2/P3 |
| `/gemini-review [N\|SHA\|range]` | Review via Gemini CLI (free, Google OAuth) |
| `/codex-review [N\|SHA\|range]` | Review via OpenAI Codex CLI |
| `/runtime-fix-review` | Verify claimed fixes are structurally correct and reachable at runtime |
| `/simplify` ¹ | Review changed code for reuse, quality and efficiency |
| `/review` ¹ | Review an open pull request |
| `/security-review` ¹ | Security-focused review of current branch changes |

### Debugging

| Skill | What it does |
|---|---|
| `/debug-polya` | Structured 4-phase Pólya framework — understand before acting |
| `/mp-diagnose` | Disciplined loop: reproduce → minimise → hypothesise → instrument → fix → regression-test |

### Spec-Driven Development

Use these for building new features with a structured, spec-first approach.

| Skill | What it does |
|---|---|
| `/speckit-constitution` | Create or update the project constitution (principles, conventions) |
| `/speckit-specify` | Write the feature spec from a natural-language description |
| `/speckit-clarify` | Identify and resolve underspecified areas in the spec |
| `/speckit-plan` | Generate design artifacts (architecture, data model, API contracts) |
| `/speckit-tasks` | Generate a dependency-ordered task list |
| `/speckit-analyze` | Cross-check consistency across spec, plan and tasks |
| `/speckit-implement` | Execute tasks from tasks.md one by one |
| `/speckit-checklist` | Generate a custom checklist for the current feature |

### TDD & Prototyping

| Skill | What it does |
|---|---|
| `/mp-tdd` | Test-driven development with red-green-refactor loop |
| `/mp-prototype` | Build a throwaway prototype to validate a design before committing |

### Architecture

| Skill | What it does |
|---|---|
| `/mp-improve-codebase-architecture` | Find deepening opportunities informed by CONTEXT.md and ADRs |
| `/mp-zoom-out` | Systemic context — understand the bigger picture before diving in |

### Discovery & Planning

| Skill | What it does |
|---|---|
| `/mp-grill-me` | Stress-test a plan relentlessly — no code, just questions |
| `/mp-grill-with-docs` | Grill your plan against the existing domain model |
| `/mp-to-prd` | Turn the current conversation into a PRD |
| `/mp-to-issues` | Break a plan into independently-grabbable GitHub issues |
| `/mp-triage` | Triage issues through a state machine driven by triage roles |

### Git & Setup

| Skill | What it does |
|---|---|
| `/mp-git-guardrails-claude-code` | Add hooks to block dangerous git commands (push, reset --hard, clean) |
| `/mp-setup-pre-commit` | Set up Husky + lint-staged (Prettier) + type checking + tests |
| `/speckit-git-initialize` | Initialize a git repo with an initial commit |
| `/speckit-git-feature` | Create a feature branch with sequential numbering |
| `/speckit-git-commit` | Auto-commit after a Spec Kit command completes |
| `/speckit-git-remote` | Detect git remote URL for GitHub integration |
| `/speckit-git-validate` | Validate current branch follows feature branch conventions |

### Scaffolding & Migration

| Skill | What it does |
|---|---|
| `/mp-scaffold-exercises` | Create exercise directory structures with sections and solutions |
| `/mp-migrate-to-shoehorn` | Migrate `as` type assertions to `@total-typescript/shoehorn` in tests |
| `/speckit-taskstoissues` | Convert tasks.md into actionable GitHub issues |

### Documentation

| Skill | What it does |
|---|---|
| `/registrar-incidente` | Register incidents and technical learnings in a central hub |
| `/init` ¹ | Initialize a CLAUDE.md with codebase documentation |

### Productivity

| Skill | What it does |
|---|---|
| `/mp-caveman` | Ultra-compressed communication mode — ~75% fewer tokens |
| `/mp-handoff` | Compact the current conversation into a handoff doc for another agent |
| `/mp-write-a-skill` | Create new skills with correct structure and progressive disclosure |
| `/fewer-permission-prompts` ¹ | Scan transcripts and add an allowlist to reduce permission prompts |

> ¹ Built-in Claude Code skill — not included in this repo. Available in Claude Code by default.

---

## Workflows

Common combinations for real-world scenarios:

- [New Feature](docs/workflows/new-feature.md) — spec → plan → implement → review
- [Debugging](docs/workflows/debugging.md) — reproduce → diagnose → fix → verify
- [Code Review](docs/workflows/code-review.md) — single model or cross-model review + post-fix verification

---

## Project Setup Recommendations

For best results, add two files to each project:

**`CONTEXT.md`** — ubiquitous language and domain model. Multiple skills (`/mp-grill-with-docs`, `/mp-improve-codebase-architecture`, `/mp-diagnose`) read this to stay aligned with your domain.

```markdown
# Project: My App

## Domain Language
- **Order** — a confirmed purchase...
- **Cart** — temporary collection of items...

## Key Invariants
- Orders are immutable after confirmation
...
```

**`docs/adr/`** — Architecture Decision Records. One file per significant decision (`0001-use-postgres.md`). Skills use these to avoid proposing changes that contradict past decisions.

---

## Credits

This collection bundles skills from three sources:

- **`mp-*` skills** — [Matt Pocock](https://github.com/mattpocock/skills). Original work by Matt Pocock, adapted for this distribution. MIT License.
- **`speckit-*` skills** — [Spec-Kit](https://github.com/github/spec-kit) by GitHub. Spec-Driven Development framework.
- **`debug-polya`, `claude-review`, `codex-review`, `gemini-review`, `runtime-fix-review`, `registrar-incidente`** — Original skills by [Felipe Salgueiro](https://github.com/felipeluissalgueiro) / [Posicionamento Digital](https://github.com/Posicionamento-Digital).

---

## Contributing

1. Fork the repo
2. Add your skill under `skills/your-skill-name/SKILL.md`
3. Follow the [SKILL.md format](https://code.claude.com/docs/en/skills) — YAML frontmatter + markdown instructions
4. Open a PR with a short description of what the skill does and when to trigger it

---

## License

MIT — see [LICENSE](LICENSE).

---

## About the Author

**Felipe Salgueiro** is a developer, entrepreneur, and AI builder based in Sorocaba, Brazil.

He founded [Posicionamento Digital](https://posicionamentodigital.com) — a digital marketing and AI automation agency — and built [Cadencia](https://cadencia.app.br), a platform that automates content pipelines for businesses using AI agents.

These skills were assembled out of necessity. Running multiple software projects simultaneously while maintaining code quality requires discipline that doesn't come free — it has to be engineered. Over time, he curated and built this collection to enforce structure around the parts of development that slip most easily: reviewing code before it ships, diagnosing bugs methodically instead of guessing, writing specs before writing code, and verifying that fixes actually work at runtime.

The collection pulls the best from [Matt Pocock's engineering skills](https://github.com/mattpocock/skills), [GitHub's Spec-Kit framework](https://github.com/github/spec-kit), and original skills built from hard lessons across dozens of production projects.

**Links:**
- Site: [posicionamentodigital.com](https://posicionamentodigital.com)
- AI Platform: [cadencia.app.br](https://cadencia.app.br)
- AI Content: [insightartificial.ia.br](https://insightartificial.ia.br)
- GitHub: [@felipeluissalgueiro](https://github.com/felipeluissalgueiro)
- LinkedIn: [felipe-luis-salgueiro](https://linkedin.com/in/felipe-luis-salgueiro)
- Instagram: [@felipeluissalgueiro](https://instagram.com/felipeluissalgueiro)
- TikTok: [@felipeluissalgueiro](https://tiktok.com/@felipeluissalgueiro)
