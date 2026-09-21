# AI PRD Template

## 0. 基本信息
产品/功能：
版本：
Owner：
日期：
关联BRD/数据：

## 1. 背景
### 1.1 业务现状与问题
### 1.2 用户/客户
### 1.3 为什么必须用AI
人工/规则/搜索/传统ML替代方案：
AI不可替代性：
失败容忍度：
ROI假设：
### 1.4 竞品
### 1.5 业务目标
### 1.6 模型/系统目标

## 2. Scope
### P0
### P1
### P2
### Out of scope
### Frozen baseline

## 3. 用户流程
用户 → 输入 → AI反馈 → 用户下一步 → 结果

## 4. 系统流程
Input
→ Pre-process
→ Context / RAG
→ Router
→ Model / Agent
→ Tool
→ Validation
→ Output
→ Feedback / Logging

异常分支：
人工节点：
权限确认：

## 5. AI架构
Prompt：
RAG：
Workflow：
Agent：
Multi-Agent：
Skill：
MCP/Tools：
Harness/runtime：
Model：
Fallback/failover：

## 6. 模型选型
Eval set：
候选模型：
质量：
Latency：
Cost：
Context：
Multimodal：
Tool calling：
Structured output：
主模型：
备用模型：
重新评测周期：

## 7. Prompt / Skill
版本：
角色：
边界：
输出Schema：
Few-shot：
禁止项：
Skill触发：
references/scripts：
变更后回归要求：

## 8. 数据
输入数据：
PII：
知识源：
权限：
埋点：
显式反馈：
隐式反馈：
Good Case：
Bad Case：

## 9. Eval
### Offline
### Online
### Business
### Education/Learning（如适用）
### Guardrail
Release Gate：

## 10. UX
Loading/streaming：
不确定性：
Citation：
Edit：
Retry：
Regenerate：
Confirmation：
Human handoff：
Error：

## 11. Cost / ROI
Token/API：
GPU/infra：
人工：
标注：
维护：
错误成本：
业务价值：
单次成功任务成本：

## 12. Rollout
Internal
→ Alpha
→ Gray
→ A/B
→ Full

每阶段：
流量：
周期：
目标：
Guardrail：
晋级条件：

## 13. Rollback
触发：
步骤：
恢复版本：
影响范围：

## 14. AI能力边界
能做：
不能做：
已知缺陷：
本版不修：
必须人工确认：

## 15. 风险
模型：
安全：
隐私：
合规：
成本：
依赖：
组织采用：
未成年人/教育：

## 16. 数据飞轮
用户行为
→ Bad Case
→ 分类
→ Eval更新
→ 根因
→ Prompt/RAG/Model/UX优化
→ 回归
→ 灰度
