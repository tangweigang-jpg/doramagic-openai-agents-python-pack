# Openai Agents Python AI Context Pack for Claude Code, Codex, Cursor, and Aider

Pack version: `v1.0.0` · Last updated: `2026-05-14`

[![Pack v1.0.0](https://img.shields.io/badge/pack-v1.0.0-blue)](./CHANGELOG.md)
[![License](https://img.shields.io/github/license/tangweigang-jpg/doramagic-openai-agents-python-pack)](./LICENSE)
[![Issues](https://img.shields.io/github/issues/tangweigang-jpg/doramagic-openai-agents-python-pack)](https://github.com/tangweigang-jpg/doramagic-openai-agents-python-pack/issues)

Languages: English | [中文](./README.zh-CN.md)

## The Problem

You want to use OpenAI's Agents SDK in your project. But the first time you try:

- `pip install openai-agents` — but the repo is named `openai-agents-python`, not `openai-agents`. You spend 20 minutes finding the right package.
- The quickstart tells you to "create an agent" without explaining what happens when two agents hand off a task and the context gets lost.
- The first time your agent calls a tool and the tool name clashes with a built-in, there is no recovery path — just a stack trace and a GitHub issue.
- You run the examples in the repo and they work fine. Then you add your own workflow and hit silent failures that only show up in production.

This pack exists because the upstream docs are good for happy-path demos, but they do not package the failure modes, boundary checks, or recovery steps that you need when things break.

## Copy / Run / Verify

1. Copy `AGENTS.md` or `CLAUDE.md` into your AI coding host.
2. Run the first prompt in `01_PROMPT_PREVIEW.md`.
3. Verify behavior with `06_EVALS/smoke_check.md`, then recover with `03_PITFALL_LOG.md` if it fails.

Quick links:
[Start](./AGENTS.md) · [Prompt](./01_PROMPT_PREVIEW.md) · [Evals](./06_EVALS/) · [Pitfalls](./03_PITFALL_LOG.md) · [Manual](./05_HUMAN_MANUAL.md)

## AGENTS.md for Claude Code and AI Coding Agents

Use `AGENTS.md` for agent hosts that support repository instructions. Use `CLAUDE.md` when Claude Code is the target host.

## openai/openai-agents-python Pitfalls and Recovery

Start with `03_PITFALL_LOG.md` when setup, permissions, runtime behavior, or verification fails.

## What This Pack Adds

This is an independent AI context resource pack for openai/openai-agents-python.: host instructions, prompt preview, evals, pitfalls, and recovery rules you can load into Claude Code, Codex, Cursor, Aider, and other AI coding agents.

- A loadable `AGENTS.md` / `CLAUDE.md` with specific tool boundaries, handoff checks, and stop conditions.
- Eval prompts that verify the agent can reason about your workflow before it claims success.
- A pitfall log with actual GitHub issues, version-specific risks, and step-by-step recovery.
- A boundary risk card that tells the agent when to stop instead of guessing.

> This is an independent capability pack. It is not affiliated with or endorsed by openai/openai-agents-python unless explicitly stated.

## When This Helps

Use this pack when you want an AI coding agent to understand the upstream project context, setup boundaries, common pitfalls, and verification steps before it edits files, installs dependencies, or claims the tool is ready.


## What You Get

- Host instructions for AI coding agents.
- A copyable prompt preview.
- Acceptance checks.
- Pitfall log and recovery steps.
- Boundary and risk card.
- Human reference manual (`05_HUMAN_MANUAL.md`) — architecture, components, and failure taxonomy.
- Source attribution and upstream links.

If this pack helps your agent work from evidence instead of guesses, star the repo so future updates are easier to find. Open an issue for bugs, usage questions, or new pitfall reports.

## Source Attribution

This project pack was assembled by [Doramagic](https://doramagic.ai/projects/openai-agents-python/) to make openai/openai-agents-python usable as a portable AI capability asset.

- Upstream/source: https://github.com/openai/openai-agents-python
- License: MIT
- Pack contents: prompts, host instructions, checks, guardrails, and validation notes
- Relationship: independent pack; not affiliated with or endorsed by openai/openai-agents-python unless explicitly stated

If you maintain the upstream project and want attribution changed or removed, open an issue in this repository.
