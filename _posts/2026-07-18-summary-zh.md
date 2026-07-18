---
layout: default
title: "Horizon Summary: 2026-07-18 (ZH)"
date: 2026-07-18
lang: zh
---

> 从 64 条内容中筛选出 13 条重要资讯。

---

1. [指南：用闲置 Mac 让 Claude Code 接管控制](#item-1) ⭐️ 9.0/10
2. [Waylou：Gemini CLI 的多提供商分支，用于代码生成](#item-2) ⭐️ 9.0/10
3. [Peek-CLI 让 Claude Code 查看并迭代前端设计](#item-3) ⭐️ 9.0/10
4. [Warden：面向 Agentic RAG 的授权网关](#item-4) ⭐️ 9.0/10
5. [Show HN: Talon – 用于长期运行 AI 代理的自托管容器](#item-5) ⭐️ 9.0/10
6. [OpenPangu-2.0-Flash 92B MoE 模型加入 ik_llama.cpp GGUF 格式](#item-6) ⭐️ 9.0/10
7. [Cache-Hunter 工具检测 LLM 缓存失效问题](#item-7) ⭐️ 9.0/10
8. [Kimi K3 登顶 DeepSWE 第三名](#item-8) ⭐️ 9.0/10
9. [面向 Agent 的 Codex 主题管理网站](#item-9) ⭐️ 9.0/10
10. [SQLite 查询解释器：浏览器工具解读查询计划](#item-10) ⭐️ 8.0/10
11. [字节精确 KV 缓存嫁接将 Gemma 4 性能提升至 AIME 90%](#item-11) ⭐️ 8.0/10
12. [B 站 WAIC 展示'猫娘计划'开源 AI 伙伴](#item-12) ⭐️ 8.0/10
13. [用于世界模型的牧羊强化学习环境](#item-13) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [指南：用闲置 Mac 让 Claude Code 接管控制](https://ykdojo.github.io/claude-controls-mac/) ⭐️ 9.0/10

一篇新的分步指南介绍了如何将闲置 Mac 设置为 Anthropic 的 Claude Code AI 代理的远程控制机器，使其能够自主执行任务。 这篇实用指南降低了开发者在隔离硬件上实验 AI 代理的门槛，解决了安全性和可靠性问题，同时扩展了 Claude Code 的有用场景。 该指南建议使用专用 Mac 进行隔离而非虚拟机，但社区成员指出，基于 libvirt 的虚拟机可以提供类似的隔离效果，且恢复速度更快。

hackernews · ykev · 7月18日 16:12 · [社区讨论](https://news.ycombinator.com/item?id=48959392)

**背景**: Claude Code 是 Anthropic 的智能编码工具，能够理解代码库、编辑文件并在终端中运行命令。像 Claude Code 这样的 AI 代理可以自主执行复杂任务，但在用户主环境中运行可能对系统稳定性和数据安全构成风险。将代理隔离在单独的硬件或虚拟机上可以缓解这些风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>

</ul>
</details>

**社区讨论**: 社区评论强调了使用 libvirt 虚拟机的替代隔离方法，质疑为什么特别需要闲置 Mac（例如 iMessage），并表示很难找到令人信服的 24/7 AI 使用场景。一位用户指出，许多人可能没有闲置的 Mac。

**标签**: `#AI agents`, `#Claude`, `#Mac automation`, `#practical guide`

---

<a id="item-2"></a>
## [Waylou：Gemini CLI 的多提供商分支，用于代码生成](https://github.com/helis-d/waylou) ⭐️ 9.0/10

Waylou 是一个从 Google 的 Gemini CLI 分叉而来的新型开源 CLI 编码代理，允许用户直接在终端中使用多种 AI 提供商（如 Gemini、OpenAI）进行代码生成。 这个分支解决了绑定单一 AI 提供商的限制，为开发者提供了灵活性，让他们在熟悉 CLI 界面的同时可以选择不同的编码工作流。 Waylou 在 GitHub 上的仓库 helis-d/waylou 中可用，它保留了 Gemini CLI 的核心功能，并通过类似插件的架构扩展了提供商支持。

rss · Show HN (self-made tools) · 7月18日 19:45

**背景**: Gemini CLI 是 Google 开发的一个开源 AI 代理，将 Gemini 的能力带到终端中。它提供免费访问、大上下文窗口和网络搜索功能。Waylou 分叉了这个项目，以支持多个提供商，而不仅仅是 Gemini。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/google-gemini/gemini-cli">GitHub - google-gemini/gemini-cli: An open-source AI agent that brings the power of Gemini directly into your terminal. · GitHub</a></li>
<li><a href="https://en.wikipedia.org/wiki/Gemini_(language_model)">Gemini (language model)</a></li>
<li><a href="https://grokipedia.com/page/Gemini_CLI">Gemini CLI</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#CLI`, `#coding agent`, `#multi-provider`, `#GitHub`

---

<a id="item-3"></a>
## [Peek-CLI 让 Claude Code 查看并迭代前端设计](https://github.com/puffinsoft/peek-cli) ⭐️ 9.0/10

Peek-CLI 是一个新的开源命令行工具，它允许 Anthropic 的 AI 编程助手 Claude Code 从终端直接查看并在浏览器中迭代前端设计。 该工具弥合了 AI 编程代理与可视化 UI 开发之间的鸿沟，使得无需离开终端环境就能更高效、更快速地进行前端迭代。 Peek-CLI 使用 Rust 构建，可以即时在默认网页浏览器中预览任何文件类型。它向 Claude Code 展示渲染后的设计，使 AI 能够修改代码并查看结果。

rss · Show HN (self-made tools) · 7月18日 19:02

**背景**: Claude Code 是 Anthropic 的代理型编程工具，运行在终端中，能够理解代码库、编辑文件并执行命令。但它缺乏查看前端设计等视觉输出的能力。Peek-CLI 旨在为 Claude Code 提供进入浏览器的“透视眼”，使其在编程过程中获得可视化反馈。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/puffinsoft/peek-cli">GitHub - puffinsoft/peek-cli: Let coding agents see your ...</a></li>
<li><a href="https://nameocean.net/article/peek-cli-giving-ai-coding-agents-x-ray-vision-into-your-browser/">peek-cli: Giving AI Coding Agents X-Ray Vision Into Your ...</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#front-end`, `#CLI`, `#Claude Code`, `#tool`

---

<a id="item-4"></a>
## [Warden：面向 Agentic RAG 的授权网关](https://github.com/geminimir/warden) ⭐️ 9.0/10

Warden 是一个开源授权网关，在 agentic RAG 系统的检索路径中强制执行基于关系、感知拒绝、跨租户的文档权限，提供故障关闭的安全边界和防篡改审计轨迹。 随着 agentic RAG 系统日益普及，确保对检索文档的适当访问控制对企业采用至关重要；Warden 通过将授权直接嵌入检索管道，解决了关键的安全漏洞，防止未经授权的数据泄露。 Warden 实现了故障关闭语义，即如果无法确定授权，默认拒绝访问，并支持代理上下文重新验证以适应权限变化。它还以防篡改审计轨迹记录所有决策，以满足合规要求。

rss · Show HN (self-made tools) · 7月18日 17:06

**背景**: Agentic RAG 结合了大语言模型（LLMs）与自主代理，这些代理检索并处理实时数据以回答问题或执行任务。在企业环境中，文档通常具有基于用户角色、关系和租户的复杂访问控制，但传统 RAG 系统在检索和展示信息时可能绕过这些控制，导致数据泄露。像 Warden 这样的授权网关位于检索路径中，在文档到达 LLM 或代理之前强制执行权限。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/geminimir/warden">GitHub - geminimir/warden: Fail-closed authorization gateway ...</a></li>
<li><a href="https://www.geeksforgeeks.org/artificial-intelligence/what-is-agentic-rag/">Agentic RAG - GeeksforGeeks</a></li>
<li><a href="https://aws.amazon.com/blogs/security/authorizing-access-to-data-with-rag-implementations/">Authorizing access to data with RAG implementations</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#RAG`, `#authorization`, `#GitHub`, `#tool`

---

<a id="item-5"></a>
## [Show HN: Talon – 用于长期运行 AI 代理的自托管容器](https://github.com/dylanneve1/talon) ⭐️ 9.0/10

Talon 是一个新的开源、自托管的容器，用于构建和运行长期存在的 AI 代理，它能跨会话管理状态、工具和执行。 随着 AI 代理从单次查询转向多步骤、持久化任务，像 Talon 这样的容器填补了生产级代理部署的关键基础设施缺口。 Talon 托管在 GitHub 上（github.com/dylanneve1/talon），专为需要自托管控制其代理基础设施、避免供应商锁定的开发者设计。

rss · Show HN (self-made tools) · 7月18日 16:24

**背景**: AI 代理容器是围绕大语言模型的软件基础设施，使其能够作为代理运行：管理工具使用、记忆、状态持久化和反馈循环。长期运行的代理必须能够在数小时、数天或数周内运行，从故障中恢复并在多次交互中保持上下文。没有容器，大语言模型是无状态的，仅限于单轮交互；容器将记录存储卸载到结构化环境中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Agent_harness">Agent harness</a></li>
<li><a href="https://addyosmani.com/blog/long-running-agents/">AddyOsmani.com - Long-running Agents</a></li>
<li><a href="https://www.databricks.com/blog/ai-harness">What is an AI Agent Harness ? | Databricks Blog</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#self-hosted`, `#open-source`, `#agent framework`

---

<a id="item-6"></a>
## [OpenPangu-2.0-Flash 92B MoE 模型加入 ik_llama.cpp GGUF 格式](https://www.reddit.com/r/LocalLLaMA/comments/1v03psf/model_add_openpangu20flash_92ba6b_with_mlalatent/) ⭐️ 9.0/10

OpenPangu-2.0-Flash 模型（总参数量 92B，激活参数 6B 的 MoE）已通过拉取请求加入 ik_llama.cpp，并提供 GGUF 格式文件用于本地推理。该模型支持 512K 上下文长度，并采用了 Multi-Head Latent Attention (MLA)、Dynamic Sparse Attention (DSA)/Sliding Window Attention (SWA) 和多头多 token 预测 (MTP) 等技术。 这一进展使一个拥有超长上下文的大规模高效 MoE 模型能够在消费级硬件上本地运行，让开发者可以私有地部署先进 LLM。MLA 和 DSA/SWA 的加入降低了内存与计算成本，使高性能推理更加普及。 该模型总参数量 92B，但由于混合专家 (MoE) 架构，每个 token 仅激活 6B 参数，并支持 512K token 的上下文窗口。GGUF 文件专为 ik_llama.cpp 编译，这是 llama.cpp 的一个分支，常包含实验性特性，拉取请求提及了 MLA 潜在缓存、DSA/SWA 和多头 MTP。

reddit · r/LocalLLaMA · /u/pmttyji · 7月18日 18:38

**背景**: 混合专家 (MoE) 模型每个 token 仅激活部分参数，从而在较低计算成本下实现大容量。Multi-Head Latent Attention (MLA) 通过将键和值压缩为低秩潜在表示来减少 KV 缓存内存。滑动窗口注意力 (SWA) 将注意力限制在局部窗口内从而降低复杂度，而动态稀疏注意力 (DSA) 自适应地选择要关注的 token。多 token 预测 (MTP) 同时预测多个未来 token，可能提升吞吐量。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/NormalUhr/mla-explanation">MLA: Redefining KV-Cache Through Low-Rank Projections and On-Demand Decompression</a></li>
<li><a href="https://www.pythonalchemist.com/llm-architectures/attention-variants">Attention Variants Explained: MHA, GQA, MQA, MLA, SWA , DSA</a></li>
<li><a href="https://www.spheron.network/blog/multi-token-prediction-mtp-gpu-cloud-deployment-guide/">Multi -Token Prediction on GPU Cloud: Deploy MTP ... | Spheron Blog</a></li>

</ul>
</details>

**标签**: `#model`, `#openPangu`, `#MoE`, `#local LLM`, `#GGUF`

---

<a id="item-7"></a>
## [Cache-Hunter 工具检测 LLM 缓存失效问题](https://www.reddit.com/r/LocalLLaMA/comments/1uztipo/if_youre_building_a_harness_here_is_a_simple_tool/) ⭐️ 9.0/10

一款名为 cache-hunter 的新工具通过捕获会话并突出显示不稳定的参数（如系统提示或工具），帮助 LLM 框架构建者识别缓存失效问题。 缓存失效是 LLM 应用中常见且棘手的问题，该工具提供了一种实用的调试方案，有助于提升框架性能并降低预填充成本。 该工具作为代理运行：将框架指向 cache-hunter 的本地端口，启动捕获，运行一个会话，任何红色单元格都表示不稳定性。作者已使用 OpenCode、Claude Code、Cline、Pi、Hermes 和 Vibe 进行测试，发现系统提示、工具和消息顺序不稳定等问题。

reddit · r/LocalLLaMA · /u/t4a8945 · 7月18日 11:34

**背景**: LLM 缓存失效发生在系统提示、工具、消息顺序或推理参数发生变化时，导致缓存过时，从而迫使重新计算预填充。许多框架构建者忽视了这些触发因素。cache-hunter 工具帮助开发者实时可视化这些变化，从而更容易调试和优化缓存策略。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.respan.ai/articles/cache-invalidation-llm-apps">LLM Cache Invalidation: 6 Triggers Engineers Miss (2026)</a></li>
<li><a href="https://ssimplifi.com/blog/cache-invalidation-strategies-for-llm-apis">Cache invalidation strategies for LLM APIs: TTL, prompt ...</a></li>
<li><a href="https://github.com/HKUDS/OpenHarness">GitHub - HKUDS/OpenHarness: "OpenHarness: Open Agent Harness with a Built-in Personal Agent--Ohmo!" · GitHub</a></li>

</ul>
</details>

**标签**: `#LLM`, `#AI agent`, `#caching`, `#tool`, `#harness`

---

<a id="item-8"></a>
## [Kimi K3 登顶 DeepSWE 第三名](https://deepswe.datacurve.ai/blog/deepswe-v1-1) ⭐️ 9.0/10

月之暗面发布的开源权重模型 Kimi K3 在 DeepSWE 基准测试中排名第三，性能接近 Claude Fable 5 和 GPT-5.6 Sol 等顶级闭源模型。 这表明开源权重模型正在缩小与专有前沿模型的差距，可能加速 AI 编程智能体的采用，减少对封闭 API 的依赖。 Kimi K3 拥有 2.8 万亿参数、100 万 token 上下文窗口，并采用 Kimi Delta Attention 和 Attention Residuals 技术；它是首个开放的三万亿参数级模型。

telegram · zaihuapd · 7月18日 02:29

**背景**: DeepSWE 是一个长周期软件工程基准测试，通过使用活跃开源仓库中的原始任务来区分前沿编码智能体。开源权重模型公开了参数，任何人都可以下载运行，而闭源模型仅通过 API 访问。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepswe.datacurve.ai/">DeepSWE</a></li>
<li><a href="https://openlm.ai/kimi-k3/">Kimi K3 - openlm.ai</a></li>
<li><a href="https://platform.kimi.ai/docs/guide/kimi-k3-quickstart">Kimi K3 - Kimi API Platform</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#coding benchmark`, `#open-weight model`, `#Kimi K3`, `#DeepSWE`

---

<a id="item-9"></a>
## [面向 Agent 的 Codex 主题管理网站](https://x.com/zjp1997720/status/2078369755678093639) ⭐️ 9.0/10

开发者@zjp1997720 推出了 CodexThemes，这是一个面向 Agent 的网站，用户可以通过向 Codex 发送提示词来完全管理 Codex 主题的创建、分享、查找、安装和启用。 该工具提供了一个完整的、面向 Agent 的 Codex 主题管理工作流程，大大减少了手动操作，并实现了对 Codex 界面的 AI 驱动定制。 该网站被设计为 Agent 原生，意味着给定正确提示词后，Codex 可以自主处理主题管理任务，形成从创建到启用的闭环。

twitter · zjp1997720 · 7月18日 06:42

**背景**: Codex 是 OpenAI 推出的 AI 编程助手。Codex 主题允许用户自定义 Codex 桌面应用的外观。面向 Agent 的网站意味着人类和 AI 代理都可以无缝与其交互，从而实现 AI 自主执行任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-codex/">Introducing Codex | OpenAI</a></li>
<li><a href="https://www.builder.io/blog/agent-native-architecture">Agent-Native: The Next Architecture for Software - Builder.io</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#Codex themes`, `#agent-native`, `#developer workflow`

---

<a id="item-10"></a>
## [SQLite 查询解释器：浏览器工具解读查询计划](https://simonwillison.net/2026/Jul/18/sqlite-query-explainer/#atom-everything) ⭐️ 8.0/10

Simon Willison 发布了一款基于浏览器的交互式工具，通过 Pyodide（WebAssembly 中的 Python）运行 SQLite，来解释 EXPLAIN 和 EXPLAIN QUERY PLAN 的输出。该工具受 Julia Evans 关于学习 SQLite 查询计划的博客文章启发。 该工具降低了开发者理解 SQLite 查询计划的门槛，而查询计划对优化数据库性能至关重要。通过完全在浏览器中运行，它提供了一种无需安装即可体验查询解释的便捷方式。 该工具将 EXPLAIN 和 EXPLAIN QUERY PLAN 的结果与解释性注释相结合，帮助用户理解每一步。它通过 Pyodide（将 CPython 移植到 WebAssembly）在浏览器中运行 SQLite。

rss · Simon Willison · 7月18日 17:19

**背景**: SQLite 的 EXPLAIN QUERY PLAN 命令显示执行查询的高级策略，但其输出对于新手来说可能难以理解。WebAssembly（Wasm）是一种二进制指令格式，可在浏览器中实现高性能执行。Pyodide 是将 CPython 移植到 WebAssembly 的项目，允许 Python 代码在浏览器中运行。该工具将这些技术串联在一起，实现交互式学习。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.sqlite.org/eqp.html">Explain query plan</a></li>
<li><a href="https://en.wikipedia.org/wiki/WebAssembly">WebAssembly</a></li>
<li><a href="https://pyodide.org/">Pyodide — Version 314.0.2</a></li>

</ul>
</details>

**标签**: `#sqlite`, `#sql`, `#query-planning`, `#webassembly`, `#tool`

---

<a id="item-11"></a>
## [字节精确 KV 缓存嫁接将 Gemma 4 性能提升至 AIME 90%](https://www.reddit.com/r/LocalLLaMA/comments/1v07tib/byte_exact_kv_cache_grafting_on_frozen_gemma_4/) ⭐️ 8.0/10

研究人员提出了 Taliesin 和 Galahad 方法，能够对已验证知识的 KV 缓存状态进行字节精确存储与恢复。在冻结的 Gemma 4 12B 模型上，该方法无需重新训练即将 AIME 2025 准确率从 76.7%提升至 90.0%。 该技术能在冻结的 LLM 上实现显著的性能提升，为无需昂贵微调的模块化知识注入开辟了可能。它有望加速更高效、更具适应性的 AI 智能体的研发。 该方法保证了与原始计算字节完全一致的输出，并将可用上下文从 32,768 个 token 扩展到 2,854,766 个 token，且无需额外加速内存。该方案在 Blackwell RTX 5090 上进行了本地测试。

reddit · r/LocalLLaMA · /u/MindPsychological140 · 7月18日 21:24

**背景**: KV 缓存嫁接是一种将语言模型注意力层先前计算出的键值状态存储下来，并直接复用这些状态来提供上下文或知识、避免重复计算的技术。字节精确嫁接确保恢复的缓存能产生与从头计算完全相同的输出，从而实现可靠的知识缓存。该方法无需修改模型权重，与传统微调方式形成鲜明对比。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=48942804">Show HN: KV - Cache Grafting – Boosting frozen... | Hacker News</a></li>
<li><a href="https://blog.jarv.tech/p/kv-cache-grafting-novyi-metod-povysheniya-tochnosti-llm-bez-7c652495bc93cb7a">KV - Cache Grafting : новый метод повышения... — blog.jarv.tech</a></li>

</ul>
</details>

**标签**: `#KV cache`, `#LLM`, `#Gemma`, `#knowledge caching`, `#AI optimization`

---

<a id="item-12"></a>
## [B 站 WAIC 展示'猫娘计划'开源 AI 伙伴](https://finance.sina.com.cn/roll/2026-07-18/doc-iniifanf8394663.shtml) ⭐️ 8.0/10

哔哩哔哩在 2026 世界人工智能大会上展示了开源 AI 数字生命生态企划'猫娘计划'，其核心产品 N.E.K.O.是一款主动式全模态 AI 伙伴，能通过屏幕捕获理解桌面内容并主动对话。项目在 GitHub 获千星，Steam 用户过万。 这代表着面向用户的 AI 智能体迈出重要一步，它能够主动协助桌面任务，融合情感交互与实用功能。开源特性使开发者可以定制和改进这一技术，推动 AI 伴侣领域的社区驱动创新。 系统支持 Live2D 和 VRM 两种角色模型引擎，内置物理反馈引擎与 TTS 语音模块，支持多语言切换和声线克隆。其采用 UI、AI 大脑与记忆系统分离的架构，用户可将核心数据完全保留在本地以确保隐私。

telegram · zaihuapd · 7月18日 06:45

**背景**: Live2D 是一种让 2D 插图动起来的技术，广泛用于游戏和虚拟主播；VRM 是用于 VR 应用的标准 3D 虚拟角色格式。声线克隆技术可根据短音频样本生成合成语音。这些技术结合创造出更沉浸、更个性化的 AI 伴侣。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Live2D">Live2D - Wikipedia</a></li>
<li><a href="https://vrm.dev/en/">3D humanoid avatar file format for VR | VRM</a></li>
<li><a href="https://soundtools.io/voice-cloning/">Free AI Voice Cloning — Clone Any Voice Online | SoundTools</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#open-source`, `#multimodal`, `#WAIC`, `#AI partner`

---

<a id="item-13"></a>
## [用于世界模型的牧羊强化学习环境](https://github.com/midhunharikumar/sheepdog-rl) ⭐️ 7.0/10

一个用于牧羊的强化学习环境已在 GitHub 上发布，专门用于测试世界模型。该仓库面向希望尝试基于模型的强化学习的中级开发者。 该环境为 AI 研究人员和开发者提供了一个实用工具，可以在有趣且具有挑战性的领域探索世界模型。它有助于加速基于模型的强化学习的实验，这对于样本高效的人工智能至关重要。 该环境使用 Python 实现，并在 GitHub 上以 MIT 许可证提供。它设计轻量且易于设置，允许快速迭代以测试世界模型。

rss · Show HN (self-made tools) · 7月18日 16:45

**背景**: 强化学习（RL）是一种机器学习范式，智能体通过与环境的交互来最大化累积奖励。世界模型是内部预测模型，允许智能体模拟环境并规划行动，从而减少与真实世界的交互需求。这个牧羊任务涉及控制一只牧羊犬智能体将羊群赶入围栏，这是一个用于测试 RL 算法的具有挑战性的控制问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/1803.10122">[1803.10122] World Models - arXiv.org [2505.13934] RLVR-World: Training World Models with ... World Models | RL Journal Club Operator World Models for Reinforcement Learning World Models Mastering diverse control tasks through world models | Nature World Models in Reinforcement Learning - emergentmind.com</a></li>
<li><a href="https://rljclub.github.io/posts/world-models/">World Models | RL Journal Club</a></li>

</ul>
</details>

**标签**: `#reinforcement learning`, `#RL environment`, `#GitHub`, `#world models`, `#AI tool`

---