# 自适应训练闭环

# 1. 为什么需要闭环

题库只能提高熟悉度。
真正目标是把弱点迁移到不同业务题里反复训练，直到用户能在陌生题里稳定做出判断。

# 2. 每轮记录

记录：
- company
- role
- round
- question
- user_answer
- score
- weak_tags
- unsupported assumptions
- missing metrics
- missing boundary
- revised_answer
- next_drill
- primary_story / supporting_evidence
- target_competencies
- answer_depth
- behavioral_checks（行为题时记录）

# 3. 弱点权重

每个标签维护0–5：

0 = 未观察
1 = 基本稳定
2 = 偶尔遗漏
3 = 明显弱点
4 = 高风险
5 = 连续多次失败

标签：
business_goal
user_segmentation
ai_fit
model_selection
prompt
rag
agent
multi_agent
skill
harness
data_flow
eval
metric_definition
cost_roi
fallback
prd
education_pedagogy
b2b_adoption
communication

行为能力标签：
demanding_goal
leadership
analysis_planning
influence
collaboration
innovation
prioritization
learning_agility
ownership
reflection
story_specificity
result_evidence

八类能力定义见[答案组织与深度](18-interview-answer-architecture.md)，选故事见[候选人故事库](19-candidate-story-bank.md)。未观察到某项记为未观察，不自动判弱。

# 4. 下一题选择

优先：
最高弱点标签 × 不同业务场景。

例：
用户在Ninefold题里“指标定义”弱；
下一题不要再问Ninefold，
改问腾讯企业Agent或广告素材的北极星指标。

目的：
验证能力能否迁移，而不是背案例。

保留最近两题的主案例。如果连续两次用同一案例，下一题优先要求换一个案例；面试官主动深挖时继续原故事。不要为避免重复强行编造另一段经历。

# 5. 难度层级

L1：定义/基础判断  
L2：单一业务场景  
L3：加入数据与冲突  
L4：加入成本、技术边界、跨团队  
L5：压力追问/反事实/信息不完整

得分85+自动升一级。
连续两题<70降一级并集中弱点。

# 6. 复习

同一弱点：
当天：不同场景再练1次
2–3天：重新抽题
7天：压力追问
14天：公司定向实战

# 7. 不要形成“答案依赖”

每隔3题至少1题：
- 新行业
- 无模板数据
- 要求先提澄清问题
- 或必须拒绝AI方案、选择规则/人工

# 8. 结束一轮的输出

只给：
1. 当前分数
2. 最强一项
3. 最弱两项
4. 符合本题深度的修正版；用户指定90秒时按90秒
5. 下一轮训练目标

不要输出十条空泛建议。

## 9. 行为题的附加诊断

在原产品能力评分之外记录以下六项为“有证据 / 部分 / 缺失”，各用一句指出依据，不另造混淆原总分的加权分数：

| 项目 | 观察内容 |
| --- | --- |
| 具体例子 | 是否有事件、困难与行动，而非性格宣言 |
| Action主导 | 行动、原因、调整是否占50%–65%；不足50%则修订 |
| ownership | 自己做了什么、团队做了什么、谁决定什么 |
| Result证据 | 数字范围、来源、交付成果及局限是否明确 |
| Reflection | 有无真实判断变化与重做建议，是否冒充已完成改进 |
| target role迁移 | 是否解释了这段经历对目标岗位具体问题的价值 |

优先训练最高的1–2项弱点，换场景或案例后检验。缺乏事实证据属于result_evidence/story_specificity缺口，先补证据或换故事，不能编造结果。Action占比只作表达诊断，不能替代行动质量。
