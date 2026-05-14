# AGENTS.md

## Goal

Use this pack to help an AI coding agent work with `openai/openai-agents-python` safely and verifiably.

## When To Load

Load this pack when any of the following is true:

- A developer says "I want to build a multi-agent workflow with OpenAI's Agents SDK" and you need to set up tool boundaries before writing any code.
- A developer ran `pip install openai-agents` but is confused because the repo name does not match the install package name.
- A developer reports that agent handoffs lose context, tools return unexpected results, or the workflow hangs after the first step.
- You need to verify that `openai-agents` is installed correctly, the API key is accessible, and the basic agent loop works — before claiming the workflow is production-ready.
- A developer wants to add tracing, guardrails, or per-run budget limits and needs to know which version of the SDK supports which feature.
- A developer encounters a specific GitHub issue (e.g., AdvancedSQLiteSession.delete_branch leaves orphaned messages, retry delays ignoring max_delay) and needs a version-checked workaround.

Do NOT load this pack when the developer is just asking for a general Python tutorial or a non-agentic OpenAI API usage question.

## How To Use

Step-by-step:

1. **Read `00_QUICK_START.md`** to confirm the official install command (`pip install openai-agents`).
2. **Verify the host environment**: check Python version (3.9+ required), check pip install succeeds, check `OPENAI_API_KEY` is set or that the host can access it.
3. **Check `03_PITFALL_LOG.md`** before doing anything involving tool calls, handoffs, or multi-agent flows. The top 3 pitfalls are immediately actionable at the top of that file.
4. **Check `04_BOUNDARY_RISK_CARD.md`** before making any network calls, browser actions, or filesystem writes.
5. **Run `06_EVALS/smoke_check.md`** to confirm the agent can restate the task, identify boundaries, and propose a verification step — without claiming the tool is installed.
6. If the smoke check passes, propose a minimal first step (e.g., verify imports only, no live API calls).
7. If the smoke check fails, consult the Recovery Table below.

## Recovery Table

| Failure signal | Likely pitfall | Recovery step | When to stop |
|---|---|---|---|
| Package not found after `pip install openai-agents` | Repo name vs install name mismatch (Pitfall 1) | Confirm package name is `openai-agents` not `openai-agents-python`; verify with `pip show openai-agents` | Stop when pip shows no such package and PyPI search also returns nothing |
| Agent loses context after handoff | `AdvancedSQLiteSession.delete_branch()` leaves orphaned messages (Pitfall 2) | Check GitHub issue #3346; avoid multi-branch sessions in the current version or implement explicit context transfer | Stop when handoff behavior is required for the use case and no workaround is available |
| Retry delays exceed max_delay | `retry-after` ignoring `max_delay` (Pitfall 3) | Check GitHub issue #3266; set explicit `max_delay` in client config; cap retry durations manually | Stop when retry behavior is safety-critical and the cap is not enforceable |
| Conversations API rejects reasoning item | `OpenAIConversationsSession` persists empty reasoning (Pitfall 4) | Check GitHub issue #3268; filter out empty `{"type":"reasoning","summary":[]}` items before sending | Stop when the Conversations API is the primary interface |
| Tracer shutdown blocks forever | `Tracing shutdown cannot interrupt exporter backoff` (Pitfall 5) | Check GitHub issue #3354; run tracing in a subprocess or set a timeout | Stop when tracing is required for compliance |
| Agent claims success without running any verification | Smoke check failure | Run `06_EVALS/smoke_check.md` explicitly and report what the agent missed | Stop when the agent fabricates facts |
| Agent asks for secrets without user approval | Boundary violation | Halt. Do not provide credentials. Report the boundary that was violated | Stop immediately |
| Agent proceeds with browser/network without asking | Boundary violation | Halt. Re-read `04_BOUNDARY_RISK_CARD.md` and re-state permissions | Stop immediately |

## Inputs Expected From User

- Target host or coding environment.
- Task goal (what the first agent workflow should accomplish).
- Safety boundary (which tools, network, filesystem, or credential actions are approved).
- Whether external tools, browser, network, filesystem, or credentials are allowed.

## Allowed Actions

- Read files in this pack.
- Ask clarifying questions.
- Produce a plan.
- Run only user-approved verification commands.
- Record failures in the pitfall log format.

## Disallowed Actions

- Do not claim official endorsement.
- Do not access secrets by default.
- Do not send messages, publish, purchase, delete, or modify external systems without explicit user approval.
- Do not claim the upstream tool works until an acceptance check passes.

## Verification Steps

1. Read `00_QUICK_START.md`.
2. Run at least one eval in `06_EVALS/`.
3. Check `03_PITFALL_LOG.md` before escalating.
4. Check `04_BOUNDARY_RISK_CARD.md` before using external tools.

## Failure Recovery

If verification fails, stop and report:

- Which eval failed.
- Expected result.
- Actual result.
- Suspected cause.
- Recovery step from `03_PITFALL_LOG.md`.

## Source / Risk Reminder

This is an independent Doramagic pack. Use `SOURCE_MAP.md` for evidence and source links.
