---
layout: default
title: "Horizon Summary: 2026-08-11 (ZH)"
date: 2026-08-11
lang: zh
---

> 从 69 条内容中筛选出 15 条重要资讯。

---

1. [如何从专有 LLM API 中窃取隐藏的推理轨迹](#item-1) ⭐️ 9.0/10
2. [H3-metal 让 MiniMax-H3 推理原生运行于苹果芯片](#item-2) ⭐️ 9.0/10
3. [Meta 发布 Muse Glimmer：Apache 2.0 许可的开源 30B 智能体模型](#item-3) ⭐️ 9.0/10
4. [Unsloth 推出开源桌面应用，支持本地 AI 训练与推理](#item-4) ⭐️ 9.0/10
5. [英伟达发布 Nemotron 3.5 Lightning 与 NeMo Switchyard，提升智能体 AI 效率](#item-5) ⭐️ 8.0/10
6. [开发者用中间人代理截获 GitHub Copilot 流量，揭示其内部运作](#item-6) ⭐️ 8.0/10
7. [Longscribe：免费为长视频和播客提供 AI 转录](#item-7) ⭐️ 8.0/10
8. [面向 AI 代理的开源追加式决策日志](#item-8) ⭐️ 8.0/10
9. [Tura 声称将 MCP 交互中的 LLM 轮次削减 75% 以上](#item-9) ⭐️ 8.0/10
10. [IBM 研究展示如何用更少 Token 实现 ACE](#item-10) ⭐️ 8.0/10
11. [封闭 AI 模型的加密推理可 100%还原](#item-11) ⭐️ 8.0/10
12. [DeepSeek V4 0731 量化测评：两大转换 Bug、位精确修复与 13 项基准](#item-12) ⭐️ 8.0/10
13. [Anthropic 宣布 Claude Sonnet 5 优惠定价永久生效](#item-13) ⭐️ 8.0/10
14. [Hermes 以 Browser Use CLI 3.0 将 12 个浏览器工具合为一](#item-14) ⭐️ 8.0/10
15. [GPU 直通让 Apple Silicon macOS 虚拟机中的 llama.cpp 大幅提速](#item-15) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [如何从专有 LLM API 中窃取隐藏的推理轨迹](https://stolen-thoughts.com/) ⭐️ 9.0/10

一份新的实用指南展示了如何从专有 LLM API 中提取隐藏的推理轨迹，方法包括将前沿模型的轨迹重放到较弱的同源模型中并对其进行越狱，或诱使模型直接暴露其思维链。这些技术让用户能够恢复 API 提供商刻意隐藏的推理内容。 如果这些方法被广泛使用，将削弱领先 AI 实验室围绕思维链输出设置的保护，这些输出被视为专有且涉及安全敏感信息。构建智能体或评估的开发者可以更深入地了解模型推理过程，而服务提供商则面临保护其 API 免受轨迹提取的新压力。 这些技术利用了与前沿模型共享训练数据的较弱的同源模型；将前沿模型的轨迹重放给它们并越狱，可以暴露出底层推理过程。其他技巧包括禁用思考模式但提供一个“deep_think”工具，这会导致某些模型在工具调用中输出其内部思维链。

hackernews · quantumgarbage · 8月11日 13:22 · [社区讨论](https://news.ycombinator.com/item?id=49257876)

**背景**: 推理模型是经过微调的大型语言模型，通过生成中间步骤（通常称为推理轨迹或思维链）来执行多步问题求解。许多专有 LLM API 对用户隐藏这些轨迹，将其视为专有且涉及安全敏感的内容。模型提取攻击利用对模型的查询访问权限来构建模仿其行为的替代模型，类似的技术也可用于恢复隐藏的推理内容。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Chain-of-thought_prompting">Chain-of-thought prompting</a></li>
<li><a href="https://www.ibm.com/think/topics/reasoning-model">What Is a Reasoning Model? | IBM</a></li>
<li><a href="https://www.praetorian.com/blog/stealing-ai-models-through-the-api-a-practical-model-extraction-attack/">Stealing AI Models Through the API: A Practical Model Extraction Attack | Praetorian</a></li>

</ul>
</details>

**社区讨论**: 评论区观点不一：有人认为用户已为 token 付费，“窃取”一词不当，训练于其他模型输出应属常态；也有人对跨模型重放这一技巧表示好奇，猜测是否是提供方有意为之。还有评论补充了通过“deep_think”工具诱导模型泄露思维链的简化方法，并指出模型在 AIME 问题上明显经过大量训练。

**标签**: `#LLM`, `#reasoning traces`, `#API`, `#practical technique`, `#AI agents`

---

<a id="item-2"></a>
## [H3-metal 让 MiniMax-H3 推理原生运行于苹果芯片](https://github.com/antirez/h3.c) ⭐️ 9.0/10

由 antirez 发布的 GitHub 仓库 H3-metal 提供了在苹果芯片上原生运行 MiniMax-H3 视频生成推理的实现。社区还分享了将其与 ComfyUI 及 GGUF 量化模型集成的工作流。 这使先进的跨模态视频生成模型能够在苹果本地硬件上运行，减少了对云端 API 的依赖，为私密、离线的 AI 视频创作打开了大门。同时也凸显了开源社区在将先进模型移植到消费级设备中的重要作用。 用户报告使用了 GGUF 量化版本如 Q5_K_M 和 Q8_0（34GB），并通过 ComfyUI-GGUF 自定义节点的 UnetLoaderGGUF 替代默认加载器。性能目前仍然较慢，一个约 9 秒、480x864 分辨率、20 步的片段需要一小时以上；antirez 还在尝试 --sparse-attention 模式以寻求加速。

hackernews · swyx · 8月11日 01:22 · [社区讨论](https://news.ycombinator.com/item?id=49252179)

**背景**: MiniMax H3 是 MiniMax 推出的通用全模态生成系统，能够理解文本、图像、视频和音频，并生成带原生立体声音频、最高 2K 分辨率、时长 15 秒的视频。GGUF 是一种存储量化模型权重的文件格式，可降低内存需求，让模型能在苹果芯片等具有统一内存的消费级硬件上运行。该项目正是在这些基础之上，将 H3 推理带到 Mac 上。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/MiniMax-AI/MiniMax-H3">GitHub - MiniMax-AI/MiniMax-H3 · GitHub</a></li>
<li><a href="https://www.minimax.io/blog/minimax-h3">MiniMax H3: An Open Model Breaking the Boundaries Between ...</a></li>
<li><a href="https://huggingface.co/docs/hub/en/gguf">GGUF · Hugging Face</a></li>

</ul>
</details>

**社区讨论**: 用户们正在分享实测结果：Meleagris 发现 H3 在 64GB 的 M5 Pro MacBook Pro 上通过 ComfyUI 配合 GGUF 量化运行效果非常好，但速度是主要瓶颈。linzhangrun 报告在 128GB 的 M4 Max Mac Studio 上生成一段 15 秒 480p 视频需要一个半小时；TechSquidTV 则询问是否必须 128GB 内存，表明对最低硬件配置存在疑问。

**标签**: `#AI video generation`, `#Apple Silicon`, `#MiniMax H3`, `#Inference`, `#GitHub`

---

<a id="item-3"></a>
## [Meta 发布 Muse Glimmer：Apache 2.0 许可的开源 30B 智能体模型](https://simonwillison.net/2026/Aug/10/introducing-muse-glimmer/#atom-everything) ⭐️ 9.0/10

Meta 发布了 Muse Glimmer，这是一款采用 Apache 2.0 许可的全新 30B 开源权重模型，专门针对端到端智能体任务完成、可靠工具调用和多步推理进行了优化。该模型已可通过 LM Studio 在本地试用，Simon Willison 展示了它生成图像以及使用编码智能体插件探索代码库的能力。 转向 Apache 2.0 是相对于 Meta 之前 Llama 许可的重大改进，它移除了使用限制，使该模型对商业和本地应用更具吸引力。由于 Muse Glimmer 针对智能体工作流进行了优化，它可能会加速开放权重 AI 智能体的发展，使这些智能体能够可靠地使用工具并在多步任务中进行推理。 Muse Glimmer 是一个 30B 参数的视觉语言模型，在 LM Studio 中提供 18.16 GB 的量化版本，运行流畅仅需约 32 GB 内存，并可同时运行其他应用。Meta 声称该模型在 DeepSearch QA、MCP-Atlas、τ-Bench 和 SWE-Bench 等基准测试中表现出色，这些基准涵盖了从多工具编排到代码调试等能力。

rss · Simon Willison · 8月10日 23:56

**背景**: 开放权重模型是指公开发布权重的大语言模型，开发者可以在本地运行或针对特定任务进行微调。智能体 AI 指能够自主规划并执行多步任务的系统，通常通过模型上下文协议（MCP）等协议调用外部工具。SWE-Bench、τ-Bench 以及较新的 MCP-Atlas 等基准测试用于评估模型在处理真实世界编码任务、工具-智能体-用户交互以及多工具 MCP 工作流方面的表现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/scaleapi/mcp-atlas">GitHub - scaleapi/mcp-atlas: MCP Atlas</a></li>
<li><a href="https://arxiv.org/abs/2406.12045">[2406.12045] $τ$-bench: A Benchmark for Tool-Agent-User Interaction in Real-World Domains</a></li>
<li><a href="https://www.swebench.com/">SWE - bench Leaderboards</a></li>

</ul>
</details>

**标签**: `#meta`, `#open-weights`, `#agentic-model`, `#tool-use`, `#local-llm`

---

<a id="item-4"></a>
## [Unsloth 推出开源桌面应用，支持本地 AI 训练与推理](https://www.reddit.com/r/LocalLLaMA/comments/1vlj87v/introducing_unsloth_desktop_app/) ⭐️ 9.0/10

Unsloth 发布了 Unsloth Desktop，这是其首款开源桌面应用，支持在 Mac、Windows 和 Linux 上本地运行和训练 AI 模型。该应用支持 MLX、GGUF、扩散图像/视频模型、音频模型，以及 NVIDIA、AMD、Intel 和 Mac 硬件的多 GPU 配置。 这意义重大，因为它降低了本地运行和微调 LLM 的门槛，提供了基于云服务之外免费开源的替代方案。通过集成 Claude Code 和 Codex 代理、RAG、MCP 以及 Cloudflare 远程部署，它成为面向开发者与注重隐私用户的实用工具。 该应用声称训练速度提升 2 倍，同时 VRAM 占用减少 70%，并通过沙盒代码执行实现 50% 更准确的自愈型工具调用。它包含私密网页搜索、深度研究、RAG、MCP，以及 NVFP4 和 GGUF 格式的模型导出功能，且不收集任何遥测数据或用户数据。

reddit · r/LocalLLaMA · /u/danielhanchen · 8月11日 14:36

**背景**: 本地 LLM 工具让用户在自己的硬件上运行 Llama 或 Qwen 等模型，而无需将数据发送到云端 API。MLX 是 Apple 面向 Apple Silicon 的机器学习框架；GGUF 是 llama.cpp 项目推出的模型权重与元数据文件格式；MCP（模型上下文协议）是 Anthropic 提出的开放标准，用于将 AI 模型连接到外部工具和数据源。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ml-explore/mlx">GitHub - ml-explore/mlx: MLX: An array framework for Apple ... Exploring LLMs with MLX and the Neural Accelerators in the M5 ... What Is MLX? A Practical Introduction to Apple's Machine ... Introduction to MLX: Apple’s Machine Learning Framework Live Code File Format (.mlx) - MATLAB & Simulink - MathWorks What Is MLX? Apple Silicon ML & Inference Framework | AI/TLDR</a></li>
<li><a href="https://en.wikipedia.org/wiki/GGUF">GGUF - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>

</ul>
</details>

**标签**: `#local-LLM`, `#fine-tuning`, `#AI-tools`, `#desktop-app`, `#open-source`

---

<a id="item-5"></a>
## [英伟达发布 Nemotron 3.5 Lightning 与 NeMo Switchyard，提升智能体 AI 效率](https://blogs.nvidia.com/blog/nemotron-lightning-switchyard-rtx-dgx/) ⭐️ 8.0/10

英伟达发布了 Nemotron 3.5 Lightning——一个 300 亿参数的开放混合专家（MoE）模型，仅有 30 亿激活参数，专为低延迟智能体工作负载优化；同时还发布了开源模型路由库 NeMo Switchyard。 此次发布加强了英伟达在面向智能体 AI 的小型高效模型领域的地位，让开发者能在从边缘到云的环境中精细控制模型选择、成本和延迟。它直接顺应了行业向小型模型和智能路由以平衡质量与效率的趋势。 Nemotron 3.5 Lightning 采用混合架构，将 Mamba-2 层、MoE 层与部分注意力层交错组合，支持推测解码、NVFP4/BF16 检查点，吞吐量可提升至 4 倍。NeMo Switchyard 根据模型能力、成本和基础设施信号路由请求，已在 GitHub 的 NVIDIA-NeMo 组织下开源。

hackernews · droidjj · 8月11日 19:35 · [社区讨论](https://news.ycombinator.com/item?id=49263340)

**背景**: Nemotron 3.5 Lightning 是英伟达 Nemotron 系列开放大语言模型的一员，专为高并发、常驻的 AI 智能体设计。模型路由是一种新兴技术，由路由器为每个请求选择最合适的模型，在降低成本与延迟的同时保持输出质量。英伟达将这些工具定位为可部署在边缘设备、PC、工作站、数据中心和云端的解决方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.nvidia.com/blog/nvidia-nemotron-3-5-lightning-delivers-fast-accurate-specialized-task-execution-for-long-running-agents/">NVIDIA Nemotron 3.5 Lightning Delivers Fast ... - NVIDIA Developer</a></li>
<li><a href="https://developer.nvidia.com/blog/route-ai-agent-workloads-across-models-with-nvidia-nemo-switchyard/">Route AI Agents Across Models with NVIDIA NeMo Switchyard | NVIDIA Technical Blog</a></li>
<li><a href="https://github.com/NVIDIA-NeMo/Switchyard">GitHub - NVIDIA-NeMo/Switchyard · GitHub</a></li>

</ul>
</details>

**社区讨论**: 评论者强调了小型高效模型的大趋势，有人指出数万亿参数模型可能“从根本上缺少某些东西”。还有人提出了一个技术问题：像 NeMo Switchyard 这样的路由器如何处理跨请求的提示词缓存，会话是否会固定到同一模型。有用户指出基准图表遗漏了 Qwen 系列模型，也有人称赞该模型通过 MLX 在 Apple Silicon 上运行良好。

**标签**: `#AI models`, `#NVIDIA`, `#NeMo`, `#small models`, `#model routing`

---

<a id="item-6"></a>
## [开发者用中间人代理截获 GitHub Copilot 流量，揭示其内部运作](https://www.lighthousenewsletter.com/p/i-put-github-copilot-behind-a-mitm) ⭐️ 8.0/10

一名开发者使用 mitmproxy 拦截了 GitHub Copilot 的网络流量，揭示了该助手如何进行模型/能力发现与路由、如何向幽灵补全（ghost completions）注入上下文，以及如何消耗配额。他们还发现，最近的编辑可以从当前编辑文件之外的文件中拉取上下文，并注意到其缺少针对 .env 文件的规则。 这次实践调查揭开了这一广泛使用的 AI 编码工具的神秘面纱，帮助开发者理解为什么 Copilot 配额会快速耗尽，以及哪些数据被发送到服务器。它还引发了关于 AI 辅助开发工具默认安全规则的讨论，例如是否应该默认保护 .env 文件。 作者实时观察了模型和能力发现与路由过程，检查了幽灵补全所发送的上下文中注入了什么内容，并确认最近的编辑可能包含来自其他文件的上下文。他们还指出，一个与 GitHub 深度集成的工具竟然没有排除环境文件的规则，这令人意外。

hackernews · j0selit0 · 8月11日 10:40 · [社区讨论](https://news.ycombinator.com/item?id=49256057)

**背景**: GitHub Copilot 是一款 AI 结对编程助手，由大语言模型驱动，在编辑器和 IDE 中内联提供代码建议。中间人（MitM）代理（如 mitmproxy）可以拦截 HTTPS 流量，使开发者能够检查并调试 API 请求和响应。为了平衡成本与质量，许多 AI 助手会使用模型路由——为较简单的查询选择更便宜或更小的模型——以及上下文裁剪，以便只将最相关的代码放入模型有限的上下文窗口中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.mitmproxy.org/">mitmproxy - an interactive HTTPS proxy</a></li>
<li><a href="https://github.com/lm-sys/RouteLLM">GitHub - lm-sys/RouteLLM: A framework for serving and ...</a></li>
<li><a href="https://redis.io/blog/llm-router-architecture-best-practices/">LLM router architecture: best practices for 2026 - Redis</a></li>

</ul>
</details>

**社区讨论**: 评论区普遍称赞这次深入剖析，p1llus 指出 eBPF 可以在加密前捕获明文，从而绕过证书固定和 mTLS。ameliaquining 做了一个事实更正，指出 Codex 客户端是开源的；_davide_ 则不同意作者关于精心策划上下文的结论。tolugenius 也表达了对 .env 文件没有排除规则的惊讶。

**标签**: `#GitHub Copilot`, `#mitmproxy`, `#AI coding tools`, `#reverse engineering`, `#LLM context`

---

<a id="item-7"></a>
## [Longscribe：免费为长视频和播客提供 AI 转录](https://longscribe.com/) ⭐️ 8.0/10

Longscribe 是一款在 Hacker News 上发布的免费网页工具，用于转写长视频和播客。它支持粘贴 YouTube 链接或上传文件，并可将转录稿导出为 TXT、SRT、DOCX 或 JSON 格式。 长内容转写通常价格昂贵或有时长限制，免费的长音频/视频转写工具填补了这一实际需求，对内容创作者、研究人员和媒体团队很有价值。这也体现了 AI 转写技术正变得普及且价格亲民的趋势。 Longscribe 提供多种模式，包括从 YouTube 提取现有字幕或用 AI 转写音频，并允许用户编辑带时间戳的转录稿。该工具面向团队和企业，而 Show HN 上的版本定位为免费处理长视频和播客。

rss · Show HN (self-made tools) · 8月11日 21:50

**背景**: AI 转写利用语音识别技术将音频/视频转换为文本，通常带有时间戳。许多工具按分钟收费或有长度上限，使得转写长播客和视频成本较高。Longscribe 旨在通过免费转写长内容来消除这一障碍，并提供编辑和导出为常见格式的功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://longscribe.com/for-business">AI Transcription Software for Teams and Businesses · Longscribe</a></li>
<li><a href="https://longscribe.com/youtube-transcription">YouTube Video Transcript Free | YouTube to Transcript · Longscribe</a></li>

</ul>
</details>

**标签**: `#transcription`, `#AI tool`, `#podcast`, `#video`, `#free`

---

<a id="item-8"></a>
## [面向 AI 代理的开源追加式决策日志](https://github.com/swe-workflow/log-decisions) ⭐️ 8.0/10

一个新的开源 GitHub 项目 log-decisions 提供了一个专门为 AI 代理设计的追加式决策日志，用于记录代理的决策过程。该项目以 Show HN 的形式在 Hacker News 上分享，为代理决策日志提供了一个具体工具。 这很重要，因为 AI 代理越来越需要可审计的决策轨迹，用于调试、安全和治理。追加式日志帮助开发者和运营者理解代理为何采取特定行动，这对自主系统的信任和问责至关重要。 该项目托管在 GitHub 上的 swe-workflow/log-decisions 仓库中，其核心特性是一个追加式决策日志，意味着条目一旦写入便不可更新或删除。它面向 AI 代理开发流程，提供持久且防篡改的代理决策记录。

rss · Show HN (self-made tools) · 8月11日 21:15

**背景**: 决策日志是个人和团队用来记录重要决策、背景和预期结果的工具。在 AI 代理的语境中，追加式决策账本提供了一份防篡改的记录，包含每次 AI 建议和人工裁决，这对可审计性和治理至关重要。追加式结构确保过去的决策无法被追溯修改，从而支持事后分析和自主系统的问责制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://governanceai.io/blog/ai-audit-trail-append-only-decision-ledger">The append - only decision ledger AI governance needs</a></li>
<li><a href="https://skillselion.com/skills/affaan-m/everything-claude-code/recursive-decision-ledger">recursive- decision -ledger - Claude Code Skill (1.2k installs) · Skillselion</a></li>
<li><a href="https://wilsonblogger.com/agentic-ai-for-beginners-5-moves-now/">Agentic AI for Beginners: 5 Real Moves I’m Riding Right Now</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#GitHub`, `#developer tools`, `#logging`, `#workflow`

---

<a id="item-9"></a>
## [Tura 声称将 MCP 交互中的 LLM 轮次削减 75% 以上](https://github.com/Tura-AI/tura) ⭐️ 8.0/10

GitHub 项目 Tura 声称能将基于 MCP 的 AI 智能体交互中的 LLM 轮次减少 75% 以上，从而提升效率。该项目提供了可供开发者尝试的代码仓库，声称智能体可以用更少的模型调用获得相当或更好的结果。 这一点很重要，因为 MCP 正成为将 LLM 连接到外部工具的关键标准，而减少 LLM 轮次可以直接降低 AI 智能体的成本和延迟。如果该说法成立，它可能成为开发智能体工作流的重要优化工具。 该仓库似乎介绍了一个本地、开源的编码智能体，早期宣传也称“节省 80% 的 token”。然而，Hacker News 帖子目前没有评论，因此 75% 的数字尚未得到验证，社区反馈也不得而知。

rss · Show HN (self-made tools) · 8月11日 20:39

**背景**: MCP（模型上下文协议）是 Anthropic 于 2024 年 11 月推出的开放标准，旨在规范 AI 系统与外部工具和数据源的集成方式。在基于 MCP 的智能体工作流中，每次工具调用或上下文交换都可能消耗多个 LLM 轮次，因此减少这种开销是一项有价值的优化。Tura 是近期众多试图提高 AI 智能体效率的项目之一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://modelcontextprotocol.io/">What is the Model Context Protocol ( MCP )?</a></li>
<li><a href="https://github.com/Tura-AI/tura">GitHub - Tura-AI/tura: Build agent that uses 80% less token and delivers better results. · GitHub</a></li>

</ul>
</details>

**社区讨论**: Hacker News 帖子下暂无评论，因此没有社区讨论可总结。

**标签**: `#MCP`, `#AI agents`, `#LLM efficiency`, `#GitHub`, `#tooling`

---

<a id="item-10"></a>
## [IBM 研究展示如何用更少 Token 实现 ACE](https://huggingface.co/blog/ibm-research/altk-evolve-sldd) ⭐️ 8.0/10

IBM Research 在 Hugging Face 上发布了一篇博客文章，介绍了 ALTK-Evolve-SLDD——一种面向代理上下文工程（ACE）任务的令牌高效方法。该方法据称能在使用更少 Token 的同时达到与标准 ACE 相当的性能。 Token 使用量直接影响 AI 代理系统的成本和延迟，因此减少 Token 消耗能让 ACE 在大规模应用中更加实用。使用长上下文模型构建代理的开发者可以通过这种优化来降低运营开销。 该技术名为 ALTK-Evolve-SLDD，不过根据现有信息，博客的具体实验设置和指标尚未完全核实。该方法很可能基于 ACE 框架，该框架通过生成、反思和策展来管理不断演变的上下文，目标是在不牺牲任务质量的前提下节省 Token。

rss · Hugging Face Blog · 8月11日 13:37

**背景**: ACE（代理上下文工程）是近期一篇论文中提出的框架，它将代理的上下文视为不断演变的操作手册，通过生成、反思和策展的模块化过程来防止上下文崩溃，并随长上下文模型扩展。标准 ACE 因不断积累和精炼信息而可能消耗大量 Token。IBM Research 的这篇博文针对这一问题，提出了面向类似代理任务的令牌高效变体。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2510.04618">Agentic Context Engineering: Evolving Contexts for Self ...</a></li>
<li><a href="https://www.anthropic.com/engineering/effective-context-engineering-for-ai-agents">Effective context engineering for AI agents \ Anthropic</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#token efficiency`, `#LLM techniques`, `#IBM Research`, `#Hugging Face`

---

<a id="item-11"></a>
## [封闭 AI 模型的加密推理可 100%还原](https://www.reddit.com/r/LocalLLaMA/comments/1vllbjh/encrypted_reasoning_from_closedai_et_al_100/) ⭐️ 8.0/10

一篇新论文（arXiv:2608.09867）证明，来自 OpenAI、Anthropic、Google 等专有 LLM API 的加密推理块可在会话、用户和模型之间重放和互换，从而完整还原隐藏的思维链。Reddit 帖子呼吁用户在厂商修复该问题之前收集 Claude Opus 5 的轨迹数据。 这一发现破坏了专有 LLM 推理的保密性，可能暴露隐藏在加密思维链中的知识产权和敏感信息。它影响到依赖前沿模型 API 推理的 AI 开发者、安全研究人员以及各类企业。 加密的思维链以 AEAD 密文块形式打包，客户端在每次请求时将其回传；攻击者可以在不同会话、甚至不同模型之间交换或重放这些块，从而完整揭示底层推理。论文还报告了公共日志中泄露的 182 个凭据，且截至 Reddit 发帖时该漏洞尚未被修复。

reddit · r/LocalLLaMA · /u/Dany0 · 8月11日 15:52

**背景**: 包括 Anthropic 和 OpenAI 在内的前沿 LLM 提供商为保护知识产权并减少信息泄露，会隐藏模型的逐步思维链。提供商并不在服务端存储轨迹，而是将轨迹以加密文本块形式返回给客户端，客户端在后续请求中再将其传回。此前的研究和博客文章（如 2026 年 5 月的《密码学工程》）已表明这些块可在不同账户间重放。Claude Opus 5 是 Anthropic 于 2026 年 7 月 24 日发布的最新旗舰模型，目前正是收集推理轨迹的目标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2608.09867">Stealing Reasoning Traces from Proprietary LLM APIs</a></li>
<li><a href="https://www.explainx.ai/blog/stealing-reasoning-traces-encrypted-cot-vulnerability-august-2026">Encrypted CoT Flaw: 182 Credentials Leaked from Public Logs ...</a></li>
<li><a href="https://blog.cryptographyengineering.com/2026/05/29/fooling-around-with-encrypted-reasoning-blobs/">Let’s talk about encrypted reasoning – A Few Thoughts on ...</a></li>

</ul>
</details>

**标签**: `#LLM`, `#reasoning`, `#security`, `#arxiv`, `#model analysis`

---

<a id="item-12"></a>
## [DeepSeek V4 0731 量化测评：两大转换 Bug、位精确修复与 13 项基准](https://www.reddit.com/r/LocalLLaMA/comments/1vlurlv/we_quantized_deepseek_v4_0731_and_benchmarked_it/) ⭐️ 8.0/10

一个团队对 DeepSeek V4 0731 进行了量化，并在 safetensors 转 GGUF 的流程中发现两个转换 Bug：缺少--no-lazy 选项会导致 token_embd 权重出现 NaN，而硬编码的 FP8 转 Q8_0 降级会悄悄改变权重。他们将相关张量替换为 BF16 以获得位精确的基础模型，随后制作了 13 个 imatrix 量化版本，并在同一台 8×RTX 5090 机器上对全部 38 个量化文件进行了基准测试。 这为本地 LLM 开发者提供了量化 DeepSeek V4 的具体解决方案，并揭示了一个重要问题：由于 llama.cpp 仅在消费级 Blackwell 上启用 MXFP4 快速路径，不同 GPU 上公布的量化指标无法直接比较。此外，它还指出 Hugging Face 上量化命名缺乏标准，因此按文件大小比较比按名称更可靠。 以位精确的 BF16 基础模型为参照，默认的 162GB“无损”转换与原始权重的平均 KLD 偏差为 0.219，而他们的 118GB 量化版仅为 0.2065，意味着 3-bit 量化比默认基线更接近原始模型。他们的 AD-IQ2_M 量化版（104GB，每个专家权重 2.79 比特）在 128GB 硬件上达到了 83.6%的 top-1 准确率；同一量化文件在 RTX 5090 上测得的 PPL 为 4.5381，在 H100 上为 4.3406。

reddit · r/LocalLLaMA · /u/gladkos · 8月11日 21:34

**背景**: 量化通过 Q8_0 等基于分块的格式以较低精度存储权重，从而减小模型内存占用，但生硬的转换会引入与原始模型之间的偏差。imatrix（重要性矩阵）技术为各张量分配重要性分数，使量化过程优先保留最关键权重；像 DeepSeek V4 这样的混合专家（MoE）模型需要对每个专家单独设置量化参数，因为每个专家相当于一个独立的前馈网络。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepwiki.com/ikawrakow/ik_llama.cpp/4.2.2-importance-matrix-and-advanced-quantization">Importance Matrix and Advanced Quantization | ikawrakow/ik ...</a></li>
<li><a href="https://deepwiki.com/ggml-org/llama.cpp/7.3-quantization-techniques">Quantization Techniques | ggml-org/llama.cpp | DeepWiki</a></li>
<li><a href="https://apxml.com/courses/mixture-of-experts-advanced-implementation/chapter-4-efficient-moe-inference/moe-quantization-techniques">Quantization for MoE Layers</a></li>

</ul>
</details>

**标签**: `#quantization`, `#DeepSeek`, `#LLM`, `#local-inference`, `#RTX-5090`

---

<a id="item-13"></a>
## [Anthropic 宣布 Claude Sonnet 5 优惠定价永久生效](https://x.com/claudeai/status/2086891169217122586) ⭐️ 8.0/10

8 月 10 日，Anthropic 宣布 Claude Sonnet 5 的优惠定价永久生效，取消了原定 9 月 1 日的涨价计划。输入和输出价格分别保持在每百万 token 2 美元和 10 美元。 这消除了依赖 Claude Sonnet 5 的开发者与初创企业在短期内面临的价格不确定性，让成本规划更加稳定。这也让 Anthropic 在与 OpenAI 等模型提供商的 API 价格竞争中保持竞争力。 这一优惠价格是该模型 6 月上线时推出的，原计划仅持续到 8 月 31 日，之后恢复为每百万 token 输入 3 美元、输出 15 美元。现在折扣将永久适用，不过 Anthropic 并未说明未来新版本模型是否也会延续相同定价。

telegram · zaihuapd · 8月11日 03:39

**背景**: 在 AI 语言模型中，token（词元）是模型处理文本的基本单位，可以是一个单词、单词的一部分或一个字符，它既决定模型的上下文窗口大小，也决定 API 的调用成本。提供商按每百万 token 计价，因此即使单价小幅变化，也会对大规模生产负载的成本产生显著影响。今年以来，Anthropic 与 OpenAI 等竞争对手多次调整模型定价，以吸引开发者采用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://zplatform.ai/guides/what-are-tokens-in-ai/">What Are Tokens in AI? Simple Explanation + Examples ...</a></li>
<li><a href="https://www.geeksforgeeks.org/artificial-intelligence/tokens-and-context-windows-in-llms/">Tokens and Context Windows in LLMs - GeeksforGeeks</a></li>
<li><a href="https://blogs.nvidia.com/blog/ai-tokens-explained/">What Are AI Tokens? The Language and Currency Powering Modern AI</a></li>

</ul>
</details>

**标签**: `#Claude`, `#Anthropic`, `#AI定价`, `#AI福利`

---

<a id="item-14"></a>
## [Hermes 以 Browser Use CLI 3.0 将 12 个浏览器工具合为一](https://x.com/zjp1997720/status/2086971452990054410) ⭐️ 8.0/10

NousResearch 宣布，Hermes 现在推出了 Browser Use 模式，用一个由 Browser Use CLI 3.0 驱动的单一工具取代了原先十二个独立的浏览器工具。代理不再为每次点击发送十几个 schema 和工具调用，而是编写脚本来控制浏览器。 这简化了 AI 代理的浏览器自动化，大幅降低 token 消耗和开销，同时保持准确性。它让基于代理的网页交互更高效，可能降低运行代理工作流的成本，惠及更广泛的 AI 代理生态。 据公告所述，这一切换将 token 使用量降低了 48%–66%，且准确性没有下降。Browser Use CLI 3.0 为编码代理提供直接的 CDP 浏览器控制，支持本地 Chrome/Chromium、Browser Use 云浏览器，以及任何可通过 CDP 端点访问的浏览器。

twitter · zjp1997720 · 8月11日 00:22

**背景**: Hermes 是 Nous Research 开发的 AI 代理，拥有一套工具集，涵盖网络搜索、图像生成、TTS 和浏览器自动化。传统上，浏览器自动化需要许多独立工具，每个都有自己的 schema，每个动作都需要一次工具调用，这会消耗大量上下文。Browser Use CLI 3.0 基于 Browser Harness 构建，让代理通过 Python 脚本控制浏览器，而不是使用离散的工具调用，从而降低了开销。这一方法与让编码代理直接、可脚本化控制浏览器的更广泛趋势一致。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.browser-use.com/open-source/browser-use-cli">Browser Use CLI - Browser Use</a></li>
<li><a href="https://digg.com/tech/4gmf9ywk">Nous Research Adds Browser Use Mode to Hermes · Digg</a></li>
<li><a href="https://unrollnow.com/status/2086881660658663469">Thread By @ NousResearch - Hermes has twelve browser tools ....</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#browser automation`, `#Hermes`, `#browser-use`, `#CLI`

---

<a id="item-15"></a>
## [GPU 直通让 Apple Silicon macOS 虚拟机中的 llama.cpp 大幅提速](https://github.com/trycua/cua/blob/main/blog/gpu-passthrough-macos-vms.md) ⭐️ 7.0/10

trycua 发布的新指南介绍了如何在 Apple Silicon 上的 macOS 虚拟机中配置 GPU 直通，从而修复 llama.cpp 在虚拟化环境中的内核选择问题。与该工作负载在同一普通虚拟机中的表现相比，整体推理速度提升了 11.08 倍，生成 token 的速度提升了 16.36 倍。 这对在 macOS 虚拟机中运行本地大模型推理的开发者来说非常重要，因为它大幅提升了性能，让这类配置更加实用。同时，它也揭示了 Virtualization.framework 的简化 Metal 功能集如何降低 GPU 工作负载的性能，并展示了 GPU 直通在 Apple Silicon 上作为有效解决方案的作用。 该修复绕过的是 Virtualization.framework 的限制：其简化的 Metal 功能集会导致 llama.cpp 选错 GPU 内核；因此该提速效果仅适用于虚拟机，并非 llama.cpp 的通用优化。基准测试在 M1 Ultra 主机上完成，文中未提供 M1 Pro 或 M3 Pro 的结果。

hackernews · frabonacci · 8月11日 14:50 · [社区讨论](https://news.ycombinator.com/item?id=49259339)

**背景**: llama.cpp 是一个开源的 C/C++ 库，用于在本地运行大型语言模型，也是 Ollama、LM Studio 等工具的核心引擎。在 Apple Silicon 上，它利用 Apple 的 Metal API 进行 GPU 加速。Virtualization.framework 是 Apple 在 macOS 上提供的原生虚拟化 API，它会暴露一个 Metal 功能集受限的虚拟 GPU，这可能误导 llama.cpp 选择效率低下的内核。GPU 直通则将宿主机的 GPU 直接分配给虚拟机，恢复完整的硬件能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Llama.cpp">Llama.cpp</a></li>
<li><a href="https://developer.apple.com/metal/">Metal Overview - Apple Developer</a></li>
<li><a href="https://github.com/bryansteiner/gpu-passthrough-tutorial/">GitHub - bryansteiner/gpu-passthrough-tutorial</a></li>

</ul>
</details>

**社区讨论**: 评论者澄清说，该提速效果仅适用于 Virtualization.framework 虚拟机，并非 llama.cpp 的通用改进，并认为这一区分非常重要。有用户质疑为什么 Virtualization.framework 会暴露简化的 Metal 功能集，另一位用户则询问是否有 M1 Pro 和 M3 Pro 芯片的基准测试结果。

**标签**: `#llama.cpp`, `#Apple Silicon`, `#macOS VMs`, `#GPU passthrough`, `#LLM inference`

---