# 教育 AIPM 场景答案

# 1. 小学生英语口语应用

目标不是“让孩子跟AI多聊”，而是让孩子在可承受难度下持续开口并形成可观察进步。

交互：
示范 → 跟读 → 一次一个纠错 → 再说 → 小情境迁移 → 总结。

Prompt/Agent输入：
年龄、等级、本轮目标、已掌握内容、ASR confidence、最近错误。

规则：
- 每轮一句
- 一次只纠一个重点
- 语言短
- 具体鼓励
- 连续失败降难
- ASR低置信度不把识别错误当学生错误

指标：
开口率、speaking turns、completion、correction uptake、迁移表现、ASR失败率、D7（辅助）、learning gain（长期）。

# 2. 教育AI如何保证正确性

Prompt只是一层。

课程范围
→ 权威知识/RAG
→ Structured Output
→ 计算器/规则/代码
→ second-pass verifier
→ confidence/abstain
→ 高风险人工复核
→ Bad Case回归。

物理里公式、数值、单位、方向尽量确定性校验。

# 3. 学生水平不同怎么自适应

维护student state，而不是每次从0猜。

state：
知识点mastery、misconception、reading level、response latency、hint dependency、recent success。

调整：
词汇、句长、问题开放度、提示层级、数值复杂度、情境复杂度。

每次答题更新状态，不永久贴标签。

# 4. 害羞孩子不说话

沉默是一种状态，不是失败。

梯度：
等待 → 二选一 → 跟读一个词 → TTS示范 → 点击/图片替代 → 再邀请语音。

避免倒计时压迫、负面评价、连续逼问。
区分孩子沉默和ASR没收音。

# 5. “这条线/那个点”指代不清

共享视觉上下文：
- 对象结构化为object IDs
- 触摸/鼠标/手写笔坐标是强信号
- 结合当前视图、最近操作、对话历史做grounding
- 低置信度就反问

例：
“你说的是左边斜线AB，还是右边竖线CD？”

# 6. AI批改论文

先定：formative feedback还是正式summative grade。

正式高风险：
模型不单独决定最终成绩。

流程：
rubric → criterion evidence → score suggestion → confidence → consistency check → human moderation / appeal。

指标：
与多位教师评分一致性、criterion accuracy、evidence grounding、群体bias、appeal overturn rate。

# 7. 教师AI资源产品

优先高频耗时任务：
课程范围找资源 → 改成适合本班 → 生成练习/课件 → 教师编辑 → 课堂使用 → 反馈。

核心：
curriculum、teacher control、provenance、editable output、class context、reuse。

# 8. 资源推荐不准

先拆“不准”：
主题、年级、难度、风格、班级适配、时效。

再定位：
metadata、retrieval、ranking、teacher profile、intent、cold start。

可改：
标签/课程图谱、query rewrite、hybrid retrieval、rerank、teacher feedback、class profile、save/use signals。

评测：
offline relevance + online save/use/edit + repeat usage。

# 9. 学习辅助vs防抄袭

按模式：
- 练习：优先提示/追问
- 检查：学生先交自己的过程，再看解析
- 复习：可完整讲解
- 高风险作业：限制直接答案并保留过程

指标：
独立作答比例、hint-to-success、复制行为、迁移题表现。

# 10. AI Tutor满意度高但续费低

“回答好”不等于付费价值。

拆：
高频需求？免费替代？学习结果可感知？家长看到价值？付费权益差异？考试季低频？

不要先优惠，先找持续付费理由。

# 11. 学习机为什么需要硬件

硬件价值：
- 专注环境
- 家长控制
- 书写/摄像头/麦克风
- 连续学情
- 内容授权
- 端侧/低延迟
- 线下渠道
- 学习场景一体化

这些都不成立时，App可能更合理。

# 12. A-Level / IB / AP 共用Tutor还是拆

底层可共用：
对话、状态、Agent、工具、评测框架。

课程层必须拆：
syllabus、知识图谱、题型、mark scheme、术语、难度、考试规则。

不要为了“一个Agent”把课程差异抹平。

# 13. 如何避免生成学生没学内容

输入：
课程、考试局、学期、已完成topic、当前topic。

RAG/课程resolver只召回允许范围；
题目blueprint先确定知识点和难度；
生成后做规则/知识点检查；
越界直接拒绝/重生。

# 14. 如何验证“学会了”

不要只看：
使用时长、满意度、做题量。

更强证据：
独立作答、减少提示依赖、延迟后保持、迁移题、前后测、相似知识点新情境。

产品指标与学习指标并存。
