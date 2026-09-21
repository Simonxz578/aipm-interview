# 模型选型、Eval、成本与 ROI

# 1. 模型选型不是看排行榜

流程：
1. 定义真实业务任务；
2. 建代表性Eval Set；
3. 确认约束；
4. 候选模型盲测；
5. 做质量/延迟/成本Pareto；
6. 选主模型；
7. 选fallback/failover；
8. 灰度；
9. 周期回归。

维度：
任务质量、reasoning、多模态、tool calling、structured output、context、latency、throughput、cost、stability、vendor/compliance、private deployment。

原则：
**能用小模型稳定完成，就不要为“最强模型”多付成本。**

# 2. 评测三层

## Offline
task set、rubric/golden answer、bad-case taxonomy、model comparison、trace grading。

## Online
completion、retry、fallback、user correction、latency、abandonment、edit acceptance。

## Business
retention、conversion、paid retention、productivity、cost、teacher adoption、learning outcome。

benchmark不能直接等于产品价值。

# 3. North Star vs Process

Agent北极星不要用“发送成功率”这种技术动作。

销售Agent例：
North Star：
有效商机回复率 / qualified meeting booked / 有业务价值的task success。

Process：
search precision、contact match、personalization、send success、reply、human edit、tool error。

# 4. 搜索准确率怎么定义

先明确任务：
- 找对文档？
- 找对候选人？
- 找到支持答案的证据？

可选：
precision@k、recall@k、MRR、human relevance、evidence coverage。

降低人评成本：
人工做gold set → rule/LLM预标 → 抽样人工校准 → disagreement进人工 → 定期重审rubric。

# 5. ROI

AI项目ROI = 增量价值 - 总成本。

总成本：
Token/API、GPU、人工审核、标注、工程、运维、错误成本、延迟造成的损失。

价值：
节省人时、提升转化、增加供给、提高留存/成功率、降低风险。

# 6. 92%→94%，但慢200ms

不要直接说“准确率更重要”。

看：
- 这2%是不是关键错误；
- 200ms是否用户可感知；
- 是否实时任务；
- 业务价值；
- 是否可分层路由。

方案可能是：
简单query小模型，复杂query强模型，高风险强模型，异步任务允许更慢。

最终在线实验看：
task success + latency + retention/conversion + cost。
