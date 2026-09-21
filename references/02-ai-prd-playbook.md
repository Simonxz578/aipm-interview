# AI 产品 PRD Playbook

本文件根据用户上传的《大模型产品模板 PRD》（14页）和林木视频整理。

# 1. 背景

## 1.1 业务背景
写清：
- 当前业务现状
- 用户/组织痛点
- 数据证据
- 机会
- 需求来源：业务价值 / 用户体验 / 问题修复

## 1.2 为什么用大模型
这是AI PRD最重要的新增问题。

必须比较：
- 人工
- 规则引擎
- 搜索
- 传统ML
- LLM / 多模态模型

回答：
- 传统方案局限
- LLM不可替代性
- 效果、成本、覆盖、体验、扩展性
- 失败是否可控
- ROI

## 1.3 竞品
不要只列功能。
至少对比：
目标用户、技术路线、模型、核心差异、效果、商业模式/价格（如公开）。

## 1.4 产品目标

### 业务目标
如问题解决率、转化、留存、人均效率、成本。

### 模型/系统目标
如任务成功率、回答正确率、格式遵循、hallucination、tool call success、交互轮数、latency。

模型目标必须解释如何影响业务目标。

# 2. 需求描述

## 2.1 需求清单
P0/P1/P2。
每项写需求点、优先级、描述、依赖。

## 2.2 分类

### 功能
语言理解、生成、多模态、工具调用等。

### 性能
首Token、P95、QPS、并发、可用性。

### 安全
隐私、加密、权限、数据出境、审计、内容安全。

### 数据
- 埋点：执行链路/用户操作
- 正负Case：接受/修改/拒绝
- 业务数据：是否创造真实价值

# 3. 业务流程
用户视角：
用户做什么 → 系统反馈 → 用户下一步。

# 4. 系统流程

必须标：
- LLM节点：模型/任务/延迟
- Tool节点：API/外部系统
- Route：分类/条件
- Human：确认/审核
- Error：超时/无结果/格式错误/权限失败

Agent项目额外：
state / memory / checkpoint / stop condition。

# 5. 模型选型

原则：
**先用业务Eval测，再谈哪个模型强。**

约束：
- 单次成本
- 首Token/总延迟
- context
- multimodal
- tool calling
- structured output
- QPS
- 部署
- 数据安全
- 商用许可
- 微调能力

重要原则：
**效果相似时优先小模型。**

节点级选型：
- 路由：小模型/规则
- 抽取：小模型
- 复杂推理：强模型
- 验证：规则/另一个模型

定义：
主模型、备用模型、failover、周期回归。

# 6. Prompt工程

Prompt是产品交付物。

## System Prompt
- Role
- Boundary
- Output
- Core instructions
- Safety/prohibited

## 策略
Few-shot、结构化输出、标签分区、任务拆解、自检、工具说明等按需使用。

## 版本
version / change / eval score / status / date。

硬规则：
**Prompt变更 → 回归评测 → 达标 → 灰度。**

# 7. 训练/知识数据

SFT/RAG按需记录：
- 知识数据
- 参考示例
- 约束
- Good Case
- Bad Case

数据源应有：
owner / freshness / permission / provenance。

# 8. 评测

## 数据来源
- PM人工
- 真实用户query
- LLM生成+人工筛
- 线上Bad Case

## 覆盖
可参考：
核心70%、边界20%、对抗5%、安全5%。
最终尽量接近真实流量和业务风险。

## 规模
MVP几十到百级，灰度百级，全量持续扩充。
不是固定数字，风险越高越严格。

## 维度
accuracy、completeness、relevance、grounding、format、safety、style、latency、cost。

安全可一票否决。

## 执行
- PM手工
- 专业人工
- LLM-as-Judge（需校准）
- 自动规则

## 触发
Prompt修改、模型升级、新功能、Bad Case累计、周期回归。

# 9. 效果保障与稳定性

## 输出质量
Schema、parser/validator、retry、post-processing、rule checks。

## 幻觉
RAG、citation、cross-check、confidence/abstain、human confirmation。

## 稳定性
timeout、retry、failover、rate limit、cache、circuit breaker、fallback、logging/tracing。

## 一致性
Temperature/Top-p/Seed（如支持），关键事实外置到规则/Tool。

# 10. AI原型交互

必须设计：
loading/streaming、uncertainty、retry、regenerate、edit、feedback、citations、tool action confirmation、human handoff。

# 11. 能力边界
明确：
- 能做
- 不能做
- 已知缺陷
- 本版不修
- 人工确认条件

# 12. 数据飞轮

用户使用
→ 行为/反馈
→ Bad Case
→ 分类
→ Eval更新
→ 归因
→ Prompt/RAG/Model/UX优化
→ 回归
→ 发布

收数据本身不叫飞轮。

# 13. 上线

## 灰度/AB
流量、时长、核心指标、guardrail、进入下一阶段条件。

## 成本
Token、API、GPU、人工审核、单次成功任务成本。

## 回滚
触发条件、版本、流量切换、用户影响、数据兼容。

# 14. 风险
模型、隐私、安全、业务、成本、依赖、组织采用、教育/未成年人。
每项写概率/影响/mitigation/owner。
