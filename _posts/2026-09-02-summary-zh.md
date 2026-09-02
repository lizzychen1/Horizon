---
layout: default
title: "Horizon Summary: 2026-09-02 (ZH)"
date: 2026-09-02
lang: zh
---

> 从 64 条内容中筛选出 10 条重要资讯。

---

1. [谷歌发布 Gemini 3.8 Flash 与 Flash Cyber](#item-1) ⭐️ 9.0/10
2. [Perplexity 开源针对 Qwen 3.6 优化的 Mac 推理服务器 Lily](#item-2) ⭐️ 9.0/10
3. [Meta 发布低成本高性能 AI 模型 Muse Spark 1.3](#item-3) ⭐️ 8.0/10
4. [llm-gemini 0.34 新增对 Gemini 3.8 Flash 的思考级别支持](#item-4) ⭐️ 8.0/10
5. [Anthropic 发布 Claude Fable 5.1，科学基准测试大幅领先](#item-5) ⭐️ 8.0/10
6. [用户用本地 GLM 5.3 Flash 打造《我的世界》黑洞模组](#item-6) ⭐️ 8.0/10
7. [DeepSeek-V4-Flash-Vision-Exp 完成视觉支持合并并发布 GGUF](#item-7) ⭐️ 8.0/10
8. [Paint.NET 开发者称 Claude 编写了 18 万行 Direct2D/Wine 代码](#item-8) ⭐️ 7.0/10
9. [在 Confluent 上部署 IBM 时间序列模型实现实时智能](#item-9) ⭐️ 7.0/10
10. [阿里发布 Qwen3.8-Max-0902，CodeArena 编程榜 1691 分夺冠](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [谷歌发布 Gemini 3.8 Flash 与 Flash Cyber](https://blog.google/innovation-and-ai/models-and-research/gemini-models/3-8-flash-and-3-8-flash-cyber/) ⭐️ 9.0/10

谷歌发布了 Gemini 3.8 Flash 和 3.8 Flash Cyber，这是 Gemini 3 系列的最新模型。Flash 模型针对长时程编码和自主智能体场景，相较 3.7 Flash 有显著提升。 这使得接近前沿水平的模型智能以 Flash 级的速度和成本变得可用，用户已展示了不到两美分生成真实输出的实例。该模型还扩展了音频/视频输入等多模态能力，可能重塑智能体、编程和媒体分析等工作流。 据社区报告，Gemini 3.8 Flash 在 DeepSwe 基准测试中排名第一，超过 Opus 5，并在 Artificial Analysis 的智能指数上获得 59 分，与 Opus 5 medium 持平。Simon Willison 演示了 1.8 美分、耗时 13 秒的 HTML 生成实验，但他指出低思考档位相比 3.7 可能有所退步。

hackernews · bratao · 9月2日 15:12 · [社区讨论](https://news.ycombinator.com/item?id=49537553)

**背景**: Gemini Flash 模型是谷歌 Gemini 3 系列中的轻量级高性价比模型，面向高并发或低延迟场景。新的 3.8 Flash 在 3.7 Flash 基础上改进，在软件工程和智能体工作流方面有所提升。3.8 Flash Cyber 是在 Flash 基础上针对防御者微调的变体，旨在以更低成本检测漏洞并自动修复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/models-and-research/gemini-models/3-8-flash-and-3-8-flash-cyber/">Introducing Gemini 3 . 8 Flash and 3 . 8 Flash Cyber</a></li>
<li><a href="https://deepmind.google/models/model-cards/gemini-3-8-flash/">Gemini 3 . 8 Flash - Model Card — Google DeepMind</a></li>
<li><a href="https://deepmind.google/models/gemini/cyber/">Gemini 3.8 Flash Cyber — Google DeepMind</a></li>

</ul>
</details>

**社区讨论**: Hacker News 评论者对此反应热烈，多位用户分享了实际使用体验和基准测试结果。Simon Willison 强调该模型的 HTML/JavaScript 能力和多模态输入是最引人注目的特点，其他人报告它在 DeepSwe 及个人应用基准上超过了更大的模型。有评论者提出，低思考档位的质量可能与 3.7 相比有所退步。

**标签**: `#Gemini`, `#AI model`, `#LLM`, `#Google`, `#coding`

---

<a id="item-2"></a>
## [Perplexity 开源针对 Qwen 3.6 优化的 Mac 推理服务器 Lily](https://www.reddit.com/r/LocalLLaMA/comments/1w5ozl4/perplexity_opensourced_their_mac_inference_server/) ⭐️ 9.0/10

Perplexity 已开源 Lily——一个为 Apple Silicon 上的 Qwen3.6-35B-A3B 设计的小型 Metal 推理服务器。相关代码已发布在 pplx-garden GitHub 仓库，据称在 M5 Max 上表现优于 MLX-LM。 这为开发者提供了一个来自头部 AI 公司、可直接上手的高效本地推理参考实现。同时，它也表明针对单一检查点特化的引擎可以把 Apple Silicon 上的性能推得比通用运行时更高。 Lily 只针对一个检查点优化：转换为 MLX affine 4-bit 权重的 Qwen3.6-35B-A3B，并且仅暴露 OpenAI Chat Completions API 的精简子集，始终使用贪婪解码。Perplexity 表示，它是为 Perplexity Computer 中的混合计算而构建，目的是让端侧推理不会拖慢 Computer 任务。

reddit · r/LocalLLaMA · /u/Specter_Origin · 9月2日 22:13

**背景**: Apple Silicon 的统一内存使得大模型能在本地运行，但高效推理需要经过调优的运行时。Lily 基于 Apple 的 Metal 图形/计算框架，而 MLX 是 Apple 面向机器学习的数组框架——MLX-LM 是运行这类模型时常见的基准实现。Qwen 3.6 是阿里巴巴的开源权重模型系列，其中 Qwen3.6-35B-A3B 是混合专家（MoE）模型，只有约 3B 激活参数，非常适合端侧推理。据报道，Lily 在 M5 Max 上的 prefill 速度比 MLX-LM 快 1.23 倍，decode 速度快 1.35 倍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/perplexityai/pplx-garden/tree/main/lily">pplx-garden/lily at main · perplexityai/pplx-garden · GitHub</a></li>
<li><a href="https://alphasignal.ai/news/perplexity-s-lily-beats-mlx-lm-by-1-35x-running-qwen3-6-on-apple-silicon">Perplexity's Lily Beats MLX-LM by 1.35x Running Qwen3.6 on Apple ...</a></li>
<li><a href="https://x.com/denisyarats/status/2095243141456781499">Denis Yarats on X: "we are open-sourcing Lily, lightweight local ...</a></li>

</ul>
</details>

**标签**: `#open-source`, `#local-LLM`, `#inference`, `#Apple-Silicon`, `#GitHub`

---

<a id="item-3"></a>
## [Meta 发布低成本高性能 AI 模型 Muse Spark 1.3](https://developer.meta.com/ai/models/muse-spark/) ⭐️ 8.0/10

Meta 发布了 Muse Spark 1.3，这是一个面向长时运行智能体、多智能体和编程工作流的多模态推理模型。它在 DeepSWE 基准测试中取得 75.4 分，社区用户已经在实际编程和生成任务中开始测试它。 这次发布表明，一个成本低得多的模型也能在长视野软件工程基准测试中接近最先进水平。这可能会促使其他 AI 实验室下调编程智能体的价格，让开发者更容易用上强大的 AI。 根据 OpenRouter 的模型页面，Muse Spark 1.3 是为智能体、多智能体和编程用途打造的多模态推理模型。社区中的一项测试在约 38 秒内生成了一个 SVG，花费约 4.2 美分；还有用户指出，该模型允许 Meta 使用用户数据进行训练，以此换取更低价格。

hackernews · bvaldivielso · 9月2日 19:35 · [社区讨论](https://news.ycombinator.com/item?id=49541256)

**背景**: DeepSWE 是一个长视野、无数据污染的软件工程基准测试，用于区分顶尖编程智能体。Muse Spark 是 Meta 旗下“超级智能实验室”（Superintelligence Labs）发布的首个模型，该实验室是 Meta 为推进前沿 AI 研究而斥巨资组建的。Muse Spark 1.3 现已在 OpenRouter 上通过 API 提供商提供，开发者可以在 Claude Code 等工具或自建框架中试用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openrouter.ai/meta/muse-spark-1.3">Muse Spark 1.3 - API Pricing & Providers | OpenRouter</a></li>
<li><a href="https://www.businessinsider.com/muse-spark-meta-ai-model-2026-4">Meta Releases Hotly Anticipated Muse Spark Model - Business Insider</a></li>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE measures frontier coding agents on original, long-horizon...</a></li>

</ul>
</details>

**社区讨论**: 社区反响总体积极：Simon Willison 分享了一个廉价快速的 SVG 生成测试，称 1.3 版本“绝对更好”于上一版；另一位用户则表示自己很享受在日常开发中使用 Spark 1.2。还有人急切地想把它与现有编程智能体对比，指出它每次任务只需几美分，却能达到接近排行榜的成绩。也有评论拿 Meta 的法律麻烦开玩笑，但整体情绪是对这一发布性价比的称赞。

**标签**: `#meta`, `#muse-spark`, `#ai-model`, `#coding-agent`, `#benchmark`

---

<a id="item-4"></a>
## [llm-gemini 0.34 新增对 Gemini 3.8 Flash 的思考级别支持](https://simonwillison.net/2026/Sep/2/llm-gemini/) ⭐️ 8.0/10

llm-gemini 插件发布了 0.34 版本，新增对刚发布的 gemini-3.8-flash 模型的支持，提供低、中、高三档思考级别。同时还修复了异步响应未能记录已解析模型版本的问题。 此次发布让谷歌刚推出的 Gemini 3.8 Flash 可以立即在流行的命令行工具中使用，开发者无需自定义集成就能试用新模型。由于 Flash 系列定位为快速、便宜且能力扎实，CLI 的广泛支持降低了实际试用与智能体工作流的上手门槛。 根据 llm-stats，Gemini 3.8 Flash 支持 100 万 token 的上下文窗口，定价为每百万输入 token 0.75 美元、每百万输出 token 3.75 美元。思考级别对应 Gemini API 的 thinking_level 参数，可设为 LOW、MEDIUM 或 HIGH；相关的 3.8 Flash Cyber 模型仅限“可信防御者”使用。

rss · Simon Willison · 9月2日 16:39

**背景**: llm-gemini 是 Simon Willison 的 llm 命令行工具的插件，让开发者可以在终端中直接向 Gemini 模型发送提示词。Gemini 3.8 Flash 是 Google DeepMind 于 2026 年 9 月发布的最新 Flash 模型，定位为 Gemini 3.7 Flash 的继任者，在软件工程和智能体知识工作方面有所提升。Gemini 模型默认会进行“动态思考”，3.x 系列通过 thinking_level 参数让用户在更深入推理与更低延迟、更低成本之间做取舍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/models/model-cards/gemini-3-8-flash/">Gemini 3 . 8 Flash - Model Card — Google DeepMind</a></li>
<li><a href="https://ai.google.dev/gemini-api/docs/thinking">Gemini thinking - Interactions API | Google AI for Developers</a></li>
<li><a href="https://llm-stats.com/models/gemini-3.8-flash">Gemini 3 . 8 Flash API Pricing, Context Window & Benchmarks</a></li>

</ul>
</details>

**标签**: `#llm`, `#gemini`, `#cli`, `#release`, `#ai-tools`

---

<a id="item-5"></a>
## [Anthropic 发布 Claude Fable 5.1，科学基准测试大幅领先](https://simonwillison.net/2026/Sep/1/claude-fable-5-1/) ⭐️ 8.0/10

Anthropic 发布了 Claude Fable（及 Mythos）5.1，声称在编码、知识工作和长期问题求解任务上树立了新标准。新模型在全新的 Terminal-Bench-Science 0.1 基准上获得 52.6%，而 Fable 5 只有 24.7%；Simon Willison 随后用“骑自行车的鹈鹕”SVG 提示词在多个推理档位进行测试，生成了质量不错的结果。 这次发布表明 Anthropic 最新的前沿模型在科研工作流和长期智能体任务上尤其出色，而这些已成为大模型落地应用越来越重要的方向。Simon 的“鹈鹕”对比能让开发者直观了解“推理强度”档位如何影响输出质量、token 成本和可见的推理过程。 Claude Fable 5.1 提供 low、medium、high、xhigh、max 五个推理强度档位，且无法完全关闭推理。Simon 的测试中，low 和 medium 档分别消耗约 1,998 和 1,977 个输出 token，没有可见的推理文本；high 档则消耗 2,612 个输出 token，耗时 29.6 秒，费用约为 13.087 美分。

rss · Simon Willison · 9月1日 23:57

**背景**: “鹈鹕基准测试”（pelican benchmark）是 Simon Willison 于 2024 年底创建的非正式 LLM 测试，使用单一提示词“生成一个骑自行车的鹈鹕的 SVG”，用来快速判断模型生成代码和遵循指令的能力。Terminal-Bench-Science 于 8 月 27 日首次对外发布，是一个持续演进的基准测试，包含来自生命、物理、地球、数学和计算科学领域的 70 个专家精选任务，旨在评估 AI 智能体在真实科研工作流中的表现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tbench.ai/news/terminal-bench-science-0-1">TERMINAL-BENCH-SCIENCE 0.1</a></li>
<li><a href="https://grokipedia.com/page/Pelican_on_a_bicycle_AI_benchmark">Pelican on a bicycle (AI benchmark)</a></li>
<li><a href="https://snorkel.ai/leaderboard/terminal-bench-science/">Terminal-Bench-Science | Snorkel AI</a></li>

</ul>
</details>

**标签**: `#claude`, `#ai-model`, `#benchmark`, `#llm`, `#coding`

---

<a id="item-6"></a>
## [用户用本地 GLM 5.3 Flash 打造《我的世界》黑洞模组](https://www.reddit.com/r/LocalLLaMA/comments/1w5gk2b/glm_53_flash_makes_a_black_hole_minecraft_mod/) ⭐️ 8.0/10

一位 Reddit 用户演示了在租赁的 4x RTX PRO 6000 工作站上使用本地运行的 GLM 5.3 Flash 模型（Q4 量化版），以迭代方式开发了一个为《我的世界》添加黑洞步枪功能的 Fabric 模组。该工作流在每次请求修改之间进行人工审查，并加入参考图像来优化视觉效果，总共消耗约 9 小时和 760 万输出 token。 这是一个本地大语言模型处理真实世界复杂编码任务的实用案例，而不仅仅是简单示例或基准测试，包括迭代调试和视觉优化。这表明 GLM 5.3 Flash 及类似模型在 AI 辅助游戏模组开发和长期智能体任务中正变得切实可行。 所用模型为 Q4 量化格式的 GLM 5.3 Flash，解码速度约为每秒 96 个 token。该模组先通过黑洞步枪射出黑洞，黑洞会吸入方块并显示收缩光环，最终产生大型爆炸坑并摧毁多个区块；模组已发布在 GitHub 上。

reddit · r/LocalLLaMA · /u/Top-Eye-8104 · 9月2日 17:13

**背景**: 《我的世界》模组可以基于 Fabric API 等模组框架开发，该框架提供向游戏添加自定义物品、实体和行为所需的核心库与钩子。GLM 5.3 Flash 是 Z.ai 推出的原生多模态模型，官方称其适合高效编码和长期智能体任务；Q4 之类的量化会以少量精度换取本地运行时大幅降低的内存占用。发帖人提到他们使用 Atomic.chat 运行本地模型，并称自己是 Atomic 团队成员。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/zai-org/GLM-5.3-Flash">zai-org/ GLM - 5 . 3 - Flash · Hugging Face</a></li>
<li><a href="https://deepinfra.com/zai-org/GLM-5.3-Flash">GLM 5 . 3 Flash API - Demo - DeepInfra</a></li>
<li><a href="https://modrinth.com/project/P7dR8mSH">Fabric API - Minecraft Mod</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#coding-agent`, `#minecraft-mod`, `#GLM`, `#Fabric API`

---

<a id="item-7"></a>
## [DeepSeek-V4-Flash-Vision-Exp 完成视觉支持合并并发布 GGUF](https://www.reddit.com/r/LocalLLaMA/comments/1w5e9fi/vision_support_merged_for_deepseekv4flashvisionexp/) ⭐️ 8.0/10

Reddit 上的公告确认，DeepSeek-V4-Flash-Vision-Exp（一个实验性多模态 DeepSeek 模型）已完成视觉支持合并。Unsloth 已在 HuggingFace 上发布该模型的 GGUF 量化版本，用户可直接下载用于本地推理。 这次发布让本地 AI 开发者能够在无需使用付费 API 的情况下，以开源权重方式测试 DeepSeek 的视觉-语言能力。由于 GGUF 量化版可在消费级 GPU 和 CPU 上高效运行，它降低了本地 LLM 社区进行多模态实验的门槛。 DeepSeek-V4-Flash-Vision-Exp 是在 DeepSeek-V4-Flash 基础上构建的实验性版本，增加了视觉理解能力并提升了多模态智能体性能，同时保留纯文本智能体能力。HuggingFace 仓库 unsloth/DeepSeek-V4-Flash-Vision-Exp-GGUF 提供了多个量化变体，便于本地运行。

reddit · r/LocalLLaMA · /u/fmillar · 9月2日 15:52

**背景**: GGUF 是一种能打包量化后的大语言模型文件格式，便于在本地硬件上通过 llama.cpp 等工具高效推理。Unsloth 是知名的社区项目，专门制作开箱即用的 GGUF 量化版本，通常在新模型出现后不久就会发布。DeepSeek-V4-Flash 是 DeepSeek-V4 系列中的轻量级版本；Vision-Exp 是该系列中首个实验性多模态模型，支持文本并接受 JPEG、PNG、GIF 或 WebP 图像输入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp">deepseek-ai/ DeepSeek - V 4 - Flash - Vision - Exp · Hugging Face</a></li>
<li><a href="https://chat-deep.ai/models/">DeepSeek Models: V 4 Pro, Flash , Vision Exp & More</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#Vision`, `#GGUF`, `#LocalLLaMA`, `#Model Release`

---

<a id="item-8"></a>
## [Paint.NET 开发者称 Claude 编写了 18 万行 Direct2D/Wine 代码](https://simonwillison.net/2026/Sep/2/rick-brewster/) ⭐️ 7.0/10

Paint.NET 首席开发者 Rick Brewster 宣布，该应用现在内置了一个从零开始、以净室逆向工程方式重写的 Direct2D API 版本，用于在 Wine 上运行，并通过 /wine 命令行参数触发。他表示，这约 18 万行代码大部分由 Anthropic 的 Claude AI 编写，如果没有它，这件事“根本不可能发生”。 这是一个标志性案例：AI 编写了 18 万行技术难度极高、需要细致逆向工程的底层代码。它让开发者既看到“vibe coding”的强大之处，也看到为何人工监督仍然必不可少。 这一重写代码位于 PaintDotNet.Windows.Direct2D1.Managed.dll 中，只有当 Paint.NET 使用 /wine 参数启动时才会启用。Brewster 称其中大部分代码属于“vibe coding”的产物，从未被彻底审查过；他不得不经常盯着 Claude，纠正资源管理方面的问题（例如遗漏 COM AddRef() 调用）和一些糟糕的设计或架构决策，但他也称赞了 Claude 在逆向推导 Direct2D 内置效果库所需公式时的聪明与不知疲倦。

rss · Simon Willison · 9月2日 05:50

**背景**: Direct2D 是微软为 Windows 提供的硬件加速、即时模式 2D 图形 API，用于渲染几何图形、位图和文本。Wine 是一个免费开源兼容层，主要通过黑盒逆向工程让 Windows 应用程序能够运行在 Linux、macOS 等类 Unix 系统上。所谓“vibe coding”指的是一种 AI 辅助开发方式：开发者用自然语言描述目标，由 Claude 这类大语言模型直接生成代码。在这个案例中，Claude 被要求从零重写一套复杂的 Windows 图形 API，以便 Paint.NET 在缺乏微软 Direct2D 实现的 Wine 环境中运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Direct2D">Direct2D - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Wine_(software)">Wine (software) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI coding`, `#Claude`, `#vibe coding`, `#reverse engineering`, `#Paint.NET`

---

<a id="item-9"></a>
## [在 Confluent 上部署 IBM 时间序列模型实现实时智能](https://huggingface.co/blog/ibm-research/real-time-intelligence) ⭐️ 7.0/10

IBM Research 在 Hugging Face 上发布了一篇新博客，展示了如何在 Confluent 上部署 IBM 时间序列基础模型以实现实时智能。该方法将时间序列模型与实时上下文相结合，并强调零配置、内置治理和高效率。 这件事之所以重要，是因为越来越多的运营决策需要基于流式数据进行预测，而非依赖离线批处理分析。IBM 发布了将时间序列模型接入 Confluent 的实用范式，为数据团队构建实时 AI 管道、缩短获取洞察的时间提供了可复用的蓝图。 这篇博客提到了与所需决策相匹配的 IBM 时间序列基础模型组合，包括轻量级 Granite 模型 Tiny Time Mixer（TTM）和 Time Series Pulse（TSPulse），它们仅有数百万参数，且无需 GPU 即可推理。该方案基于 Confluent 的实时流式平台构建，文章提供的是架构层面的指导，而非完整的仓库或工具列表。

rss · Hugging Face Blog · 9月2日 13:49

**背景**: 时间序列预测是根据带时间戳的历史数据来预测未来数值，传统上通过批处理作业完成，这会带来额外延迟。IBM Granite Time Series 包含 TTM 和 TSPulse 等超轻量级预训练基础模型，专为无需 GPU 的高效推理而设计。Confluent 是基于 Kafka 的数据流平台，能让团队实时处理事件，因此非常适合在数据持续流动的过程中承载时间序列模型推理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/ibm-research/real-time-intelligence">Real- Time Intelligence with IBM Time Series Models on Confluent</a></li>
<li><a href="https://www.ibm.com/granite/docs/models/time-series/">IBM Granite Time Series Documentation – IBM Granite</a></li>
<li><a href="https://github.com/ibm-granite/granite-tsfm">ibm - granite / granite -tsfm: Foundation Models for Time Series · GitHub</a></li>

</ul>
</details>

**标签**: `#time-series`, `#real-time`, `#confluent`, `#model-deployment`, `#hugging-face`

---

<a id="item-10"></a>
## [阿里发布 Qwen3.8-Max-0902，CodeArena 编程榜 1691 分夺冠](https://mp.weixin.qq.com/s/BfKRXMAR5ykD58LDkBftLg) ⭐️ 7.0/10

阿里通义千问团队发布了 Qwen3.8-Max-0902，这是 Qwen3.8-Max 模型的新版本，针对编程与专业办公任务进行了进一步后训练。它在 CodeArena 前端编程总榜中以 1691 分夺冠，比旧版提升 22 分。 此次发布以顶尖的基准成绩配合激进定价，加剧了高端编程模型间的竞争。其 API 综合均价约为每百万 tokens 5 美元，明显低于榜单第二、第三名模型的 20 美元和 12 美元，这可能会给竞品带来压力，并让先进的 AI 编程辅助更加亲民。 新模型拥有 2.4T 参数与 1M 上下文长度，API 输入价格为每百万 tokens 2 美元、输出价格为 6 美元。该版本已上线千问 AI 平台，并接入千问办公、Qoder 与千问 APP。

telegram · zaihuapd · 9月2日 06:05

**背景**: CodeArena 是一个大规模、动态的在线评测平台，用于评估大语言模型的代码生成能力与自主编程代理的综合表现，同时应对静态基准测试中常见的数据污染问题。Qwen3.8-Max 是阿里云旗下面向旗舰级 2.4T 参数的 MoE（混合专家）模型，提供开源权重和预览等不同版本。Qoder 是阿里巴巴推出的智能体 AI 编程平台，目前已与新版本打通，定位上类似于 Cursor 这类工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://medium.com/@huguosuo/codearena-a-dynamic-benchmark-for-evaluating-autonomous-coding-agents-501eec40758b">CodeArena : A Dynamic Benchmark for Evaluating... | Medium</a></li>
<li><a href="https://kie.ai/blog/what-is-qwen3-8-max">What Is Qwen 3 . 8 - Max ? Alibaba's 2.4T Flagship</a></li>
<li><a href="https://docs.qoder.com/">What is Qoder - Qoder</a></li>

</ul>
</details>

**标签**: `#Qwen`, `#编程模型`, `#CodeArena`, `#AI发布`

---