---
title: AI Agent Reading Log
layout: page
---

# AI Agent Reading Log

创建时间: 2026-06-01 15:24 KST

用途: 记录官方 AI Agent 学习资料的阅读打卡。`read_at_kst` 请填实际完成阅读的韩国时间,例如 `2026-06-01 21:10 KST`。不要为了完成表格而补假时间;未读保持空白。

网页打卡入口: [Check-in](checkin.html)。

状态枚举:

- `todo`: 未开始。
- `reading`: 已开始但未完成。
- `done`: 已完成阅读和笔记。
- `review`: 已读,等待二刷或项目映射。

---

## Official Docs Tracker

| 编号 | 状态 | 来源 | 主题 | 计划分钟 | 阅读完成时间_KST | 实际分钟 | 产出 / 笔记 |
|---|---|---|---|---:|---|---:|---|
| L1-A | todo | [Anthropic: Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | workflow vs agent, simple patterns | 60 |  |  |  |
| L1-B | todo | [OpenAI: A practical guide to building AI agents](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | model/tools/instructions, run loop, guardrails | 75 |  |  |  |
| L2-A | todo | [Microsoft: Agent architecture components](https://learn.microsoft.com/en-us/agents/architecture/components-of-agent-architecture) | enterprise architecture layers | 45 |  |  |  |
| L2-B | todo | [Google ADK: Technical Overview](https://adk.dev/get-started/about/) | agent/tool/session/state/memory/runner | 60 |  |  |  |
| L3-A | todo | [OpenAI: Agents SDK docs](https://developers.openai.com/api/docs/guides/agents) | orchestration, state, guardrails, evals | 60 |  |  |  |
| L3-B | todo | [OpenAI Agents SDK Python: Agents](https://openai.github.io/openai-agents-python/agents/) | Agent and Runner concepts | 45 |  |  |  |
| L3-C | todo | [OpenAI Agents SDK Python: Multi-agent orchestration](https://openai.github.io/openai-agents-python/multi_agent/) | manager, handoff, agents-as-tools | 45 |  |  |  |
| L4-A | todo | [OpenAI: Using tools](https://developers.openai.com/api/docs/guides/tools) | tool surface and hosted tools | 60 |  |  |  |
| L4-B | todo | [Claude Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) | Claude SDK runtime and tool model | 45 |  |  |  |
| L5-A | todo | [Google ADK: Memory](https://google.github.io/adk-docs/sessions/memory/) | session state vs long-term memory | 45 |  |  |  |
| L6-A | todo | [OpenAI Agents SDK Python: Guardrails](https://openai.github.io/openai-agents-python/guardrails/) | input/output guardrails | 45 |  |  |  |
| L7-A | todo | [OpenAI: Agent evals](https://platform.openai.com/docs/guides/agent-evals) | agent workflow evaluation | 60 |  |  |  |
| L7-B | todo | [OpenAI: Working with evals](https://developers.openai.com/api/docs/guides/evals) | eval methodology and datasets | 60 |  |  |  |
| L7-C | todo | [DeepLearning.AI: Evaluating AI Agents](https://www.deeplearning.ai/courses/evaluating-ai-agents/) | agent evaluation practice | 90 |  |  |  |
| L8-A | todo | [Anthropic: Building Effective AI Agents resource](https://resources.anthropic.com/building-effective-ai-agents) | production-ready patterns | 90 |  |  |  |
| L9-A | todo | [DeepLearning.AI: Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | reflection, tools, planning, multi-agent workflows | 360 |  |  |  |

---

## 总学习日程:每日总计 60 分钟

规划原则:

- 每天总学习时间只安排 60 分钟,包括官方文档、Anthropic Academy 课程、笔记和 Alex/工程实践映射。
- 如果某个资料超过 60 分钟,就拆成多天;不要同一天再额外加 Anthropic 课程。
- 课程时长核对(2026-06-01):Anthropic Academy/Claude 官方信息显示,AI Capabilities and Limitations 是 13 lectures、0.25 hours of video、1 quiz,完整课程约 90 分钟;AI Fluency: Framework & Foundations 是 14 lectures、1.1 hours of video、1 quiz,官网估计完整课程 3-4 小时;AI Fluency for Small Businesses 是 9 lectures、0.9 hours of video、1 quiz。
- 因此表里的 60 分钟是每日学习块,不是课程总时长;超过 60 分钟的课程按模块拆开。
- `阅读完成时间_KST` 仍然只填实际完成时间,不要提前填计划日期。
- 主线目标:先建立 agentic system 判断力,再补 small business 场景分析能力,最后进入 Claude Code、API、MCP、Skills、Subagents 和 eval。

| 编号 | 状态 | 日程 | 来源 | 主题 | 计划分钟 | 阅读完成时间_KST | 实际分钟 | 产出 / 笔记 |
|---|---|---|---|---|---:|---|---:|---|
| D01 | todo | Day 01 | [L1-A: Anthropic Building effective agents](https://www.anthropic.com/engineering/building-effective-agents) | workflow vs agent、简单模式优先 | 60 |  |  | F1-F6 标注 workflow / agent |
| D02 | todo | Day 02 | [L1-B: OpenAI Practical guide](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | model、tools、instructions、run loop | 60 |  |  | 画 agent 最小构件图 |
| D03 | todo | Day 03 | [L1-B: OpenAI Practical guide](https://openai.com/business/guides-and-resources/a-practical-guide-to-building-ai-agents/) | orchestration、guardrails、适用场景 | 60 |  |  | 写 Alex 哪些路径不该进 agent loop |
| D04 | todo | Day 04 | [Anthropic: AI Capabilities and Limitations](https://anthropic.skilljar.com/ai-capabilities-and-limitations) | Getting started、What We Mean by AI、How AI Gets Its Character、Next Token Prediction | 60 |  |  | 写一页:AI 为什么会流畅但不一定正确 |
| D05 | todo | Day 05 | [Anthropic: AI Capabilities and Limitations](https://anthropic.skilljar.com/ai-capabilities-and-limitations) | Knowledge、Working Memory、Steerability、When Properties Collide、quiz | 60 |  |  | 做一张 4 properties 诊断表:出错时先判断是哪类问题 |
| D06 | todo | Day 06 | [Anthropic: AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | AI Fluency 导论、生成式 AI 基础、能力/限制、4D 总览 | 60 |  |  | 写出 4D 与 AI properties 的对应关系 |
| D07 | todo | Day 07 | [Anthropic: AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | Delegation、任务适配度、何时不该交给 AI | 60 |  |  | 整理 Delegation 判断标准和反例 |
| D08 | todo | Day 08 | [Anthropic: AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | Description、Discernment、prompt/context、输出评估 | 60 |  |  | 做一套需求描述和输出验收 checklist |
| D09 | todo | Day 09 | [Anthropic: AI Fluency: Framework & Foundations](https://anthropic.skilljar.com/ai-fluency-framework-foundations) | Diligence、责任边界、最终测验和证书 | 60 |  |  | 写一页:哪些 AI 产出必须人工复核 |
| D10 | todo | Day 10 | [Anthropic: AI Fluency for Small Businesses](https://anthropic.skilljar.com/ai-fluency-for-small-businesses) | How AI works、小企业目标/价值/约束 | 60 |  |  | 做一版业务场景 AI 机会诊断表 |
| D11 | todo | Day 11 | [Anthropic: AI Fluency for Small Businesses](https://anthropic.skilljar.com/ai-fluency-for-small-businesses) | Using AI in practice、Description-Discernment loop、customer data | 60 |  |  | 把一个真实业务任务改写成可交给 AI 的 workflow |
| D12 | todo | Day 12 | [Anthropic: AI Fluency for Small Businesses](https://anthropic.skilljar.com/ai-fluency-for-small-businesses) | Putting it all together、AI use policy、quiz/certificate | 60 |  |  | 做一版小企业 AI 使用政策模板 |
| D13 | todo | Day 13 | [L2-A: Microsoft Agent architecture components](https://learn.microsoft.com/en-us/agents/architecture/components-of-agent-architecture) | enterprise agent 架构分层 | 60 |  |  | 画 Alex 的 Microsoft-style component diagram |
| D14 | todo | Day 14 | [L2-B: Google ADK Technical Overview](https://adk.dev/get-started/about/) | Agent、Tool、Session、State、Memory、Runner | 60 |  |  | 写 Session/State/Memory 区别 |
| D15 | todo | Day 15 | [Anthropic: Claude 101](https://anthropic.skilljar.com/claude-101) | Claude 基础、对话、提示、日常工作任务 | 60 |  |  | 整理 5 个产品演示用 Claude 场景 |
| D16 | todo | Day 16 | [Anthropic: Claude 101](https://anthropic.skilljar.com/claude-101) | Projects、Artifacts、Skills、连接工具、Research | 60 |  |  | 做一页 Claude 功能到业务问题的映射表 |
| D17 | todo | Day 17 | [Anthropic: Introduction to Claude Cowork](https://anthropic.skilljar.com/introduction-to-claude-cowork) | Cowork task loop、文件/项目协作、上下文 | 60 |  |  | 写一套 AI 协作工作流 |
| D18 | todo | Day 18 | [Anthropic: Introduction to Claude Cowork](https://anthropic.skilljar.com/introduction-to-claude-cowork) | plugins、skills、安全协作、团队共享 | 60 |  |  | 写一套项目协作安全检查清单 |
| D19 | todo | Day 19 | [L3-A: OpenAI Agents SDK docs](https://developers.openai.com/api/docs/guides/agents) | agent run loop、state、guardrails、evals | 60 |  |  | 写 agent run 的停止条件 |
| D20 | todo | Day 20 | [L3-B: OpenAI Agents SDK Python Agents](https://openai.github.io/openai-agents-python/agents/) | Agent 和 Runner 概念 | 60 |  |  | 对比 Alex orchestrator 和 SDK Runner |
| D21 | todo | Day 21 | [L3-C: OpenAI Agents SDK Multi-agent orchestration](https://openai.github.io/openai-agents-python/multi_agent/) | manager、handoff、agents-as-tools | 60 |  |  | 写 manager vs handoff 判断标准 |
| D22 | todo | Day 22 | [Anthropic: Claude Code 101](https://anthropic.skilljar.com/claude-code-101) | Claude Code、agentic loop、安装和第一轮 prompt | 60 |  |  | 复述 Claude Code 和聊天式助手的区别 |
| D23 | todo | Day 23 | [Anthropic: Claude Code 101](https://anthropic.skilljar.com/claude-code-101) | Explore -> Plan -> Code -> Commit、context management、code review | 60 |  |  | 形成自己的 Claude Code 实施节奏 |
| D24 | todo | Day 24 | [Anthropic: Claude Code 101](https://anthropic.skilljar.com/claude-code-101) | CLAUDE.md、subagents、skills、MCP、hooks | 60 |  |  | 写一版项目级 CLAUDE.md 模板 |
| D25 | todo | Day 25 | [Anthropic: Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) | Claude Code 架构、项目 setup、添加上下文、改代码 | 60 |  |  | 记录一个完整 Explore -> Plan -> Code 案例 |
| D26 | todo | Day 26 | [Anthropic: Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) | context 控制、custom commands、MCP servers、GitHub integration | 60 |  |  | 列出可复用的 custom command 候选 |
| D27 | todo | Day 27 | [Anthropic: Claude Code in Action](https://anthropic.skilljar.com/claude-code-in-action) | hooks、Claude Code SDK、测验和证书 | 60 |  |  | 写一份高风险命令/写入操作 hook 需求 |
| D28 | todo | Day 28 | [L4-A: OpenAI Using tools](https://developers.openai.com/api/docs/guides/tools) | tools as action surface、tool risk | 60 |  |  | 定义 read/write/destructive 工具等级 |
| D29 | todo | Day 29 | [L4-B: Claude Agent SDK overview](https://code.claude.com/docs/en/agent-sdk/overview) | Claude SDK runtime 和工具模型 | 60 |  |  | 写 Claude SDK 接入点判断 |
| D30 | todo | Day 30 | [L5-A: Google ADK Memory](https://google.github.io/adk-docs/sessions/memory/) | session state vs long-term memory | 60 |  |  | 写 Alex memory 分层原则 |
| D31 | todo | Day 31 | [L6-A: OpenAI Agents SDK Guardrails](https://openai.github.io/openai-agents-python/guardrails/) | input/output guardrails、人类确认 | 60 |  |  | 写 human gate checklist |
| D32 | todo | Day 32 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | API getting started: auth、basic request、messages | 60 |  |  | 跑通最小 API 请求并记录输入/输出 |
| D33 | todo | Day 33 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | conversations、streaming、system prompts、structured output | 60 |  |  | 写一个需求结构化提取 prompt |
| D34 | todo | Day 34 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | prompt engineering 和 evaluation 上半部分 | 60 |  |  | 写 5 条 prompt eval case |
| D35 | todo | Day 35 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | prompt engineering 和 automated testing 下半部分 | 60 |  |  | 做一版 prompt regression checklist |
| D36 | todo | Day 36 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | tool use 上半部分: custom tools、function calling | 60 |  |  | 定义 3 个外部系统工具 schema |
| D37 | todo | Day 37 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | tool use 下半部分: multi-turn tools、batch tools、errors | 60 |  |  | 给工具分 read/write/destructive 风险等级 |
| D38 | todo | Day 38 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | RAG 上半部分: chunking、embeddings、hybrid search | 60 |  |  | 写 Alex / 项目知识库 chunking 原则 |
| D39 | todo | Day 39 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | RAG 下半部分: reranking、contextual retrieval、evidence | 60 |  |  | 写一版回答必须带证据的验收标准 |
| D40 | todo | Day 40 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | API 课内 MCP 上半部分: tools/resources/prompts | 60 |  |  | 画 MCP primitives 到外部系统的映射 |
| D41 | todo | Day 41 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | API 课内 MCP 下半部分: server/client integration | 60 |  |  | 设计一个文件系统 MCP server 草图 |
| D42 | todo | Day 42 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | Claude Code & Computer Use | 60 |  |  | 判断哪些业务流程适合 UI automation |
| D43 | todo | Day 43 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | agents and workflows 上半部分: chaining、routing、parallelism | 60 |  |  | 给业务流程标注 workflow / agent |
| D44 | todo | Day 44 | [Anthropic: Building with the Claude API](https://anthropic.skilljar.com/claude-with-the-anthropic-api/287725) | agents and workflows 下半部分: debugging、quizzes、证书 | 60 |  |  | 写一版 agent workflow debug checklist |
| D45 | todo | Day 45 | [Anthropic: Introduction to Model Context Protocol](https://anthropic.skilljar.com/introduction-to-model-context-protocol) | MCP architecture、clients、servers、tools | 60 |  |  | 跑通或复述一个最小 MCP server |
| D46 | todo | Day 46 | [Anthropic: Introduction to Model Context Protocol](https://anthropic.skilljar.com/introduction-to-model-context-protocol) | resources、prompts、client integration、assessment | 60 |  |  | 写 tools/resources/prompts 使用边界 |
| D47 | todo | Day 47 | [Anthropic: Model Context Protocol: Advanced Topics](https://anthropic.skilljar.com/model-context-protocol-advanced-topics/296289) | sampling、notifications、roots、file access | 60 |  |  | 写一版 MCP 文件访问权限原则 |
| D48 | todo | Day 48 | [Anthropic: Model Context Protocol: Advanced Topics](https://anthropic.skilljar.com/model-context-protocol-advanced-topics/296289) | stdio、StreamableHTTP、state、production transport | 60 |  |  | 选型:本地开发工具用 stdio 还是 HTTP |
| D49 | todo | Day 49 | [Anthropic: Introduction to agent skills](https://anthropic.skilljar.com/introduction-to-agent-skills) | Skills 基础、SKILL.md、触发描述、目录结构 | 60 |  |  | 写一个需求访谈 Skill 草案 |
| D50 | todo | Day 50 | [Anthropic: Introduction to agent skills](https://anthropic.skilljar.com/introduction-to-agent-skills) | allowed-tools、多文件 skill、分享、troubleshooting | 60 |  |  | 写一套项目实施 skills 列表 |
| D51 | todo | Day 51 | [Anthropic: Introduction to subagents](https://anthropic.skilljar.com/introduction-to-subagents) | subagents、上下文隔离、任务委派 | 60 |  |  | 设计 researcher / implementer / reviewer 三个 subagent |
| D52 | todo | Day 52 | [Anthropic: Introduction to subagents](https://anthropic.skilljar.com/introduction-to-subagents) | specialized workflows、主对话清洁、测验和证书 | 60 |  |  | 写一版 subagent 使用边界和反模式 |
| D53 | todo | Day 53 | [L7-A: OpenAI Agent evals](https://platform.openai.com/docs/guides/agent-evals) | agent workflow evaluation | 60 |  |  | 设计一组 agent task eval |
| D54 | todo | Day 54 | [L7-B: OpenAI Working with evals](https://developers.openai.com/api/docs/guides/evals) | eval methodology and datasets | 60 |  |  | 写 eval dataset 结构 |
| D55 | todo | Day 55 | [L7-C: DeepLearning.AI Evaluating AI Agents](https://www.deeplearning.ai/courses/evaluating-ai-agents/) | agent evaluation practice 上半部分 | 60 |  |  | 写一版项目验收 eval |
| D56 | todo | Day 56 | [L7-C: DeepLearning.AI Evaluating AI Agents](https://www.deeplearning.ai/courses/evaluating-ai-agents/) | agent evaluation practice 下半部分 | 60 |  |  | 把 eval 映射到 Alex F3/F4 |
| D57 | todo | Day 57 | [L8-A: Anthropic Building Effective AI Agents resource](https://resources.anthropic.com/building-effective-ai-agents) | production-ready patterns 上半部分 | 60 |  |  | 摘出 5 个生产反模式 |
| D58 | todo | Day 58 | [L8-A: Anthropic Building Effective AI Agents resource](https://resources.anthropic.com/building-effective-ai-agents) | production-ready patterns 下半部分 | 60 |  |  | 写 Alex production gap list |
| D59 | todo | Day 59 | [L9-A: DeepLearning.AI Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | reflection | 60 |  |  | 记录 reflection 是否适合 Alex |
| D60 | todo | Day 60 | [L9-A: DeepLearning.AI Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | tool use | 60 |  |  | 复盘 tool risk 设计 |
| D61 | todo | Day 61 | [L9-A: DeepLearning.AI Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | planning | 60 |  |  | 写 planning 适用/不适用场景 |
| D62 | todo | Day 62 | [L9-A: DeepLearning.AI Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | multi-agent workflows | 60 |  |  | 设计 future agent team 草图 |
| D63 | todo | Day 63 | [L9-A: DeepLearning.AI Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | external tools、evaluation | 60 |  |  | 补齐 eval 和 tool telemetry |
| D64 | todo | Day 64 | [L9-A: DeepLearning.AI Agentic AI](https://www.deeplearning.ai/courses/agentic-ai) | optimization、course wrap-up | 60 |  |  | 写一页课程总复盘 |
| D65 | todo | Day 65 | Anthropic 课程复盘 | 证书整理、公开展示材料映射 | 60 |  |  | 更新课程证书记录和公开简介草稿 |
| D66 | todo | Day 66 | Anthropic + official docs 总复盘 | AI agent 应用方法论文档 | 60 |  |  | 输出一页:如何把业务问题建模成 AI workflow |

### 平台专项,按需替换主线中的复盘日

| 编号 | 状态 | 推荐时机 | 来源 | 主题 | 计划分钟 | 阅读完成时间_KST | 实际分钟 | 产出 / 笔记 |
|---|---|---|---|---|---:|---|---:|---|
| OPT01 | todo | 需要 AWS 接入时 | [Anthropic: Claude with Amazon Bedrock](https://anthropic.skilljar.com/claude-in-amazon-bedrock/276724) | Bedrock 上的 Claude 部署和企业集成 | 60 |  |  | 写 AWS 平台接入注意事项 |
| OPT02 | todo | 需要 GCP 接入时 | [Anthropic: Claude with Google Cloud's Vertex AI](https://anthropic.skilljar.com/claude-with-google-vertex/289151) | Vertex AI 上的 Claude 部署和企业集成 | 60 |  |  | 写 GCP 平台接入注意事项 |

---

## Check-in Template

复制一段到下面,每次学习结束后填写。

```md
### YYYY-MM-DD HH:mm KST - SOURCE_ID

- Status:
- Actual minutes:
- What I learned:
- Alex mapping:
- Open question:
- Next action:
```

---

## Check-ins
