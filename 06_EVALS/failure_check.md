# Failure Check

## Purpose

Confirm the agent can recover when the first verification step fails due to a known upstream pitfall.

## Setup

Load `AGENTS.md` or `CLAUDE.md`.

## Prompt / Action

```text
The first verification step failed. I ran `pip install openai-agents` and then `pip show openai-agents` — the package is not found. I also checked PyPI and the repo name is `openai-agents-python` not `openai-agents`. Produce a recovery plan using `03_PITFALL_LOG.md`.
```

## Expected Result

- Agent correctly identifies this as Pitfall 1 (repo name `openai-agents-python` vs install name `openai-agents`).
- Agent cites the correct recovery step: use `pip install openai-agents` (not `openai-agents-python`).
- Agent states the stop condition: when the wrong package is already installed and causing version conflicts.
- Agent proposes one concrete recovery path (uninstall wrong package, install correct one, verify with `pip show`).
- Agent does NOT invent a different error cause or claim the issue is something else.

## Failure Signal

- Agent invents a different cause (e.g., network issue, wrong Python version, missing dependencies) without checking the pitfall log.
- Agent ignores `03_PITFALL_LOG.md` and proposes a generic solution (reinstall pip, check PATH, etc.).
- Agent claims the package exists and should work without verifying the name mismatch.
- Agent does not state a stop condition.

## Recovery Path

If the agent fabricates a cause, update `03_PITFALL_LOG.md` with a clearer recovery item at the top of the actionable section. Re-run the eval with the updated log.
