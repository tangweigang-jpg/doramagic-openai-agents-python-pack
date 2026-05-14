# Differentiation

## Existing GitHub Assets Found

- Official docs: https://github.com/openai/openai-agents-python
- Official upstream README explains how to install and use the project.
- Release and issue history expose setup, runtime, or integration failure modes that a normal quickstart rarely packages as agent recovery rules.
- This pack is scoped as a portable AGENTS.md / CLAUDE.md capability bundle with evals, source mapping, and pitfall recovery.

## What This Pack Adds vs. Upstream

| Dimension | Upstream (openai-agents-python) | This Doramagic Pack |
|---|---|---|
| Install verification | README says `pip install openai-agents`; no name-mismatch warning | Pitfall 1 explicitly calls out repo name `openai-agents-python` vs install name `openai-agents` |
| Happy-path docs | Quickstart demo for single-agent | Multi-agent handoff with explicit context transfer rules |
| Failure modes | GitHub issues scattered across releases | Top 3 actionable pitfalls at the top of `03_PITFALL_LOG.md` with recovery steps and stop conditions |
| Eval / verification | None packaged | Three evals: smoke check, boundary check, failure check — specific to OpenAI Agents SDK workflows |
| Boundary / risk card | None | `04_BOUNDARY_RISK_CARD.md` with permissions, hard boundaries, stop conditions |
| Agent host instructions | None | `AGENTS.md` (generic) and `CLAUDE.md` (Claude Code-specific) with step-by-step how-to |
| Version-specific issues | Release notes only | Version-tagged pitfalls with issue links and workaround hints |
| Prompt preview | None | `01_PROMPT_PREVIEW.md` with copy-paste体验剧本 for pre-install evaluation |

## Why This Doramagic Pack Is Different

- Risk-first angle: this pack starts with pitfalls, boundaries, and verification.
- Eval-backed checks: the repo includes smoke, boundary, and failure checks with upstream-specific commands.
- Host portability: it provides AGENTS.md and CLAUDE.md for different agent hosts.
- Failure recovery: it includes a pitfall log with actionable recovery steps and stop conditions.
- Source-backed packaging: SOURCE_MAP.md records Doramagic and upstream sources so users can inspect what was used.

## What This Pack Deliberately Does Not Do

- Not an official mirror.
- Not a generic starter.
- Not an awesome list.
- Not an SEO backlink repo.
- Not a substitute for the upstream documentation — it supplements it with agent-host-specific instructions and failure recovery.
