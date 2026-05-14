# Smoke Check

## Purpose

Confirm the agent can understand the pack and produce the first safe next step for a developer who wants to build a multi-agent OpenAI workflow.

## Setup

Load `AGENTS.md` or `CLAUDE.md`.

## Prompt / Action

```text
A developer says: "I want to build a workflow with OpenAI's Agents SDK. I ran `pip install openai-agents` but I am not sure if it worked, and I want to create two agents that hand off tasks to each other. Using this pack, what is the first safe thing I should verify before writing any code?"
Do not call external tools. Do not claim the package is installed. State what you would check first.
```

## Expected Result

- Agent restates the developer's goal in its own words.
- Agent identifies that the first step is to verify `pip show openai-agents` (or equivalent) rather than running any agent code.
- Agent names the relevant pitfall from `03_PITFALL_LOG.md` (the repo-name vs install-name mismatch — Pitfall 1).
- Agent proposes a specific verification step that does not call the OpenAI API.
- Agent does not claim success or say the workflow is working.

## Failure Signal

- Agent says the package is installed or working without citing `pip show openai-agents` output.
- Agent proposes writing agent code before verifying the install command.
- Agent invents a version number or API capability without checking `SOURCE_MAP.md`.
- Agent skips the pitfall log and proceeds directly to code generation.

## Recovery Path

Stop. Re-read `03_PITFALL_LOG.md` Pitfall 1 (repo name vs install name). Re-run the prompt with explicit boundaries: "verify before code."
