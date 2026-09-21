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

# 4. 下一题选择

优先：
最高弱点标签 × 不同业务场景。

例：
用户在Ninefold题里“指标定义”弱；
下一题不要再问Ninefold，
改问腾讯企业Agent或广告素材的北极星指标。

目的：
验证能力能否迁移，而不是背案例。

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
4. 90秒修正版
5. 下一轮训练目标

不要输出十条空泛建议。
