# AI 产品的六个层次
## 会用 AI coding 做东西，不等于会做 AI 系统

前者是：AI 帮你写代码。

后者是：你设计一个系统，让 AI 在用户使用时承担理解、判断、行动、记忆、协作和交付。

判断一个东西是不是 AI 产品，关键不看开发时有没有用 AI，而看用户使用时 AI 是否参与 runtime。

如果 AI 只在开发过程中帮你写代码，那是 AI-assisted building。

如果 AI 在产品运行时读取上下文、调用工具、做决策、执行任务，那才是 AI product / AI system。

AI 产品可以分成六个层次：

## 1. Prompt Wrapper：薄 AI 工具

用户输入 → prompt → LLM → 输出。

比如标题生成器、邮件润色器、简历优化器。

这是最基础的 AI 产品形式。它只是在产品里加入了一层文本生成能力，但通常没有真实上下文、业务状态、工具调用，也没有行动能力。

本质上，它只是：

Model as a feature

---

## 2. Grounded AI / RAG：带知识的 AI 应用

AI 能检索文档、知识库、数据库，再基于资料回答。

比如公司知识库助手、课程助教、客服 FAQ。

这类应用的核心不再只是“写得更像人”，而是让模型能够访问真实资料、业务信息和用户上下文。

典型结构：

用户问题
→ query rewrite / intent detection
→ 检索知识库 / 数据库
→ rerank / filter
→ 拼接上下文
→ LLM 生成答案
→ citation / source tracking

它的本质是：

AI knows more, but still mostly answers.

它比单纯 prompt wrapper 强很多，但大多仍然主要是回答型 AI，而不是替你做事。

---

## 3. Tool-using AI：能调用工具的 AI 应用

AI 不只是回答，还能调用 API、查日历、读邮件、更新 CRM、生成文件。

这时，AI 不再只是“说”，而开始“做”。

典型结构：

用户目标
→ LLM 判断需要什么工具
→ function call / API call
→ 获取结果
→ 继续回答或执行下一步

这类系统通常具备：

- tool schema
- function calling
- API integration
- auth / permission
- parameter validation
- confirmation before action
- error handling

它的本质是：

Model as an interface to tools

它开始有“手脚”了，但很多时候仍然只有一次性的工具调用，没有循环执行、长期状态和复杂规划。

---

## 4. LLM Workflow：固定流程里的 AI

AI 被放进一个可控业务流程中，按步骤完成分类、检索、判断、生成、审批、执行。

这不是完全自主的 agent，而是一套事先设计好的流程。程序员把流程拆好，LLM 在其中扮演某一节点的角色。

例如：

1. 判断任务类型
2. 检索相关资料
3. 抽取关键信息
4. 调用业务 API
5. 生成建议方案
6. 人类确认
7. 执行动作
8. 记录日志和评估结果

它的本质是：

AI inside a controlled process

这通常是企业落地 AI 的主战场，因为它比完全自主 agent 更稳定、更可控。

---

## 5. Agentic Core：真正的智能体核心

AI 能 plan → act → observe → update state → continue / stop，自主决定下一步并循环执行。

这是真正意义上的 agent。

它不再是固定 pipeline，而是一个循环：

Goal
→ Plan / Reason
→ Choose tool
→ Act
→ Observe result
→ Update state
→ Continue / Stop / Ask human

关键组件包括：

- planner / reasoner
- tool registry
- memory / state
- RAG / grounding
- execution loop
- evaluator / verifier
- guardrails
- human handoff
- tracing / logs
- retry / fallback
- stop condition

它的本质是：

Model as a controller

也就是说，模型不只是生成内容，而是在控制任务执行。

---

## 6. AI-native Product / System：真正落地的 AI 系统

AI 有低摩擦交互、上下文智能、记忆、权限、主动触发、评估、guardrails 和 runtime，成为产品或组织的智能层。

这不是单个 agent，而是一整套 AI-native 产品系统。

它需要三类能力：

### 1) Frictionless interaction

AI 融入用户原本的工作流，而不是让用户专门打开一个聊天框。

例如：

- chat
- voice
- command palette
- browser extension
- inline edit
- sidebar
- one-click apply
- approval UI
- undo / review
- human-in-the-loop

### 2) Contextual intelligence

AI 能获取用户上下文、记忆、权限和数据流，而不是每次都让用户重头喂资料。

例如：

- user profile
- workspace context
- conversation state
- documents
- emails
- calendar
- CRM
- tickets
- RAG
- entity graph
- long-term memory
- permission filtering
- source tracking

### 3) Proactive intelligence

系统能根据事件主动触发，而不是永远等用户提问。

例如：

- cron jobs
- event triggers
- webhooks
- monitoring
- notification queue
- agent runner
- approval policy
- action queue

它的本质是：

AI 不再是一个功能，而是系统的智能层。

这才是最完整的 AI-native product / system。

---

# 人的 AI 能力分成四档

## L3：The AI Consumer
关键词：Chatting

这是大多数人的阶段。

你把 AI 当成更聪明的 Google 或耐心的咨询师，主要是消费模型输出。

典型行为：

- 提问题
- AI 给答案
- 自己判断是否可用
- 不满意就重试或换问法

本质上：

把 AI 当咨询师。

---

## L4：The AI Tinkerer / Vibe Coder
关键词：One-off

你可以用 AI coding 做 demo、小工具、脚本、网页。

但通常停留在 happy path，容易出现：

- 数据简单
- 用户只有自己
- 报错不严重
- 不需要长期维护
- 不需要复杂权限和稳定运行

它能解决个人小问题，但很难承担职场中的高风险任务。

本质上：

把 AI 当外包。

---

## L5：The AI Builder
关键词：Reliability & Iteration

这是职业选手和业余玩家的分界线。

L5 不是“生成一个 demo”，而是“构建一个可靠 workflow”。

你开始关注：

- 如何拆解复杂任务
- 如何为每一步定义输入和输出
- 如何让 AI 和代码分别完成不同工作
- 如何接入知识库和业务数据
- 如何设计 prompt 和 structured output
- 如何评估质量
- 如何通过迭代提高稳定性
- 如何在关键环节加人工确认

核心能力包括：

### 1) Context Engineering
上下文不是越多越好，而是要在正确时间看到正确的信息。

### 2) Evaluation
不能只看“我觉得还行”，而要定义质量标准，并不断验证结果。

### 3) Iterative Mindset
AI 系统是需要迭代优化的，而不是一次性生成完毕。

本质上：

把 AI 当逻辑引擎。

---

## L6：The AI Architect
关键词：Orchestration & Integration

L6 不再只是“用 AI 做工具”，而是设计一个真实世界里能长期运行的 AI architecture。

它关注的不是单次输出，而是整个系统如何长期运行、如何协同、如何评估、如何安全地执行。

核心包括：

- multi-model routing
- single-agent / multi-agent orchestration
- tool registry
- RAG / GraphRAG / Agentic RAG
- short-term state
- long-term memory
- transactional memory
- permission system
- human handoff
- guardrails
- evals
- tracing
- runtime
- proactive triggers

本质上：

把 AI 当系统架构的一部分。

---

# L3 到 L6 的本质变化

- L3：我会问 AI。
- L4：我会让 AI 帮我做一个东西。
- L5：我会把 AI 放进一个可靠流程。
- L6：我会设计一个 AI 驱动的系统。

真正的壁垒不在“会不会调模型”，而在：

能不能把模型放进真实工作流，并让它稳定、可控、可评估、可迭代、可主动运行。

---

# 重新理解 “AI coding” 和 “AI product”

很多人会用 AI coding 做一个网页、一个小插件、一个脚本、一个工具。它当然有价值，但它不一定是 AI product。

如果 AI 只参与开发阶段，那它只是：

AI-assisted building

如果 AI 在产品运行时参与理解、判断、行动，那才是：

AI product / AI system

同样是“浏览器工具”，它可能只是一个 demo，也可能是一个完整的 AI research agent；区别不在 UI，而在 AI runtime 的深度。

---

# 一个实用判断框架

判断一个 AI 项目属于哪一层，可以问这些问题：

1. AI 是否只在开发时参与？
2. 用户使用时，AI 是否参与？
3. AI 是否只是一次性生成文本？
4. AI 是否接入了外部知识和业务上下文？
5. AI 是否能调用工具或 API？
6. AI 是否被嵌入稳定业务流程？
7. AI 是否能决定下一步、循环执行、观察结果并调整？
8. AI 是否有 memory、permission、guardrails、evals、handoff、runtime？
9. AI 是否能根据事件主动触发？
10. AI 是否成为个人或组织工作系统的一部分？

如果是，这就不再只是“会用 AI”，而是“正在构建 AI system”。

---

# 结论

AI 时代的能力分层，不是“谁会用最新工具”，而是“谁能设计可靠系统”。

- L3 消费 AI
- L4 调动 AI
- L5 驯化 AI
- L6 架构 AI

从 L3 到 L4，是从聊天到创造。

从 L4 到 L5，是从 demo 到可靠 workflow。

从 L5 到 L6，是从 workflow 到系统架构。

真正的终点不是“我会用 AI”，而是：

我能设计一个 AI 系统，让它在真实世界里可靠地替我工作。
