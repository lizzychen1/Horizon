---
layout: default
title: "Horizon Summary: 2026-07-09 (ZH)"
date: 2026-07-09
lang: zh
---

> 从 76 条内容中筛选出 15 条重要资讯。

---

1. [蚂蚁灵波开源全球首个 MoE 具身视频生成模型](#item-1) ⭐️ 10.0/10
2. [Dify 1.16.0-rc1 发布实验性 Agent 构建器，集成 Linux 沙箱](#item-2) ⭐️ 9.0/10
3. [Meta 发布 Muse Spark 1.1 智能体 AI 模型](#item-3) ⭐️ 9.0/10
4. [展示 HN：将任何智能体用作编排器](#item-4) ⭐️ 9.0/10
5. [Demo_CLI：AI 代理操作的一键撤销](#item-5) ⭐️ 9.0/10
6. [在 25GB 内存的消费级机器上运行 744B GLM-5.2 MoE 模型](#item-6) ⭐️ 9.0/10
7. [NVIDIA Puzzle-75B-A9B MoE 在三张 3090 上达到 132 token/秒](#item-7) ⭐️ 9.0/10
8. [升级公众号排版技能，加入动画和组件系统](#item-8) ⭐️ 9.0/10
9. [插件集成 GLM 5.2 和 GPT 5.5，通过 Codex 子代理执行任务](#item-9) ⭐️ 9.0/10
10. [在慢速电脑上运行 GLM 5.2：int4 量化、MTP 与 DSA](#item-10) ⭐️ 8.0/10
11. [腾讯 Hy3 小型 LLM 在 OpenRouter 上免费至 7 月 21 日](#item-11) ⭐️ 8.0/10
12. [用 LLM 将 Postgres 重写为 Rust，通过所有回归测试](#item-12) ⭐️ 8.0/10
13. [OpenAI 发布 GPT-5.6 系列：Luna、Terra、Sol](#item-13) ⭐️ 8.0/10
14. [LocalClip：一款本地优先的 AI 视频剪辑工具，适用于 Mac](#item-14) ⭐️ 8.0/10
15. [买卖闲置 AI 积分，Claude 积分半价入手](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [蚂蚁灵波开源全球首个 MoE 具身视频生成模型](https://www.qbitai.com/2026/07/446458.html) ⭐️ 10.0/10

蚂蚁灵波开源了全球首个基于混合专家（MoE）架构的具身智能视频生成基础模型 LingBot-Video。该模型总参数量为 30B，但每次推理仅激活约 3B 参数，效率约为同等规模稠密模型的 3 倍。 此次开源显著推动了具身智能发展，提供了一个高效、开源的模型，可用于机器人动作预测和仿真数据生成。它能加速机器人和世界模型领域的研究，降低具身领域高质量视频生成的计算门槛。 LingBot-Video 采用 DiT+MoE 设计、多维强化学习奖励系统（侧重物理合理性和任务完成度），以及包含 7 万小时具身数据的画像引擎。在 RBench 评测基准上，它以 0.620 的总分超越了 Wan2.6、Seedance1.5 Pro 和 Cosmos3 Super 等模型。

telegram · zaihuapd · 7月9日 04:30

**背景**: 混合专家（MoE）是一种神经网络架构，每次输入仅激活部分参数，从而在较低计算成本下支持更大的模型。扩散变换器（DiT）将扩散模型与 Transformer 主干结合，用于高质量视频生成。具身智能关注能够感知并交互物理世界的智能体，如机器人。LingBot-Video 融合了这些技术，从文本或动作指令生成机器人操作视频。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Mixture_of_experts">Mixture of experts - Wikipedia</a></li>
<li><a href="https://www.nvidia.com/en-us/glossary/mixture-of-experts/">What Is Mixture of Experts (MoE) and How It Works? | NVIDIA Glossary</a></li>
<li><a href="https://arxiv.org/abs/2212.09748">[2212.09748] Scalable Diffusion Models with Transformers</a></li>

</ul>
</details>

**标签**: `#AI模型`, `#开源`, `#具身智能`, `#视频生成`, `#MoE`

---

<a id="item-2"></a>
## [Dify 1.16.0-rc1 发布实验性 Agent 构建器，集成 Linux 沙箱](https://github.com/langgenius/dify/releases/tag/1.16.0-rc1) ⭐️ 9.0/10

Dify 发布了 1.16.0-rc1 版本，引入了一个运行在 Linux 沙箱中的实验性 Agent 构建器。用户可以通过 UI 设置提示词、上传 Skills 和文件，并连接 Dify 生态系统中的工具和知识来创建自定义 Agent。 此版本是开源 AI Agent 发展的重要一步，使用户能够在 Dify 生态系统中以沙箱安全方式构建和部署自定义 Agent。它降低了创建复杂基于 LLM 的 Agent 的门槛，并将其集成到工作流和 Web 应用中。 在当前实验性版本中，所有 Agent 共享同一个沙箱，没有严格的隔离，因此仅推荐用于可信用户。此外，当使用 Agent 节点时，Dify Workflow DSL 导出等功能不可用。

github · QuantumGhost · 7月9日 14:06

**背景**: Dify 是一个用于构建 LLM 应用的开源平台。基于 Shell 的 LLM Agent 范式允许 Agent 通过自然语言执行 Shell 命令，极大地扩展了其能力。Dify Skills 是标准化模块，用于封装 Agent 功能以实现复用。此次版本将这些概念整合到一个带有沙箱运行时的可视化构建器中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://unix.stackexchange.com/questions/790351/llm-agent-user-interface">shell - LLM-Agent User Interface - Unix & Linux Stack Exchange</a></li>
<li><a href="https://forum.dify.ai/t/1-14-0-rc1-dify-x-agent-skills-for-production-workflows-collaboration-beta/1115">1.14.0-rc1: Dify x Agent Skills for Production Workflows & Collaboration (beta) - Announcements - Dify Community</a></li>

</ul>
</details>

**标签**: `#dify`, `#agent`, `#open-source`, `#ai-tools`, `#agent-framework`

---

<a id="item-3"></a>
## [Meta 发布 Muse Spark 1.1 智能体 AI 模型](https://ai.meta.com/blog/introducing-muse-spark-meta-model-api/) ⭐️ 9.0/10

Meta 发布了 Muse Spark 1.1，一个提供 API 访问并附带评估报告的智能体 AI 模型。社区成员 Simon Willison 还为 LLM 命令行工具开发了插件，方便用户测试该模型。 此次发布标志着 Meta 在智能体 AI 市场的大力进军，其具有竞争力的定价和开放访问可能颠覆 OpenAI 和 Anthropic 等既有玩家。低廉的定价（每百万 token 1.25/4.5 美元）和开放权重策略可能使编程模型商品化，并扩大 AI 智能体的应用。 定价为每百万输入 token 1.25 美元，每百万输出 token 4.5 美元，每百万缓存输入 token 0.15 美元。评估报告受到社区成员批评，称基准测试中使用的资源限制（6 个 CPU 核心、8GB 内存）导致结果不符合 Terminal-Bench 2.1 的要求。

hackernews · ot · 7月9日 14:10 · [社区讨论](https://news.ycombinator.com/item?id=48846184)

**背景**: 智能体 AI 指的是能够自主感知、推理并采取行动以实现目标的 AI 系统，通常涉及工具使用和多步骤规划。Muse Spark 是 Meta 于 2026 年 4 月推出的原生多模态推理模型，专为复杂推理和工具编排设计，目前已用于 Meta 的 AI 助手。1.1 版本是一次迭代更新，提供了 API 访问和透明的评估报告。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ai.meta.com/blog/introducing-muse-spark-msl/">Introducing Muse Spark: Scaling Towards Personal Superintelligence</a></li>
<li><a href="https://mitsloan.mit.edu/ideas-made-to-matter/agentic-ai-explained">Agentic AI, explained | MIT Sloan</a></li>

</ul>
</details>

**社区讨论**: 社区反响不一：一些人赞扬低价格和开放访问，而另一些人则因资源限制不同而质疑基准测试结果的有效性。用户 jacobgold 建议 Meta 应扮演“破坏者”角色，通过开源前沿模型使竞争对手的产品商品化；Tiberium 则强调了极低的缓存输入价格。

**标签**: `#AI model`, `#Meta`, `#coding agent`, `#LLM`, `#open source`

---

<a id="item-4"></a>
## [展示 HN：将任何智能体用作编排器](https://github.com/backnotprop/orchestrator) ⭐️ 9.0/10

一个开源 GitHub 仓库展示了一种灵活的方法，通过将任何 AI 智能体视为编排器来编排多智能体工作流，实现动态任务委派和协调。 这种模式通过重用现有智能体作为编排器，简化了复杂多智能体系统的构建，减少了对专门编排代码的需求，促进了模块化、可扩展的架构。 该仓库提供了实用的代码示例，展示了如何在智能体之间委派任务和移交控制权，利用任何智能体的原生能力进行编排，而无需固定的中央控制器。

rss · Show HN (self-made tools) · 7月9日 22:26

**背景**: 多智能体编排模式（如监督者、移交和扇出）在 AI 系统中很常见，用于协调多个智能体。通常，专门的编排智能体或外部工作流引擎管理任务分配。该项目挑战了这一点，允许任何智能体动态充当编排器，反映了向更去中心化智能体架构的趋势。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://learn.microsoft.com/en-us/microsoft-copilot-studio/guidance/multi-agent-patterns">Multi-agent orchestration patterns and best practices ...</a></li>
<li><a href="https://learn.microsoft.com/en-us/azure/architecture/ai-ml/guide/ai-agent-design-patterns">AI Agent Orchestration Patterns - Azure Architecture Center</a></li>
<li><a href="https://www.digitalapplied.com/blog/multi-agent-orchestration-5-patterns-that-work">Multi-Agent Orchestration: 5 Patterns That Work in 2026</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#orchestration`, `#GitHub`, `#open source`

---

<a id="item-5"></a>
## [Demo_CLI：AI 代理操作的一键撤销](https://github.com/WePwn/demo_cli) ⭐️ 9.0/10

Demo_CLI 是一个命令行工具，可在 AI 代理执行类似 `rm -rf` 的破坏性命令前自动对文件系统进行快照，并提供一键撤销功能。 随着 AI 代理在执行 shell 命令方面越来越自主，该工具通过防止不可逆的数据丢失填补了关键的安全空白。它让开发者能够放心地用 AI 代理进行实验，而不必担心灾难性错误。 该工具可能使用 LVM 或 ZFS 快照等文件系统快照机制，或通过 rsync 等创建写时复制备份。它通过拦截危险命令并提示创建快照来集成到 AI 代理工作流中。

rss · Show HN (self-made tools) · 7月9日 20:56

**背景**: AI 代理是能够代表用户执行命令的程序，通常无需人类监督。如果代理运行了类似 `rm -rf /` 的命令，可能导致意外数据删除。基于快照的回滚是一种常见的系统管理技术，用于撤销不想要的更改。

**标签**: `#AI agents`, `#CLI tool`, `#safety`, `#undo`, `#snapshot`

---

<a id="item-6"></a>
## [在 25GB 内存的消费级机器上运行 744B GLM-5.2 MoE 模型](https://www.reddit.com/r/LocalLLaMA/comments/1us5m0g/glm52_744b_moe_on_a_25gbram_consumer_machine/) ⭐️ 9.0/10

这一突破使前沿级编程 AI 能够在普通硬件上运行，无需昂贵的云端 GPU 即可本地部署。同时凸显了 MoE 架构在消费级应用中的效率优势。 GLM-5.2 虽总参数为 744B，但每次仅激活 40B，大幅降低了计算量。为了在 25GB 内存中运行，用户很可能采用了 4 位或更低量化，并将部分层卸载到 CPU 内存，这是 Ollama 或 llama.cpp 等框架的常见做法。

reddit · r/LocalLLaMA · /u/yogthos · 7月9日 22:43

**背景**: 混合专家（MoE）模型使用多个专用子网络（专家）和一个门控机制，每次输入只激活一部分专家，从而在低每次 token 成本下实现大总参数量。消费级 GPU 通常只有 24GB 显存，未量化模型只能运行约 14B 参数；量化（降低比特精度）和卸载（将层分散到 GPU 和 CPU）等技术允许在有限硬件上运行更大的模型。GLM-5.2 是智谱 AI 推出的开源 744B MoE 模型，在编程和设计任务上表现出色。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.spheron.network/blog/deploy-glm-5-2-gpu-cloud/">Deploy GLM-5.2 on GPU Cloud: Self-Host Z.ai's 744B Coding MoE with 1M Context (2026 Guide) | Spheron Blog</a></li>
<li><a href="https://huggingface.co/blog/moe">Mixture of Experts Explained - Hugging Face</a></li>
<li><a href="https://www.mindstudio.ai/blog/what-is-glm-5-2-open-weight-model-6">What Is GLM 5.2? The Open-Weight Model With Frontier-Level Coding and Design Taste | MindStudio</a></li>

</ul>
</details>

**标签**: `#LLM`, `#local-llm`, `#model-optimization`, `#consumer-hardware`, `#MoE`

---

<a id="item-7"></a>
## [NVIDIA Puzzle-75B-A9B MoE 在三张 3090 上达到 132 token/秒](https://www.reddit.com/r/LocalLLaMA/comments/1uru9ja/nvidia_puzzle75ba9b_nvfp4_at_132_ts_on_33090_why/) ⭐️ 9.0/10

一位 Reddit 用户报告称，使用 vLLM 0.22.1 在三张 RTX 3090 显卡上以 NVFP4 格式运行 Nemotron-3-Puzzle-75B-A9B 混合专家模型，在三个并发流上实现了每秒 132 token 的解码速度和 1949 token/秒的预填充速度，系统总功耗低于 500 瓦。 这一配置完美填满了三张 24GB 显卡的 72GB 显存，属于罕见的大小类别，以远小于密集模型的速度带来了密集模型的质量，实现了之前不可能在不溢出到内存或深度量化的情况下完成的高效本地 LLM 部署。 该模型采用混合 Mamba 架构以保持 KV 缓存极小，vLLM 的新 Marlin 回退机制使得 FP4 推理能在 3090 等 Ampere 显卡上运行。该设置以流水线并行方式在三张功耗上限为 200W 的显卡上运行，释放了第四张显卡用于其他任务。

reddit · r/LocalLLaMA · /u/Important_Quote_1180 · 7月9日 15:53

**背景**: 混合专家（MoE）模型每个 token 只激活部分参数，从而允许更大的总参数量同时保持高效计算。NVFP4 是 NVIDIA 推出的 4 位浮点格式，在精度和内存效率之间取得平衡。vLLM 是一个高吞吐量推理引擎。RTX 3090 拥有 24GB 显存，三张卡共 72GB，这对于高精度模式下密集型 70B+ 模型来说不够，但非常适合像 Puzzle-75B-A9B（总参数量 75B，活跃参数 9B）这样经过精心量化的 MoE 模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.nvidia.com/blog/introducing-nvfp4-for-efficient-and-accurate-low-precision-inference/">Introducing NVFP4 for Efficient and Accurate Low-Precision ...</a></li>
<li><a href="https://github.com/vllm-project/vllm">GitHub - vllm-project/vllm: A high-throughput and memory ...</a></li>
<li><a href="https://arxiv.org/abs/2403.19887">Jamba: A Hybrid Transformer-Mamba Language Model A hybrid model based on transformer and Mamba for enhanced ... GitHub - state-spaces/mamba: Mamba SSM architecture Understanding and Enhancing Mamba-Transformer Hybrids for ... A hybrid model based on transformer and Mamba for enhanced ... Jamba: A Hybrid Transformer-Mamba Language Model with Mixture ...</a></li>

</ul>
</details>

**标签**: `#MoE`, `#local LLM`, `#inference optimization`, `#VRAM`, `#3090`

---

<a id="item-8"></a>
## [升级公众号排版技能，加入动画和组件系统](https://x.com/zjp1997720/status/2075194356299096341) ⭐️ 9.0/10

用户升级了其微信公众号排版 AI Skill，增加了开场动画和组件系统，灵感来源于“摸鱼小李”。同时提供了展示链接。 此次升级使自动化文章排版更具吸引力和灵活性，可能为内容创作者节省时间并提升视觉效果。这与微信公众号 AI 驱动内容创作工具的发展趋势相一致。 该技能可能输出兼容微信编辑器的内联 CSS HTML，类似于 GitHub 上已有的开源工具 wechat-layout。组件系统支持可复用的格式化模块，以实现一致的设计。

twitter · zjp1997720 · 7月9日 12:24

**背景**: 微信公众号排版编辑传统上需要手动设置样式或使用第三方编辑器。此类 AI Skill 利用大语言模型直接生成格式化 HTML，简化了工作流程。开源项目 wechat-layout 通过提供预设样式和自动样式提取，为这类技能奠定了基础。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Greatbeing/wechat-layout">GitHub - Greatbeing/wechat-layout: 微信公众号图文排版设计器 | WeC...</a></li>
<li><a href="https://wechalet.cn/en/appstore/detail/40bl">Typesetting editor for WeChat official account_WeChalet Site ...</a></li>

</ul>
</details>

**标签**: `#AI排版`, `#公众号`, `#技能`, `#AI工具`

---

<a id="item-9"></a>
## [插件集成 GLM 5.2 和 GPT 5.5，通过 Codex 子代理执行任务](https://x.com/zjp1997720/status/2075088921760026666) ⭐️ 9.0/10

一位开发者为 zcode 制作了一个插件，使用 GLM 5.2 作为主控模型，通过 Codex 调用 GPT 5.5 作为子代理执行任务，解决了 GPT 5.5 表现不佳的问题。 该插件展示了一种实用的多模型编排方法，利用更强的开源模型作为控制器来弥补较弱模型的不足，这是 AI 智能体开发中的常见挑战。 该插件强制 GPT 5.5 作为子代理在 GLM 5.2 的指导下运行，可能克服了 GPT 5.5 输出质量不佳的倾向。Codex 被用作子代理执行框架。

twitter · zjp1997720 · 7月9日 05:25

**背景**: ZCode 是一个 AI 编码平台，集成了用于规划、编码和审查的 AI 智能体。GLM 5.2 是一款在长周期任务上表现出色的开源模型，而 GPT 5.5 是专有模型，有时结果较弱。多智能体设置允许组合模型以发挥各自优势。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zcode.z.ai/en">ZCode - Simple, Fast, Vibe‑Ready | Official Harness for GLM-5.2</a></li>
<li><a href="https://openlm.ai/glm-5.2/">GLM-5.2 - openlm.ai</a></li>
<li><a href="https://venturebeat.com/technology/z-ai-launches-zcode-to-challenge-cursor-claude-code-and-github-copilot-in-ai-coding">Z.ai launches ZCode to challenge Cursor, Claude Code and ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#multi-model orchestration`, `#zcode plugin`, `#Codex`, `#LLM integration`

---

<a id="item-10"></a>
## [在慢速电脑上运行 GLM 5.2：int4 量化、MTP 与 DSA](https://github.com/JustVugg/colibri) ⭐️ 8.0/10

一位开发者创建了 Colibrì，这是一个基于 C 语言的推理引擎，通过 int4 量化、多令牌预测（MTP）和动态稀疏注意力（DSA），在 32GB RAM 的笔记本电脑上运行 744B 参数的 GLM 5.2 模型，速度约为 0.1 tok/s。 这表明大型混合专家模型可以在没有昂贵 GPU 的情况下经济地运行，使前沿 LLM 在消费级硬件上变得可及。它展示了实用的优化技术，可能会启发类似项目。 该引擎按需从磁盘流式加载 21,504 个路由专家（约 370GB），使用 LRU 缓存和操作系统页面缓存，仅约 9.9GB 的密集参数以 int4 常驻 RAM。项目是单文件 C 语言实现（约 1300 行），无需 BLAS 或 Python 运行时依赖。

hackernews · vforno · 7月9日 08:05 · [社区讨论](https://news.ycombinator.com/item?id=48842459)

**背景**: int4 量化将模型权重降低到 4 位整数，大幅减少内存使用且精度损失极小。多令牌预测（MTP）允许模型同时预测多个未来令牌，加速推理。动态稀疏注意力（DSA）选择性关注相关令牌，降低长上下文的计算成本。这些技术共同实现了在有限硬件上运行大型模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2301.12017">[PDF] Understanding INT4 Quantization for Language Models: Latency ... - arXiv</a></li>
<li><a href="https://ai.google.dev/gemma/docs/mtp/mtp">Gemma 4 Multi-Token Prediction (MTP) using Hugging Face ...</a></li>
<li><a href="https://amitray.com/deepseek-sparse-attention-dsa-a-comprehensive-review/">DeepSeek Sparse Attention (DSA): A Comprehensive Review</a></li>

</ul>
</details>

**社区讨论**: 社区评论表达了兴趣并分享了类似工作：一位用户正在 Apple Silicon 上使用 Unsloth 拆分 GGUF 和原生 Metal 内核；另一位质疑 0.1 tok/s 是否可用（每分钟 1 个 token 可能更实用）；第三位提到了 mmap 方法和 Medusa 头；还有关于流式加载导致 SSD 磨损的担忧，repo 中已包含警告。

**标签**: `#GLM`, `#LLM optimization`, `#local LLM`, `#int4 quantization`, `#GitHub project`

---

<a id="item-11"></a>
## [腾讯 Hy3 小型 LLM 在 OpenRouter 上免费至 7 月 21 日](https://hy.tencent.com/research/hy3) ⭐️ 8.0/10

腾讯的 Hy3 模型是一款 295B 参数混合专家（MoE）小型 LLM，具有 21B 激活参数，现通过 Novita Labs 的推广在 OpenRouter 上免费使用，截止至 7 月 21 日。 这次免费试用降低了开发者测试一款能力媲美更大模型的小型 LLM 的门槛，可能推动其在资源受限环境中的采用。 Hy3 采用 Apache 2.0 许可证开源，性能优于同类尺寸模型，与 DeepSeek V4 Pro 等旗舰模型竞争力相当。OpenRouter 上的免费层由 Novita Labs 提供，将于 2026 年 7 月 21 日结束。

hackernews · andai · 7月9日 15:27 · [社区讨论](https://news.ycombinator.com/item?id=48847552)

**背景**: Hy3 是一种混合专家（MoE）模型，每次推理只使用部分参数（21B 激活），因此效率很高。OpenRouter 是一个统一 API 平台，提供对数百种 LLM 的访问，包括免费层和促销活动。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Tencent-Hunyuan/Hy3">GitHub - Tencent-Hunyuan/Hy3: Hy3 (295B A21B), a leading ...</a></li>
<li><a href="https://www.tencent.com/en-us/articles/2202386.html">Tencent Hunyuan Officially Releases Hy3, Advancing Agent ...</a></li>
<li><a href="https://www.datacamp.com/tutorial/openrouter">OpenRouter: A Guide With Practical Examples | DataCamp</a></li>

</ul>
</details>

**社区讨论**: 社区指出，Hy3 此前在 OpenRouter 排名中位居榜首，现已降至第 8-9 位。一些用户将其与 DeepSeek Flash V4 比较，认为定价和尺寸相似，并对其在重度量化下的表现表示好奇。

**标签**: `#AI model`, `#LLM`, `#Tencent`, `#OpenRouter`, `#free trial`

---

<a id="item-12"></a>
## [用 LLM 将 Postgres 重写为 Rust，通过所有回归测试](https://github.com/malisper/pgrust) ⭐️ 8.0/10

开发者 malisper 创建了 pgrust 项目，利用大语言模型将 PostgreSQL 数据库完全用 Rust 重写，现已 100%通过官方 Postgres 回归测试。 这展示了 LLM 辅助重写大型成熟代码库的潜力，可能催生更安全、高性能的 PostgreSQL 替代品，同时引发关于许可证兼容性和代码可审查性的讨论。 该项目在不到一个月内产生了 7101 次提交，使得传统代码审查不切实际；作者正在开发一个包含更多技术的新版本，尚未发布。许可证从 PostgreSQL 许可证改为 AGPL。

hackernews · SweetSoftPillow · 7月9日 06:18 · [社区讨论](https://news.ycombinator.com/item?id=48841676)

**背景**: PostgreSQL 是一款广泛使用的开源关系型数据库，已有 30 多年历史。Rust 是一种注重安全性和并发性的系统编程语言。该项目利用 LLM 自动将 C 代码翻译为 Rust，展示了人工智能辅助大规模软件迁移的能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/curtis-sun/LLM4Rewrite/blob/main/README.md">LLM4Rewrite/README.md at main · curtis-sun/LLM4Rewrite · GitHub</a></li>
<li><a href="https://markaicode.com/postgresql-ai-schema-migrations-automation/">PostgreSQL + AI: Automating Schema Migrations That Actually ...</a></li>

</ul>
</details>

**社区讨论**: 社区评论关注 LLM 生成代码的可审查性问题（一个月内 7101 次提交）以及许可证从 PostgreSQL 许可证改为 AGPL，有建议通过生产环境中镜像查询来测试。作者确认正在开发改进版本。

**标签**: `#AI-assisted coding`, `#Rust`, `#PostgreSQL`, `#GitHub project`, `#LLM`

---

<a id="item-13"></a>
## [OpenAI 发布 GPT-5.6 系列：Luna、Terra、Sol](https://simonwillison.net/2026/Jul/9/gpt-5-6/#atom-everything) ⭐️ 8.0/10

OpenAI 宣布 GPT-5.6 系列全面上市，该系列包括三个尺寸——Luna、Terra 和 Sol——具备更强的代理性能、百万 token 上下文窗口，以及程序化工具调用和多智能体支持等新 API 功能。 GPT-5.6 在长时间代理任务上树立了新标杆，在 Agent's Last Exam 中大幅超越 Claude Fable 5，且成本显著降低，这可能会改变 AI 代理开发的竞争格局。 三个模型的知识截止日期均为 2026 年 2 月 16 日，拥有百万 token 上下文窗口和 128,000 最大输出 token。定价从 Luna 的每百万输入/输出 token $1/$6 到 Sol 的 $5/$30 不等。

rss · Simon Willison · 7月9日 19:46

**背景**: 像 GPT 和 Claude 这样的大型语言模型通过预测 token 来生成文本。代理性能指的是模型自主完成多步骤任务的能力。Agent's Last Exam 等基准评估了跨多个领域的长时间专业工作流程，以衡量实际效用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2606.05405">[2606.05405] Agents' Last Exam - arXiv.org</a></li>
<li><a href="https://agents-last-exam.org/">AI Agent Benchmark for Real-World Professional Workflows</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一：有人强调 Sol 在 ARC-AGI-3 上达到最新最优，也有人指出 OpenAI 在生物基准中未包含 Fable 5，因为它拒绝回答。与 Claude Code 的比较以及开放性与能力的争论仍在继续。

**标签**: `#GPT-5.6`, `#OpenAI`, `#language models`, `#agentic performance`

---

<a id="item-14"></a>
## [LocalClip：一款本地优先的 AI 视频剪辑工具，适用于 Mac](https://localclip.io/?lang=en) ⭐️ 8.0/10

LocalClip 是一款新推出的本地优先 AI 视频剪辑工具，专为 Mac 设计，用户无需将任何数据上传到云端即可剪辑视频，确保隐私和离线可用性。 该工具通过完全在设备端实现强大的 AI 视频剪辑，解决了日益增长的隐私担忧和对互联网连接的依赖，为 Mac 上注重隐私的媒体工具树立了先例。 LocalClip 在 Mac 本地运行 AI 模型，利用硬件加速（如 Apple Silicon）实现实时处理；它支持常见视频格式，并直接将剪辑导出到文件系统。

rss · Show HN (self-made tools) · 7月9日 21:03

**背景**: 本地优先软件是一种应用程序主要将数据存储在用户自己设备上而非远程服务器的方法，支持离线工作和增强隐私。这个概念由 Ink & Switch 在 2019 年的一篇论文中推广，与依赖服务器端处理的传统云端应用形成对比。LocalClip 通过在 Mac 本地执行所有视频剪辑任务体现了这一理念。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Local-first_software">Local-first software</a></li>
<li><a href="https://lofi.so/">Local-First Software</a></li>
<li><a href="https://www.inkandswitch.com/local-first-software/">Local-first Software</a></li>

</ul>
</details>

**标签**: `#AI tool`, `#video clipper`, `#Mac`, `#local-first`

---

<a id="item-15"></a>
## [买卖闲置 AI 积分，Claude 积分半价入手](https://secondhandtokens.com/) ⭐️ 8.0/10

新平台 Second Hand Tokens 允许开发者买卖未使用的 AI 积分，其中 Claude 积分可享半价优惠。 该市场减少了闲置 AI 积分造成的财务浪费，让开发者能以更低成本使用优质 AI 模型，可能改变 AI 资源的分配和消费方式。 该平台支持 Claude、Llama 和 DeepSeek 代币，采用点对点交易模式，卖家以五折价格出售闲置积分。平台于 2026 年 6 月 22 日上线，目前正在积累用户。

rss · Show HN (self-made tools) · 7月9日 20:51

**背景**: AI 积分是用于 Claude、Llama 和 DeepSeek 等服务的预付费使用额度。付费套餐用户在用完包含的使用限制后，可购买积分继续使用模型。闲置积分往往被浪费，Second Hand Tokens 通过创建二级市场来解决这一问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://secondhandtokens.com/">Second Hand Tokens — AI tokens at 50% off the price</a></li>
<li><a href="https://claude.com/pricing">Plans & Pricing | Claude by Anthropic</a></li>
<li><a href="https://support.claude.com/en/articles/12429409-manage-usage-credits-for-paid-claude-plans">Manage usage credits for paid Claude plans</a></li>

</ul>
</details>

**标签**: `#AI credits`, `#discount`, `#Claude`, `#marketplace`, `#resource`

---