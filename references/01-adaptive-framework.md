# AIPM 自适应通解：从模型能力到业务结果

# 1. 先识别问题层级

## 用户/业务
问为什么做、给谁做、为什么不用、指标为什么掉：
先讲用户与业务，不要先讲模型。

## AI Fit
问为什么AI、规则能不能做：
先比较人工/规则/传统ML/LLM。

## AI Productization
问怎么稳定、怎么失败回退：
讲状态、交互、规则、fallback、eval。

## Agent Architecture
问Agent/Multi-Agent/Tool/Harness：
讲state/action/tool/loop/harness。

## 商业化/ROI
问值不值得、自建还是API：
讲单位经济性和业务结果。

# 2. AI适配性

强判断句：

> 模型刚获得什么能力 → 哪类用户任务能容忍当前不确定性 → 如何嵌入工作流 → 如何定义状态、动作、失败 → 如何用真实反馈逐步扩大自主权。

看：
- 输入是否开放/多模态；
- 规则能否穷举；
- 输出是否允许弹性；
- 失败是否可发现和修复；
- 是否有反馈；
- 是否高频重复；
- ROI是否成立。

# 3. 产品学习循环

模型能力
→ 企业吸收
→ 工作流重构
→ 用户行为
→ 数据与评测
→ 产品/模型迭代

谈数据飞轮必须具体：
收什么 → 谁标 → 怎么归因 → 改哪层 → 如何回归 → 什么指标证明变好。

# 4. AI Native

AI Native不等于所有东西交给AI。

高阶认知：
- 接受概率输出；
- 自然语言成为接口；
- 流程可动态变化；
- 模型做模糊判断，程序做确定事实；
- 状态、权限、责任、回退可观察；
- 质量门槛靠eval；
- 随模型能力升级重新划边界。

一句话：
**AI Native 是重新设计谁判断、谁执行、谁负责、怎么验证。**

# 5. Frozen Baseline：Vibe Coding产品化

MVP：最小变化是什么？  
Frozen：什么绝对不能动？  
Reuse：旧资产、Git history、组件、Skill能复用什么？  
Boundary：模型只做擅长的模糊判断。  
Change Set：一次一个变化。  
Acceptance：怎样算完成？  
Release Gate：没达到什么绝不发布？  
Token ROI：不会改变模型决策的上下文，不重复发。

Ninefold真实教训：
本来只需改变旧世界与Physics的连接，却让Agent获得重新实现旧视觉的自由，导致旧资产重复生成、质量下降、Token浪费。

正确写法：
Objective → Source of truth → Frozen → Change → Acceptance → Deploy gate。

# 6. 开放题：先宏观再下钻

例如Push：
宏观拆：
- 供给/内容
- 人群
- 时机
- 频控
- 触达形式
- 个性化
- 落地承接
- 实验反馈

然后选最关键一项讲深，而不是直接跳Prompt。
