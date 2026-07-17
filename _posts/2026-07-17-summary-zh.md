---
layout: default
title: "Horizon Summary: 2026-07-17 (ZH)"
date: 2026-07-17
lang: zh
---

> 从 68 条内容中筛选出 14 条重要资讯。

---

1. [Dify 1.16.0 发布 Dify Agent 测试版，集成沙盒环境](#item-1) ⭐️ 9.0/10
2. [Wado：完全由 AI 编码代理构建的类 Rust 语言](#item-2) ⭐️ 9.0/10
3. [Bonsai 27B：1 位量化模型在 iPhone 上运行，仅 3.9GB](#item-3) ⭐️ 9.0/10
4. [Gemma4-31b 在多智能体编码中优于 Qwen3.6-27b](#item-4) ⭐️ 9.0/10
5. [Trellis.cpp 图像转 3D 质量追平参考](#item-5) ⭐️ 9.0/10
6. [DeepSeek V4 Flash 在 RTX 5090 上运行 100 万上下文](#item-6) ⭐️ 9.0/10
7. [Kimi K3：开源 2.8 万亿参数模型登顶前端编程榜](#item-7) ⭐️ 9.0/10
8. [LLM 陈词滥调高亮工具发布](#item-8) ⭐️ 8.0/10
9. [PrintBlocks：为 AI 智能体提供热敏打印机 API/MCP 服务器](#item-9) ⭐️ 8.0/10
10. [LIA：基于 FastAPI 和 LangGraph 的自托管多智能体 AI 助手](#item-10) ⭐️ 8.0/10
11. [Maxx：带滚动窗口的实时 CLI 令牌追踪器](#item-11) ⭐️ 8.0/10
12. [使用 NVIDIA NeMo 和 Diffusers 规模化微调视频与图像模型](#item-12) ⭐️ 8.0/10
13. [Browser-use 0.13.5 发布，支持 MCP 注册表](#item-13) ⭐️ 7.0/10
14. [Visuali.io：一个用于图像处理和分析的 Claude Code 式工具](#item-14) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Dify 1.16.0 发布 Dify Agent 测试版，集成沙盒环境](https://github.com/langgenius/dify/releases/tag/1.16.0) ⭐️ 9.0/10

Dify 1.16.0 推出 Dify Agent 公开测试版，这是一个基于 Linux 沙盒的智能体构建器，能够集成工具、技能、文件和知识，并可在 Dify Workflow 中使用或作为独立的 Web 应用部署。 此次发布大幅降低了在 Dify 生态中构建自定义 AI 智能体的门槛，用户可以通过标准化的技能和流畅的工作流集成，创建功能强大且沙盒化的智能体。 Dify Agent 使用 Linux 沙盒安全执行代码和 shell 命令，支持技能系统（SKILL.md 格式，.zip/.skill 文件最大 50 MB），并允许通过对话方式让智能体创建其他智能体。此外，该版本将 OpenAI API 默认类型从 Chat Completions 更新为 Responses，以兼容 GPT-5.6。

github · wylswz · 7月17日 11:14

**背景**: 基于 shell 的 LLM 智能体范式允许智能体在终端环境中执行命令和代码，大大扩展了其能力。Dify 的技能系统提供了一种标准化格式（SKILL.md）来封装可复用的能力。Linux 沙盒（通常通过 Docker 或 microVM 实现）将智能体与主机系统隔离，确保安全性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepwiki.com/xun404/dify-agent-skill-plugin/4.3.1-skill.md-format">SKILL.md Format | xun404/dify-agent-skill-plugin | DeepWiki</a></li>

</ul>
</details>

**标签**: `#dify`, `#agent framework`, `#AI agent`, `#GitHub release`, `#sandbox`

---

<a id="item-2"></a>
## [Wado：完全由 AI 编码代理构建的类 Rust 语言](https://wado-lang.org/playground/) ⭐️ 9.0/10

Wado 是一种新型的类 Rust 编程语言，带有垃圾回收，针对 WebAssembly 组件模型，其整个编译器完全由 AI 编码代理编写，没有人工编写的代码。 这表明 AI 编码代理现在能够从零开始构建复杂的、面向生产的系统（如编译器），有望加速语言开发并减少人力投入。 Wado 编译为 WebAssembly 组件，具有类 Rust 语法并支持垃圾回收，还包含一个在线 playground 供实验。该项目始于 2025 年 1 月，创建者负责设计和品味，代理编写了所有代码。

rss · Show HN (self-made tools) · 7月17日 21:32

**背景**: WebAssembly (Wasm) 是一种基于栈的虚拟机的二进制指令格式，被设计为可移植的编译目标。WebAssembly 组件模型通过标准接口扩展了 Wasm，以支持可互操作的组件。AI 编码代理是一种能够自主生成、调试和重构代码的工具；最近的进展使它们能够根据自然语言规范构建整个代码库。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://component-model.bytecodealliance.org/">Introduction - The WebAssembly Component Model</a></li>
<li><a href="https://github.com/WebAssembly/component-model">GitHub - WebAssembly / component - model : Repository for design...</a></li>
<li><a href="https://agentic.ai/best/coding-agents">20 Best AI Coding Agents in 2026 — Agentic.ai</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#programming language`, `#WebAssembly`

---

<a id="item-3"></a>
## [Bonsai 27B：1 位量化模型在 iPhone 上运行，仅 3.9GB](https://www.reddit.com/r/LocalLLaMA/comments/1uyz9n2/bonsai_27b_runs_locally_on_an_iphone_a_27b_model/) ⭐️ 9.0/10

PrismML 发布了 Bonsai 27B，这是一个基于 Qwen3.6-27B 的 1 位二进制量化模型，将其大小从约 54GB 缩减至 3.9GB，可在 iPhone 上运行，同时保留约 90%的基准性能。 这种极端量化的演示使得大型语言模型能够在移动设备上本地运行，可能改变设备端 AI 的能力和隐私敏感型应用。 该模型使用真正的二进制量化（'binary g128'），每个权重只有一个符号位，每 128 个权重共享一个 FP16 缩放因子，因此每个权重仅约 1.125 位，没有高精度逃逸机制。内存使用量在 4K 上下文时约为 5.2GB，在 100K 上下文加 4 位 KV 缓存时约为 6.8GB。

reddit · r/LocalLLaMA · /u/ElmBark · 7月17日 13:08

**背景**: 二进制量化将神经网络权重压缩到 1 位（值为+1 或-1），大幅减小模型大小，使得在资源受限的设备上进行推理成为可能。分组量化中，组大小为 128（g128）意味着每 128 个权重共享一个缩放因子以保持精度。1 位神经网络在缩放定律中显示出潜力，表明它们可能成为高效 AI 的标准。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://weaviate.io/blog/binary-quantization">32x Reduced Memory Usage With Binary Quantization | Weaviate</a></li>
<li><a href="https://arxiv.org/abs/2411.01663">[2411.01663] Unlocking the Theory Behind Scaling 1-Bit Neural Networks</a></li>
<li><a href="https://huggingface.co/petergilani/Qwen3-Coder-Next-3bit-g128">petergilani/Qwen3-Coder-Next-3bit-g128 · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#quantization`, `#mobile-ai`, `#binary-quantization`, `#bonsai`

---

<a id="item-4"></a>
## [Gemma4-31b 在多智能体编码中优于 Qwen3.6-27b](https://www.reddit.com/r/LocalLLaMA/comments/1uz8532/gemma431b_better_than_qwen3627b/) ⭐️ 9.0/10

一位开发者报告在多智能体工作流中将主要编码代理从 Qwen3.6-27b 替换为 Gemma4-31b，结果在一天内解决了多个错误并实现了可工作的原型。 这一亲身对比凸显了两种流行本地 LLM 在编码任务上的实际性能差异，为构建多智能体系统的开发者提供了可操作的指导。 用户对两个模型都使用了 Q8_0 量化，并将 Qwen3.6-27b 重新分配给 QA 和审阅角色，而 Gemma4-31b 负责编码，另用 35b 模型处理运维和研究。

reddit · r/LocalLLaMA · /u/d4mations · 7月17日 18:34

**背景**: Gemma 4 31B 是谷歌的开源多模态模型，拥有 310 亿参数和 256K token 上下文窗口，专为生产环境设计。Q8_0 是一种 8 位量化格式，在显著减小模型尺寸的同时保持几乎无损的质量。多智能体工作流涉及多个具有专业化角色的 LLM，由中央模型协调。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gemma4.dev/models/gemma-4-31b">Gemma 4 31B — Enterprise-Grade Local LLM | gemma4.dev</a></li>
<li><a href="https://build.nvidia.com/google/gemma-4-31b-it/modelcard">gemma-4-31b-it Model by Google | NVIDIA NIM</a></li>
<li><a href="https://huggingface.co/google/gemma-4-31B">google/gemma-4-31B · Hugging Face</a></li>

</ul>
</details>

**标签**: `#model-comparison`, `#coding-agent`, `#local-llm`, `#agent-workflow`, `#gemma4`

---

<a id="item-5"></a>
## [Trellis.cpp 图像转 3D 质量追平参考](https://www.reddit.com/r/LocalLLaMA/comments/1uyw64s/trelliscpp_now_produces_high_quality_assets/) ⭐️ 9.0/10

开发者 ilintar 修复了 trellis.cpp 中的多个错误，使其生成的 3D 资产质量与官方参考实现持平。这意味着顶级开源图像转 3D 生成现在无需 CUDA，可在 CPU 或任意 GPU 上运行。 这一进展消除了对 CUDA 的依赖，使拥有各种硬件的开发者都能从图像生成高质量 3D 模型，从而推动了 3D 资产生成的民主化。这也增强了 3D 生成的开源生态系统，类似于 llama.cpp 在消费级硬件上运行大语言模型的意义。 trellis.cpp 的代码仓库位于 GitHub 的 github.com/pwilkin/trellis.cpp，并可与 Lemonade 集成使用，提供包含可选文本转 3D 管线的统一体验。基于 GGML 的移植版本支持 CPU 执行和 AMD GPU，无需专有 CUDA 库。

reddit · r/LocalLLaMA · /u/ilintar · 7月17日 10:45

**背景**: TRELLIS 是微软开发的大型 3D 资产生成模型，能够根据文本或图像提示生成高质量的 3D 资产。GGML 是一种针对机器学习推理优化的张量库，以 llama.cpp 项目闻名，后者使大语言模型能在多种硬件上运行。通过将 TRELLIS 移植到 GGML，trellis.cpp 实现了无需 CUDA 的推理，大大提高了可及性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ggml-org/ggml">GitHub - ggml -org/ ggml : Tensor library for machine learning · GitHub</a></li>
<li><a href="https://microsoft.github.io/TRELLIS/">TRELLIS: Structured 3D Latents for Scalable and Versatile 3D ...</a></li>
<li><a href="https://github.com/microsoft/TRELLIS">GitHub - microsoft/TRELLIS: Official repo for paper ...</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#3D generation`, `#open source`, `#GitHub`, `#image-to-3D`

---

<a id="item-6"></a>
## [DeepSeek V4 Flash 在 RTX 5090 上运行 100 万上下文](https://www.reddit.com/r/LocalLLaMA/comments/1uz5w3y/deepseek_v4_flash_on_5090_in_llamacpp_with_1/) ⭐️ 9.0/10

一位 Reddit 用户分享了在 RTX 5090 上使用 llama.cpp 运行 DeepSeek V4 Flash 模型（284B MoE）的配置和基准测试，支持 100 万 token 上下文窗口，预填充速度达到 650–700 tokens/s，解码速度为 17 tokens/s。 这表明在消费级硬件上实现极长上下文窗口（100 万 token）已成为可能，使得先进 MoE 模型的本地部署可用于长文档分析和编码智能体等应用。同时突出了 llama.cpp 对密集推理模型的持续性能优化。 用户使用了 Unsloth 提供的 DeepSeek-V4-Flash-UD-Q8_K_XL GGUF 量化版本，对 GPU 和 CPU 进行了特定的张量卸载，缓存类型设置为 q8_0，并启用了 flash attention。加载时间为 32 秒。

reddit · r/LocalLLaMA · /u/Shoddy_Bed3240 · 7月17日 17:14

**背景**: DeepSeek V4 Flash 是一个具有 2840 亿参数的混合专家模型，原生支持 100 万 token 上下文，针对编码和智能体任务进行了优化。llama.cpp 是一个高性能的开源推理引擎，可在 CPU 和 GPU 上本地运行 LLM，支持 GGUF 量化格式。Unsloth 提供预量化的 GGUF 文件以降低内存需求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://build.nvidia.com/deepseek-ai/deepseek-v4-flash/modelcard">deepseek-v4-flash Model by Deepseek-ai | NVIDIA NIM</a></li>
<li><a href="https://huggingface.co/docs/inference-endpoints/engines/llama_cpp">llama . cpp · Hugging Face</a></li>

</ul>
</details>

**标签**: `#DeepSeek V4`, `#llama.cpp`, `#RTX 5090`, `#large context`, `#local LLMs`

---

<a id="item-7"></a>
## [Kimi K3：开源 2.8 万亿参数模型登顶前端编程榜](https://www.kimi.com/blog/kimi-k3) ⭐️ 9.0/10

月之暗面发布了 Kimi K3，这是首个开源 2.8 万亿参数模型，在 Frontend Code Arena 上以 1679 分排名第一，超越了 Claude Fable 5。该模型已通过 API 及 Kimi.com 等平台上线。 Kimi K3 表明，开源模型在特定编程基准上能够与甚至超越闭源模型，使先进的 AI 编程辅助对开发者更加触手可及且价格更低。 K3 采用了 Kimi Delta Attention 和 Attention Residuals 架构，支持原生视觉和 100 万 token 上下文窗口，完整权重将于 2026 年 7 月 27 日开源。API 定价为缓存命中每百万 token 0.30 美元、缓存未命中 3.00 美元、输出 15.00 美元。

telegram · zaihuapd · 7月17日 00:02

**背景**: Kimi Delta Attention（KDA）是一种专为高效长上下文处理设计的线性注意力机制。Attention Residuals（AttnRes）用可学习的层级聚合替代了标准残差连接。Frontend Code Arena 基于真实用户提示对模型的自主前端编程任务进行评估。这些创新使 K3 在编程基准上达到了最先进的结果。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://x.com/arena/status/2056803664606679059">Arena.ai on X: "Code Arena: Frontend evaluates models on agentic frontend coding tasks from real users building apps and websites (HTML and React). Agents are an entirely different contest. More from Arena soon. Filter and dive into all the Code Arena: Frontend leaderboard details at:" / X</a></li>
<li><a href="https://www.emergentmind.com/topics/kimi-delta-attention-kda">Kimi Delta Attention : Efficient Long-Context Models</a></li>
<li><a href="https://arxiv.org/abs/2603.15031">[2603.15031] Attention Residuals</a></li>

</ul>
</details>

**标签**: `#model release`, `#open-source`, `#coding`, `#benchmark`, `#LLM`

---

<a id="item-8"></a>
## [LLM 陈词滥调高亮工具发布](https://simonwillison.net/2026/Jul/17/llm-cliche-highlighter/#atom-everything) ⭐️ 8.0/10

Simon Willison 发布了一款名为 LLM cliché highlighter 的网页应用，可检测 AI 生成文本中的十种常见陈词滥调，例如“no fluff, no filler, no jargon”。 该工具为开发者和写作者提供了一种即时实用的方法，用于识别和减少 LLM 输出中的陈词滥调，有助于提升 AI 辅助内容的质量和原创性。 该工具通过 vibe coding 方式使用 Fable 5 构建，Simon 描述想法后由 LLM 生成代码。它会高亮“delve into”、“testament”和“game-changer”等模式。

rss · Simon Willison · 7月17日 12:11

**背景**: Vibe coding 是 Andrej Karpathy 于 2025 年 2 月提出的术语，指开发者通过提示 LLM 生成代码而无需逐行审查的 AI 辅助软件开发方式。LLM 生成的文本常包含重复的陈词滥调，使内容听起来刻板且缺乏真实感。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding</a></li>

</ul>
</details>

**标签**: `#ai`, `#llm`, `#tools`, `#writing`

---

<a id="item-9"></a>
## [PrintBlocks：为 AI 智能体提供热敏打印机 API/MCP 服务器](https://gian-reto.github.io/print-blocks/) ⭐️ 8.0/10

PrintBlocks 是一个自托管的 API 和可选的 MCP 服务器，允许 AI 智能体（如 OpenClaw 或 Hermes）使用 15 个可复用的构建模块生成格式化文档并打印到热敏打印机。 这弥合了数字 AI 智能体与物理输出之间的鸿沟，支持无需屏幕的自动化早晨简报或食谱打印等应用。它利用 LLM 的格式化能力生成视觉美观的打印文档。 MCP 服务器是可选的；用户也可以直接从脚本或 cron 作业中使用 HTTP API。15 种块类型包括文本、图像、图表和条形码，在保持格式一致的同时提供了灵活性。

rss · Show HN (self-made tools) · 7月17日 22:04

**背景**: 模型上下文协议（MCP）是一种开放标准，允许 AI 助手安全地访问外部工具和数据。像 OpenClaw 和 Hermes 这样的 AI 智能体是能够使用此类协议执行任务的自主程序。热敏打印机是紧凑、低成本的打印机，常用于收据和标签，适合简单的文档输出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://modelcontextprotocol.io/docs/getting-started/intro">What is the Model Context Protocol (MCP)? - Model Context Protocol</a></li>
<li><a href="https://github.com/openclaw/openclaw">GitHub - openclaw/openclaw: Your own personal AI assistant. Any OS. Any Platform. The lobster way. 🦞</a></li>
<li><a href="https://github.com/nousresearch/hermes-agent">GitHub - NousResearch/hermes-agent: The agent that grows with you · GitHub</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#MCP`, `#thermal printer`, `#API`, `#self-hosted`

---

<a id="item-10"></a>
## [LIA：基于 FastAPI 和 LangGraph 的自托管多智能体 AI 助手](https://github.com/jgouviergmail/LIA-Assistant) ⭐️ 8.0/10

LIA 是一个全新的开源、自托管的多智能体 AI 助手，基于 FastAPI 和 LangGraph 构建，可在 GitHub 上获取并本地部署。 该项目提供了基于云的 AI 助手的实用自托管替代方案，增强了隐私和可定制性，同时展示了 LangGraph 如何在真实应用中编排多个智能体。 LIA 使用 FastAPI 作为 API 层，LangGraph 用于在基于图形的工作流中编排多个 AI 智能体。仓库包含在本地设置和运行该助手的代码及文档。

rss · Show HN (self-made tools) · 7月17日 21:21

**背景**: LangGraph 是 LangChain 推出的开源框架，旨在通过图结构构建和管理 AI 智能体工作流。它允许开发者将复杂的智能体交互定义为节点和边，使工作流更加结构化且可扩展。多智能体系统涉及多个 AI 智能体协同完成任务，而 LIA 应用了这一方法来创建多功能助手。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.langchain.com/langgraph">LangGraph: Agent Orchestration Framework for Reliable AI Agents</a></li>
<li><a href="https://www.geeksforgeeks.org/machine-learning/what-is-langgraph/">What is LangGraph - GeeksforGeeks</a></li>
<li><a href="https://www.ibm.com/think/topics/langgraph">What is LangGraph? - IBM</a></li>

</ul>
</details>

**标签**: `#AI assistant`, `#multi-agent`, `#LangGraph`, `#self-hosted`, `#FastAPI`

---

<a id="item-11"></a>
## [Maxx：带滚动窗口的实时 CLI 令牌追踪器](https://meetmaxx.co/) ⭐️ 8.0/10

Maxx 是一个全新的实时 CLI 令牌追踪器，它采用 5 小时滚动窗口来帮助开发者实时监控和管理 AI 代理的令牌消耗。 该工具解决了使用具有令牌预算的 AI 代理的开发者的关键痛点，使代理能够自我调节使用量，避免过早达到每周限制。 Maxx 每秒更新一次，提供模型权重、每周进度条和彩色编码的会话条。它暴露了一个 /maxx --session 端点，使得多个代理无需集中规划即可检查令牌可用性。

rss · Show HN (self-made tools) · 7月17日 18:41

**背景**: AI 代理，特别是由编排器生成的子代理，可能会迅速消耗订阅中的令牌，经常提前达到每周限制。令牌管理工具帮助开发者分配预算并避免超支。滚动窗口方法将每周分配分成每小时块，使代理能够根据近期使用情况查看实时可用性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.faros.ai/blog/claude-code-token-limits">Claude Code Token Limits and How to Manage AI Coding Spend</a></li>
<li><a href="https://devtk.ai/en/blog/llm-context-window-explained/">LLM Context Windows Explained: 4K to 1M Tokens (2026)</a></li>
<li><a href="https://ai-sdk.dev/docs/agents/subagents">Agents: Subagents</a></li>

</ul>
</details>

**标签**: `#token management`, `#AI agents`, `#CLI tool`, `#productivity`, `#Claude`

---

<a id="item-12"></a>
## [使用 NVIDIA NeMo 和 Diffusers 规模化微调视频与图像模型](https://huggingface.co/blog/nvidia/scale-diffusers-finetuning-nemo-automodel) ⭐️ 8.0/10

NVIDIA 与 Hugging Face 发布的一篇博客文章介绍了一种方法，利用 NVIDIA NeMo AutoModel 和 Hugging Face Diffusers 对视频和图像扩散模型进行规模化微调，从而在大型数据集上实现高效训练。 这具有重要意义，因为它为微调生成式 AI 模型提供了实用且可扩展的解决方案，减少了自定义模型适配所需的时间和资源。开发者可以利用 NVIDIA 的优化内核和 Hugging Face 的生态系统加速工作流。 NeMo AutoModel 是一个开源的、基于 PyTorch DTensor 的原生分布式训练库，支持跨多个 GPU 扩展。它与 Hugging Face Diffusers 无缝集成，用户只需极少代码改动即可微调 Stable Diffusion 等模型。

rss · Hugging Face Blog · 7月17日 15:57

**背景**: 扩散模型是一类通过逆转噪声过程来生成数据的生成式模型。微调使预训练模型适应特定任务或数据集。NVIDIA NeMo AutoModel 提供分布式训练基础设施，而 Hugging Face Diffusers 提供预训练扩散模型和流水线库。二者的结合实现了可扩展的微调。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.nvidia.com/nemo/automodel">NeMo AutoModel Documentation | NVIDIA NeMo AutoModel</a></li>
<li><a href="https://huggingface.co/docs/diffusers/index">Diffusers - Hugging Face</a></li>

</ul>
</details>

**标签**: `#fine-tuning`, `#diffusion models`, `#NVIDIA`, `#Hugging Face`, `#AI tools`

---

<a id="item-13"></a>
## [Browser-use 0.13.5 发布，支持 MCP 注册表](https://github.com/browser-use/browser-use/releases/tag/0.13.5) ⭐️ 7.0/10

浏览器自动化工具 browser-use 发布了 0.13.5 版本，新增了对 MCP 注册表的支持以及新的模型别名 'bu-qa-1'。 该版本通过支持与外部 MCP 服务器集成，增强了 browser-use 的可扩展性，这对依赖浏览器自动化的 AI 智能体开发者至关重要。 MCP 注册表支持允许用户发现并连接到多个 MCP 服务器，新的模型别名简化了模型选择。还包括了少量修复和 README 更新。

github · laithrw · 7月17日 00:49

**背景**: browser-use 是一个开源库，允许 AI 智能体以编程方式控制网页浏览器。MCP（模型上下文协议）是一个将外部工具和数据源与 AI 模型集成的框架，而 MCP 注册表是可用 MCP 服务器的集中目录。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://mcp.microsoft.com/">MCP Center - Build Your Own Enterprise MCP Registry</a></li>
<li><a href="https://www.c-sharpcorner.com/article/what-is-model-context-protocol-mcp-registry-a-complete-guide/">What Is Model Context Protocol ( MCP ) Registry ? A Complete Guide</a></li>

</ul>
</details>

**标签**: `#browser-use`, `#automation`, `#MCP`, `#release`, `#AI agent`

---

<a id="item-14"></a>
## [Visuali.io：一个用于图像处理和分析的 Claude Code 式工具](https://visuali.io/) ⭐️ 7.0/10

一款名为 Visuali.io 的新网络工具已发布，它允许用户通过自然语言指令对图像进行操作和分析，类似于 Claude Code 对代码的处理方式。 这将该 AI 智能体范式带到了视觉任务领域，可能为设计师、研究人员和普通用户简化图像编辑与分析流程，无需手动操作工具。 该工具托管在 visuali.io，集成了语言模型与图像处理能力。发布时未公布具体的模型细节或定价信息。

rss · Show HN (self-made tools) · 7月17日 21:00

**背景**: Claude Code 是 Anthropic 开发的 AI 编程助手，使用自然语言生成和编辑代码。类似地，ImageAgent 等图像智能体将视觉模型与大语言模型结合，根据用户提示自主完成图像创建、编辑和分析。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://creati.ai/ai-tools/imageagent/">ImageAgent: AI-Powered Image Generation & Editing Agent ...</a></li>

</ul>
</details>

**标签**: `#AI tool`, `#image agent`, `#workflow automation`

---