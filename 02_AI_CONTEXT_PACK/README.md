# AI Context Pack

## Pack Identity

- Upstream: https://github.com/openai/openai-agents-python
- Pack type: Durable Agent Workflow Pack
- Doramagic canonical: https://doramagic.ai/projects/openai-agents-python/
- Relationship: independent pack; not affiliated or endorsed unless explicitly stated.

## Operating Rules

- Evidence first.
- No official endorsement claim.
- Run evals before claiming success.
- Use pitfall and risk files for recovery.

## Host Files

- `../AGENTS.md`
- `../CLAUDE.md`

## Doramagic Source Extract

# openai-agents-python - Doramagic AI Context Pack

> 定位：安装前体验与判断资产。它帮助宿主 AI 有一个好的开始，但不代表已经安装、执行或验证目标项目。

## 充分原则

- **充分原则，不是压缩原则**：AI Context Pack 应该充分到让宿主 AI 在开工前理解项目价值、能力边界、使用入口、风险和证据来源；它可以分层组织，但不以最短摘要为目标。
- **压缩策略**：只压缩噪声和重复内容，不压缩会影响判断和开工质量的上下文。

## 给宿主 AI 的使用方式

你正在读取 Doramagic 为 openai-agents-python 编译的 AI Context Pack。请把它当作开工前上下文：帮助用户理解适合谁、能做什么、如何开始、哪些必须安装后验证、风险在哪里。不要声称你已经安装、运行或执行了目标项目。

## Claim 消费规则

- **事实来源**：Repo Evidence + Claim/Evidence Graph；Human Wiki 只提供显著性、术语和叙事结构。
- **事实最低状态**：`supported`
- `supported`：可以作为项目事实使用，但回答中必须引用 claim_id 和证据路径。
- `weak`：只能作为低置信度线索，必须要求用户继续核实。
- `inferred`：只能用于风险提示或待确认问题，不能包装成项目事实。
- `unverified`：不得作为事实使用，应明确说证据不足。
- `contradicted`：必须展示冲突来源，不得替用户强行选择一个版本。

## 它最适合谁

- **希望把专业流程带进宿主 AI 的用户**：仓库包含 Skill 文档。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等 Claim：`clm_0003` supported 0.86

## 它能做什么

- **AI Skill / Agent 指令资产库**（可做安装前预览）：项目包含可被宿主 AI 读取的 Skill 或 Agent 指令文件，可用于把专业流程带入 Claude、Codex、Cursor 等宿主。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等 Claim：`clm_0001` supported 0.86
- **命令行启动或安装流程**（需要安装后验证）：项目文档中存在可执行命令，真实使用需要在本地或宿主环境中运行这些命令。 证据：`README.md`, `docs/ja/quickstart.md`, `docs/ja/voice/quickstart.md` Claim：`clm_0002` supported 0.86

## 怎么开始

- `pip install openai-agents` 证据：`README.md` Claim：`clm_0004` supported 0.86, `clm_0005` unverified 0.25, `clm_0006` unverified 0.25
- `pip install 'openai-agents[voice]'` 证据：`docs/ja/voice/quickstart.md` Claim：`clm_0005` unverified 0.25
- `pip install openai-agents # or` 证据：`docs/ja/quickstart.md` Claim：`clm_0006` unverified 0.25

## 继续前判断卡

- **当前建议**：先做权限沙盒试用
- **为什么**：项目存在安装命令、宿主配置或本地写入线索，不建议直接进入主力环境，应先在隔离环境试装。

### 30 秒判断

- **现在怎么做**：先做权限沙盒试用
- **最小安全下一步**：先跑 Prompt Preview；若仍要安装，只在隔离环境试装
- **先别相信**：工具权限边界不能在安装前相信。
- **继续会触碰**：命令执行、宿主 AI 配置、本地环境或项目文件

### 现在可以相信

- **适合人群线索：希望把专业流程带进宿主 AI 的用户**（supported）：有 supported claim 或项目证据支撑，但仍不等于真实安装效果。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等 Claim：`clm_0003` supported 0.86
- **能力存在：AI Skill / Agent 指令资产库**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等 Claim：`clm_0001` supported 0.86
- **能力存在：命令行启动或安装流程**（supported）：可以相信项目包含这类能力线索；是否适合你的具体任务仍要试用或安装后验证。 证据：`README.md`, `docs/ja/quickstart.md`, `docs/ja/voice/quickstart.md` Claim：`clm_0002` supported 0.86
- **存在 Quick Start / 安装命令线索**（supported）：可以相信项目文档出现过启动或安装入口；不要因此直接在主力环境运行。 证据：`README.md` Claim：`clm_0004` supported 0.86, `clm_0005` unverified 0.25, `clm_0006` unverified 0.25

### 现在还不能相信

- **工具权限边界不能在安装前相信。**（unverified）：MCP/tool 类项目通常会触碰文件、网络、浏览器或外部 API，必须真实检查权限和日志。
- **真实输出质量不能在安装前相信。**（unverified）：Prompt Preview 只能展示引导方式，不能证明真实项目中的结果质量。
- **宿主 AI 版本兼容性不能在安装前相信。**（unverified）：Claude、Cursor、Codex、Gemini 等宿主加载规则和版本差异必须在真实环境验证。
- **不会污染现有宿主 AI 行为，不能直接相信。**（inferred）：Skill、plugin、AGENTS/CLAUDE/GEMINI 指令可能改变宿主 AI 的默认行为。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等
- **可安全回滚不能默认相信。**（unverified）：除非项目明确提供卸载和恢复说明，否则必须先在隔离环境验证。
- **真实安装后是否与用户当前宿主 AI 版本兼容？**（unverified）：兼容性只能通过实际宿主环境验证。
- **项目输出质量是否满足用户具体任务？**（unverified）：安装前预览只能展示流程和边界，不能替代真实评测。
- **安装命令是否需要网络、权限或全局写入？**（unverified）：这影响企业环境和个人环境的安装风险。 证据：`README.md`

### 继续会触碰什么

- **命令执行**：包管理器、网络下载、本地插件目录、项目配置或用户主目录。 原因：运行第一条命令就可能产生环境改动；必须先判断是否值得跑。 证据：`README.md`, `docs/ja/quickstart.md`, `docs/ja/voice/quickstart.md`
- **宿主 AI 配置**：Claude/Codex/Cursor/Gemini/OpenCode 等宿主的 plugin、Skill 或规则加载配置。 原因：宿主配置会改变 AI 后续工作方式，可能和用户已有规则冲突。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等
- **本地环境或项目文件**：安装结果、插件缓存、项目配置或本地依赖目录。 原因：安装前无法证明写入范围和回滚方式，需要隔离验证。 证据：`README.md`, `docs/ja/quickstart.md`, `docs/ja/voice/quickstart.md`
- **宿主 AI 上下文**：AI Context Pack、Prompt Preview、Skill 路由、风险规则和项目事实。 原因：导入上下文会影响宿主 AI 后续判断，必须避免把未验证项包装成事实。

### 最小安全下一步

- **先跑 Prompt Preview**：用安装前交互式试用判断工作方式是否匹配，不需要授权或改环境。（适用：任何项目都适用，尤其是输出质量未知时。）
- **只在隔离目录或测试账号试装**：避免安装命令污染主力宿主 AI、真实项目或用户主目录。（适用：存在命令执行、插件配置或本地写入线索时。）
- **先备份宿主 AI 配置**：Skill、plugin、规则文件可能改变 Claude/Cursor/Codex 的默认行为。（适用：存在插件 manifest、Skill 或宿主规则入口时。）
- **安装后只验证一个最小任务**：先验证加载、兼容、输出质量和回滚，再决定是否深用。（适用：准备从试用进入真实工作流时。）

### 退出方式

- **保留安装前状态**：记录原始宿主配置和项目状态，后续才能判断是否可恢复。
- **准备移除宿主 plugin / Skill / 规则入口**：如果试装后行为异常，可以把宿主 AI 恢复到试装前状态。
- **记录安装命令和写入路径**：没有明确卸载说明时，至少要知道哪些目录或配置需要手动清理。
- **如果没有回滚路径，不进入主力环境**：不可回滚是继续前阻断项，不应靠信任或运气继续。

## 哪些只能预览

- 解释项目适合谁和能做什么
- 基于项目文档演示典型对话流程
- 帮助用户判断是否值得安装或继续研究

## 哪些必须安装后验证

- 真实安装 Skill、插件或 CLI
- 执行脚本、修改本地文件或访问外部服务
- 验证真实输出质量、性能和兼容性

## 边界与风险判断卡

- **把安装前预览误认为真实运行**：用户可能高估项目已经完成的配置、权限和兼容性验证。 处理方式：明确区分 prompt_preview_can_do 与 runtime_required。 Claim：`clm_0007` inferred 0.45
- **命令执行会修改本地环境**：安装命令可能写入用户主目录、宿主插件目录或项目配置。 处理方式：先在隔离环境或测试账号中运行。 证据：`README.md`, `docs/ja/quickstart.md`, `docs/ja/voice/quickstart.md` Claim：`clm_0008` supported 0.86
- **待确认**：真实安装后是否与用户当前宿主 AI 版本兼容？。原因：兼容性只能通过实际宿主环境验证。
- **待确认**：项目输出质量是否满足用户具体任务？。原因：安装前预览只能展示流程和边界，不能替代真实评测。
- **待确认**：安装命令是否需要网络、权限或全局写入？。原因：这影响企业环境和个人环境的安装风险。

## 开工前工作上下文

### 加载顺序

- 先读取 how_to_use.host_ai_instruction，建立安装前判断资产的边界。
- 读取 claim_graph_summary，确认事实来自 Claim/Evidence Graph，而不是 Human Wiki 叙事。
- 再读取 intended_users、capabilities 和 quick_start_candidates，判断用户是否匹配。
- 需要执行具体任务时，优先查 role_skill_index，再查 evidence_index。
- 遇到真实安装、文件修改、网络访问、性能或兼容性问题时，转入 risk_card 和 boundaries.runtime_required。

### 任务路由

- **AI Skill / Agent 指令资产库**：先基于 role_skill_index / evidence_index 帮用户挑选可用角色、Skill 或工作流。 边界：可做安装前 Prompt 体验。 证据：`.agents/skills/code-change-verification/SKILL.md`, `.agents/skills/docs-sync/SKILL.md`, `.agents/skills/examples-auto-run/SKILL.md`, `.agents/skills/final-release-review/SKILL.md` 等 Claim：`clm_0001` supported 0.86
- **命令行启动或安装流程**：先说明这是安装后验证能力，再给出安装前检查清单。 边界：必须真实安装或运行后验证。 证据：`README.md`, `docs/ja/quickstart.md`, `docs/ja/voice/quickstart.md` Claim：`clm_0002` supported 0.86

### 上下文规模

- 文件总数：1306
- 重要文件覆盖：40/1306
- 证据索引条目：80
- 角色 / Skill 条目：13

### 证据不足时的处理

- **missing_evidence**：说明证据不足，要求用户提供目标文件、README 段落或安装后验证记录；不要补全事实。
- **out_of_scope_request**：说明该任务超出当前 AI Context Pack 证据范围，并建议用户先查看 Human Manual 或真实安装后验证。
- **runtime_request**：给出安装前检查清单和命令来源，但不要替用户执行命令或声称已执行。
- **source_conflict**：同时展示冲突来源，标记为待核实，不要强行选择一个版本。

## Prompt Recipes

### 适配判断

- 目标：判断这个项目是否适合用户当前任务。
- 预期输出：适配结论、关键理由、证据引用、安装前可预览内容、必须安装后验证内容、下一步建议。

```text
请基于 openai-agents-python 的 AI Context Pack，先问我 3 个必要问题，然后判断它是否适合我的任务。回答必须包含：适合谁、能做什么、不能做什么、是否值得安装、证据来自哪里。所有项目事实必须引用 evidence_refs、source_paths 或 claim_id。
```

### 安装前体验

- 目标：让用户在安装前感受核心工作流，同时避免把预览包装成真实能力或营销承诺。
- 预期输出：一段带边界标签的体验剧本、安装后验证清单和谨慎建议；不含真实运行承诺或强营销表述。

```text
请把 openai-agents-python 当作安装前体验资产，而不是已安装工具或真实运行环境。

请严格输出四段：
1. 先问我 3 个必要问题。
2. 给出一段“体验剧本”：用 [安装前可预览]、[必须安装后验证]、[证据不足] 三种标签展示它可能如何引导工作流。
3. 给出安装后验证清单：列出哪些能力只有真实安装、真实宿主加载、真实项目运行后才能确认。
4. 给出谨慎建议：只能说“值得继续研究/试装”“先补充信息后再判断”或“不建议继续”，不得替项目背书。

硬性边界：
- 不要声称已经安装、运行、执行测试、修改文件或产生真实结果。
- 不要写“自动适配”“确保通过”“完美适配”“强烈建议安装”等承诺性表达。
- 如果描述安装后的工作方式，必须使用“如果安装成功且宿主正确加载 Skill，它可能会……”这种条件句。
- 体验剧本只能写成“示例台词/假设流程”：使用“可能会询问/可能会建议/可能会展示”，不要写“已写入、已生成、已通过、正在运行、正在生成”。
- Prompt Preview 不负责给安装命令；如用户准备试装，只能提示先阅读 Quick Start 和 Risk Card，并在隔离环境验证。
- 所有项目事实必须来自 supported claim、evidence_refs 或 source_paths；inferred/unverified 只能作风险或待确认项。

```

### 角色 / Skill 选择

- 目标：从项目里的角色或 Skill 中挑选最匹配的资产。
- 预期输出：候选角色或 Skill 列表，每项包含适用场景、证据路径、风险边界和是否需要安装后验证。

```text
请读取 role_skill_index，根据我的目标任务推荐 3-5 个最相关的角色或 Skill。每个推荐都要说明适用场景、可能输出、风险边界和 evidence_refs。
```

### 风险预检

- 目标：安装或引入前识别环境、权限、规则冲突和质量风险。
- 预期输出：环境、权限、依赖、许可、宿主冲突、质量风险和未知项的检查清单。

```text
请基于 risk_card、boundaries 和 quick_start_candidates，给我一份安装前风险预检清单。不要替我执行命令，只说明我应该检查什么、为什么检查、失败会有什么影响。
```

### 宿主 AI 开工指令

- 目标：把项目上下文转成一次对话开始前的宿主 AI 指令。
- 预期输出：一段边界明确、证据引用明确、适合复制给宿主 AI 的开工前指令。

```text
请基于 openai-agents-python 的 AI Context Pack，生成一段我可以粘贴给宿主 AI 的开工前指令。这段指令必须遵守 not_runtime=true，不能声称项目已经安装、运行或产生真实结果。
```


## 角色 / Skill 索引

- 共索引 13 个角色 / Skill / 项目文档条目。

- **code-change-verification**（skill）：Run the mandatory verification stack when changes affect runtime code, tests, or build/test behavior in the OpenAI Agents Python repository. 激活提示：当用户任务与“code-change-verification”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/code-change-verification/SKILL.md`
- **docs-sync**（skill）：Analyze main branch implementation and configuration to find missing, incorrect, or outdated documentation in docs/. Use when asked to audit doc coverage, sync docs with code, or propose doc updates/structure changes. Only update English docs under docs/ and never touch translated docs under docs/ja, docs/ko, or docs/zh. Provide a report and ask for approval before editing docs. 激活提示：当用户任务与“docs-sync”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/docs-sync/SKILL.md`
- **examples-auto-run**（skill）：Run python examples in auto mode with logging, rerun helpers, and background control. 激活提示：当用户任务与“examples-auto-run”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/examples-auto-run/SKILL.md`
- **final-release-review**（skill）：Perform a release-readiness review by locating the previous release tag from remote tags and auditing the diff e.g., v1.2.3... for breaking changes, regressions, improvement opportunities, and risks before releasing openai-agents-python. 激活提示：当用户任务与“final-release-review”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/final-release-review/SKILL.md`
- **implementation-strategy**（skill）：Decide how to implement runtime and API changes in openai-agents-python before editing code. Use when a task changes exported APIs, runtime behavior, serialized state, tests, or docs and you need to choose the compatibility boundary, whether shims or migrations are warranted, and when unreleased interfaces can be rewritten directly. 激活提示：当用户任务与“implementation-strategy”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/implementation-strategy/SKILL.md`
- **openai-knowledge**（skill）：Use when working with the OpenAI API Responses API or OpenAI platform features tools, streaming, Realtime API, auth, models, rate limits, MCP and you need authoritative, up-to-date documentation schemas, examples, limits, edge cases . Prefer the OpenAI Developer Documentation MCP server tools when available; otherwise guide the user to enable openaiDeveloperDocs . 激活提示：当用户任务与“openai-knowledge”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/openai-knowledge/SKILL.md`
- **pr-draft-summary**（skill）：Create the required PR-ready summary block, branch suggestion, title, and draft description for openai-agents-python. Use in the final handoff after moderate-or-larger changes to runtime code, tests, examples, build/test configuration, or docs with behavior impact; skip only for trivial or conversation-only tasks, repo-meta/doc-only tasks without behavior impact, or when the user explicitly says not to include the P… 激活提示：当用户任务与“pr-draft-summary”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/pr-draft-summary/SKILL.md`
- **runtime-behavior-probe**（skill）：Plan and execute runtime-behavior investigations with temporary probe scripts, validation matrices, state controls, and findings-first reports. Use only when the user explicitly invokes this skill to verify actual runtime behavior beyond normal code-level checks, especially to uncover edge cases, undocumented behavior, or common failure modes in local or live integrations. A baseline smoke check is fine as an entry… 激活提示：当用户任务与“runtime-behavior-probe”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/runtime-behavior-probe/SKILL.md`
- **test-coverage-improver**（skill）：Improve test coverage in the OpenAI Agents Python repository: run make coverage , inspect coverage artifacts, identify low-coverage files, propose high-impact tests, and confirm with the user before writing tests. 激活提示：当用户任务与“test-coverage-improver”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`.agents/skills/test-coverage-improver/SKILL.md`
- **credit-note-fixer**（skill）：Fix the tiny credit-note formatting bug and rerun the exact targeted test command. 激活提示：当用户任务与“credit-note-fixer”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`examples/sandbox/docs/skills/credit-note-fixer/SKILL.md`
- **prior-auth-packet-builder**（skill）：Build a concise prior authorization packet from local case files and payer policy docs. 激活提示：当用户任务与“prior-auth-packet-builder”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`examples/sandbox/healthcare_support/skills/prior-auth-packet-builder/SKILL.md`
- **playwright**（skill）：Use when the task requires capturing or automating a real browser from the terminal. 激活提示：当用户任务与“playwright”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`examples/sandbox/tutorials/vision_website_clone/skills/playwright/SKILL.md`
- **csv-workbench**（skill）：Analyze CSV files in /mnt/data and return concise numeric summaries. 激活提示：当用户任务与“csv-workbench”描述的流程高度相关时，先用它做安装前体验，再决定是否安装。 证据：`examples/tools/skills/csv-workbench/SKILL.md`

## 证据索引

- 共索引 80 条证据。

- **Agents**（documentation）：Agents are the core building block in your apps. An agent is a large language model LLM configured with instructions, tools, and optional runtime behavior such as handoffs, guardrails, and structured outputs. 证据：`docs/agents.md`
- **エージェント**（documentation）：エージェントは、アプリにおける中核的な構成要素です。エージェントは、 instructions、tools、およびハンドオフ、ガードレール、structured outputs などの任意のランタイム動作で設定された大規模言語モデル LLM です。 证据：`docs/ja/agents.md`
- **에이전트**（documentation）：에이전트는 앱의 핵심 구성 요소입니다. 에이전트는 instructions, tools, 그리고 핸드오프, 가드레일, structured outputs 같은 선택적 런타임 동작으로 구성된 대규모 언어 모델 LLM 입니다. 证据：`docs/ko/agents.md`
- **智能体**（documentation）：智能体是应用中的核心构建块。智能体是一个大语言模型（LLM），配置了 instructions、工具，以及可选的运行时行为，例如任务转移、安全防护措施和 structured outputs。 证据：`docs/zh/agents.md`
- **Credit Note Example Repo**（documentation）：This tiny repo exists to support examples/sandbox/docs/coding task.py . 证据：`examples/sandbox/docs/repo/README.md`
- **Credit Note Fixer**（skill_instruction）：1. Read repo/task.md . 2. Inspect repo/credit note.sh and repo/tests/test credit note.sh . 3. Make the smallest correct change that keeps the output label as credit and the amount positive. If you use apply patch , use workspace-root-relative paths such as repo/credit note.sh and repo/tests/test credit note.sh . 4. Run exactly sh tests/test credit note.sh from repo/ . 5. In the final answer, summarize the bug, the fix, and the exact verification command. 证据：`examples/sandbox/docs/skills/credit-note-fixer/SKILL.md`
- **Contributor Guide**（documentation）：This guide helps new contributors get started with the OpenAI Agents Python repository. It covers repo structure, how to test your work, available utilities, and guidelines for commits and PRs. 证据：`AGENTS.md`
- **OpenAI Agents SDK ! PyPI https://img.shields.io/pypi/v/openai-agents?label=pypi%20package https://pypi.org/project/open…**（documentation）：OpenAI Agents SDK ! PyPI https://img.shields.io/pypi/v/openai-agents?label=pypi%20package https://pypi.org/project/openai-agents/ 证据：`README.md`
- **Tests**（documentation）：Before running any tests, make sure you have uv installed and ideally run make sync after . 证据：`tests/README.md`
- **Common agentic patterns**（documentation）：This folder contains examples of different common patterns for agents. 证据：`examples/agent_patterns/README.md`
- **Financial Research Agent Example**（documentation）：This example shows how you might compose a richer financial research agent using the Agents SDK. The pattern is similar to the research bot example, but with more specialized sub‑agents and a verification step. 证据：`examples/financial_research_agent/README.md`
- **MCP Filesystem Example**（documentation）：This example uses the filesystem MCP server https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem , running locally via npx . 证据：`examples/mcp/filesystem_example/README.md`
- **MCP get all mcp tools Example**（documentation）：Python port of the JS examples/mcp/get-all-mcp-tools-example.ts . It demonstrates: 证据：`examples/mcp/get_all_mcp_tools_example/README.md`
- **MCP Git Example**（documentation）：This example uses the git MCP server https://github.com/modelcontextprotocol/servers/tree/main/src/git , running locally via uvx . 证据：`examples/mcp/git_example/README.md`
- **MCP Manager Example FastAPI**（documentation）：This example shows how to use MCPServerManager to keep MCP server lifecycle management in a single task inside a FastAPI app with the Streamable HTTP transport. 证据：`examples/mcp/manager_example/README.md`
- **MCP Prompt Server Example**（documentation）：This example uses a local MCP prompt server in server.py server.py . 证据：`examples/mcp/prompt_server/README.md`
- **MCP SSE Example**（documentation）：This example uses a local SSE server in server.py server.py . 证据：`examples/mcp/sse_example/README.md`
- **MCP SSE Remote Example**（documentation）：Python port of the JS examples/mcp/sse-example.ts . By default it starts the bundled local SSE MCP server and lets the agent use those tools. Set MCP SSE REMOTE URL to try a compatible remote SSE server instead. 证据：`examples/mcp/sse_remote_example/README.md`
- **MCP Streamable HTTP Remote Example**（documentation）：Python port of the JS examples/mcp/streamable-http-example.ts . It connects to DeepWiki over the Streamable HTTP transport https://mcp.deepwiki.com/mcp and lets the agent use those tools. 证据：`examples/mcp/streamable_http_remote_example/README.md`
- **Custom HTTP Client Factory Example**（documentation）：This example demonstrates how to use the new httpx client factory parameter in MCPServerStreamableHttp to configure custom HTTP client behavior for MCP StreamableHTTP connections. 证据：`examples/mcp/streamablehttp_custom_client_example/README.md`
- **MCP Streamable HTTP Example**（documentation）：This example uses a local Streamable HTTP server in server.py server.py . 证据：`examples/mcp/streamablehttp_example/README.md`
- **MCP Tool Filter Example**（documentation）：Python port of the JS examples/mcp/tool-filter-example.ts . It shows how to: 证据：`examples/mcp/tool_filter_example/README.md`
- **Model provider examples**（documentation）：The examples in this directory show how to route models through adapter layers such as LiteLLM and any-llm. The default examples all use OpenRouter so you only need one API key: 证据：`examples/model_providers/README.md`
- **Realtime Demo App**（documentation）：A web-based realtime voice assistant demo with a FastAPI backend and HTML/JS frontend. 证据：`examples/realtime/app/README.md`
- **Realtime Twilio Integration**（documentation）：This example demonstrates how to connect the OpenAI Realtime API to a phone call using Twilio's Media Streams. The server handles incoming phone calls and streams audio between Twilio and the OpenAI Realtime API, enabling real-time voice conversations with an AI agent over the phone. 证据：`examples/realtime/twilio/README.md`
- **Twilio SIP Realtime Example**（documentation）：This example shows how to handle OpenAI Realtime SIP calls with the Agents SDK. Incoming calls are accepted through the Realtime Calls API, a triage agent answers with a fixed greeting, and handoffs route the caller to specialist agents FAQ lookup and record updates similar to the realtime UI demo. 证据：`examples/realtime/twilio_sip/README.md`
- **Research bot**（documentation）：This is a simple example of a multi-agent research bot. To run it: 证据：`examples/research_bot/README.md`
- **Sandbox examples**（documentation）：These examples show how to run agents with an isolated workspace. Start with the small API examples when you want the smallest surface area, or use the tutorial scaffold when you want the shared layout for guided sandbox tutorials. 证据：`examples/sandbox/README.md`
- **Cloud Sandbox Extension Examples**（documentation）：These examples are for manual verification of the cloud sandbox backends that live under agents.extensions.sandbox . 证据：`examples/sandbox/extensions/README.md`
- **NASA Spending Text-to-SQL Agent**（documentation）：Multi-turn conversational agent that translates natural-language questions about NASA federal spending into SQL queries, executes them against a local SQLite database, and returns structured tabular results. 证据：`examples/sandbox/extensions/daytona/usaspending_text2sql/README.md`
- **Temporal Sandbox Agent**（documentation）：A conversational coding agent that runs as a durable Temporal workflow with support for multiple sandbox backends Daytona, Docker, E2B, local unix . 证据：`examples/sandbox/extensions/temporal/README.md`
- **Healthcare support**（documentation）：This example shows how to build a healthcare support workflow with Agents SDK using both standard agents and a sandbox agent. The scenario is intentionally synthetic and generic: a patient asks a billing or coverage question, the workflow checks local records, inspects policy documents in an isolated sandbox workspace, writes support artifacts, and optionally routes one ambiguous case to a human reviewer. 证据：`examples/sandbox/healthcare_support/README.md`
- **Dataroom metric extract**（documentation）：Extract financial metrics from a synthetic 10-K packet, write the resulting table as CSV or JSONL, then validate the generated artifact with a deterministic eval script. 证据：`examples/sandbox/tutorials/dataroom_metric_extract/README.md`
- **Dataroom Q&A**（documentation）：Answer grounded financial questions over a synthetic 10-K packet. 证据：`examples/sandbox/tutorials/dataroom_qa/README.md`
- **Repo code review**（documentation）：Review a small public git repository, run its tests, leave line-level review comments in the structured output, and write a patch-oriented review artifact. 证据：`examples/sandbox/tutorials/repo_code_review/README.md`
- **Sandbox resume**（documentation）：This example shows a small sandbox resume flow with AGENTS.md mounted in the sandbox and loaded into the agent instructions. It runs in two steps: first it builds the app and smoke tests it, then it serializes the sandbox session state, resumes the sandbox, and adds pytest coverage. 证据：`examples/sandbox/tutorials/sandbox_resume/README.md`
- **Vision UI reproduction**（documentation）：Use the sandbox view image tool to inspect a reference app screenshot, then reproduce the visible screen as a static HTML/CSS artifact. This is a narrow UI repro target for vision and screenshot-debugging; it is not a web-app scaffold. 证据：`examples/sandbox/tutorials/vision_website_clone/README.md`
- **Static voice demo**（documentation）：This demo operates by capturing a recording, then running a voice pipeline on it. 证据：`examples/voice/static/README.md`
- **Streamed voice demo**（documentation）：This is an interactive demo, where you can talk to an Agent conversationally. It uses the voice pipeline's built in turn detection feature, so if you stop speaking the Agent responds. 证据：`examples/voice/streamed/README.md`
- **Realtime**（documentation）：Realtime agents are in beta: expect some breaking changes over the next few weeks as we find issues and fix them. 证据：`src/agents/realtime/README.md`
- **Code Change Verification**（skill_instruction）：Ensure work is only marked complete after formatting, linting, type checking, and tests pass. Use this skill when changes affect runtime code, tests, or build/test configuration. You can skip it for docs-only or repository metadata unless a user asks for the full stack. 证据：`.agents/skills/code-change-verification/SKILL.md`
- **Docs Sync**（skill_instruction）：Identify doc coverage gaps and inaccuracies by comparing main branch features and configuration options against the current docs structure, then propose targeted improvements. 证据：`.agents/skills/docs-sync/SKILL.md`
- **examples-auto-run**（skill_instruction）：- Runs uv run examples/run examples.py with: - Optional dependency extras enabled by default: litellm , any-llm , sqlalchemy , redis , blaxel , modal , runloop , and temporal . - EXAMPLES INTERACTIVE MODE=auto auto-input/auto-approve . - Per-example logs under .tmp/examples-start-logs/ . - Main summary log path passed via --main-log also under .tmp/examples-start-logs/ . - Generates a rerun list of failures at .tmp/examples-rerun.txt when --write-rerun is set. - Provides start/stop/status/logs/tail/collect/rerun helpers via run.sh . - Background option keeps the process running with a pidfile; stop cleans it up. 证据：`.agents/skills/examples-auto-run/SKILL.md`
- **Final Release Review**（skill_instruction）：Use this skill when validating the latest release candidate commit default tip of origin/main for release. It guides you to fetch remote tags, pick the previous release tag, and thoroughly inspect the BASE TAG...TARGET diff for breaking changes, introduced bugs/regressions, improvement opportunities, and release risks. 证据：`.agents/skills/final-release-review/SKILL.md`
- **Implementation Strategy**（skill_instruction）：Use this skill before editing code when the task changes runtime behavior or anything that might look like a compatibility concern. The goal is to keep implementations simple while protecting real released contracts. 证据：`.agents/skills/implementation-strategy/SKILL.md`
- **OpenAI Knowledge**（skill_instruction）：Use the OpenAI Developer Documentation MCP server to search and fetch exact docs markdown , then base your answer on that text instead of guessing. 证据：`.agents/skills/openai-knowledge/SKILL.md`
- **PR Draft Summary**（skill_instruction）：Purpose Produce the PR-ready summary required in this repository after substantive code work is complete: a concise summary plus a PR-ready title and draft description that begins with "This pull request ...". The block should be ready to paste into a PR for openai-agents-python. 证据：`.agents/skills/pr-draft-summary/SKILL.md`
- **Runtime Behavior Probe**（skill_instruction）：Use this skill to investigate real runtime behavior, not to restate code or documentation. Start by planning the investigation, then execute a case matrix, record observed behavior, and report both the findings and the method used to obtain them. 证据：`.agents/skills/runtime-behavior-probe/SKILL.md`
- **Prior Auth Packet Builder**（skill_instruction）：Use this skill when a case requires prior authorization review, referral validation, imaging review, or payer-specific policy checks. 证据：`examples/sandbox/healthcare_support/skills/prior-auth-packet-builder/SKILL.md`
- **Playwright**（skill_instruction）：Use Playwright to capture the static site directly. Do not start a server for this example. 证据：`examples/sandbox/tutorials/vision_website_clone/skills/playwright/SKILL.md`
- **CSV Workbench**（skill_instruction）：Use this skill when the user asks for quick analysis of tabular data. 证据：`examples/tools/skills/csv-workbench/SKILL.md`
- **Test Coverage Improver**（skill_instruction）：Use this skill whenever coverage needs assessment or improvement coverage regressions, failing thresholds, or user requests for stronger tests . It runs the coverage suite, analyzes results, highlights the biggest gaps, and prepares test additions while confirming with the user before changing code. 证据：`.agents/skills/test-coverage-improver/SKILL.md`
- **License**（source_file）：Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files the "Software" , to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions: 证据：`LICENSE`
- **Configuration**（documentation）：This page covers SDK-wide defaults that you usually set once during application startup, such as the default OpenAI key or client, the default OpenAI API shape, tracing export defaults, and logging behavior. 证据：`docs/config.md`
- **Context management**（documentation）：Context is an overloaded term. There are two main classes of context you might care about: 证据：`docs/context.md`
- **Examples**（documentation）：Check out a variety of sample implementations of the SDK in the examples section of the repo https://github.com/openai/openai-agents-python/tree/main/examples . The examples are organized into several categories that demonstrate different patterns and capabilities. 证据：`docs/examples.md`
- **Guardrails**（documentation）：Guardrails enable you to do checks and validations of user input and agent output. For example, imagine you have an agent that uses a very smart and hence slow/expensive model to help with customer requests. You wouldn't want malicious users to ask the model to help them with their math homework. So, you can run a guardrail with a fast/cheap model. If the guardrail detects malicious usage, it can immediately raise an error and prevent the expensive model from running, saving you time and money when using blocking guardrails; for parallel guardrails, the expensive model may have already started running before the guardrail completes. See "Execution modes" below for details . 证据：`docs/guardrails.md`
- **Handoffs**（documentation）：Handoffs allow an agent to delegate tasks to another agent. This is particularly useful in scenarios where different agents specialize in distinct areas. For example, a customer support app might have agents that each specifically handle tasks like order status, refunds, FAQs, etc. 证据：`docs/handoffs.md`
- **Human-in-the-loop**（documentation）：Use the human-in-the-loop HITL flow to pause agent execution until a person approves or rejects sensitive tool calls. Tools declare when they need approval, run results surface pending approvals as interruptions, and RunState lets you serialize and resume runs after decisions are made. 证据：`docs/human_in_the_loop.md`
- **OpenAI Agents SDK**（documentation）：The OpenAI Agents SDK https://github.com/openai/openai-agents-python enables you to build agentic AI apps in a lightweight, easy-to-use package with very few abstractions. It's a production-ready upgrade of our previous experimentation for agents, Swarm https://github.com/openai/swarm/tree/main . The Agents SDK has a very small set of primitives: 证据：`docs/index.md`
- 其余 20 条证据见 `AI_CONTEXT_PACK.json` 或 `EVIDENCE_INDEX.json`。

## 宿主 AI 必须遵守的规则

- **把本资产当作开工前上下文，而不是运行环境。**：AI Context Pack 只包含证据化项目理解，不包含目标项目的可执行状态。 证据：`docs/agents.md`, `docs/ja/agents.md`, `docs/ko/agents.md`
- **回答用户时区分可预览内容与必须安装后才能验证的内容。**：安装前体验的消费者价值来自降低误装和误判，而不是伪装成真实运行。 证据：`docs/agents.md`, `docs/ja/agents.md`, `docs/ko/agents.md`

## 用户开工前应该回答的问题

- 你准备在哪个宿主 AI 或本地环境中使用它？
- 你只是想先体验工作流，还是准备真实安装？
- 你最在意的是安装成本、输出质量、还是和现有规则的冲突？

## 验收标准

- 所有能力声明都能回指到 evidence_refs 中的文件路径。
- AI_CONTEXT_PACK.md 没有把预览包装成真实运行。
- 用户能在 3 分钟内看懂适合谁、能做什么、如何开始和风险边界。

---

## Doramagic Context Augmentation

下面内容用于强化 Repomix/AI Context Pack 主体。Human Manual 只提供阅读骨架；踩坑日志会被转成宿主 AI 必须遵守的工作约束。

## Human Manual 骨架

使用规则：这里只是项目阅读路线和显著性信号，不是事实权威。具体事实仍必须回到 repo evidence / Claim Graph。

宿主 AI 硬性规则：
- 不得把页标题、章节顺序、摘要或 importance 当作项目事实证据。
- 解释 Human Manual 骨架时，必须明确说它只是阅读路线/显著性信号。
- 能力、安装、兼容性、运行状态和风险判断必须引用 repo evidence、source path 或 Claim Graph。

- **项目概述**：importance `high`
  - source_paths: README.md, pyproject.toml, src/agents/version.py
- **快速开始指南**：importance `high`
  - source_paths: docs/quickstart.md, examples/basic/hello_world.py, examples/basic/hello_world_jupyter.ipynb
- **核心概念**：importance `high`
  - source_paths: src/agents/agent.py, src/agents/tool.py, src/agents/guardrail.py, src/agents/handoffs/__init__.py, src/agents/items.py
- **Agent 核心框架**：importance `high`
  - source_paths: src/agents/agent.py, src/agents/run.py, src/agents/run_config.py, src/agents/run_context.py, src/agents/run_state.py
- **工具系统**：importance `high`
  - source_paths: src/agents/tool.py, src/agents/function_schema.py, src/agents/tool_context.py, src/agents/tool_guardrails.py, examples/basic/tools.py
- **MCP 协议集成**：importance `medium`
  - source_paths: src/agents/mcp/manager.py, src/agents/mcp/server.py, src/agents/mcp/util.py, src/agents/_mcp_tool_metadata.py, examples/mcp
- **Agent 转交机制**：importance `medium`
  - source_paths: src/agents/handoffs/__init__.py, src/agents/handoffs/history.py, src/agents/extensions/handoff_filters.py, src/agents/extensions/handoff_prompt.py, examples/handoffs/message_filter.py
- **Guardrails 安全机制**：importance `medium`
  - source_paths: src/agents/guardrail.py, src/agents/tool_guardrails.py, src/agents/run_internal/guardrails.py, examples/agent_patterns/input_guardrails.py, examples/agent_patterns/output_guardrails.py

## Repo Inspection Evidence / 源码检查证据

- repo_clone_verified: true
- repo_inspection_verified: true
- repo_commit: `92e014a4cc4d3cbaac6934cd12af1b641f204ab4`
- inspected_files: `pyproject.toml`, `README.md`, `uv.lock`, `docs/tracing.md`, `docs/tools.md`, `docs/repl.md`, `docs/human_in_the_loop.md`, `docs/index.md`, `docs/context.md`, `docs/quickstart.md`, `docs/streaming.md`, `docs/usage.md`, `docs/multi_agent.md`, `docs/examples.md`, `docs/sandbox_agents.md`, `docs/results.md`, `docs/running_agents.md`, `docs/agents.md`, `docs/handoffs.md`, `docs/mcp.md`

宿主 AI 硬性规则：
- 没有 repo_clone_verified=true 时，不得声称已经读过源码。
- 没有 repo_inspection_verified=true 时，不得把 README/docs/package 文件判断写成事实。
- 没有 quick_start_verified=true 时，不得声称 Quick Start 已跑通。

## Doramagic Pitfall Constraints / 踩坑约束

这些规则来自 Doramagic 发现、验证或编译过程中的项目专属坑点。宿主 AI 必须把它们当作工作约束，而不是普通说明文字。

### Constraint 1: 仓库名和安装名不一致

- Trigger: 仓库名 `openai-agents-python` 与安装入口 `openai-agents` 不完全一致。
- Host AI rule: 在 npm/PyPI/GitHub 上确认包名映射和官方 README 说明。
- Why it matters: 用户照着仓库名搜索包或照着包名找仓库时容易走错入口。
- Evidence: identity.distribution | github_repo:946380199 | https://github.com/openai/openai-agents-python | repo=openai-agents-python; install=openai-agents
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 2: 来源证据：AdvancedSQLiteSession.delete_branch() leaves branch-only messages in the base table

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：AdvancedSQLiteSession.delete_branch() leaves branch-only messages in the base table
- Host AI rule: 来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_d867c75f80af49c9968398851ff8bf6a | https://github.com/openai/openai-agents-python/issues/3346 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 3: 来源证据：Clarify whether retry-after delays should respect retry max_delay

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：Clarify whether retry-after delays should respect retry max_delay
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_f486d2247bf24df8bbc7a2bd6fddbd65 | https://github.com/openai/openai-agents-python/issues/3266 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 4: 来源证据：OpenAIConversationsSession persists empty reasoning item {"type":"reasoning","summary":[]} and Conversations API reject…

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：OpenAIConversationsSession persists empty reasoning item {"type":"reasoning","summary":[]} and Conversations API rejects it as invalid
- Host AI rule: 来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_d6bad5c23bf3457eb546c22a1636cc26 | https://github.com/openai/openai-agents-python/issues/3268 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 5: 来源证据：Tracing shutdown cannot interrupt exporter retry backoff

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：Tracing shutdown cannot interrupt exporter retry backoff
- Host AI rule: 来源问题仍为 open，Pack Agent 需要复核是否仍影响当前版本。
- Why it matters: 可能阻塞安装或首次运行。
- Evidence: community_evidence:github | cevd_e1ceae098cf84c8aafae7082b13c5345 | https://github.com/openai/openai-agents-python/issues/3354 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 6: 来源证据：v0.15.2

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v0.15.2
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_b73472b5ae90447199984775aacdca67 | https://github.com/openai/openai-agents-python/releases/tag/v0.15.2 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 7: 来源证据：v0.15.3

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v0.15.3
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_7e05a382001a4d07b74eda1e1316320b | https://github.com/openai/openai-agents-python/releases/tag/v0.15.3 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 8: 来源证据：v0.16.1

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v0.16.1
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_44335088ff52486e9f2f41f72a274c35 | https://github.com/openai/openai-agents-python/releases/tag/v0.16.1 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 9: 来源证据：v0.17.0

- Trigger: GitHub 社区证据显示该项目存在一个配置相关的待验证问题：v0.17.0
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_86b81f310a6e45feadc65196a057b23b | https://github.com/openai/openai-agents-python/releases/tag/v0.17.0 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

### Constraint 10: 来源证据：v0.15.1

- Trigger: GitHub 社区证据显示该项目存在一个能力理解相关的待验证问题：v0.15.1
- Host AI rule: 来源显示可能已有修复、规避或版本变化，说明书中必须标注适用版本。
- Why it matters: 可能增加新用户试用和生产接入成本。
- Evidence: community_evidence:github | cevd_4c70d563ac704aeaa14b8e2c49976bc5 | https://github.com/openai/openai-agents-python/releases/tag/v0.15.1 | 来源讨论提到 python 相关条件，需在安装/试用前复核。
- Hard boundary: 不要把这个坑点包装成已解决、已验证或可忽略，除非后续验证证据明确证明它已经关闭。

