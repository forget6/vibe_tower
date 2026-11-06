# Vibe Knowledge Tower — Research Base（文献基座）

> 本文档汇集氛围编程（Vibe Coding）领域的 **20 篇**核心前沿论文（12 篇主体基座 + 8 篇补位扩展，2025–2026，arXiv 免费 PDF），
> 为知识塔各模块提供理论与方法论支撑；另收录**公开实践准则类非论文来源**（见 §8）。
>
> 定位：**只沉淀方法与机制，不含任何具体业务项目信息**；可独立开源。
> 使用方式：模块文档（`core/`、`extensions/`）在开头以 `> 理论支撑：…` 回指本基座编号。

## 0. 引用与下载约定

- **引用格式**：`arXiv:<id>`；正文引用使用本基座编号 `P1`–`P16`。
- **免费下载**：`https://arxiv.org/abs/<id>`（摘要页）／`https://arxiv.org/pdf/<id>`（PDF 直链）。
- **本地副本**：`docs/research/<id>v<n>.pdf`（仅作离线阅读；分发时以 arXiv 链接为准，勿转售或再分发正文）。
- **许可提示**：arXiv 预印本许可多为非独占（arXiv non-exclusive license），引用观点/数据请标注出处；本塔**只做机制归纳**，不复制原文段落。

## 1. 核心主体模块支撑（P1–P5）

| # | 论文 | arXiv | 支撑模块 | 一句话机制 |
|---|---|---|---|---|
| P1 | VibeContract: The Missing Quality Assurance Piece in Vibe Coding（Song Wang, York University） | `2603.15691` | `core/02-intent-contract.md` | 把"代码生成了但不知对不对"转为**契约优先的可校验基准** |
| P2 | FlowCheck: Helping End-Users Specify and Verify Intent in Vibe-Coded Web Apps（Reya Vir, Lydia Chilton, Zhuo Zhang, Eugene Wu；Columbia） | `2608.28880` | `core/02`、`extensions/03` | 用**用户可见信息流约束语言**表达意图，确定性翻译为 CodeQL 分析 |
| P3 | Zoro: Active Rules for Reliable Vibe Coding（Jenny Ma, Sitong Wang, Joshua H. Kung, Lydia B. Chilton；Columbia） | `2604.15625` | `core/03-active-rules.md` | **计划阶段规则锚定 + 执行期强制举证**（"规则—证据—单测"绑定到每一步） |
| P4 | The Spec Growth Engine: Spec-Anchored, Code-Coupled, Drift-Enforced Architecture（Hartwig Grabowski） | `2606.27045` | `core/01-spec-engine.md` | **机器可读规格图谱 + Spine 上下文收敛器 + 漂移强制**，治上下文爆炸与静默规格漂移 |
| P5 | SWE-chat: Coding Agent Interactions From Real Users in the Wild（Joachim Baumann 等；Stanford） | `2604.20779` | `core/03`、`extensions/04` | 真实世界 6,000 sessions／63,000 prompts／355,000 tool calls 的**行为分布证据** |

## 2. 扩展工程痛点模块支撑（P6–P9）

| # | 论文 | arXiv | 支撑模块 | 一句话机制 |
|---|---|---|---|---|
| P6 | VibeGuard: A Security Gate Framework for AI-Generated Code — Lessons from the Claude Code Source Leak（Ying Xie, Kennesaw State University） | `2604.01052` | `extensions/01-security-gate.md` | 源自 **59.8 MB source map 泄漏**（约 512,000 行私有 TypeScript）的独立安全关卡：传统 SAST/密钥扫描覆盖不到"打包配置类"故障 |
| P7 | Context Before Code: An Experience Report on Vibe Coding in Practice（Md Nasir Uddin Shuvo 等；Tampere University） | `2603.11073` | `extensions/02-architecture-boundaries.md` | 生产约束下的经验报告：**先对齐架构上下文再写码**，显式锁定不可委托区 |
| P8 | Position: Vibe Coding Needs Vibe Reasoning: Improving Vibe Coding with Formal Verification（Jacqueline Mitchell, Yasser Shaaban） | `2511.00202` | `extensions/03-formal-reasoning.md` | 轻量形式化校验：LLM 难以**调和累积的人类约束** ⇒ 需要内部状态机/推理层校验 |
| P9 | Building Software by Rolling the Dice: A Qualitative Study of Vibe Coding（Yi-Hung Chou 等；UC Irvine／Southampton；20 视频／7 直播／约 16 小时／254 prompts） | `2512.22418` | `extensions/04-stabilization-workflow.md` | 随机性风险定性：以**意图证据留存**降低反复试错内耗 |

## 3. 深度实证与工业化落地支撑（P10–P12）

| # | 论文 | arXiv | 支撑模块 | 一句话机制 |
|---|---|---|---|---|
| P10 | Understanding the (In)Security of Vibe-Coded Applications（Junquan Deng, Zhiyu Fan（Microsoft）, Ruijie Meng（NUS）） | `2606.23130` | `extensions/01`、`core/03` | 大规模安全审计：**越权访问与配置失控**为高危分布主类，夯实"反例防线" |
| P11 | Formal-Method-Guided Vibe Coding: Closing the Verification Loop on AI-Generated Safety-Critical Software Through Model-Driven Engineering（Ran Wei, Le Zhu, Haochi Wang, Jim Woodcock, Fang Yan, Simon Foster, Xiangyang Ji） | `2606.22413` | `extensions/03`、`templates/iteration-checkpoint.md` | Forge 式闭环：把自然语言意图与演绎验证/模型驱动对齐，面向 DO-178C／IEC 61508／ISO 26262 |
| P12 | Vibe Coding: An Experiment with Test-Driven Development（Moritz Mock, Barbara Russo） | `2607.22406` | `extensions/04`、`templates/prompt-guidelines.md` | 四种协作模型（solo／collaborative／fully automated 等）实证：TDD 协作模式管住**隐式决策点** |

## 4. 补位扩展：4 篇工程落地型新增论文（P13–P16）

> 补位原因：P1–P12 覆盖"规格—契约—规则—安全—边界—形式化—TDD"主干，但缺少 ① **绿地工程的端到端对照评估**、
> ② **开源真实协作行为的长周期刻画**、③ **"事前准备"作为可操作方法论**、④ **负责任采用与认知代价**四类工程视角。

| # | 论文 | arXiv | 支撑模块 | 一句话机制 |
|---|---|---|---|---|
| P13 | Vibe Coding Ate My Homework: An evaluation of AI approaches to greenfield software engineering and programming（Callum Barbour） | `2606.18293` | `extensions/04`、`docs/agent-execution-phases.md` | **绿地工程对照评估**：给出"从零到可用"的 AI 路线适用边界与失败模式 |
| P14 | From Conversation to Contribution: Characterizing Coding Agent in Open-Source Software（Zihan Fang, Yueke Zhang, Ningzhi Tang, Collin McMillan, Toby Jia-Jun Li, Yu Huang） | `2607.05677` | `core/03`、`extensions/05-meta-evolution-loop.md` | 开源协作刻画：**从"对话"到"贡献"**的转化率与卡点 ⇒ 规则应锚定"可合入"标准 |
| P15 | Mise en Place for Agentic Coding: Deliberate Preparation as Context Engineering Methodology（Andrew Zigler） | `2605.05400` | `core/01`、`core/03` | **"事前备料"方法论**：把语境工程前置为可复用步骤，而非生成时即兴补上下文 |
| P16 | The Vibe Shift in Software Engineering: Evaluating AI-Led Conversational Programming for Performance, Cognition, and Responsible Adoption（Sales G. Aribe, Louie Jay S. Labastida） | `2609.09560` | `extensions/05`、`README.md` | **性能—认知—责任采用**三维评估：把"能用"升级为"可持续、可问责地采用" |

## 4.2 第二批补位（P17–P20，★v0.80）：把"范式"从**主张**变成**可测、可审计、可归因**的对象

> 补位原因（★v0.80，逐条对应**当前塔的空白面**）：
> ① P1–P16 缺**范式级综述与模式分类**——各模块的"何时用哪套纪律"只能靠项目自定；
> ② 缺**意图 → 契约的解析层**（P18 给出参考架构：意图解析器 / 语义嵌入 / 生成器 / 反馈环）；
> ③ 缺**运行时基底（harness）模型**——塔长期只讲"判据与卡口"，没讲"智能体凭什么观察到项目、凭什么认定一次改动**已完成**"；
> ④ 缺**度量的方法论纪律**——同一现象可同时出现 +26% 与 −19% 的读数（P20），若不先固定"测量方法 / 范围 / 时间跨度"，判据会被拿来支持相反结论。

| # | 论文 | arXiv | 支撑模块 | 一句话机制 |
|---|---|---|---|---|
| P17 | A Survey of Vibe Coding with Large Language Models（Yuyao Ge 等 15 人；**首个系统性综述**，覆盖 1000+ 篇） | `2510.12399` | `core/03`、`docs/agent-execution-phases.md`、`core/01` | 用**受约束马尔可夫决策过程**形式化"开发者 × 项目 × 智能体"三角关系，并给出**五种开发模式**分类（无约束自动化 / 迭代对话协作 / 规划驱动 / 测试驱动 / 上下文增强）⇒ **模式 MUST 显式声明**，成功取决于**系统化上下文工程**而非仅模型能力 |
| P18 | Vibe Coding: Toward an AI-Native Paradigm for Semantic and Intent-Driven Programming（Vinay Bamil） | `2510.17842` | `core/02`、`extensions/03` | 形式化"语义与意图驱动范式"，给出参考架构：**意图解析器 → 语义嵌入 → 智能体生成器 → 交互反馈环**；点名 alignment / **reproducibility** / bias / explainability / maintainability / security 六类风险 ⇒ **意图 MUST 先解析为结构化契约**（MUST NOT 由意图直接生成） |
| P19 | AI Harness Engineering: A Runtime Substrate for Foundation-Model Software Agents（Hailin Zhong, Shengxin Zhu） | `2605.13357` | `extensions/05`、`extensions/01`、`core/03` | 能力来自 **model–harness–environment 系统**而非模型单点；harness = **11 项组件职责**（任务规格 / 上下文选择 / 工具可达 / 项目记忆 / 任务状态 / 可观测 / **失败归因** / 验证 / **权限** / **熵审计** / **介入记录**）；**H0–H3 阶梯** + **trace-based 评估 ⇒ 可审计 episode 包**（低阶只产 patch，高阶产复现日志 / 归因 / 确定性需求检查 / 结构化验证报告） |
| P20 | Vibe Coding: Practice, Performance, Productivity, and Risk — A State-of-the-Art Review（Dominik L. Michels 等 5 人） | `2608.20446` | `extensions/04`、`extensions/05`、`README.md` | 跨学科现状综述：基准饱和但**任务级能力不均衡**（可靠生成 / **薄弱故障检测** / **难审计文档**）；生产力读数**表面矛盾**（+26% 任务/周 vs 独立试验 −19% vs 代码评审时间 **+441%**）⇒ 归纳**六种离散成因**（效应衰减 / 自述 vs 独立测量背离 / **产出量被误当生产力** / 长期检验后收回论断 …）；风险面含安全失效、质量退化、版权未决、**技能退化**；提出**可证伪猜想**：收益在新代码上真实、在**成熟代码库**上缩小或反转 |

## 5. 本地 PDF 索引

| 本地文件 | 对应 |
|---|---|
| `2511.00202v1.pdf` | P8 |
| `2512.22418v2.pdf` | P9 |
| `2603.11073v1.pdf` | P7 |
| `2603.15691v1.pdf` | P1 |
| `2604.01052v1.pdf` | P6 |
| `2604.15625v2.pdf` | P3 |
| `2604.20779v1.pdf` | P5 |
| `2606.22413v2.pdf` | P11 |
| `2606.23130v4.pdf` | P10 |
| `2606.27045v1.pdf` | P4 |
| `2607.22406v1.pdf` | P12 |
| `2608.28880v1.pdf` | P2 |
| `2606.18293v2.pdf` | P13（绿地工程评估） |
| `2607.05677v1.pdf` | P14（开源协作刻画） |
| `2605.05400v1.pdf` | P15（事前备料方法论） |
| `2609.09560v1.pdf` | P16（责任采用评估） |
| `2510.12399v2.pdf` | P17（范式综述 + 五模式分类 ★v0.80） |
| `2510.17842v1.pdf` | P18（意图解析 → 契约参考架构 ★v0.80） |
| `2605.13357v1.pdf` | P19（harness 运行时基底 + episode 包 ★v0.80） |
| `2608.20446v1.pdf` | P20（度量方法论纪律 ★v0.80） |

> 说明（2026-09-20 起）：知识塔已迁出业务仓库，成为**独立仓库**（跟随项目并列迭代、但与工程解耦）。
> 上表 PDF **已随本仓库提供**（便于离线阅读与检索）；若**对外公开分发**，请让读者按上表 `abs`/`pdf` 直链自行获取
> —— arXiv 预印本的再分发受各自许可约束，本仓定位为内部/协作仓库。

## 6. 维护规则

1. **新增论文 MUST 同时更新**：本文件（编号连续）→ 对应模块的 `> 理论支撑：` 回指 → `paper-analysis-whitebook.md` 的剖析条目。
2. **编号只增不改**：P 编号一旦分配不得复用或重排（引用稳定性）。
3. **禁止写入项目私有信息**：论文归纳中不得出现任何具体业务系统、内部库表名、客户名或内部版本号。
4. **非论文来源（§8）收录口径**：MUST 公开可访问、许可明确、可给出稳定链接；MUST NOT 收录内部资料或不可引用来源。引用编号用 `E<n>`，与论文章节 `P<n>` 区分。

## 7. 附录：论文下载直链（免费 PDF，arXiv）

| # | 摘要页（abs） | PDF 直链（免费下载） |
|---|---|---|
| P1 | https://arxiv.org/abs/2603.15691 | https://arxiv.org/pdf/2603.15691 |
| P2 | https://arxiv.org/abs/2608.28880 | https://arxiv.org/pdf/2608.28880 |
| P3 | https://arxiv.org/abs/2604.15625 | https://arxiv.org/pdf/2604.15625 |
| P4 | https://arxiv.org/abs/2606.27045 | https://arxiv.org/pdf/2606.27045 |
| P5 | https://arxiv.org/abs/2604.20779 | https://arxiv.org/pdf/2604.20779 |
| P6 | https://arxiv.org/abs/2604.01052 | https://arxiv.org/pdf/2604.01052 |
| P7 | https://arxiv.org/abs/2603.11073 | https://arxiv.org/pdf/2603.11073 |
| P8 | https://arxiv.org/abs/2511.00202 | https://arxiv.org/pdf/2511.00202 |
| P9 | https://arxiv.org/abs/2512.22418 | https://arxiv.org/pdf/2512.22418 |
| P10 | https://arxiv.org/abs/2606.23130 | https://arxiv.org/pdf/2606.23130 |
| P11 | https://arxiv.org/abs/2606.22413 | https://arxiv.org/pdf/2606.22413 |
| P12 | https://arxiv.org/abs/2607.22406 | https://arxiv.org/pdf/2607.22406 |
| P13 | https://arxiv.org/abs/2606.18293 | https://arxiv.org/pdf/2606.18293 |
| P14 | https://arxiv.org/abs/2607.05677 | https://arxiv.org/pdf/2607.05677 |
| P15 | https://arxiv.org/abs/2605.05400 | https://arxiv.org/pdf/2605.05400 |
| P16 | https://arxiv.org/abs/2609.09560 | https://arxiv.org/pdf/2609.09560 |
## 8. 非论文来源（外部实践准则与公开资料）

> 与 §1–§4 的论文基座并列：本节收录的**不是学术论文**，而是公开可引用的**实践准则 / 工程惯例**。
> 收录口径见 §6 第 4 条；引用编号 `E<n>`。

| # | 来源 | 性质 / 许可 | 支撑模块 | 采用要点 |
|---|---|---|---|---|
| E1 | Karpathy-Inspired LLM Coding Guidelines（社区公开仓库 `https://github.com/multica-ai/andrej-karpathy-skills`；源自 Karpathy 对 LLM 编码陷阱的公开观察） | 实践准则 / **MIT** | `core/02` §2.1a、`extensions/02` §2.6、`README` §4 | ① **外科式改动**（每一行改动可追溯到请求、不顺手改相邻代码与格式、无关死代码只提不删）⇒ 判定化为 §2.6-A；② **简单优先**（不做投机设计、一次性不抽象、不写不可达分支、有更简解须提出）⇒ 预算化为 §2.6-B；③ **目标驱动执行**（命令式指令改写为可验证目标、多步计划逐步带验证点）⇒ §2.1a；④ **规模自适应**与**多载体分发** ⇒ `README` §4 |
| E2 | 同上准则所依据的公开观察（对 LLM 编码缺陷的公开评述：擅自假设 / 过度复杂化 / 越界改动） | 公开观察 / 无正式许可声明 | 同上 | 为 E1 的**问题陈述**提供真实观察依据（三类通病），并作为 C4「有真实反例」的外部支撑 |

**C5 已覆盖留痕（避免重复引入）**：「先想后写 / 不确定即停 / 该反驳就反驳」已在 `templates/prompt-guidelines.md` 的初始化提示词中表达（"MUST 遇到不确定就停下提问，而不是猜测后继续"）⇒ 本次**未重复新增**。

> 说明：`E` 编号与 `P` 编号**互不复用**；若后续废止某来源，MUST 保留编号并标注"已废止"（引用稳定性）。

