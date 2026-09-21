# Simon / 张翔：面试证据库

只使用已确认信息。回答时区分“真实做过”与“如果负责会做”。

证据分级：strong evidence指已有候选人材料明确记载或公开来源核实的事实，不表示全部经过独立审计；weak evidence指尚缺日志、口径、样本或独立验证的推断。具体行动和故事边界见[候选人故事库](19-candidate-story-bank.md)。

# 1. Ninefold Physics

定位：
面向海外A-Level等学生的情境化物理学习产品。

核心：
观察 → 预测 → 解释 → AI追问 → 确定性计算/动画验证。

可讲：
- contextual learning
- Socratic scaffold
- reasoning state
- 分层提示
- 学习辅助vs防抄袭
- 物理规则校验
- Agent/Multi-Agent
- Bad Case
- 公开Beta
- Codex辅助开发部署

高分点：
**模型理解学生怎么想，确定性系统判断物理上到底对不对。**

不要编：
大规模学习效果、付费、留存、准确率提升。

- strong evidence：现有候选人材料中的public beta、可运行学习流程、状态驱动追问、Physics Toolkit与规则校验、产品定义及开发部署。
- weak evidence：prototype/Beta可以验证机制可运行；当前缺少大规模learning outcome、留存、付费与对照实验结果。
- prohibited claims：已证明学习增益、达到PMF、已服务大规模学生、任意未经确认的模型版本或指标改善。
- best use：0→1、教育Agent、教学目标与模型边界、产品机制、评测设计。语音/文字、Rain/Leaf、first divergence、快通道可按既有产品口径解释，不扩写未确认的上线覆盖。

# 2. 经纬恒润 AI硬件产品实习

场景：
小米SU7相关PCB器件封装检查。

可讲：
- 大模型需求拆解
- Cadence Allegro/封装信息
- GLM-4/GPT-4o评测选型
- 多维Eval
- RAG
- 图像理解
- Multi-Agent
- 结果校验
- Bad Case
- 工业流程效率提升50%+

- strong evidence：候选人问答表“面试常见问题”D6/D8明确记载2024年7–8月的模型部署、调试、评估，GLM-4、GLM-4V、Qwen1.5-14B、GPT-4o，本地/API比较、内网保密约束、RAG与Agent workflow；D6支持相关环节效率提升50%以上，沿用原项目范围。
- weak evidence：50%+的基线工时、样本量、测量周期、是否含人工复核和返工，目前材料未提供；不得自行把它换算成成本、准确率或整条生产线收益。
- prohibited claims：全权负责整条产线、商业规模、零漏检、代码量等于业务成果、参与2025/2026后来发布的公司产品。问答表提到代码集成工作，可讲实施能力，代码行数不作impact。
- best use：多模型选型、本地部署与API、工业数据保密、多模态、RAG、流程集成、Bad Case与ROI。

### 当前公司背景，独立于个人实习

2026-09-21核验：官网2025-11-06发布的[AICC展示](https://www.hirain.com/news_detail/403.html)介绍智能体、RAG、多模态知识库及开发测试工具链；2025-12-16发布的[AI与网络测试](https://www.hirain.com/news_detail/420.html)介绍LLM/AI Agent在测试准备、分析、报告及问题诊断中的应用。这些只解释公司业务方向，不证明Simon在2024年参与了这些产品。以上依据官方网页搜索索引内容；后一页面直接抓取曾返回403。

适合：
模型选型、多模态、AI硬件、工程约束、ROI、Bad Case。

# 3. 长期物理/数学教学

可讲：
真实学生误区、A-Level/AP/IB、个性化练习、学生/家长/教师多方用户、学习效果与用户喜欢不是一回事。

# 4. 教育AI研究

IJSE第一作者，研究科学教师在生成式AI教学中的经验。

### Publication metadata

- Title：Investigating science teachers’ experiences of generative AI in science teaching and learning from a GenAI-TPACK perspective
- Authors：Xiang Zhang & Michael J. Reiss
- Journal：International Journal of Science Education
- Published online：18 Sep 2026（2026-09-18）
- Access：Open Access
- DOI：[10.1080/09500693.2026.2733687](https://doi.org/10.1080/09500693.2026.2733687)
- Citation：Zhang, X., & Reiss, M. J. (2026). International Journal of Science Education, 1–20。页码按候选人提供的正式引文。
- 核验日期：2026-09-21。已在浏览器读取[Taylor & Francis全文](https://www.tandfonline.com/doi/full/10.1080/09500693.2026.2733687)的署名、发表日期、开放获取标记，以及Methodology、Discussion、Limitations、Conclusions；以全文替代先前目录索引核验。

### 已核实的样本与方法

- 20位有正式中学科学任教经历的教师，访谈时暂时休假、就读伦敦某大学硕士课程，教龄1–11年；不能从就读地点推断任教地区或国籍。
- 16位为中国籍；其中4位中国籍参与者报告在中国国际学校用英语教授GCSE/A-level课程。不要将所有受访者概括为英国教师。
- 生物8人、物理7人、化学5人。按标准目的抽样后便利招募；不是总体代表性随机抽样。
- 英文半结构访谈，每次约60–70分钟，3次面对面、17次Teams。研究分析仅纳入GenAI相关片段。
- 第一作者反复阅读转录材料、记录初步观察，进行初始编码、归并和审查主题，最终形成8个主题，再用GenAI-TPACK解释；分析阶段与第二作者讨论不确定之处，并回查原始材料。

### 可讲发现与证据边界

教师自述在备课等教师端使用中更有信心，直接面向学生的课堂使用更谨慎；研究将这种差异与审核、修改、拒绝输出的控制空间联系起来。它支持讨论教学法、学科判断、trust、control及workflow，不能推出某项功能必然提高采用或学习结果。

- strong evidence：已发表元数据、上述样本方法及论文明确的第一作者分析行动；与第二作者讨论分析的协作。
- weak evidence：数据为回顾性自述，无课堂观察、无学生访谈；单一硕士课程背景且样本较窄，信心量表未经过充分效度验证。不能直接推成教师总体、产品行为或因果效果。
- prohibited claims：论文证明功能提高留存或付费、访谈等于线上行为数据、已证明学习增益；没有额外证据时不声称独立完成全部招募/访谈、编造审稿冲突或修订轮次。
- best use：用户研究、归纳分析、与合作者校准解释、教师采用与信任、教育AIPM动机、研究到产品假设。产品推论明确用“如果做教师产品，我会……”表述，并补任务观察与行为验证。

# 5. Personalised Practice

教师自然语言反馈
→ 学习状态
→ curriculum resolver
→ 题目blueprint
→ deterministic validation
→ questions/answers。

已确认口径：
机构内100+教师使用。

# 6. Formal Hall Networking

创始人/主席。
2000+关注协会的剑桥同学，不是2000会员或活动参与者。

可讲：
0→1、活动/社群、服务流程、网站、跨团队、组织交付。

# 7. Cambridge CEO / 腾讯走访

曾作为Cambridge CEO代表组织/参与深圳创投归国行并走访腾讯，与业务团队交流，了解不同业务线和AI发展方向。

用途：
回答“为什么腾讯/CSIG”作为动机证据，不夸大为腾讯工作经历。

# 8. 真实短板

- 缺少国内互联网大厂核心产品线PM实习；
- C端大规模流量/增长直接组织经验有限。

补偿：
- 独立0→1
- AI系统深度
- 教育/物理垂直用户认知
- 工业AI
- 国际用户/教学
- 强研究与评估

可说：
“这也是我希望进入核心业务团队的原因，我想把自己在0→1和垂直场景里的判断，放到更大规模的产品组织里验证。”

问答表D10还确认三个更具体的不足：熟悉话题时背景和细节过多、结论偏晚；高保真原型与视觉表达经验不足，过去偏向直接做可运行Demo；对一次性任务过早考虑自动化，前期投入可能超过收益。已写明的纠正机制分别是短长两版与结论前置、先画低保真流程并补原型表达、先算频次/节省时间/维护成本。没有客观改善比例，回答时不虚构。

# 9. 故事复用限制

一题默认1个主案例，最多1个辅助证据。同一场面试连续两题尽量换主案例，除非面试官主动深挖；连续两次使用同一案例后，训练优先换案例。经纬恒润偏工业工程约束，Ninefold偏0→1与教育产品机制，IJSE偏研究与用户洞察。其他既有案例保留，不为贴能力标签扩写未经确认的结果。
