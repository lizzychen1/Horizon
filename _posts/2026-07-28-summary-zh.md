---
layout: default
title: "Horizon Summary: 2026-07-28 (ZH)"
date: 2026-07-28
lang: zh
---

> 从 78 条内容中筛选出 15 条重要资讯。

---

1. [Orb：自托管 AI 助手，主动向你发消息](#item-1) ⭐️ 9.0/10
2. [Minute：macOS 离线会议笔记，集成 Whisper 和 llama.cpp](#item-2) ⭐️ 9.0/10
3. [Writekin：在 Mac 上微调本地 LLM](#item-3) ⭐️ 9.0/10
4. [LFM2.5-Encoder 在 CPU 上实现快速长上下文推理](#item-4) ⭐️ 9.0/10
5. [DeepSeek V4 Flash 在 AMD Ryzen AI MAX+ 395 上达到 32 tok/s](#item-5) ⭐️ 9.0/10
6. [5B 激活参数模型知识弱但工具调用强](#item-6) ⭐️ 9.0/10
7. [开源 Codex 技能解决历史记录过大导致变慢问题](#item-7) ⭐️ 9.0/10
8. [两个爬取公众号文章的技能推荐](#item-8) ⭐️ 9.0/10
9. [Dify 1.16.1 发布，新增工具多选输入等功能](#item-9) ⭐️ 8.0/10
10. [OpenAI 开源 Codex Security CLI](#item-10) ⭐️ 8.0/10
11. [Kimi K3 架构：NoPE 与 KDA 创新](#item-11) ⭐️ 8.0/10
12. [Hamza 在发送前屏蔽 AI 编码工具中的秘密和 PII](#item-12) ⭐️ 8.0/10
13. [CogniKernel：支持跨会话记忆的 AI 编码工具现已发布 PyPI 包](#item-13) ⭐️ 8.0/10
14. [Claude 学习模式：拒绝直接写代码](#item-14) ⭐️ 8.0/10
15. [FedTerm：类似 Spotlight 的 macOS 终端，索引 Claude 会话](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Orb：自托管 AI 助手，主动向你发消息](https://github.com/getorb/Orb-Backend) ⭐️ 9.0/10

Orb 是一个自托管的人工智能助手，能够主动先给你发消息，作为开源项目在 GitHub 上可用。 该工具将人工智能助手从被动响应转变为主动发送，使开发人员能够自动化日程安排和邮件管理等任务，同时完全掌控自己的数据。 Orb 集成了消息平台，可以在已连接的电脑上执行实际操作，然后向用户报告结果。

rss · Show HN (self-made tools) · 7月28日 20:08

**背景**: 自托管人工智能助手运行在用户自己的基础设施上，提供隐私和定制化能力。主动式代理根据触发器或日程安排主动发起对话，不同于等待用户输入的传统聊天机器人。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/LHXHL/orb">LHXHL/orb: Self-evolving AI agent framework - GitHub</a></li>
<li><a href="https://orb.nathanlangley.dev/">Orb — the AI assistant that talks first</a></li>

</ul>
</details>

**标签**: `#AI assistant`, `#self-hosted`, `#agent`, `#GitHub`, `#open source`

---

<a id="item-2"></a>
## [Minute：macOS 离线会议笔记，集成 Whisper 和 llama.cpp](https://github.com/mraza007/minute) ⭐️ 9.0/10

一位开发者发布了 Minute，这是一款开源 macOS 应用，使用 OpenAI 的 Whisper 进行语音识别，并通过 llama.cpp 进行本地 LLM 推理，实现会议转录和摘要的完全离线处理。 Minute 通过将会议数据完全保留在设备上，消除了向云服务发送音频的必要，解决了日益增长的隐私和延迟问题。它展示了本地 AI 模型的实用集成，能够在不牺牲数据安全的情况下提高开发者的生产力。 Minute 使用 Tauri、Rust、React 和 Metal 加速构建，笔记以纯文本、JSON 和 WAV 文件格式本地存储。在初始模型下载后，整个流程（音频捕获、转录、摘要）均在进程内运行，无需账户、服务器或遥测。

rss · Show HN (self-made tools) · 7月28日 19:31

**背景**: Whisper 是 OpenAI 的开源语音识别模型，可转录多种语言的音频。llama.cpp 是一个开源的 C/C++ 库，能够在消费级硬件（如笔记本电脑）上高效推理大型语言模型（LLM）。两者结合，使得 AI 驱动的功能可以完全离线运行，无需往返云服务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Llama.cpp">llama.cpp - Wikipedia</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp">GitHub - ggml-org/llama.cpp: LLM inference in C/C++</a></li>
<li><a href="https://tech-insider.org/llama-cpp-tutorial-2026/">llama.cpp Tutorial: Run a Local LLM in 12 Steps [2026]</a></li>

</ul>
</details>

**标签**: `#offline-ai`, `#whisper`, `#llama.cpp`, `#open-source`, `#productivity`

---

<a id="item-3"></a>
## [Writekin：在 Mac 上微调本地 LLM](https://github.com/scouttyg/writekin) ⭐️ 9.0/10

Writekin 是一款新工具，它通过读取用户个人写作数据（包括 Apple Mail、iMessage、本地文档和聊天记录）来微调本地大语言模型，从而生成模仿用户写作风格的内容。整个过程完全在用户 Mac 上运行，使用 Apple 的 MLX 框架和 QLoRA 进行高效的设备端微调。 该工具直接解决了用户常遇到的痛点：即使提供风格提示或指南，AI 生成的文字仍然显得千篇一律。通过在本地微调个人写作数据，它提供了一种保护隐私的方式，生成真正反映用户个人风格的文字，对于作家、专业人士以及任何希望获得 AI 辅助又不愿失去个人风格的用户来说都很有价值。 该工具目前是 0.9 版本，作者指出输出质量不稳定——有时能完美复刻用户风格，有时则完全不匹配。它需要配备 Apple Silicon 芯片的 Mac，通过 Apple 的 MLX 框架使用 QLoRA 进行内存高效的微调，仅有的网络请求是从 Hugging Face 下载模型权重和通过 Sparkle 检查更新。

rss · Show HN (self-made tools) · 7月28日 19:05

**背景**: QLoRA 是一种高效的微调技术，它通过将预训练语言模型量化到 4 位，同时只训练少量适配器参数，从而大幅降低内存占用，使得在 Mac 等消费级硬件上微调大型语言模型成为可能。Apple MLX 是面向 Apple Silicon 的机器学习数组框架，为微调和推理等操作提供高效实现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ml-explore/mlx">GitHub - ml-explore/mlx: MLX: An array framework for Apple ... Exploring LLMs with MLX and the Neural Accelerators in the M5 ... MLX MLX — MLX 0.32.0 documentation - GitHub Pages Run local agentic AI on the Mac using MLX - Apple Developer Get started with MLX for Apple silicon - WWDC25 - Videos ...</a></li>
<li><a href="https://github.com/artidoro/qlora">GitHub - artidoro/qlora: QLoRA: Efficient Finetuning of ... [2305.14314] QLoRA: Efficient Finetuning of Quantized LLMs Master LoRA and QLoRA: Fine-Tuning LLMs on Consumer GPUs QLoRA – How to Fine-Tune an LLM on a Single GPU Fine-Tuning Large Language Models (LLMs) Using QLoRA Fine-Tuning LLMs with LoRA and QLoRA in Python — A Complete ...</a></li>
<li><a href="https://www.geeksforgeeks.org/deep-learning/fine-tuning-using-lora-and-qlora/">Fine-Tuning using LoRA and QLoRA - GeeksforGeeks</a></li>

</ul>
</details>

**标签**: `#fine-tuning`, `#local LLM`, `#writing tool`, `#Mac`

---

<a id="item-4"></a>
## [LFM2.5-Encoder 在 CPU 上实现快速长上下文推理](https://huggingface.co/blog/LiquidAI/lfm2-5-encoders) ⭐️ 9.0/10

Liquid AI 发布了 LFM2.5-Encoder 系列模型，该模型针对在 CPU 上进行高效长上下文推理进行了优化，无需 GPU 加速。 此次发布使得长上下文 AI 模型能够在标准 CPU 硬件上运行，大幅降低了开发者和组织的成本及基础设施门槛。 该系列模型包括一个 350M 参数的 PII 检测器变体，并设计为与 Hugging Face Transformers 兼容。它们利用 LFM2.5 架构，针对 CPU 上的长序列处理进行了优化。

rss · Hugging Face Blog · 7月28日 15:01

**背景**: 长上下文推理通常需要大量 GPU 内存和计算，限制了部署。编码器常用于分类和检索任务，Liquid AI 的 LFM2.5-Encoder 基于其 Liquid Foundation Model（LFM）技术，能够在 CPU 上高效运行，扩大了可及性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://reymer.ai/news/liquid-ai-lfm2-5-encoders-cpu">Возрождение энкодеров: Liquid AI выпустила модели LFM 2 . 5 ...</a></li>
<li><a href="https://huggingface.co/LiquidAI/LFM2.5-Encoder-350M-PII-Detector">LiquidAI/ LFM 2 . 5 - Encoder -350M-PII-Detector · Hugging Face</a></li>
<li><a href="https://www.liquid.ai/blog/lfm2-5-retrievers">LFM 2 . 5 Retrievers: Bi-directional LFMs for Fast... — Liquid AI</a></li>

</ul>
</details>

**标签**: `#AI`, `#LLM`, `#inference`, `#optimization`, `#CPU`

---

<a id="item-5"></a>
## [DeepSeek V4 Flash 在 AMD Ryzen AI MAX+ 395 上达到 32 tok/s](https://www.reddit.com/r/LocalLLaMA/comments/1v9100b/deepseek_v4_flash_up_to_32_toks_on_amd_ryzen_ai/) ⭐️ 9.0/10

一个团队成功地在单块 AMD Ryzen AI MAX+ 395（128 GB 统一内存）上运行了 284B 参数的 MoE 模型 DeepSeek V4 Flash，利用开源的 ROCmFPX 量化和推测解码，实现了高达 32 tok/s 的解码速度。 这证明了大型语言模型可以在消费级 AMD 硬件上高效运行，挑战了 NVIDIA 在本地 LLM 推理中的主导地位，为 AMD 平台上的开发者开辟了新的可能性。 量化使用了混合精度方案，包括 ROCmFP2、ROCmFP3 和 ROCmFP4 格式，将模型压缩至 102.3 GB（每参数 2.88 比特），并使用一个小型草稿模型进行推测解码，速度比自回归解码提升了 26.4%。

reddit · r/LocalLLaMA · /u/sandropuppo · 7月28日 15:00

**背景**: ROCmFPX 是一个针对 AMD ROCm/HIP 优化的开源量化格式家族，将权重打包成低位编码并附带每块缩放。推测解码通过让一个小型草稿模型提议多个 token，再由大模型一次性验证，从而减少延迟，加速推理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Speculative_decoding">Speculative decoding</a></li>

</ul>
</details>

**标签**: `#LocalLLM`, `#AMD`, `#DeepSeek`, `#Quantization`, `#OpenSource`

---

<a id="item-6"></a>
## [5B 激活参数模型知识弱但工具调用强](https://www.reddit.com/r/LocalLLaMA/comments/1v952ka/a_5bactive_model_doesnt_know_much_and_ive_stopped/) ⭐️ 9.0/10

一位 Reddit 用户指出，仅有 5B 激活参数的小型 MoE 模型（如 Ling-3.0-flash）在事实回忆方面表现不佳，但在工具调用方面出奇地有效，使其成为依赖检索而非内部知识的代理工作流的理想选择。 这一见解将 AI 代理的评估重点从 MMLU 等知识基准转向工具调用能力，可能加速在需要最新信息的实际任务中采用更小、更快的模型。 用户强调，存储在权重中的知识无法更新或审计，而工具调用可以获取最新数据。然而，模型有时仍会编造看似合理的答案而非使用工具，用户希望有一个明确训练在低置信度时回退到工具的模型。

reddit · r/LocalLLaMA · /u/AcanthisittaOk1699 · 7月28日 17:25

**背景**: 大型语言模型存在总参数（所有权重）和激活参数（每 token 使用的参数）的区别。混合专家模型（MoE）如文中所述，实现了高总参数量同时保持低激活参数，从而加快推理速度。工具调用使 LLM 能够访问外部函数和 API，扩展其超越静态训练数据的能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.f22labs.com/blogs/active-vs-total-parameters-whats-the-difference/">Active vs Total Parameters: What’s the Difference?</a></li>
<li><a href="https://machinelearningmastery.com/mastering-llm-tool-calling-the-complete-framework-for-connecting-models-to-the-real-world/">Mastering LLM Tool Calling: The Complete Framework for ...</a></li>

</ul>
</details>

**社区讨论**: 该帖子获得了强烈赞同，许多人指出工具调用能力在标准基准中被低估。一些人担心模型猜测时的过度自信，而另一些人则建议检索增强生成流程可以缓解这一问题。

**标签**: `#AI agents`, `#small language models`, `#tool use`, `#retrieval-augmented generation`

---

<a id="item-7"></a>
## [开源 Codex 技能解决历史记录过大导致变慢问题](https://x.com/zjp1997720/status/2082080366438097297) ⭐️ 9.0/10

OpenAI 用户@zjp1997720 开源了一个名为 codex-handoff 的 Codex 技能，用于解决因任务历史记录过大导致的 Codex 变慢问题，他发现 1.3GB 的记录文件导致每轮处理 98k-117k tokens，耗时 43 分钟。 这直接解决了长期运行的 Codex 代理的关键性能瓶颈，大幅提升开发效率，使 Codex 在长时间任务中更加实用。 该技能采用仅追加文件的交接协议来管理任务上下文，减少 token 开销，并支持异步多代理协作。这一发现源于一个运行了 8 天、记录文件达 1.3GB 的任务。

twitter · zjp1997720 · 7月28日 12:26

**背景**: Codex 是 OpenAI 于 2025 年发布的 AI 编程代理，用于软件工程任务。随着时间推移，累积的任务历史会导致上下文窗口膨胀，造成严重减速。codex-handoff 技能使代理能够在不携带全部历史的情况下高效交接工作，类似于人类开发者使用问题跟踪器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Codex_(AI_agent)">Codex (AI agent)</a></li>
<li><a href="https://openai.com/codex/">Codex in ChatGPT | AI Coding Agents for Software Engineering | OpenAI</a></li>
<li><a href="https://github.com/OpenMOSS/claude-codex-handoff">GitHub - OpenMOSS/claude-codex-handoff: Drop-in async file-based handoff protocol for two AI coding agents (Claude Code + Codex), installed as one shared .handoff/ in your project. · GitHub</a></li>

</ul>
</details>

**标签**: `#Codex`, `#AI agent`, `#开源`, `#性能优化`, `#Skill`

---

<a id="item-8"></a>
## [两个爬取公众号文章的技能推荐](https://x.com/zjp1997720/status/2081937770256441765) ⭐️ 9.0/10

一位开发者推荐了两个爬取微信公众号文章的技能：一个是从 workbuddy 中优化而来的，基于搜狗 API；另一个是刚开源的批量爬取技能，已在 GitHub 上发布。 这些工具让 AI Agent 和开发者更容易获取微信封闭生态中的内容，从而实现大规模自动化信息检索和分析。 第一个技能从 workbuddy 内置的搜狗搜索中优化而来，处理了边界问题，实时性很强。第二个技能支持批量爬取，最近已开源在 GitHub 上。

twitter · zjp1997720 · 7月28日 03:00

**背景**: 微信公众号是中国重要的内容平台，但其文章不易通过标准网络搜索获取。搜狗的微信搜索是少数公开的发现入口之一。workbuddy 是腾讯的 AI Agent 平台，可集成办公工具；而开源仓库提供了一个无需 API Key 的爬取方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.workbuddy.ai/">WorkBuddy - AI Agent for Everyday Office Work</a></li>
<li><a href="https://apify.com/jungle_synthesizer/sogou-wechat-article-search-scraper">Sogou WeChat Article Search Scraper - Apify</a></li>
<li><a href="https://github.com/zjp1997720/wechat-article-search">zjp1997720/wechat-article-search - GitHub</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#web scraping`, `#WeChat`, `#open source`, `#tools`

---

<a id="item-9"></a>
## [Dify 1.16.1 发布，新增工具多选输入等功能](https://github.com/langgenius/dify/releases/tag/1.16.1) ⭐️ 8.0/10

Dify 1.16.1 版本引入了工作流节点的多选输入、工作流节点定位器、改进的模块选择器、从侧边栏导出 Agent DSL 以及增强的知识追踪可观测性。此外，还修复了工作流协作、RAG、Agent、UI 和后端等多个领域的众多错误。 这些改进简化了 Dify 中 Agent 和工作流的开发，使构建复杂的 AI 应用更加容易。多选工具输入和节点定位器提升了开发效率，而 Agent DSL 导出功能促进了 Agent 配置的版本控制和共享。 多选输入允许用户从预定义列表中选择多个值作为工具参数。节点定位器允许点击日志中的 node_id 来高亮对应的工作流节点。知识追踪为 RAG 文档处理操作增加了可观测性追踪。

github · wylswz · 7月28日 03:43

**背景**: Dify 是一个用于构建 AI 应用的开源平台，包括工作流和 Agent。领域特定语言（DSL）是一种针对特定问题领域的专门语言；在这里，Agent DSL 允许以 YAML 格式导出 Agent 配置以进行版本控制。此处的知识追踪指的是监控和追踪 RAG 系统中的数据处理管道，而非教育领域追踪学生知识的概念。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prefactor.tech/blog/designing-a-dsl-for-agent-access-control">Designing a DSL for Agent Access Control | Prefactor</a></li>
<li><a href="https://en.wikipedia.org/wiki/Bayesian_knowledge_tracing">Bayesian knowledge tracing - Wikipedia</a></li>

</ul>
</details>

**标签**: `#dify`, `#ai-tools`, `#workflow`, `#agent`, `#open-source`

---

<a id="item-10"></a>
## [OpenAI 开源 Codex Security CLI](https://github.com/openai/codex-security) ⭐️ 8.0/10

OpenAI 已开源 Codex Security CLI 命令行工具，该工具可扫描代码中的安全漏洞并提供 AI 驱动的修复建议。该工具现已在 GitHub 上供社区使用和贡献。 此次开源使得 AI 驱动的安全扫描更加普及，开发者可以将其集成到工作流中进行高级漏洞检测。然而，早期用户反馈的扫描时间长和 API 消耗高的问题，可能限制其在大型项目中的实用性。 该工具通过 `npx codex-security scan .` 运行，并需要 Codex 身份验证。有用户反映，扫描一个小型仓库耗时近一小时，并消耗了 Pro 计划一半的周使用配额，且扫描在完成前被中断。

hackernews · bakigul · 7月28日 20:52 · [社区讨论](https://news.ycombinator.com/item?id=49089755)

**背景**: Codex Security CLI 是 OpenAI Codex 生态系统的一部分，该生态系统包括 AI 驱动的编码助手。该工具旨在帮助开发者在终端内识别和修复安全问题。OpenAI 还发布了相关的 Codex CLI 和学习文档网站。此次开源使得社区可以审查、改进和扩展该工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.openai.com/codex/security">Codex Security | ChatGPT Learn</a></li>
<li><a href="https://developers.openai.com/codex/cli">Codex CLI | ChatGPT Learn</a></li>

</ul>
</details>

**社区讨论**: 社区反馈褒贬不一：有人赞赏开源举措和 AI 安全扫描的潜力，也有人批评该工具的性能和昂贵的 API 成本。有评论者将 AI 安全工具比作由纵火犯运营的消防部门，质疑 AI 公司的动机。OpenAI 的代表承认了这些问题并承诺快速改进。

**标签**: `#open-source`, `#security`, `#Codex`, `#AI tool`, `#developer productivity`

---

<a id="item-11"></a>
## [Kimi K3 架构：NoPE 与 KDA 创新](https://sebastianraschka.com/blog/2026/kimi-k3-architecture-notes.html) ⭐️ 8.0/10

Sebastian Raschka 发表了一篇关于 Kimi K3 架构的详细分析，指出该模型用 NoPE（无位置嵌入）替换了所有 RoPE 层，并引入了 Kimi Delta Attention (KDA)。 这一分析深入揭示了 Kimi K3 区别于西方大语言模型的新技术，反驳了其仅依赖蒸馏的说法，并为 AI 开发者提供了宝贵知识。 Kimi K3 拥有 2.8 万亿参数，采用混合专家架构（896 个专家），文本主干包含 93 层，其中 69 层 KDA 层与 24 层 Gated MLA 层交错排列。

hackernews · ModelForge · 7月28日 15:48 · [社区讨论](https://news.ycombinator.com/item?id=49085698)

**背景**: 像 RoPE（旋转位置嵌入）这样的位置嵌入通常用于 Transformer 中编码 token 顺序。NoPE 移除显式位置编码，依赖注意力推断位置。Kimi Delta Attention (KDA) 是一种混合线性注意力机制，旨在提高长序列效率。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sebastianraschka.com/llm-architecture-gallery/nope/">No Positional Embeddings (NoPE) | Sebastian Raschka, PhD</a></li>
<li><a href="https://platform.kimi.ai/docs/guide/kimi-k3-quickstart">Kimi K3 - Kimi API Platform</a></li>
<li><a href="https://sebastianraschka.com/blog/2026/kimi-k3-architecture-notes.html">Kimi K3 Architecture Notes | Sebastian Raschka, PhD</a></li>

</ul>
</details>

**社区讨论**: 评论者赞扬了这一分析，有人对 NoPE 在没有位置信息的情况下仍能工作感到惊讶，也有人指出 Kimi 的创新证明它不仅仅是蒸馏的结果。

**标签**: `#LLM`, `#Architecture`, `#Kimi K3`, `#Deep Learning`

---

<a id="item-12"></a>
## [Hamza 在发送前屏蔽 AI 编码工具中的秘密和 PII](https://github.com/softcane/hamza) ⭐️ 8.0/10

Hamza 是一个新的 GitHub 工具，能在代码发送给 Claude Code 或 Codex 之前自动屏蔽其中的秘密和 personally identifiable information（PII，个人身份信息），从而防止意外数据泄露。 随着开发者越来越多地依赖 AI 编码助手，无意中暴露凭证或敏感数据的风险也随之增加；Hamza 提供了一个轻量级的隐私层，在不干扰工作流程的情况下减轻这种风险。 该工具作为 GitHub pre-commit hook 或 CLI 包装器在本地运行，在发送到 Claude Code 或 Codex 之前扫描 API 密钥和令牌等模式。目前支持常见的秘密格式，并可配置自定义模式。

rss · Show HN (self-made tools) · 7月28日 21:35

**背景**: Claude Code 和 Codex 是由 AI 驱动的编码助手，通过直接与代码库交互来帮助开发者编写和调试代码。然而，在将代码片段发送到这些基于云的工具时，存在泄露密码或 API 密钥等敏感信息的风险。Hamza 通过在传输前在本地编辑这些数据来解决这个问题，确保只有安全的代码到达 AI。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://openai.com/codex/">Codex in ChatGPT | AI Coding Agents for Software Engineering</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#privacy`, `#Claude Code`, `#Codex`, `#GitHub`

---

<a id="item-13"></a>
## [CogniKernel：支持跨会话记忆的 AI 编码工具现已发布 PyPI 包](https://github.com/KanishkNoir/cognikernel) ⭐️ 8.0/10

CogniKernel 现已作为 PyPI 包提供，可通过单个 pip 命令轻松安装。它为 Claude Code 和 Codex 等 AI 编码助手提供持久化、结构化的记忆，跨会话和平台保持上下文。 这解决了 AI 辅助开发中的一大痛点：会话间的上下文丢失。通过启用跨会话记忆，开发者可以保留架构决策和项目上下文，提高生产力并减少重复工作。 CogniKernel 监控编码会话，提取关键决策、约束和放弃的方法，将它们整合到事件溯源存储中，并在未来会话中作为上下文注入。它在本地运行，数据保留在用户机器上，无需外部传输。

rss · Show HN (self-made tools) · 7月28日 21:28

**背景**: Claude Code 和 Codex 等 AI 编码助手功能强大，但缺乏跨会话的持久记忆，导致每次都需要重新分析代码库。CogniKernel 提供本地结构化的记忆，跨会话和平台持久化，充当 AI 代理的“记忆库”。它是开源的，现在可通过 PyPI 轻松安装，无需手动克隆仓库。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/KanishkNoir/cognikernel">GitHub - KanishkNoir/cognikernel: Persistent, structured ...</a></li>
<li><a href="https://aiindigo.com/tool/cognikernel">Cognikernel Review, Pricing & Alternatives 2026 | AI Indigo ...</a></li>

</ul>
</details>

**标签**: `#AI coding`, `#memory`, `#tool`, `#Claude`, `#Codex`

---

<a id="item-14"></a>
## [Claude 学习模式：拒绝直接写代码](https://github.com/melsayedx/learning-mode) ⭐️ 8.0/10

一个名为“Learning Mode”的新 GitHub 仓库提供了一种配置，使 Anthropic 的 Claude 拒绝编写代码，转而引导用户自己学习和编写。 该工具通过防止过度依赖 AI 代码生成来促进主动学习，可能帮助开发者加深对编程概念的理解。 该仓库包含一个自定义系统提示，指示 Claude 拒绝代码编写请求，而是提供解释和指导。它适用于 Claude 的 API 或聊天界面。

rss · Show HN (self-made tools) · 7月28日 20:21

**背景**: Claude 是由 Anthropic 开发的大型语言模型，旨在提供有用、无害且诚实的帮助。许多用户依赖 AI 助手生成代码，这可能会阻碍学习。“学习模式”通过强制 AI 采取教学方法（教而非做）来解决这一问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/">Claude</a></li>
<li><a href="https://github.com/sguzen/library">GitHub - sguzen/library · GitHub</a></li>

</ul>
</details>

**标签**: `#AI tool`, `#Claude`, `#learning`, `#prompting`, `#GitHub`

---

<a id="item-15"></a>
## [FedTerm：类似 Spotlight 的 macOS 终端，索引 Claude 会话](https://github.com/feod1/fedterm) ⭐️ 8.0/10

FedTerm 是一款新的 macOS 终端应用，可通过热键像 Spotlight 一样弹出，并索引 Claude Code 会话、Shell 历史记录和 SSH 主机，以便快速搜索和恢复。 FedTerm 通过将 Claude Code 会话管理直接集成到终端覆盖层中，简化了 AI 代理工作流程，使 macOS 开发者能更轻松地恢复历史对话并访问 Shell 历史。 FedTerm 使用 Swift 和 SwiftTerm 构建，采用 MIT 许可证，无需账户，并在本地索引所有 Claude Code 会话、Shell 历史和 SSH 主机以实现即时检索。

rss · Show HN (self-made tools) · 7月28日 19:06

**背景**: Claude Code 会话是绑定到项目目录的保存对话，允许用户恢复或分支之前的工作。SwiftTerm 是一个用于 Swift 应用的开源 VT100/Xterm 终端模拟器库。FedTerm 结合了这些功能，提供了一个类似 Spotlight 的轻量级终端覆盖层。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://code.claude.com/docs/en/sessions">Manage sessions - Claude Code Docs</a></li>
<li><a href="https://github.com/migueldeicaza/SwiftTerm">GitHub - migueldeicaza/ SwiftTerm : Xterm/VT100 Terminal emulator in...</a></li>

</ul>
</details>

**标签**: `#macOS`, `#terminal`, `#Claude`, `#AI tool`, `#open source`

---