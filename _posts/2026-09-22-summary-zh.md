---
layout: default
title: "Horizon Summary: 2026-09-22 (ZH)"
date: 2026-09-22
lang: zh
---

> 从 64 条内容中筛选出 8 条重要资讯。

---

1. [phantom-kv 通过注入 18MB KV 缓存实现 LLM 去审查，无需改动权重](#item-1) ⭐️ 8.0/10
2. [月之暗面发布 Kimi Code 桌面客户端，macOS 与 Windows 同步上线](#item-2) ⭐️ 8.0/10
3. [小米开源 MiMo-V2.6 Pro 与 Flash，并公开实时强化学习训练看板](#item-3) ⭐️ 7.0/10
4. [Transformer Explainer：在浏览器中实时运行 GPT-2 的可视化讲解工具](#item-4) ⭐️ 7.0/10
5. [Kev：基于 Qwen3.5 构建的微型 Jev 式决策模型家族](#item-5) ⭐️ 7.0/10
6. [TypeSafe AI 发布 Jev：一种只输出决策数值而非文本的「System One」模型](#item-6) ⭐️ 7.0/10
7. [Jevopt 借助 Jev 智能模型做 LLVM 内联决策以优化二进制体积](#item-7) ⭐️ 7.0/10
8. [SupraLabs 发布 Supra2-IMG：1 亿参数的开源文生图模型](#item-8) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [phantom-kv 通过注入 18MB KV 缓存实现 LLM 去审查，无需改动权重](https://www.reddit.com/r/LocalLLaMA/comments/1wms904/uncensor_an_llm_without_touching_weights_inject_a/) ⭐️ 8.0/10

开发者发布了 phantom-kv 这一开源系统，它通过将一小块经过训练的键/值张量库（约 18MB）作为上下文加载进模型的 KV 缓存来消除大语言模型的拒答行为，使模型权重保持逐字节不变。由于该“移植物”存在于缓存而非检查点中，去审查就变成了可针对单次请求、可随时热插拔的能力模式——随时可以卸载；作者还演示了防御（“蓝药丸”）与攻击（“红药丸”）两种模式，它们以缓存槽位而非独立检查点的形式提供。 这提供了一条与前两种主流方法截然不同的去拒答路径：权重空间消融（abliteration，会永久重写检查点）和激活空间投影（通过引擎钩子在运行时打补丁修改信号通路）。新方法使得按请求开关安全行为成为可能，无需重新刷写权重，也无需针对不同量化分别重建。这对本地 LLM 用户以及希望获得“部署可控”能力模式（而非对模型做一次性永久修改）的攻防安全团队最有价值。 phantom-kv 是针对模型自身目标离线训练的：对有害提示学会配合，同时对无害提示保持原有行为；它只通过注意力本就消费的输入通道影响模型，因此不依赖一维“拒答方向”假设，也不需要前向传播钩子或针对新架构的重建。作者用 8B 评判模型做的自审发现：词汇层面的拒答抑制指标会高估实际配合度（语义上的拒答常常以改述形式残留）；该移植物在长会话中会衰减，半衰期约 2–4k token（可通过实测出的再注入节奏缓解）；并且回答仍会带有法律与伦理层面的表述框架。

reddit · r/LocalLLaMA · /u/Anony6666 · 9月21日 22:55

**背景**: 拒答行为指对齐后的模型拒绝那些听起来有害或未获授权请求的倾向。此前的“去审查”技术大致分为两类：一是权重空间消融（abliteration），即在模型权重中识别并移除“拒答方向”——这是一种永久性修改，必须通过重新刷写权重才能撤销，而且会因量化方式不同而失效；二是激活空间投影，即通过引擎钩子，在运行中逐 token、逐层地减去拒答方向。KV 缓存是 Transformer 为已见上下文保存的键/值注意力状态；phantom-kv 的思路正是向其中提供训练好的缓存内容，让注意力把它当作“已经在场”的对话历史来读取，而不是去改动模型本身。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/lukey03/Qwen3.5-9B-abliterated/raw/main/README.md">huggingface.co/lukey03/Qwen3.5-9B-abliterated/raw/main/README.md</a></li>
<li><a href="https://arxiv.org/html/2510.17902v1">Activation Manifold Projection: Liberating Task-Specific Behaviors from LLM Architectures</a></li>
<li><a href="https://symbl.ai/developers/blog/a-guide-to-quantization-in-llms/">A Guide to Quantization in LLMs | Symbl.ai</a></li>

</ul>
</details>

**标签**: `#llm`, `#open-source`, `#local-llm`, `#inference`, `#tool`

---

<a id="item-2"></a>
## [月之暗面发布 Kimi Code 桌面客户端，macOS 与 Windows 同步上线](http://kimi.com/code) ⭐️ 8.0/10

月之暗面发布 Kimi Code Desktop 桌面客户端，作为 Kimi Code 的官方桌面端产品，macOS 与 Windows 版本同步上线，可在 kimi.com/code 安装使用。该客户端支持通过对话读写代码、运行命令并完成自动化任务，同时内置终端、浏览器和 Git 状态查看功能。 这意味着 Kimi Code 从命令行 agent 升级为完整的桌面图形客户端，使月之暗面直接与 Cursor、Claude Code、GitHub Copilot、Cline 等成熟 AI 编程工具展开竞争。它为开发者（尤其中国开发者）提供了一个由 Kimi 模型驱动、可立即安装试用的一体化编程入口，而不再局限于终端或网页界面。 客户端将终端、浏览器与 Git/PR 跟踪集成在一起，开发者无需离开应用即可运行调试项目、审阅代码改动并跟踪 PR 进度。月之暗面尚未公布定价、支持的操作系统版本以及底层调用的具体 Kimi 模型版本，因此它目前更像是围绕既有 Kimi Code agent 构建的桌面外壳。

telegram · zaihuapd · 9月21日 08:48

**背景**: 月之暗面是一家总部位于北京的人工智能公司，成立于 2023 年 3 月，是中国所谓“AI 六小虎”之一；其 Kimi 系列模型通过网页、API 以及 Kimi Code 命令行 agent 对外提供。所谓 coding agent（编程智能体），是指能够自主编写、审阅、修改和重构代码的 AI 系统，通常由“模型 + 工具与执行环境组成的 harness”构成。2026 年这一赛道竞争激烈，常被提及的领先者包括 Cursor、Claude Code、Codex、GitHub Copilot 和 Cline。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Moonshot_AI">Moonshot AI</a></li>
<li><a href="https://en.wikipedia.org/wiki/Kimi_(AI)">Kimi (AI) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/AI_coding_agent">AI coding agent</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agent`, `#Kimi`, `#developer tools`, `#Moonshot AI`

---

<a id="item-3"></a>
## [小米开源 MiMo-V2.6 Pro 与 Flash，并公开实时强化学习训练看板](https://mimo.xiaomi.com/mimo-v2-6) ⭐️ 7.0/10

9 月 22 日，小米 MiMo 团队发布并开源 MiMo-V2.6 系列，包括定位旗舰的 MiMo-V2.6-Pro 和主打效率与成本的 MiMo-V2.6-Flash，两款均为原生全模态模型，面向编程、电脑操作、3D 场景与视听内容创作等智能体任务。面向高吞吐场景的 Pro-UltraSpeed 也在逐步推出，官方称在同等质量下输出速度最高可提升 20 倍，网页体验、API 与 Hugging Face 模型入口均已开放。 这为开源权重模型阵营再添一个来自中国厂商的有力竞争者，而当前这一领域正越来越多地由中国模型发布所主导；同时它把透明度推得比多数同行更远，不仅公布了详细技术报告，还公开了强化学习训练看板。受益最大的是构建智能体或需要大吞吐推理负载的开发者，因为社区最关心的正是其基准成绩与大幅降低的价格之间的组合。 MiMo 负责人罗福莉称，这可能是开源模型团队中按算力计规模最大的单次强化学习训练之一：先用 MixRL 联合训练中等难度、可验证的代码与智能体任务，再把游戏、3D、主观评测等难以验证或超长任务单独训练，并通过 MOPD 合并能力。除模型本身外，团队还开放了由 MiMo 训练轨迹蒸馏出的 Qwen 模型、7000 个多样化环境以及完整的强化学习框架；不过价格效率的说法与 20 倍加速数据均为官方口径，UltraSpeed 版本也尚未全面开放。

hackernews · volf_ · 9月21日 20:12 · [社区讨论](https://news.ycombinator.com/item?id=49792730)

**背景**: MiMo 是小米自研的 AI 模型系列，也是其「人车家全生态」战略中的核心模型，团队由罗福莉领导，她此前曾在 DeepSeek 工作，2025 年底加入小米。强化学习属于语言模型的后训练阶段，模型依据奖励信号进行优化，例如生成的代码能否通过测试，而多数实验室并不公开由此产生的训练曲线与基础设施。开源社区一直在争论这类发布到底有多「开放」，因为很多团队只公开模型权重，而保留训练数据与训练代码。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Xiaomi_MiMo">Xiaomi MiMo - Wikipedia</a></li>
<li><a href="https://www.intelligentliving.co/mimo-v2-6-rl-training/">MiMo-V2.6 RL Training : Xiaomi Livestreams $3M+ AI Run in Real Time</a></li>
<li><a href="https://mimo.mi.com/">Xiaomi MiMo-V2.6 Series: 3 New Models Officially Released</a></li>

</ul>
</details>

**社区讨论**: 评论者普遍赞赏其透明度，有人表示实时强化学习看板是极佳的学习与教学工具，技术报告也异常详尽。另一些人则聚焦成本问题，有人追问小米如何做到模型规模大于 GLM 5.3、价格却不到其 10% 的情况下仍与 GLM 5.3 表现相当；讨论随后转向中美 AI 竞赛，认为电力与电网建设是美国长期的决胜瓶颈。Simon Willison 还对 Flash 与 Pro 分别做了经典的「鹈鹕」SVG 生成测试。

**标签**: `#open-source-models`, `#LLM`, `#model-release`, `#Xiaomi`, `#training-transparency`

---

<a id="item-4"></a>
## [Transformer Explainer：在浏览器中实时运行 GPT-2 的可视化讲解工具](https://poloclub.github.io/transformer-explainer/) ⭐️ 7.0/10

佐治亚理工的 Polo Club 发布了 Transformer Explainer，这是一个交互式网页，能在浏览器中直接运行一个实时的 GPT-2 模型，并随着你输入文本实时可视化模型的内部机制——注意力模式、词元嵌入以及下一个词元的概率分布。该工具在 Hacker News 上被分享，评论者补充了 Jalammar《The Illustrated Transformer》的链接，并就注意力头与温度采样的解释方式展开讨论。 大多数关于 Transformer 的讲解都是静态图表，而让学习者输入提示词、实时观察真实模型的注意力权重和概率输出变化，能把抽象架构变得具体可感。这降低了开发者理解 LLM 工作原理的门槛，HN 上的讨论也表明这类工具还能成为纠正常见误解的聚集地。 该演示在浏览器端本地运行 GPT-2（而非调用远程 API），并同时展示注意力矩阵和最终的 softmax 词元分布，方便用户试验采样设置。Hacker News 上的批评集中在工具把低温度解释为“安全性”这一措辞上：温度 0 生成的文本往往呈现出平淡、缺乏惊喜的人工感，而不仅仅是“安全”。

hackernews · aray07 · 9月21日 19:43 · [社区讨论](https://news.ycombinator.com/item?id=49792342)

**背景**: Transformer 是一种基于多头注意力机制的神经网络架构：输入文本被切分成词元（token），每个词元变成数值向量，注意力机制让每个词元能够权衡序列中其他词元的信息。GPT-2 是 OpenAI 于 2019 年发布的生成式预训练 Transformer，其体量小到足以在浏览器中运行，因此常被用作教学模型。该讲解工具与 Jay Alammar 的《The Illustrated Transformer》和《The Illustrated GPT-2》等经典图文教程相呼应，后者被普遍推荐为入门必读。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Transformer_(deep_learning)">Transformer (deep learning) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/GPT-2">GPT-2 - Wikipedia</a></li>
<li><a href="https://www.ibm.com/think/topics/attention-mechanism">What is an attention mechanism? | IBM</a></li>

</ul>
</details>

**社区讨论**: 评论整体反应积极：有人强烈推荐新手阅读 Jalammar 的《The Illustrated Transformer》；还有人提出了一个相当深刻的观点——注意力头的行为类似于一个全连接层，只不过它的权重是在推理时由 Query 和 Key 向量动态构建出来的。也有人反驳该工具将温度描述为“安全性与创造性之间的权衡”，认为温度 0 的输出是沉闷而做作的，而非单纯的“安全”；此外还有不少人调侃“transformer”一词总与电力变压器混淆。

**标签**: `#transformers`, `#llm-education`, `#interactive-visualization`, `#attention-mechanism`, `#deep-learning`

---

<a id="item-5"></a>
## [Kev：基于 Qwen3.5 构建的微型 Jev 式决策模型家族](https://github.com/jaredpalmer/kev/tree/main) ⭐️ 7.0/10

Jared Palmer 在 GitHub 上发布了一个名为 Kev 的仓库，它是一组基于 Qwen3.5 构建的微型 Jev 式决策/分类模型，并附带了一套实用的“嵌入向量 + 逻辑分类器”配方。该发布同时在 Hacker News 上引发了关于近期 Jev 类项目热潮的热烈讨论。 它给开发者提供了一个可直接克隆的具体范例：把通用大模型改造成快速、窄域的决策模型，而不是又一个聊天机器人或 Agent 封装，这种模式因成本和延迟优势正变得越来越有吸引力。相关讨论还给出了一套可复用的生产级方案——嵌入向量加逻辑回归分类器——只需很少数据即可达到高准确率，可直接用于邮件分类等任务。 Kev 被定位为一个微型、窄域模型家族，而非通用助手，并且是直接基于 Qwen3.5 的权重构建，而非从零训练。被引用最多的评论描述了一套相关流水线：据称仅用 50–100 个训练样本即可在邮件分类上达到 95% 准确率，在 CPU 上训练耗时不到 5 分钟，模型体积小于 1MB，推理时间低于 100ms；此外还有人分享了社区维护的 Jev 类模型排行榜页面。

hackernews · tosh · 9月21日 07:11 · [社区讨论](https://news.ycombinator.com/item?id=49783999)

**背景**: Jev 是 TypeSafe AI 推出的“System One”决策模型，它返回带校准概率的类型化决策结果，而不是自由生成的文本，据称运行速度比前沿大模型快 40–200 倍。Qwen3.5 是阿里巴巴开放权重 Qwen 基础模型家族的最新一代，涵盖从极小到超大规模的稠密与混合专家（MoE）变体。因此“Jev 式”指的是在其他模型权重之上模仿这种类型化决策、高速推理范式的项目；而“嵌入向量 + 逻辑回归”方案则是用冻结的嵌入模型把文本转成向量，再在其上训练一个简单廉价的分类器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.datacamp.com/blog/system-one-models-jev">Jev : TypeSafe's System One Model Explained | DataCamp</a></li>
<li><a href="https://qwen-ai.com/qwen-3-5/">Qwen 3 . 5 : All 8 Models , Benchmarks & Local Setup Guide</a></li>
<li><a href="https://x321.org/embeddings-as-features-classify-text-with-sentence-embeddings-and-logistic-regression/">Embeddings as features: classify text with sentence embeddings and logistic regression - The Official Site Of NAIT (Native AI Teams)</a></li>

</ul>
</details>

**社区讨论**: 评论意见分化：一位用户分享了实用的“嵌入向量 + 逻辑分类器”方案并给出了具体数据（邮件分类 95% 准确率、模型小于 1MB、推理低于 100ms），另一位则贴出了 Jev 类模型的社区基准测试链接。也有人持怀疑态度，其中一位表示已经对满屏的“Jev 讨论”感到疲惫，认为大量 Jev 形态的发布更像机会主义而非真正用心维护；还有人质疑，Jev 本身是用 RLCD 训练的，而基于 RLHF 训练的 Qwen 做出来的模型凭什么能被称为 Jev 式。

**标签**: `#ai-models`, `#open-source-repo`, `#classification`, `#qwen`, `#practical-technique`

---

<a id="item-6"></a>
## [TypeSafe AI 发布 Jev：一种只输出决策数值而非文本的「System One」模型](https://simonwillison.net/2026/Sep/21/jev/) ⭐️ 7.0/10

TypeSafe AI 发布了 Jev，这是其所谓「System One 模型」的第一个实例（Simon Willison 更倾向于称之为「决策模型」）：它接收非结构化文本或半结构化的「state」对象，返回的是浮点置信度、类别选择或评分档位，而不是生成的文本。它只对输入计费，价格为每百万 token 0.042 美元，比 OpenAI 的 GPT-5 Nano（每百万 0.05 美元）还便宜，输出则完全免费。 Jev 定义了一个面向机器而非人类的新模型类别：它不输出需要解析的文本，而是给出可直接被代码用于 if 判断、路由表或排序流程的类型化概率决策。对于从事分类、门控、打标、优先级排序或搜索重排的 agent 开发者来说，一个比通用 LLM 快两个数量级、便宜两个数量级的模型，有望取代大量靠提示词工程硬凑的胶水代码。 Jev 支持三类问题：名为 Noul（即伯努利）的是/否问题，返回 0 到 1 之间的置信度；选择类问题，返回在所给选项上的概率分布；以及评分类问题，返回落在给定数值档位区间内的浮点数。同一个 state 上的所有问题并行计算，因此问很多问题的耗时与只问一个问题差不多。明显的代价是可解释性缺失——由于只返回一个浮点数，没有任何理由可供审查，这在诸如求职者排序等高风险场景中会引发对隐性偏见的真实担忧。

rss · Simon Willison · 9月21日 23:09

**背景**: System One 模型是 TypeSafe AI 试图原生面向机器消费而构建的模型，与传统的、逐 token 思考并返回人类可读文本的 LLM（该公司称之为「System Two」模型）形成对照。TypeSafe 表示他们为此构建了全新的模型架构、并行采样器，以及一种名为「面向校准决策的强化学习」（RLCD）的训练方法，并声称 Jev 在 System One 任务上达到现有 LLM 的智能水平，同时速度与效率约高两个数量级。这一命名借鉴了双过程理论，而「Noul」问题类型的名字则来自伯努利分布。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://typesafe.ai/blog/introducing-system-one-models-and-jev">Introducing System One Models & Jev - TypeSafe AI Blog</a></li>
<li><a href="https://www.langchain.com/blog/building-a-harness-with-jev">What Is Jev? A Guide to TypeSafe AI’s System One Model</a></li>
<li><a href="https://docs.typesafe.ai/introduction">Introduction - TypeSafe AI</a></li>

</ul>
</details>

**社区讨论**: 围绕此次发布的讨论部分集中在命名上：TypeSafe 的 CEO 在 Hacker News 上确认「Noul」是伯努利的缩写，而 Maggie Appleton 提出的「决策模型」这一比「System One 模型」更清晰的叫法，得到了包括 Simon Willison 在内的评论者认同。

**标签**: `#llm`, `#decision-models`, `#agents`, `#model-release`, `#inference-cost`

---

<a id="item-7"></a>
## [Jevopt 借助 Jev 智能模型做 LLVM 内联决策以优化二进制体积](https://github.com/Ramneet-Singh/jevopt) ⭐️ 7.0/10

一个名为 jevopt 的开源 Show HN 项目利用 Jev 模型，在每个可自由选择的 LLVM IR 调用点决定是否内联函数，目标是让编译出的二进制更小。在全部 19 个 Embench 1.0 程序上的评测显示，jevopt 生成的 .text 段按几何平均比 clang -Oz 大 7.87%（总体落败），但它在 19 个程序中的 7 个上胜过成熟的 clang 启发式，其中 Statemate 上实现了 58% 的缩减（2382B 对 5698B）。 它表明基于模型的判断有时能胜过经过数十年调优的编译器启发式，暗示出一条可行的混合路线：编译器同时运行自身启发式和模型，然后取体积更小的结果。由于在编译期测量代码体积几乎是零成本的，这种做法只需多一次编译外加几分钱的模型 API 调用，对每一字节 flash 都要计较的嵌入式和系统开发者很有意义。 在每个可自由选择的调用点，Jev 会收到当前的调用者/被调用者 LLVM IR、原始 C/C++ 源码、构建上下文以及关于程序的 7 项结构化事实，并只返回一个类型化选择：内联或保持独立函数。作者强调 jevopt 并非生产级软件，总体上是落败的，并认为针对内联任务专门微调一个类 Jev 模型有望让总体结果转为胜出。

rss · Show HN (self-made tools) · 9月22日 00:11

**背景**: LLVM IR 是 clang 等前端把 C/C++ 降低后、在优化与代码生成之前使用的中间表示，而内联是其中影响最大的优化 pass 之一：内联一个调用可能复制代码、增大二进制，但也可能暴露出更多优化，最终删掉的代码比新增的还多。Jev 由 TypeSafe AI 于 2026 年 9 月 15 日发布限量早期访问版本，它不是生成文本的 LLM，而是返回类型化结果（如选择、分数或是/否概率）并附带置信度，专为被其他软件直接消费而设计。Embench 是面向深度嵌入式系统的现代免费开源基准测试套件，常被视为 Dhrystone 和 Coremark 的继任者。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Jev_(AI_model)">Jev (AI model)</a></li>
<li><a href="https://www.embench.org/">embench .org</a></li>
<li><a href="https://www.cs.cornell.edu/courses/cs6120/2019fa/blog/llvm-function-inlining/">CS 6120: LLVM Function Inlining Pass</a></li>

</ul>
</details>

**标签**: `#AI`, `#compiler optimization`, `#LLVM`, `#GitHub`, `#developer tools`

---

<a id="item-8"></a>
## [SupraLabs 发布 Supra2-IMG：1 亿参数的开源文生图模型](https://www.reddit.com/r/LocalLLaMA/comments/1wmftr3/massive_release_supra2img_a_tiny_100m_texttoimage/) ⭐️ 7.0/10

SupraLabs 发布了 Supra2-IMG，这是一个 1 亿参数的扩散 Transformer（DiT）文生图模型，完全从零开始训练，仅在 Runpod 上租用的一块 H100 GPU 上用了不到 10 小时。模型权重已开放在 Hugging Face 上，同时提供了一个可直接下载的 inference.py 推理脚本，可生成 256x256 分辨率的图像。 这说明一个可用的开源权重文生图模型可以在单块 GPU 上、一天之内完成端到端训练，并能在本地运行，大幅降低了个人和小型实验室在算力与成本上的门槛。如果其宣称的画质能够经得起验证，将进一步推动“小而可下载”的图像模型趋势，使其能在消费级硬件上微调和部署。 作者称在 CPU 上生成一张图约需 20 秒，在 GPU 上约 2 秒；并声称展示的样例并非精挑细选，全部使用相同设置生成：种子 0、50 步采样、无分类器引导系数 3.0。需要注意的是，其输出分辨率仅为 256x256，且“最先进（SOTA）”的画质说法属于自述，尚未经第三方验证。

reddit · r/LocalLLaMA · /u/LH-Tech_AI · 9月21日 15:21

**背景**: 扩散 Transformer（DiT）是一类潜在扩散模型，它用作用于潜在表示切块的 Transformer 取代了传统的 U-Net 主干，这一思路由 2022 年的论文《Scalable Diffusion Models with Transformers》推广开来。文生图通常依赖无分类器引导（classifier-free guidance），即通过在条件预测与无条件预测之间插值来让生成结果更贴合文本提示，并由 CFG 系数控制强度。Nvidia H100 是采用 Hopper 架构的数据中心 GPU，广泛用于大模型训练，而 Runpod 则是按小时出租这类 GPU 的云服务平台。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2212.09748">[2212.09748] Scalable Diffusion Models with Transformers</a></li>
<li><a href="https://grokipedia.com/page/Classifier-free_guidance">Classifier-free guidance</a></li>
<li><a href="https://en.wikipedia.org/wiki/NVIDIA_H100_GPU">NVIDIA H100 GPU</a></li>

</ul>
</details>

**标签**: `#text-to-image`, `#open-source-model`, `#diffusion-transformer`, `#local-inference`, `#huggingface`

---