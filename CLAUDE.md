# CLAUDE.md

This file provides runtime instructions for Claude Code when it is the target host for this pack.

## Loading This Pack

Claude Code reads `.claude.md` and `CLAUDE.md` files in the current working directory. Copy this file (or the relevant sections) into your project root as `CLAUDE.md` before starting a session that will work with `openai/openai-agents-python`.

Alternatively, paste the contents of `AGENTS.md` as the first message in your session.

## Before You Start

Run the following to confirm the upstream package is accessible:

```
pip show openai-agents
```

If the package is not found, stop. Consult `03_PITFALL_LOG.md` Pitfall 1 first.

Confirm your `OPENAI_API_KEY` environment variable is set before attempting any live agent runs.

## Runtime Rules

1. **Tool use must be explicit.** Before calling any tool — `Bash`, `Read`, `Write`, `WebFetch`, or browser — state what you are doing and why.
2. **Ask before risky actions.** Do not run `pip install` (except to verify), make network calls, access credentials, or modify the filesystem without explicit user approval.
3. **Verify before claiming.** Do not say "the agent works" or "the tool is installed" until `06_EVALS/smoke_check.md` passes conceptually.
4. **Use the pitfall log.** When something fails, open `03_PITFALL_LOG.md` and find the matching symptom before proposing a fix.
5. **Respect the boundary card.** Before using browser automation, external HTTP calls, or reading sensitive files, re-read `04_BOUNDARY_RISK_CARD.md`.
6. **No fabricated facts.** If you encounter a GitHub issue number or version claim, verify it against the links in `SOURCE_MAP.md`. Do not assert a bug is fixed unless you can cite the commit or PR.
7. **Record failures.** If an eval fails, write the failure into `TEST_LOG.md` with the expected result, actual result, and suspected cause.

## How To Use This Pack in a Session

```
1. Read 00_QUICK_START.md to confirm the install command.
2. Run the smoke_check eval conceptually (do not execute code unless approved).
3. If the user asks you to build a workflow, propose a minimal first step that does not call the OpenAI API.
4. If the user asks you to fix a failure, open 03_PITFALL_LOG.md first.
5. If the user asks you to verify the setup, use 06_EVALS/smoke_check.md as the checklist.
```

## Stop Conditions

Stop and ask for clarification when:

- The user asks you to install the package and you have not verified `pip show openai-agents` works.
- The user asks you to run an agent loop without confirming the API key is available.
- The user asks you to take an action that touches production credentials, external systems, or the filesystem beyond the current project directory.
- You cannot find a matching pitfall in `03_PITFALL_LOG.md` and the failure is not self-explanatory.

## Source Attribution

This is an independent Doramagic pack. See `SOURCE_MAP.md` for evidence links. The upstream project is `openai/openai-agents-python` (MIT license).
