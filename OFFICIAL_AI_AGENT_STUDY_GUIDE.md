---
title: 课程说明
layout: page
---

# 课程说明

创建时间: 2026-06-01 15:24 KST

目标: 解释 Study Dashboard 里的 66 天学习计划如何组织,以及每个阶段如何映射到 Alex / `ai-chief-of-staff` 的真实架构。Dashboard 是执行计划;本页是阶段说明和理论框架。

---

## 使用方法

每一课都按同一个节奏完成:

1. 阅读官方资料。
2. 写 5-10 条原子笔记,只记录可用于工程决策的内容。
3. 回答本课的检查问题。
4. 把概念映射到 Alex 的一个模块或 ADR。
5. 在 Study Dashboard 记录 `read_at_kst`,实际用时,产出链接。

推荐每次 60-90 分钟:

| 阶段 | 时间 | 产出 |
|---|---:|---|
| 精读 | 25-35 min | 标出核心概念和框架图 |
| 摘要 | 10-15 min | 5-10 条原子笔记 |
| 映射 | 15-25 min | 对应到 Alex 的模块/ADR |
| 反思 | 10 min | 一条"我会怎么改 Alex" |
| 打卡 | 5 min | 更新 reading log |

---

## Dashboard 阶段对照

Study Dashboard 里的每日计划不是简单照搬下面 9 个 Lesson。实际顺序加入了 AI fluency、Claude 产品能力、Claude Code、API、MCP、Skills 和 Subagents,因为这些内容是把 agent 理论落到 Alex 工程实践所需的补充阶段。

| Dashboard 天数 | 阶段 | 对应课程说明 | 阶段产出 |
|---|---|---|---|
| D01-D03 | Agentic system 入门 | Lesson 1 + Lesson 3 的前置概念 | F1-F6 workflow / agent 分类,agent 最小构件图 |
| D04-D12 | AI fluency 与业务判断 | 补充阶段,不在 9 个核心 Lesson 内 | AI 能力限制诊断表,业务场景 AI 机会表,小企业 AI policy |
| D13-D14 | 架构组件 | Lesson 2 | Alex component diagram,Session/State/Memory 区分 |
| D15-D18 | Claude 产品协作能力 | 补充阶段 | Claude 场景映射,AI 协作工作流,协作安全检查清单 |
| D19-D21 | Agent runtime 与 orchestration | Lesson 3 | Agent run 停止条件,manager vs handoff 判断标准 |
| D22-D27 | Claude Code 工程实践 | 补充阶段 | Claude Code 实施节奏,CLAUDE.md 模板,高风险操作 hook 需求 |
| D28-D31 | Tools / Memory / Guardrails | Lesson 4、5、6 | Tool risk matrix,memory policy,human gate checklist |
| D32-D44 | Claude API / RAG / workflow agents | Lesson 3、4、5、7 的 API 实作扩展 | API 请求、structured output、prompt eval、RAG evidence、agent workflow debug checklist |
| D45-D52 | MCP / Skills / Subagents | Lesson 8 的生产前置能力 | MCP server 草图,tools/resources/prompts 边界,skills 列表,subagent 边界 |
| D53-D58 | Evaluation 与 production patterns | Lesson 7、8 | Eval dataset,agent task eval,production gap list |
| D59-D64 | Agentic AI pattern practice | Lesson 9 | Reflection/tool/planning/multi-agent 应用判断,课程总复盘 |
| D65-D66 | 总复盘 | 全部阶段汇总 | 证书/展示材料整理,AI agent 应用方法论文档 |

使用方式:

1. 在 Study Dashboard 按 D 编号学习和打卡。
2. 需要理解某个阶段为什么这样安排时,回到本页看阶段说明。
3. 下面 9 个 Lesson 是理论骨架,Dashboard 是把骨架展开成每日执行块。

---

## 核心理论模块

### Lesson 1: 什么是 agentic system

官方资料:

- Anthropic: [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents)
- OpenAI: [A practical guide to building AI agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/)

学习目标:

- 区分 `single LLM call`, `workflow`, `agent`, `multi-agent system`。
- 理解为什么 Anthropic 建议先用简单可组合模式,不要过早上复杂框架。
- 理解 OpenAI 的核心构件: model, tools, instructions, guardrails, run loop。

检查问题:

- 为什么"能调用 LLM"不等于"是 agent"?
- workflow 和 agent 的关键区别是什么?
- 什么情况下应该坚持 deterministic workflow?

Alex 映射:

- `src/aipm/ingest/pipeline.py` 是 agentic workflow,不是 autonomous agent。
- `src/aipm/qa/engine.py` 是 RAG workflow,不是 full agent loop。
- QA browser agent 和未来 PM project agent 更接近 true agent。

交付:

- 写一张表: F1-F6 分别属于 deterministic workflow / LLM workflow / true agent / future agent。

### Lesson 2: Agent 架构组件

官方资料:

- Microsoft Learn: [Agent architecture components](https://learn.microsoft.com/en-us/agents/architecture/components-of-agent-architecture)
- Google ADK: [Technical Overview](https://adk.dev/get-started/about/)

学习目标:

- 掌握 enterprise agent 系统分层: client, infrastructure, orchestrator, model, tools, semantic index, MCP, responsible AI。
- 掌握 ADK 原语: Agent, Tool, Session, State, Memory, Event, Runner, Planning。

检查问题:

- Alex 的 client interface 是什么?
- Alex 的 orchestrator 是代码、LLM,还是 hybrid?
- `Session/State` 和 `Memory` 的区别是什么?

Alex 映射:

- Client interface: Slack Socket Mode / Bolt。
- Infrastructure: Postgres/pgvector, Notion, Slack API, background workers。
- Orchestrator: `main.py` + deterministic workflows + LLM classifier。
- Semantic index: Layer-2 chunks。
- Responsible AI: permission map, human confirmation, grounded citations。

交付:

- 画 Alex 的 Microsoft-style component diagram。

### Lesson 3: Agent loop 和 orchestration

官方资料:

- OpenAI: [Agents SDK docs](https://developers.openai.com/api/docs/guides/agents)
- OpenAI Agents SDK Python: [Agents](https://openai.github.io/openai-agents-python/agents/)
- OpenAI Agents SDK Python: [Multi-agent orchestration](https://openai.github.io/openai-agents-python/multi_agent/)

学习目标:

- 理解 agent run loop: model turn -> tool call -> observation -> next turn -> stop。
- 理解 single-agent vs manager pattern vs handoff pattern。
- 知道什么时候单 agent 加工具足够,什么时候才拆多个 agent。

检查问题:

- 一个 agent run 的停止条件有哪些?
- manager pattern 和 handoff pattern 的区别是什么?
- Alex 中哪些路径不应该放进 SDK loop?

Alex 映射:

- 当前 F1/F3 大多应该保留 deterministic outer shell。
- Future Claude Agent SDK 接入点应优先放在 QA browser agent / PM project agent / F4 委派判断,而不是 Slack 消息消防水管入口。

交付:

- 写一页"Alex 哪些模块应该进入 agent runtime,哪些不应该"。

### Lesson 4: Tools and tool risk

官方资料:

- OpenAI: [Using tools](https://developers.openai.com/api/docs/guides/tools)
- OpenAI: [A practical guide to building AI agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/), guardrails/tool safeguards sections
- Claude Docs: [Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview)

学习目标:

- 把 tools 当 action surface,不是函数列表。
- 给每个工具定义输入 schema、输出 schema、错误模式、权限、风险等级。
- 区分 read-only, reversible write, authoritative write, destructive/high-risk actions。

检查问题:

- Notion write 为什么比 vector search 风险高?
- Slack reply 是不是一定安全?
- Tool failure 应该进入 retry、fallback,还是 human escalation?

Alex 映射:

- Read-only: Layer-1/Layer-2 retrieval。
- Reversible write: Slack card/reply。
- Authoritative write: Notion decision record,必须 human-gated。
- Future high-risk: browser form submission, permission config changes。

交付:

- 为 Alex 的 Slack / Notion / vector search / permission / browser tools 写 risk matrix。

### Lesson 5: Memory, state, and RAG

官方资料:

- Google ADK: [Memory](https://google.github.io/adk-docs/sessions/memory/)
- Google ADK: [Technical Overview](https://adk.dev/get-started/about/)
- OpenAI docs: [File search and retrieval](https://developers.openai.com/api/docs/guides/tools)

学习目标:

- 区分 session state, working memory, long-term memory, semantic index, authoritative memory。
- 理解 RAG 是证据管道,不是简单 prompt 拼接。
- 理解 memory write policy:什么可以自动写,什么必须 human-gated。

检查问题:

- Layer-2 自动写是否会污染决策?
- Layer-1 和 Layer-2 的 authority 有何不同?
- 为什么 operational memory 不能写 decision ledger?

Alex 映射:

- Layer-1: Notion decision ledger。
- Layer-2: pgvector conversation chunks。
- Layer-3: operational memory,应与权威决策库硬隔离。
- F3 Q&A: L1/L2 retrieve -> permission filter -> grounded generation。

交付:

- 写 Alex memory policy:每一类 memory 的写入者、读取者、权限边界、撤销机制。

### Lesson 6: Guardrails, permissions, and human gates

官方资料:

- OpenAI: [Agents SDK guardrails](https://openai.github.io/openai-agents-python/guardrails/)
- OpenAI: [A practical guide to building AI agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/), guardrails section
- Microsoft Learn: [Agent architecture components](https://learn.microsoft.com/en-us/agents/architecture/components-of-agent-architecture), Responsible AI and orchestration sections

学习目标:

- guardrail 不是 prompt,而是确定性机制 + 模型检查 + 人类确认 + 审计。
- 区分 authentication, authorization, content safety, tool risk, output validation。
- 学会设计 fail-closed 权限系统。

检查问题:

- 为什么 `project` 不能作为权限边界?
- 权限快照过期时应该允许还是拒绝?
- F1 card 为什么只能 current_decider 确认?

Alex 映射:

- `aipm_kernel.permissions.map.PermissionMap.can_view` 未知/过期 fail closed。
- `aipm_kernel.permissions.filter.filter_visible` 是所有 retrieval 的安全门。
- F1 Slack handler 做 decider + active user + channel member 三重检查。
- C1/C3 ADR 规定 `channel_id` 权限轴和 `project` 归属轴正交。

交付:

- 写 10 个 security golden tests: private leak, stale permission, wrong approver, bus channel, project-as-auth misuse 等。

### Lesson 7: Evaluation and observability

官方资料:

- OpenAI: [Agent evals](https://platform.openai.com/docs/guides/agent-evals)
- OpenAI: [Working with evals](https://developers.openai.com/api/docs/guides/evals)
- DeepLearning.AI: [Evaluating AI Agents](https://www.deeplearning.ai/courses/evaluating-ai-agents/)

学习目标:

- 把评测拆成模型质量、任务成功、安全、系统可靠性、运营体验。
- 建立 golden set, trace, prompt version, model version。
- 区分 hard gate 和 soft metric。

检查问题:

- `permission_leak = 0` 是指标还是硬门?
- Q&A 正确率为什么必须看 citation 支撑,不是只看答案听起来对?
- 如何定位一次错误: retrieval 错、permission 错、generation 错,还是 tool 错?

Alex 映射:

- PRD KPI K1-K5。
- F3 需要 Q&A citation golden set。
- F1 classifier 需要 decision/task/chat golden set。
- workers 已有 heartbeat/queue/notion outage age,但还需要统一 trace id。

交付:

- 建 Alex eval matrix: F1-F6 每个功能至少 5 条 golden cases。

### Lesson 8: Multi-agent systems and fleet design

官方资料:

- Anthropic: [Building effective agents](https://www.anthropic.com/engineering/building-effective-agents), multi-agent and workflow patterns
- Anthropic Resources: [Building Effective AI Agents](https://resources.anthropic.com/building-effective-ai-agents)
- OpenAI Agents SDK Python: [Multi-agent orchestration](https://openai.github.io/openai-agents-python/multi_agent/)

学习目标:

- 区分 manager pattern, decentralized handoff, agents-as-tools。
- 理解多 agent 的核心风险:状态一致性、工具权限、重复写入、handoff 丢失、责任边界不清。
- 学会为 fleet 建共享协议,而不是只建多个 prompts。

检查问题:

- Alex/PM/QA/engineer-agent 的职责边界是什么?
- writer-per-store 为什么重要?
- C2 handoff 应该传哪些字段?

Alex 映射:

- 公司层 Alex:共享决策记忆、权限过滤、Q&A。
- 项目层 PM agent:项目镜头和项目工具。
- QA agent:浏览器/产品走查 worker。
- engineer-agent:后续 interop,不在 v1 深度 handoff。
- shared kernel:权限、决策存储、Layer-2 contract、capture primitives。

交付:

- 写 Alex fleet boundary table: owner, inputs, outputs, tools, memory, write authority, failure mode。

### Lesson 9: Andrew Ng Agentic AI course

官方资料:

- DeepLearning.AI: [Agentic AI](https://www.deeplearning.ai/courses/agentic-ai)

学习目标:

- 建立常见 agentic design patterns 词汇: reflection, tool use, planning, multi-agent workflows。
- 学会把课程模式映射到生产系统,而不是机械套模式。
- 理解课程偏模式和实践,项目还需补权限/记忆/评测/审计。

检查问题:

- Reflection 可以用在哪里?不能用在哪里?
- Planning 对 F3 Q&A 是否必要?
- Multi-agent 对 Alex 是架构收益,还是复杂度负担?

Alex 映射:

- Reflection: 可用于 draft/review,不可绕过 human gate 写 decision ledger。
- Tool use: 必须有 risk matrix。
- Planning: 更适合 QA browser agent。
- Multi-agent: 要先定义 C2 handoff 和 shared kernel。

交付:

- 课程每章结束写一条"Alex application note":这个模式该不该进入 Alex,为什么。

---

## 推荐学习方法

### 1. 先分层,再读细节

不要从 SDK API 开始。先按这个顺序读:

```text
agentic system vs workflow
  -> architecture components
  -> agent loop
  -> tools
  -> memory/RAG
  -> guardrails/permissions
  -> eval/observability
  -> multi-agent/fleet
```

这样读可以避免把"会调 SDK"误认为"懂 agent 架构"。

### 2. 每篇资料只提取工程判断

笔记不要写成摘要。每篇只记录这三类:

- `Definition`: 官方怎么定义概念。
- `Decision rule`: 什么时候该用/不该用。
- `Alex implication`: 对 Alex 的架构影响。

例子:

```text
Definition: Anthropic 区分 workflow 和 agent。
Decision rule: 预定义路径足够时优先 workflow。
Alex implication: Slack 全量 ingest 不能进 agent loop,应保持两车道。
```

### 3. 用 Feynman + ADR 方式复述

每学完一课,用 150-300 字写:

- 我如何向一个工程师解释这个概念?
- 如果应用到 Alex,我会作出什么架构决策?
- 这个决策的 tradeoff 是什么?

如果写不出来,说明还只是"看过",不是"学会"。

### 4. 每周只产一个可验证 artifact

不要追求读很多链接。每周交付一个硬产物:

- Week 1: F1-F6 workflow/agent 分类表。
- Week 2: Alex component diagram。
- Week 3: tool risk matrix。
- Week 4: memory policy。
- Week 5: security golden tests。
- Week 6: eval matrix。
- Week 7: fleet boundary table。

### 5. 用项目反向检验理论

每次读官方文档都问:

- 这条原则在 Alex 哪个文件里已经体现?
- 哪个 ADR 已经做了这个决策?
- 哪个地方和官方建议冲突?
- 如果冲突,是项目合理例外,还是技术债?

### 6. 阅读打卡不是时间账,是理解账

`read_at_kst` 只记录完成时间。真正重要的是:

- `notes_link`: 有没有笔记。
- `alex_mapping`: 有没有映射到项目。
- `open_question`: 有没有留下可追踪问题。
- `next_action`: 有没有转成下一步工程动作。
