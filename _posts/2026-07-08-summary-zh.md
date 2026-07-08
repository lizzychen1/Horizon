---
layout: default
title: "Horizon Summary: 2026-07-08 (ZH)"
date: 2026-07-08
lang: zh
---

> 从 74 条内容中筛选出 15 条重要资讯。

---

1. [微软发布 Flint，面向 AI 代理的可视化语言](#item-1) ⭐️ 9.0/10
2. [AI Agent 运行时安全强制执行](#item-2) ⭐️ 9.0/10
3. [Skill-Extractor 将代理对话转化为可复用技能](#item-3) ⭐️ 9.0/10
4. [DuckDB ADBC 扩展支持跨数据库查询](#item-4) ⭐️ 9.0/10
5. [NVIDIA 与 Hugging Face 发布 AI 智能体开放数据](#item-5) ⭐️ 9.0/10
6. [Hugging Face 推出原生速度 vLLM Transformers 后端](#item-6) ⭐️ 9.0/10
7. [本地大模型搭配 RAG 准确率高，思考模式增益甚微](#item-7) ⭐️ 9.0/10
8. [本地资产生成管线及 GGML 移植](#item-8) ⭐️ 9.0/10
9. [可定制的 AI PPT 技能培训模板](#item-9) ⭐️ 9.0/10
10. [Lazy Codex 通过提示词注入让 Codex 调用子代理](#item-10) ⭐️ 9.0/10
11. [OpenAI 推出支持 GPT-5.5 后台调用的 GPT‑Live 语音模式](#item-11) ⭐️ 8.0/10
12. [Nully：极简开源 AI 聊天界面](#item-12) ⭐️ 8.0/10
13. [Onboard-CLI：基于 LLM 和 AST 的代码库可视化工具](#item-13) ⭐️ 8.0/10
14. [字节跳动发布 Seedream 5.0 Pro，支持多语言生成与精准编辑](#item-14) ⭐️ 8.0/10
15. [为 Codex 添加外部顾问](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [微软发布 Flint，面向 AI 代理的可视化语言](https://microsoft.github.io/flint-chart/#/) ⭐️ 9.0/10

微软研究院发布了 Flint，一个开源的可视化中间语言，允许 AI 代理从简单的高层规范生成高质量图表，将底层视觉细节交给编译器处理。Flint 支持微软另一个开源项目 Data Formulator。 Flint 通过在 LLM 和图表生成之间提供一个确定性层，解决了构建 AI 代理进行数据可视化的关键挑战，提高了可靠性和图表质量。这种使用中间表示的模式正在成为代理系统的最佳实践。 Flint 支持 46 种图表类型，并包含一个布局优化引擎，可以从数据、语义类型、图表类型和编码中推导出优化设置。它作为 MCP 服务器提供，便于集成到代理应用中。

hackernews · chenglong-hn · 7月8日 17:46 · [社区讨论](https://news.ycombinator.com/item?id=48834924)

**背景**: 当前的可视化语言要么过于简单（生成低质量的默认图表），要么过于冗长（需要明确的低级参数如坐标轴和间距），导致 AI 代理难以可靠使用。Flint 作为中间语言（IR），让代理指定高层语义，编译器处理视觉细节。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.microsoft.com/en-us/research/blog/flint-a-visualization-language-for-the-ai-era/">Flint: A visualization language for the AI era - Microsoft Research</a></li>
<li><a href="https://microsoft.github.io/flint-chart/">Flint: A Visualization Language for the AI Era - microsoft.github.io</a></li>
<li><a href="https://github.com/microsoft/flint-chart">GitHub - microsoft/flint-chart: 🪄 Flint is a visualization language that lets AI agents reliably create expressive, good-looking charts from simple, human-editable chart specs.</a></li>

</ul>
</details>

**社区讨论**: 社区评论反应不一：一些人称赞这种为代理系统提供确定性层的实用价值，而另一些人则质疑 LLM 是否真的对冗长代码感到困扰，或者真正的问题是否是空间理解。一些用户报告说 LLM 已经可以在没有这种工具的情况下生成不错的图表。

**标签**: `#AI agents`, `#visualization`, `#charting`, `#intermediate language`, `#Microsoft`

---

<a id="item-2"></a>
## [AI Agent 运行时安全强制执行](https://www.clayseal.com/) ⭐️ 9.0/10

哈佛和卡内基梅隆大学的研究人员开发了一种运行时安全架构，可动态限定 Agent 能力并监控可疑行为，以阻止沙箱逃逸，克服了静态沙箱的局限性。 这解决了 AI Agent 中的一个关键安全漏洞，因为静态沙箱在长时间会话中可能被绕过；所提出的系统可以显著减少诸如支付欺诈、注入攻击和 MCP rug pull 等利用行为。 该系统采用动态能力限定，持续调整用户任务所需的最小权限和文件访问集合，并结合从 AML 研究借鉴的行为监控。

rss · Show HN (self-made tools) · 7月8日 21:27

**背景**: 许多 Agent 框架依赖静态沙箱，为会话设置固定边界。然而，Agent 可以学习边界并逃逸。能力限定是一种权限模型，只授予特定操作。MCP rug pull 发生在可信工具服务器静默更改其工具定义，导致未授权操作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ssojet.com/blog/oauth-scopes-ai-agents-permission-design-agentic-applications">OAuth Scopes for AI Agents: How to Design Permissions in Agentic Applications | SSOJet - Enterprise SSO & Identity Solutions</a></li>
<li><a href="https://mcpmanager.ai/blog/mcp-rug-pull-attacks/">MCP Rug Pull Attacks: What They Are & How to Stop Them</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent security`, `#sandboxing`, `#capability scoping`

---

<a id="item-3"></a>
## [Skill-Extractor 将代理对话转化为可复用技能](https://github.com/surenode-ai/skill-extractor) ⭐️ 9.0/10

Surenode AI 发布了 Skill-Extractor，这是一个开源工具，能从编码代理的对话记录中提取可复用的技能，便于技能的共享和复用。 随着 AI 编码代理的普及，能够捕获和复用成功的工作流程而非从头开始，对于生产力和标准化至关重要；Skill-Extractor 直接满足了这一需求。 该工具在 GitHub 上可用，并可能集成了新兴的代理技能标准（SKILL.md 格式），类似于 OpenAI Codex 和 VS Code 中的相关工具。

rss · Show HN (self-made tools) · 7月8日 20:03

**背景**: 编码代理（如 GitHub Copilot 或 Claude Code）可以记录其操作过程形成对话记录。‘技能’将特定工作流程的指令和脚本打包，使代理能够可靠地执行任务。Skill-Extractor 自动从先前的对话中生成这些技能定义。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://code.visualstudio.com/docs/agent-customization/agent-skills">Use Agent Skills in VS Code</a></li>
<li><a href="https://developers.openai.com/codex/skills">Agent Skills – Codex | OpenAI Developers</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#skill extraction`, `#GitHub`, `#automation`

---

<a id="item-4"></a>
## [DuckDB ADBC 扩展支持跨数据库查询](https://github.com/columnar-tech/duckdb-adbc-client) ⭐️ 9.0/10

一个新的 DuckDB 社区扩展 duckdb-adbc-client，允许通过 read_adbc 表函数或 ATTACH 命令直接从 DuckDB 查询 Snowflake、Databricks、BigQuery、PostgreSQL、MySQL 以及任何兼容 ADBC 的数据库。 该扩展使 DuckDB 能够充当跨多个数据库的通用查询引擎，简化了数据集成，减少了复杂 ETL 管道的需求，并有益于处理异构数据源的数据工程师和分析师。 该扩展采用 Apache-2.0 许可证开源，可通过在 DuckDB 中运行 'INSTALL adbc FROM community; LOAD adbc;' 进行安装。它支持对附加的 ADBC 数据库执行 SELECT、INSERT、COPY 和 CTAS 操作，如同操作本地数据库一样。

rss · Show HN (self-made tools) · 7月8日 19:11

**背景**: ADBC（Arrow 数据库连接）是 Apache Arrow 的一个 API 标准，它返回查询结果作为 Arrow 数据流，不同于基于行的协议。DuckDB 是一个进程内分析型 SQL 数据库，具有灵活的扩展系统，可用于添加功能，包括社区贡献的扩展。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/apache/arrow-adbc">GitHub - apache/arrow-adbc: Database connectivity API standard and libraries for Apache Arrow · GitHub</a></li>
<li><a href="https://duckdb.org/docs/current/extensions/overview">Extensions – DuckDB</a></li>
<li><a href="https://duckdb.org/community_extensions/list_of_extensions">List of Community Extensions – DuckDB Community Extensions</a></li>

</ul>
</details>

**标签**: `#DuckDB`, `#database`, `#ADBC`, `#open source`, `#data engineering`

---

<a id="item-5"></a>
## [NVIDIA 与 Hugging Face 发布 AI 智能体开放数据](https://huggingface.co/blog/nvidia/open-data-for-agents) ⭐️ 9.0/10

NVIDIA 与 Hugging Face 联合发布了一系列为 AI 智能体的训练与开发而设计的开放数据集，旨在加速自主系统的研究与开发。 这为构建更强大、更可靠的 AI 智能体提供了标准化、高质量的数据基础，减轻了整个行业研究者和开发者的数据收集负担。 这些数据集涵盖导航、操作和人类交互等多种智能体任务，并托管在 Hugging Face Hub 上，便于访问和社区协作。

rss · Hugging Face Blog · 7月8日 17:16

**背景**: AI 智能体是能够感知环境并采取行动以实现目标的自主系统。高质量的训练数据对其开发至关重要，但收集和整理此类数据通常既昂贵又耗时。来自 NVIDIA 和 Hugging Face 等主要参与者的开放数据集有助于普及智能体研究。

**标签**: `#AI agents`, `#datasets`, `#open data`, `#Hugging Face`, `#NVIDIA`

---

<a id="item-6"></a>
## [Hugging Face 推出原生速度 vLLM Transformers 后端](https://huggingface.co/blog/native-speed-vllm-transformers-backend) ⭐️ 9.0/10

Hugging Face 宣布了新的原生速度 vLLM Transformers 建模后端，将 vLLM 推理引擎直接集成到 Transformers 库中，以最小的代码更改实现更快的 LLM 推理。 此集成使开发者能够直接从 Transformers 生态系统中实现高吞吐量、内存高效的 LLM 服务，大幅缩小研究与生产部署之间的性能差距。 vLLM 后端支持 Hugging Face 上 200 多种模型架构，并利用先进并行技术，包括张量并行、流水线并行、数据并行、专家并行和上下文并行，用于分布式推理。

rss · Hugging Face Blog · 7月8日 00:00

**背景**: vLLM 是一个用于大型语言模型的高吞吐量、内存高效的推理引擎，具有 PagedAttention 和连续批处理功能。Hugging Face Transformers 是加载和微调模型的广泛使用的库，但其默认推理速度较慢。这个原生后端将 vLLM 的性能优化直接引入 Transformers API。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.vllm.ai/">vLLM</a></li>
<li><a href="https://vllm.ai/">vLLM — Fast, Memory-Efficient LLM Inference & Serving</a></li>
<li><a href="https://www.redhat.com/en/topics/ai/what-is-vllm">What is vLLM?</a></li>

</ul>
</details>

**标签**: `#vLLM`, `#Transformers`, `#LLM inference`, `#Hugging Face`, `#performance optimization`

---

<a id="item-7"></a>
## [本地大模型搭配 RAG 准确率高，思考模式增益甚微](https://www.reddit.com/r/LocalLLaMA/comments/1uqpxgp/can_you_trust_local_models_to_answer_accurately/) ⭐️ 9.0/10

一位开发者使用 7,648 道技术选择题对本地大模型（具体为 unsloth Gemma QAT 模型）进行了基准测试，发现 RAG（检索增强生成）显著提升了准确率，而开启思考模式仅带来约 1%的提升。 这项基准测试为构建 AI 工具的开发者提供了可操作的见解，表明本地大模型在搭配知识库和 RAG 时能达到很高的准确率，而思考模式对于事实性技术问题可能并非必需。 测试使用了由 deepseek-v4-flash 根据 Node.js、Langchain.js、TypeScript、transformers.js 和 Vue 的 GitHub 文档生成的多选题。Apple Intelligence（AFM 2 3b）尽管仅有 4K token 的上下文长度，仍达到 86%的准确率，而其他模型则使用 32K 上下文。

reddit · r/LocalLLaMA · /u/Spiritual-Market-741 · 7月8日 11:28

**背景**: RAG（检索增强生成）通过在回答前将外部知识库中的相关文档注入提示来提升大模型的准确率。QAT（量化感知训练）在保持准确率的同时减少模型的内存占用。unsloth 的 Gemma 4 QAT 模型针对 4-bit 推理优化，性能接近原始精度。DeepSeek-V4-Flash 是一个 284B 参数的混合专家模型，在此用于生成测试问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/collections/unsloth/gemma-4-qat">Gemma 4 QAT - a unsloth Collection</a></li>
<li><a href="https://huggingface.co/unsloth/gemma-4-12B-it-qat-GGUF">unsloth/gemma-4-12B-it-qat-GGUF · Hugging Face</a></li>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash">deepseek-ai/DeepSeek-V4-Flash · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#RAG`, `#benchmarking`, `#technical-questions`, `#developer-tools`

---

<a id="item-8"></a>
## [本地资产生成管线及 GGML 移植](https://www.reddit.com/r/LocalLLaMA/comments/1ur1mim/complete_local_model_asset_generation_pipeline/) ⭐️ 9.0/10

一位开发者发布了完整的本地游戏资产生成管线，包括 OpenMOSS TTS、ThinkSound 音效和 Trellis.2 3D 生成模型的 GGML 移植，并全部集成到了 Lemonade SDK 中。 该管线让高质量的 AI 生成资产（语音、音效、3D 模型）完全本地化且免费，使开发者能够在没有云依赖或许可费用的情况下创建游戏，并通过 CUDA、Vulkan 或 ROCm 支持大多数硬件。 三个移植版本在 GitHub 上可用（pwilkin/openmoss、pwilkin/thinksound.cpp、pwilkin/trellis.cpp），整个功能集将集成到 Lemonade SDK 中，支持级联模型调用实现文本到 3D 的工作流。所有引擎支持 CUDA、Vulkan 和 ROCm，但暂不支持 macOS。

reddit · r/LocalLLaMA · /u/ilintar · 7月8日 18:42

**背景**: GGML 是一个用于机器学习的张量库，能在普通硬件上高效进行本地 AI 模型推理，是 llama.cpp 等工具的基础。OpenMOSS 是一系列开源 TTS 模型，支持语音克隆；ThinkSound 可生成音效；Trellis.2 是当前最先进的开源图像转 3D 模型。开发者将这些与 AceStep（音乐生成）和 Lemonade SDK 结合，构建了完整的本地资产生成管线。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GGML">GGML</a></li>
<li><a href="https://en.wikipedia.org/wiki/Llama.cpp">llama.cpp - Wikipedia</a></li>
<li><a href="https://github.com/ggml-org/ggml">GitHub - ggml-org/ggml: Tensor library for machine learning · GitHub</a></li>

</ul>
</details>

**标签**: `#local LLM`, `#asset generation`, `#TTS`, `#GGML`, `#pipeline`

---

<a id="item-9"></a>
## [可定制的 AI PPT 技能培训模板](https://x.com/zjp1997720/status/2074836280752685088) ⭐️ 9.0/10

一位用户分享了一个重新设计的 AI PPT 技能模板，专为外部培训打造，风格克制且具有顾问讲义感。 这使得 AI 驱动的演示文稿制作更加便捷且品牌一致，为经常提供培训的专业人士节省时间。 该模板可根据品牌风格高度定制，帖子中附带了资源链接。

twitter · zjp1997720 · 7月8日 12:41

**背景**: AI PPT 技能允许用户使用自然语言创建或更新 PowerPoint 演示文稿，同时保留模板。像 Claude PPTX Skill 这样的系统可以自动生成内容并应用品牌风格。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://smartscope.blog/en/generative-ai/claude/claude-pptx-skill-practical-guide/">Claude PPTX Skill Guide 2026: Create and Edit PowerPoint Decks - SmartScope</a></li>
<li><a href="https://medium.com/@shahsoumil519/how-i-used-ai-to-turn-our-powerpoint-template-into-a-claude-skill-in-minutes-b52c3cb02ff0">How I Used AI to Turn Our PowerPoint Template Into a Claude Skill in Minutes | by Soumil Shah | Medium</a></li>

</ul>
</details>

**标签**: `#AI PPT`, `#automation`, `#template`, `#presentation`, `#design`

---

<a id="item-10"></a>
## [Lazy Codex 通过提示词注入让 Codex 调用子代理](https://x.com/zjp1997720/status/2074833298631930009) ⭐️ 9.0/10

Lazy Codex 插件通过提示词注入的方式，提醒 Codex 主动调用子代理来完成复杂任务，从而减少人工介入的需求。 这解决了 Codex 在需要人工介入的任务中的局限性，提升了自主完成任务的能力和开发效率。 该插件通过注入提示词来协调子代理，无需修改 Codex 核心；特别适用于复杂的多步骤任务。

twitter · zjp1997720 · 7月8日 12:29

**背景**: Codex 是 OpenAI 出品的 AI 编程助手，能根据自然语言生成代码。但有些任务需要人工干预或拆分为子任务。Lazy Codex 是一个第三方插件，通过向 Codex 的提示中注入指令，让它自动调用子代理（小 AI 助手）来处理子任务，从而实现更自主的行为，无需手动提示。

**标签**: `#AI工具`, `#Codex`, `#Agent`, `#提示词注入`, `#开发效率`

---

<a id="item-11"></a>
## [OpenAI 推出支持 GPT-5.5 后台调用的 GPT‑Live 语音模式](https://openai.com/index/introducing-gpt-live/) ⭐️ 8.0/10

OpenAI 发布了 GPT‑Live，这是一种语音模式，可以在后台将复杂任务委托给 GPT-5.5，从而实现更长的对话，并让用户直接通过语音交互获得前沿模型的能力。 GPT‑Live 弥合了语音助手与最新语言模型之间的差距，让用户无需动手即可使用先进的 AI 能力。这可能会改变用户进行头脑风暴、研究和生产力任务时与 AI 互动的方式。 早期测试者展示了一次长达一小时的对话。但初始版本不支持第三方连接器和工具，限制了在语音会话中检索文档或记笔记等操作。

hackernews · logickkk1 · 7月8日 17:03 · [社区讨论](https://news.ycombinator.com/item?id=48834405)

**背景**: GPT-5.5（代号“Spud”）是 OpenAI 于 2026 年 4 月发布的最先进语言模型。此前，语音模式通常使用较小、能力较弱的模型，限制了用户只能使用较老的 AI 能力。GPT‑Live 通过允许后台调用完整的 GPT-5.5 模型解决了这一问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GPT-5.5">GPT-5.5</a></li>
<li><a href="https://openai.com/index/introducing-gpt-5-5/">Introducing GPT-5.5 - OpenAI</a></li>

</ul>
</details>

**社区讨论**: 早期测试者 simonw 赞扬了 GPT‑Live 的长对话能力和后台调用，同时报告了一个它打断对话并发出不恰当笑声的 bug。其他人则对 AI 取代人类互动表示担忧，artdigital 特别指出缺少在语音模式下使用连接器的能力。

**标签**: `#OpenAI`, `#voice AI`, `#AI agents`, `#GPT-5.5`

---

<a id="item-12"></a>
## [Nully：极简开源 AI 聊天界面](https://nully.chat/) ⭐️ 8.0/10

Nully 是一个全新的极简开源 AI 聊天界面，它通过 OpenRouter 访问模型，并将所有聊天数据本地存储在用户机器上。该工具由一位对主流 AI 聊天服务臃肿感到不满的开发者发布。 该项目为那些不需要复杂功能（如智能体模式、图像生成等）的用户提供了一种轻量、注重隐私的替代方案，避免了不必要的复杂性和数据暴露。 Nully 使用 Go 语言和原生 HTML/CSS/JS 构建，支持 OpenRouter 上的文本模型，并提供基本的附件和网页搜索功能。它没有账户、订阅或第三方代理，整个应用均可自行托管。

rss · Show HN (self-made tools) · 7月8日 20:25

**背景**: OpenRouter 是一个统一 API，提供对多个提供商的大语言模型的访问。许多 AI 聊天界面包含记忆、图像生成和智能体模式等复杂功能，这对只需要简单对话的用户来说可能过于繁琐。Nully 去除了所有臃肿部分，专注于提供干净、快速的聊天体验，并通过本地存储保障隐私。

**标签**: `#open source`, `#AI chat`, `#minimal`, `#self-hosted`, `#FOSS`

---

<a id="item-13"></a>
## [Onboard-CLI：基于 LLM 和 AST 的代码库可视化工具](https://github.com/animesh-94/Onboard-CLI) ⭐️ 8.0/10

Onboard-CLI 是一款新的命令行工具，它结合了大语言模型（LLM）和抽象语法树（AST）来生成代码库结构的交互式可视化。 该工具可以帮助开发者快速理解不熟悉的代码库，减少上手时间并提高效率。 该工具是开源的，可在 GitHub 上获取，利用 LLM 推断高层架构，利用 AST 获取精确的代码关系。

rss · Show HN (self-made tools) · 7月8日 20:09

**背景**: 大语言模型（LLM）是在大量文本数据上训练的人工智能模型，能够理解和生成类人文本。抽象语法树（AST）是表示代码语法结构的数据结构。Onboard-CLI 整合两者，生成代码依赖关系和组件的可视化地图。

**标签**: `#codebase visualization`, `#CLI tool`, `#LLM`, `#AST`, `#developer tool`

---

<a id="item-14"></a>
## [字节跳动发布 Seedream 5.0 Pro，支持多语言生成与精准编辑](https://seed.bytedance.com/en/seedream5_0_pro) ⭐️ 8.0/10

字节跳动 Seed 团队推出了 Seedream 5.0 Pro，这是一个多模态图像生成模型，支持高密度信息图、交互式编辑、摄影级画质和原生多语言文字生成，覆盖十余种语言。 该模型通过空间标注和手绘草图实现精准编辑，并原生支持图像内多语言文字生成，提升了 AI 图像生成的实用性和国际化创作能力，对教育和专业场景尤其有价值。 该模型能够分离图层进行独立编辑，并通过准确还原自然光影、阴影和皮肤纹理实现摄影级真实感。它专为生成文字密集的教育与专业场景信息图而设计。

telegram · zaihuapd · 7月8日 15:11

**背景**: 多模态图像生成模型结合文本与图像理解，根据文字提示创作视觉内容。字节跳动 Seed 团队致力于开发先进的 AI 工具，Seedream 5.0 Pro 是其最新成果，注重生成质量与可编辑性，解决了 AI 图像合成中常见的痛点。

**标签**: `#多模态生成`, `#图像编辑`, `#字节跳动`, `#AI工具`

---

<a id="item-15"></a>
## [为 Codex 添加外部顾问](https://x.com/zjp1997720/status/2074848847453675754) ⭐️ 8.0/10

一位开发者设计了两个自定义技能，让 Codex 在复杂决策任务中咨询外部顾问——Claude Code 和 AntiGravity。 该技术通过集成专门的外部 AI 代理，解决了 GPT-5.5 的局限性，为提升 AI 工作流程和决策质量提供了一种实用方法。 这些技能设计简单：Codex 独立研究 Claude Code 的无头模式和 AntiGravity 以获取建议。该方法对开发者来说直接且可行。

twitter · zjp1997720 · 7月8日 13:31

**背景**: Codex 是一个 AI 辅助编程工具，而 GPT-5.5 是指最近被批评能力不足的 OpenAI 模型。Claude Code 是 Anthropic 开发的 AI 编程助手，可协助开发任务。AntiGravity 是推文中提到的另一个外部工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://code.claude.com/docs/en/overview">Overview - Claude Code Docs</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Codex`, `#Claude Code`, `#skill design`, `#workflow optimization`

---