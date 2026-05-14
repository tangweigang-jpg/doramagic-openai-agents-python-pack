# Pitfall Log

## Top 3 Actionable Pitfalls

### P1: Repo name does not match install package name

- Symptom: `pip install openai-agents` succeeds but the repo is named `openai-agents-python`. Searching for the package by repo name fails.
- Likely cause: Identity trap — the PyPI package name (`openai-agents`) differs from the GitHub repo name (`openai-agents-python`).
- How to verify: Run `pip show openai-agents` and confirm the installed package is `openai-agents` from `github.com/openai/openai-agents-python`. Cross-check the official README.
- Recovery step: Stop. Use `pip install openai-agents` (not `openai-agents-python`). If the wrong package is already installed, `pip uninstall openai-agents-python` first, then install the correct one.
- When to stop: Stop when the package name mismatch causes a permissions issue, a fork to be used instead of the official package, or the wrong version to be installed.
- Source: https://github.com/openai/openai-agents-python | repo=openai-agents-python; install=openai-agents

### P2: AdvancedSQLiteSession.delete_branch() leaves branch-only messages in the base table

- Symptom: After calling `delete_branch()`, orphaned messages remain. Multi-agent context appears to bleed between branches.
- Likely cause: Bug in session cleanup — branch-scoped messages are not removed when the branch is deleted.
- How to verify: Run a multi-branch agent workflow, call `delete_branch()`, then query the session store for remaining messages. Compare with the expected state.
- Recovery step: Stop and check GitHub issue #3346. Do not rely on `delete_branch()` for clean context isolation in the current version. Implement explicit message deletion or use a fresh session per branch.
- When to stop: Stop when branch isolation is a hard requirement and the workaround is not acceptable for the use case.
- Source: https://github.com/openai/openai-agents-python/issues/3346

### P3: retry-after delays do not respect max_delay

- Symptom: Retries fire with delays longer than the configured `max_delay`. Rate limit backoff exceeds expected bounds.
- Likely cause: `retry-after` header processing does not cap delays at the configured `max_delay`.
- How to verify: Set `max_delay=10` in client config, trigger a 429, and measure actual delay before the next retry.
- Recovery step: Stop and check GitHub issue #3266. Manually cap delay values in your retry handler. Set `max_delay` explicitly in your client config and validate on the first retry.
- When to stop: Stop when retry behavior is safety or cost-critical and the delay cap cannot be enforced in the current version.
- Source: https://github.com/openai/openai-agents-python/issues/3266

---

## Remaining Pitfalls

### P4: OpenAIConversationsSession persists empty reasoning item

- Symptom: `{"type":"reasoning","summary":[]}` is persisted to the session store and the Conversations API rejects it as invalid.
- Severity: medium
- Evidence: https://github.com/openai/openai-agents-python/issues/3268
- Recovery: Filter out empty reasoning items before sending to the Conversations API. Check issue for version status.

### P5: Tracing shutdown cannot interrupt exporter retry backoff

- Symptom: Tracing shutdown hangs because the exporter retry backoff cannot be interrupted.
- Severity: medium
- Evidence: https://github.com/openai/openai-agents-python/issues/3354
- Recovery: Run tracing in a subprocess with a timeout, or set `tracing_export_timeout` to cap backoff.

### P6–P9: Version-specific regressions (v0.14.8–v0.17.1)

- Pitfalls: v0.14.8, v0.15.0, v0.15.1, v0.15.2, v0.15.3, v0.16.0, v0.16.1, v0.17.0, v0.17.1 each carry specific issues.
- Recovery: Pin to a known-good version. For new projects, start with the latest stable (v0.17.1 as of 2026-05-14) but verify against the release notes.
- Evidence: https://github.com/openai/openai-agents-python/releases/tag/vX.X.X

### P10: Capability assumptions are not verified

- Symptom: Documentation claims a capability works in a certain way but the behavior differs at runtime.
- Recovery: Treat all README capabilities as unverified until you run a smoke check. Do not write "verified" or "confirmed" in any output without test evidence.

### P11: Chat Completions converter sends empty tool output for non-text results

- Severity: medium
- Evidence: https://github.com/openai/openai-agents-python/issues/3310
- Recovery: Check issue for version status. Avoid passing non-text results through the converter without wrapping.

### P12: AdvancedSQLiteSession.add_items reports success after metadata failure

- Severity: medium
- Evidence: https://github.com/openai/openai-agents-python/issues/3348
- Recovery: Implement post-write validation for session store writes.

### P13: BudgetGuard proposal (per-run token/request/cost limits)

- Severity: medium
- Evidence: https://github.com/openai/openai-agents-python/issues/3353
- Recovery: This is a proposal; track the issue. Implement manual cost tracking as a workaround.

### P14: Maintenance activity is not observable

- Severity: low
- Recovery: Monitor the repo for recent commits and PR response times. Do not assume active maintenance.

### P15: Issue/PR response quality is unknown

- Severity: low
- Recovery: Check recent closed issues for response times before relying on community support.

## Doramagic Source Extract

项目：openai/openai-agents-python

摘要：发现 24 个潜在踩坑项，其中 0 个为 high/blocking；最高优先级：身份坑 - 仓库名和安装名不一致。

## 1. 身份坑 · 仓库名和安装名不一致

- 严重度：medium
- 证据强度：runtime_trace
- 发现：仓库名 `openai-agents-python` 与安装入口 `openai-agents` 不完全一致。
- 对用户的影响：用户照着仓库名搜索包或照着包名找仓库时容易走错入口。
- 建议检查：在 npm/PyPI/GitHub 上确认包名映射和官方 README 说明。
- 复现命令：`pip install openai-agents`
- 防护动作：页面必须同时展示 repo 名和真实安装入口，避免用户搜索错包。
- 证据：identity.distribution | github_repo:946380199 | https://github.com/openai/openai-agents-python | repo=openai-agents-python; install=openai-agents

## 2. 配置坑 · AdvancedSQLiteSession.delete_branch()

- 严重度：medium
- 证据强度：source_linked
- 发现：GitHub 社区证据显示该项目存在一个配置相关的待验证问题：AdvancedSQLiteSession.delete_branch() leaves branch-only messages in the base table
- 对用户的影响：可能增加新用户试用和生产接入成本。
- 建议检查：来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- 防护动作：不得脱离来源链接放大为确定性结论；需要标注适用版本和复核状态。
- 证据：community_evidence:github | cevd_d867c75f80af49c9968398851ff8bf6a | https://github.com/openai/openai-agents-python/issues/3346

## 3. 配置坑 · retry-after delays

- 严重度：medium
- 证据强度：source_linked
- 发现：Clarify whether retry-after delays should respect retry max_delay
- 对用户的影响：可能增加新用户试用和生产接入成本。
- 建议检查：来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- 防护动作：不得脱离来源链接放大为确定性结论；需要标注适用版本和复核状态。
- 证据：community_evidence:github | cevd_f486d2247bf24df8bbc7a2bd6fddbd65 | https://github.com/openai/openai-agents-python/issues/3266

## 4. 配置坑 · OpenAIConversationsSession empty reasoning

- 严重度：medium
- 证据强度：source_linked
- 发现：OpenAIConversationsSession persists empty reasoning item {"type":"reasoning","summary":[]} and Conversations API rejects it as invalid
- 对用户的影响：可能增加新用户试用和生产接入成本。
- 建议检查：来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- 防护动作：不得脱离来源链接放大为确定性结论；需要标注适用版本和复核状态。
- 证据：community_evidence:github | cevd_d6bad5c23bf3457eb546c22a1636cc26 | https://github.com/openai/openai-agents-python/issues/3268

## 5. 配置坑 · Tracing shutdown

- 严重度：medium
- 证据强度：source_linked
- 发现：Tracing shutdown cannot interrupt exporter retry backoff
- 对用户的影响：可能阻塞安装或首次运行。
- 建议检查：来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- 防护动作：不得脱离来源链接放大为确定性结论；需要标注适用版本和复核状态。
- 证据：community_evidence:github | cevd_e1ceae098cf84c8aafae7082b13c5345 | https://github.com/openai/openai-agents-python/issues/3354

## 6–22. 版本及维护坑 (v0.14.8–v0.17.1, issues, maintainer signals)

- 严重度：medium / low
- 证据强度：source_linked
- 建议检查：各 release notes 和 issue 页面复核。
- 防护动作：版本相关发现不得脱离来源链接放大为确定性结论；需要标注适用版本和复核状态。
