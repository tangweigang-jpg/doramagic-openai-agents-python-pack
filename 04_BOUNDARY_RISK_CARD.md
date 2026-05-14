# Boundary & Risk Card

## Permissions

- Browser:
- Network:
- Filesystem:
- Credentials:
- External services:

## Hard Boundaries

- Do not use secrets without explicit user approval.
- Do not claim production safety without passing evals.
- Do not imply upstream endorsement.

## Known Risks

- External tool or browser access may expose sensitive state if used without boundaries.
- Host compatibility and installed version must be verified before real use.

## Stop Conditions

- Unknown license.
- Failed dogfooding.
- Missing source attribution.
- Tool permission unclear.

## Doramagic Source Extract

# Boundary & Risk Card / 安装前决策卡

项目：openai/openai-agents-python

## Doramagic 试用结论

当前结论：可以进入发布前推荐检查；首次使用仍应从最小权限、临时目录和可回滚配置开始。

## 用户现在可以做

- 可以先阅读 Human Manual，理解项目目的和主要工作流。
- 可以复制 Prompt Preview 做安装前体验；这只验证交互感，不代表真实运行。
- 可以把官方 Quick Start 命令放到隔离环境中验证，不要直接进主力环境。

## 现在不要做

- 不要把 Prompt Preview 当成项目实际运行结果。
- 不要把 metadata-only validation 当成沙箱安装验证。
- 不要把未验证能力写成“已支持、已跑通、可放心安装”。
- 不要在首次试用时交出生产数据、私人文件、真实密钥或主力配置目录。

## 安装前检查

- 宿主 AI 是否匹配：chatgpt
- 官方安装入口状态：已发现官方入口
- 是否在临时目录、临时宿主或容器中验证：必须是
- 是否能回滚配置改动：必须能
- 是否需要 API Key、网络访问、读写文件或修改宿主配置：未确认前按高风险处理
- 是否记录了安装命令、实际输出和失败日志：必须记录

## 当前阻塞项

- 无阻塞项。

## 项目专属踩坑

- 仓库名和安装名不一致（medium）：用户照着仓库名搜索包或照着包名找仓库时容易走错入口。 建议检查：在 npm/PyPI/GitHub 上确认包名映射和官方 README 说明。
- 来源证据：AdvancedSQLiteSession.delete_branch() leaves branch-only messages in the base table（medium）：可能增加新用户试用和生产接入成本。 建议检查：来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- 来源证据：Clarify whether retry-after delays should respect retry max_delay（medium）：可能增加新用户试用和生产接入成本。 建议检查：来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- 来源证据：OpenAIConversationsSession persists empty reasoning item {"type":"reasoning","summary":[]} and Conversations API reject…（medium）：可能增加新用户试用和生产接入成本。 建议检查：来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- 来源证据：Tracing shutdown cannot interrupt exporter retry backoff（medium）：可能阻塞安装或首次运行。 建议检查：来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。

## 风险与权限提示

- no_demo: medium

## 证据缺口

- 暂未发现结构化证据缺口。

