# Prompt / RAG / Agent / Skill / Harness：面试深挖

# 1. Prompt

Prompt是某个模型调用节点的行为规格：
角色、任务、上下文、约束、输出、示例、边界。

高分点：
先任务和Eval → 写Prompt → Good/Bad Case → 版本化 → 灰度 → 回归。

Prompt什么时候不够：
- 实时/私有知识 → RAG
- 执行动作 → Tool/Agent
- 长流程 → Workflow/Harness
- 高频稳定行为 → 可考虑SFT
- 复用专业流程 → Skill

# 2. RAG

RAG不是“让模型更聪明”，而是补：
私有知识、新知识、可引用事实、训练集外上下文。

链路：
source → parse → clean → chunk → metadata → embedding/index → query rewrite → retrieve → rerank → context → answer → citation → feedback

失败：
文档解析、chunk、query mismatch、recall不足、top-k噪声、rerank、知识过时/冲突、权限泄漏。

指标：
retrieval recall@k / precision / MRR / nDCG（按需）
answer faithfulness / correctness / citation / abstention。

Agentic RAG：
Agent决定是否检索、改写query、换source、多轮检索、验证证据。
多文档和复杂条件适合；简单FAQ不要过度Agent化。

# 3. LLM Wiki vs RAG

传统RAG：
原始文档 → chunks → query-time retrieve。

LLM Wiki：
原始文档 → ingest阶段整理成结构化、链接知识页 → Agent search/read/traverse → 必要时结合retrieval。

适合：
长期团队知识、概念关系、多跳问题、持续维护/版本控制。

风险：
ingest错误固化、更新冲突、压缩丢细节。
必须保留provenance和原文回查。

# 4. Agent

Chat：
输入 → 输出。

Agent：
围绕目标维护状态：
观察 → 决策 → 调工具/行动 → 结果 → 更新状态 → 继续，直到完成/失败/人工。

Agent PRD最少定义：
Goal / State / Action / Tools / Memory / Permissions / Stop / Human handoff / Error / Eval。

# 5. Multi-Agent

先回答为什么单Agent不够。

合理：
- 专业化
- 上下文隔离
- 权限隔离
- 并行
- 独立Reviewer
- 不同模型成本分层

不合理：
“听起来更高级”。

Main/Sub通讯优先结构化contract：
status / evidence / score / risk_flags / next_action。
避免随意长文本。

# 6. Skill

Skill不是更长Prompt。

Skill是一套：
- 可触发
- 可复用
- 可版本化
- 渐进式加载
的专业SOP，可带instructions/scripts/resources。

面试回答：
“Prompt是一次调用里的指令；Skill更像岗位SOP。Agent先通过name/description判断是否需要，再按需加载核心指令和references/scripts。它解决长Prompt占上下文、跨场景反复写规则、专业流程不稳定的问题。”

值得Skill化：
高频重复 + 稳定步骤 + 专业标准 + 固定资源/工具 + 临时Prompt容易漂。

# 7. Skill vs MCP

Skill：怎么做。
MCP/Tool：能访问/执行什么。

例：
MCP给GitHub访问能力；
Skill规定团队如何review PR。

# 8. Harness

一句话：
**Harness是Agent的执行操作系统。**

模型提供推理；
Harness管理：
Context、Tools、Files、Sandbox、Permissions、Memory、Checkpoint、Retry、Subagents、Observability、Eval、Long-running lifecycle。

Claude Code/Codex强不只来自模型，而是模型被放进能读文件、改文件、跑命令、看测试、持续修正的Harness。

面试回答：
“如果只有强模型没有Harness，长任务会在上下文、工具执行、权限和失败恢复上失控。Harness把一次模型调用变成可持续执行的Agent系统。”

# 9. Workflow / Agent / Harness

Workflow：路线大体写死。
Agent：运行时决定路线。
Harness：让Agent/Workflow可靠执行。

# 10. MCP产品关注点

Tool description、input schema、permission、confirmation、error、latency、rate limit、audit。

# 11. Skill + MCP + Harness类比

Model：大脑  
Prompt：当前任务说明  
RAG：资料库  
Skill：岗位SOP  
MCP/Tools：能用的系统和工具  
Harness：工作环境和管理制度  
Eval：质量检查
