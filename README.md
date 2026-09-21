# aipm-interview

一个面向 **AI 产品经理业务面** 的自适应面试 Skill。

它不是“AI八股题库”，而是把：

- 产品判断
- Prompt
- RAG
- Workflow / Agent / Multi-Agent
- Skill / MCP / Harness
- AI PRD
- 模型选型
- Eval / Bad Case
- 成本 / ROI
- 教育 AI / 学习机 / AI Tutor
- 字节 / 火山引擎 / 腾讯 CSIG

组织成一套可以迁移到陌生业务题的回答系统。

## 核心方法

**Problem → People → AI Fit → Architecture → Control → Proof → Economics → Iteration**

回答先从业务和用户进入，再决定 AI 应该出现在哪里；不会为了显得技术先进而强行使用 Agent / Multi-Agent。

## 推荐用法

- `用 aipm-interview 模拟腾讯教育AI产品一面，一次一道题。`
- `根据这个字节火山引擎JD做业务研究，再出12道高概率题。`
- `面试官问Claude Code Harness是什么，给我30秒和2分钟版本。`
- `这是我的回答，不要安慰我，按业务面标准拆。`
- `给我一道作业帮学习机低龄儿童AI场景题，连续追问三层。`
- `把Ninefold Physics整理成3分钟项目深挖答案。`
- `为这个Agent写AI PRD并定义release gate。`

## 文件

- `SKILL.md`：Skill主入口和路由
- `SYSTEM_PROMPT.md`：完整面试教练系统提示
- `references/00-source-dossier.md`：PRD与面经整理
- `references/01-adaptive-framework.md`：自适应业务通解
- `references/02-ai-prd-playbook.md`：AI PRD方法
- `references/03-prompt-rag-agent-skill-harness.md`：技术深挖
- `references/04-evals-model-selection-roi.md`：模型选型、评测、成本
- `references/05-candidate-profile.md`：Simon个人证据
- `references/06-byte-volcengine.md`：字节/火山引擎
- `references/07-tencent-csig.md`：腾讯CSIG/腾讯教育
- `references/08-education-aipm.md`：教育AIPM场景
- `references/09-answer-bank.md`：高频答案骨架
- `references/10-question-bank.md`：214道业务/AI/教育/产品题
- `references/11-industry-theses.md`：行业观点库
- `references/12-web-research-baseline.md`：网页研究基线
- `references/13-deep-ai-topics.md`：多模态/RL/World Model/Auto Research等
- `references/14-adaptive-training-loop.md`：弱点标签与训练闭环
- `references/15-prd-source-extract.md`：上传PRD完整结构化整理
- `references/16-video-skill-semantic-transcript.md`：Skill视频完整语义稿
- `references/17-video-prd-semantic-transcript.md`：PRD视频完整语义稿
- `templates/ai-prd-template.md`
- `templates/mock-interview-scorecard.md`

## Source note

两个视频的文本基于用户上传录屏的 **可见字幕、页面内容和用户提供的文字材料** 进行完整语义重建。

当前环境没有独立的中文语音转写模型，因此它们不应被标记为“逐字音频转录”；核心观点、结构和可见字幕内容已保留。

## Design principle

模型能力越强，AIPM 面试越不应该只背模型概念。

真正的产品能力是：

> **把不确定的模型能力，转化成可控、可评测、可运营、能产生业务结果的产品系统。**
