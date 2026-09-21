# 深技术面试补充：多模态、RL、World Model、Auto Research、Serving

# 1. 多模态模型：产品经理需要理解到什么程度

典型视觉语言模型：
图像/视频
→ 视觉编码器
→ patch / visual tokens
→ projector / adapter / unified representation
→ 语言模型
→ 文本/动作输出

训练常包括：
- 图文预训练
- 多模态指令对齐
- 偏好/安全对齐

产品边界：
擅长语义理解与跨模态关联；
对精确尺寸、复杂空间关系、小字、计数、细节定位可能不稳定。

因此：
开放视觉理解可以用VLM；
精确尺寸/坐标/工业规则应配OCR、检测器、数据库或规则校验。

# 2. 强化学习三要素

最简：
State：当前环境状态
Action：Agent采取的动作
Reward：动作之后获得的反馈

策略目标：
学习在不同State下选择Action，使长期累计Reward更高。

产品经理不需要推导RL算法，但要能问：
- state是否完整？
- action空间是否安全？
- reward有没有被钻空子？
- delayed reward怎么处理？
- 探索会不会伤害真实用户？

# 3. World Model

核心直觉：
学习环境动态，预测：
当前状态 + 动作 → 下一个状态/观察。

在视频/机器人场景中也可以理解为：
根据历史和动作预测未来帧、未来状态或潜在表示。

产品价值：
- 模拟
- 规划
- 机器人控制
- 低成本试错
- 长时任务预测

边界：
预测世界不等于完全理解世界；
错误会随长预测链累积；
现实安全仍需真实传感器、规则和控制器。

# 4. Auto Research：算法迭代型

如果面试官说“Auto Research不是学生找导师，而是算法迭代”，可以这样理解：

目标：
自动提出实验假设、改代码/配置、运行实验、读取指标、比较基线、保留有效变化、回滚无效变化。

工作流：
Research goal
→ 读取代码/论文/历史实验
→ 生成候选假设
→ 排实验优先级
→ 修改代码/超参
→ sandbox运行
→ 收集metric/log
→ 与baseline比较
→ reviewer判断
→ commit/rollback
→ 写实验记忆
→ 下一轮

产品要定义：
- 可修改范围
- compute budget
- metric
- significance / minimum improvement
- stop condition
- rollback
- reproducibility
- human approval gate

核心风险：
reward hacking、过拟合benchmark、实验不可复现、成本爆炸、代码破坏、安全。

# 5. Serving

常见形态：
- 公有云API
- 专有部署/VPC
- 自托管GPU
- 端侧模型
- 混合路由

产品选择看：
数据敏感度、延迟、成本、QPS、模型能力、更新速度、运维能力。

# 6. 推理速度

可从：
- 更小模型
- 模型量化
- KV cache
- prompt caching
- batching
- speculative decoding
- 减少上下文
- 路由
- streaming
- async tool calls

产品经理重点不是背优化算法，而是知道：
哪些用户场景对首Token敏感；
哪些异步任务能换质量；
性能改动是否影响准确率/成本。

# 7. Quantization

把权重/激活从高精度压到低精度，如FP16→INT8/INT4。

收益：
内存降低、吞吐提升、端侧可部署。

代价：
部分任务质量下降，尤其复杂推理/小模型。

产品决策：
用真实业务Eval比较“质量损失是否换来值得的成本/延迟收益”。

# 8. Data Drift

线上输入分布发生变化，导致原来的模型/规则/Eval不再代表真实用户。

监控：
- 输入类型
- 长度
- 语言
- 用户群
- 设备
- 场景
- 错误类型
- 业务标签

AI应用还要关注：
模型供应商更新造成的“model drift”。

# 9. Feature Engineering

在深度模型时代仍有价值：
- 业务标签
- 检索metadata
- ranking features
- risk signals
- user state
- routing
- fraud/safety
- structured context

产品经理需要知道哪些业务信号值得结构化，而不是所有内容都塞自然语言。

# 10. API / Function Calling / Structured Output

API输入通常：
model + messages/input + tools + generation config。

Function/Tool Calling：
模型选择工具并生成结构化参数，真正执行由系统完成。

Structured Output：
按Schema约束输出，减少parser失败。

产品风险：
- tool误调用
- 参数错
- 权限
- 重复执行
- idempotency
- timeout
- confirmation
- audit

面试中要把“模型决定调用”与“系统实际执行动作”区分开。
