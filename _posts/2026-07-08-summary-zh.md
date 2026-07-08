---
layout: default
title: "Horizon Summary: 2026-07-08 (ZH)"
date: 2026-07-08
lang: zh
---

> 从 74 条内容中筛选出 15 条重要资讯。

---

1. [微软发布 Flint：面向 AI 代理的可视化中间语言](#item-1) ⭐️ 9.0/10
2. [Onboard-CLI：基于 LLM 和 AST 的代码可视化工具](#item-2) ⭐️ 9.0/10
3. [Skill-extractor：从编码代理记录中提取可复用技能](#item-3) ⭐️ 9.0/10
4. [DuckDB ADBC 扩展实现跨数据库查询](#item-4) ⭐️ 9.0/10
5. [基准测试：本地 LLM 需 RAG 才能准确回答，思维链帮助不大](#item-5) ⭐️ 9.0/10
6. [开发者将多个模型移植到 GGML，实现本地游戏资产生成管线](#item-6) ⭐️ 9.0/10
7. [字节跳动发布 Seedream 5.0 Pro，支持多语言与编辑](#item-7) ⭐️ 9.0/10
8. [用户设计技能将 Claude Code 和 AntiGravity 集成到 Codex](#item-8) ⭐️ 9.0/10
9. [新 AI 技能可制作高质量可编辑 PPT](#item-9) ⭐️ 9.0/10
10. [Lazy Codex 插件通过子代理增强 Codex](#item-10) ⭐️ 9.0/10
11. [用户展示高可玩性 PPT 技能，计划开源](#item-11) ⭐️ 9.0/10
12. [GitLost：通过提示注入攻击泄露 GitHub 私有仓库的 AI 代理](#item-12) ⭐️ 8.0/10
13. [Nully：使用 OpenRouter 的极简开源 AI 聊天界面](#item-13) ⭐️ 8.0/10
14. [NVIDIA 与 Hugging Face 推出 AI 智能体开放数据计划](#item-14) ⭐️ 8.0/10
15. [Hugging Face Transformers 原生速度 vLLM 后端](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [微软发布 Flint：面向 AI 代理的可视化中间语言](https://microsoft.github.io/flint-chart/#/) ⭐️ 9.0/10

微软发布了 Flint，这是一个开源的可视化中间语言和布局优化引擎，旨在提高 AI 代理生成图表的可靠性。Flint 允许代理表达基于语义类型的高级规范，并将其编译成详细、高质量的图表。 Flint 解决了 AI 代理系统中的一个关键瓶颈：简单但低质量图表与冗长但不可靠规范之间的权衡。通过提供确定性编译层，它使基于 LLM 的代理能够生成更可靠且视觉上美观的数据可视化，这是人-代理交互向前迈出的一步。 Flint 作为开源项目提供，并包含一个 MCP（模型上下文协议）服务器，便于集成到代理应用中。它为微软的 Data Formulator 项目提供支持，其设计侧重于使用语义类型（如“分类”、“定量”）来抽象底层可视化决策。

hackernews · chenglong-hn · 7月8日 17:46 · [社区讨论](https://news.ycombinator.com/item?id=48834924)

**背景**: 当前的可视化语言（如 Vega-Lite、matplotlib）要么需要简单但低质量的图表规范，要么需要复杂冗长的规范，而 AI 代理难以可靠地生成。中间表示（IR）是编译器用来表示源代码的数据结构，便于优化和转换；Flint 充当图表生成的此类 IR，允许编译器式的优化引擎从高级规范生成精美图表。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Intermediate_representation">Intermediate representation - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Common_Intermediate_Language">Common Intermediate Language - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论反应不一：一些评论称赞 Flint 是在代理系统中巧妙使用中间语言模式，而另一些则质疑其必要性，声称 LLM 已经能用 Python 库（如 matplotlib）生成良好的可视化。少数人指出，Flint 的真正价值在于将空间构图决策从 LLM 转移到确定性布局引擎，尽管有些人认为 LLM 可以原生处理这一问题。

**标签**: `#AI agents`, `#visualization`, `#Microsoft`, `#Flint`, `#chart generation`

---

<a id="item-2"></a>
## [Onboard-CLI：基于 LLM 和 AST 的代码可视化工具](https://github.com/animesh-94/Onboard-CLI) ⭐️ 9.0/10

Onboard-CLI 是一个新的开源命令行工具，它结合了大语言模型（LLM）和抽象语法树（AST）分析，帮助开发者可视化和理解他们的代码库。 该工具弥合了 AI 驱动的代码理解与传统静态分析之间的差距，使开发者无需手动追踪依赖关系就能更轻松地导航复杂代码库。 该工具在 GitHub 上可用，使用 AST 解析代码结构，然后利用 LLM 生成代码部分的自然语言解释或摘要。它专为需要快速上手新项目的开发者设计。

rss · Show HN (self-made tools) · 7月8日 20:09

**背景**: 抽象语法树（AST）是源代码语法结构的树形表示，每个节点代表一个构造，如函数或变量。AST 通常被编译器和静态分析工具用于理解程序结构。Onboard-CLI 将 AST 解析与 LLM 相结合，提供超越简单语法分析的高级代码理解。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Abstract_syntax_tree">Abstract syntax tree</a></li>
<li><a href="https://dev.to/balapriya/abstract-syntax-tree-ast-explained-in-plain-english-1h38">Abstract Syntax Tree (AST) - Explained in Plain English - DEV Community</a></li>

</ul>
</details>

**标签**: `#LLM`, `#AST`, `#code visualization`, `#CLI tool`, `#developer tool`

---

<a id="item-3"></a>
## [Skill-extractor：从编码代理记录中提取可复用技能](https://github.com/surenode-ai/skill-extractor) ⭐️ 9.0/10

Skill-extractor 是一个新发布的 GitHub 开源工具，它能分析编码代理的对话记录并提取可复用的技能模块，旨在帮助开发者从录制的会话中汇编代理能力库。 该工具解决了 AI 代理开发中的一个关键挑战：在不同任务间重用经过验证的工作流程。通过从记录中提取技能，它可能加速代理技能库的创建，减少重复工作并标准化最佳实践。 该工具处理来自编码代理（例如 OpenAI Codex 或类似系统生成的记录）的转录，并识别可重用模式。它集成了现有的代理框架，并以与 Claude 的 Agent Skills 等平台兼容的格式输出技能。

rss · Show HN (self-made tools) · 7月8日 20:03

**背景**: 编码代理是一种能根据自然语言指令自主编写或修改代码的 AI 系统。它们的记录保存了行动和决策的序列。可复用技能是模块化的能力，将特定任务的指令和资源打包，使代理能够利用过去的经验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://metr.org/notes/2026-02-17-exploratory-transcript-analysis-for-estimating-time-savings-from-coding-agents/">Analyzing coding agent transcripts to upper bound productivity gains from AI agents - METR</a></li>
<li><a href="https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview">Agent Skills - Claude Platform Docs</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#skill extraction`, `#GitHub`, `#developer tools`, `#coding agents`

---

<a id="item-4"></a>
## [DuckDB ADBC 扩展实现跨数据库查询](https://github.com/columnar-tech/duckdb-adbc-client) ⭐️ 9.0/10

一个新的开源 DuckDB 扩展 duckdb-adbc-client，允许通过 read_adbc 表函数或 ATTACH 命令，直接从 DuckDB 查询 Snowflake、Databricks、BigQuery、PostgreSQL 以及任何支持 ADBC 驱动程序的数据库。 该扩展极大地简化了分析管道中的数据集成，使 DuckDB 用户无需移动数据即可直接访问和操作多个来源的数据，这对现代 AI 和数据工程工作流至关重要。 该扩展支持对附加的 ADBC 数据库执行 SELECT、INSERT、COPY 和 CTAS（CREATE TABLE AS SELECT）语句，采用 Apache-2.0 许可证，并计划贡献给 Apache Arrow 项目。

rss · Show HN (self-made tools) · 7月8日 19:11

**背景**: DuckDB 是一种进程内、列式存储的 OLAP 数据库，专为分析型查询设计。ADBC（Arrow Database Connectivity）是 Apache Arrow 项目提出的开放标准，为数据库访问提供统一的列式 API，并以 Arrow 格式返回结果集。该扩展利用 ADBC 将 DuckDB 高效连接到多种数据库。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/DuckDB">DuckDB</a></li>
<li><a href="https://arrow.apache.org/docs/format/ADBC.html">ADBC: Arrow Database Connectivity — Apache Arrow v24.0.0</a></li>
<li><a href="https://en.wikipedia.org/wiki/Apache_Arrow">Apache Arrow</a></li>

</ul>
</details>

**标签**: `#DuckDB`, `#ADBC`, `#database`, `#open source`, `#extension`

---

<a id="item-5"></a>
## [基准测试：本地 LLM 需 RAG 才能准确回答，思维链帮助不大](https://www.reddit.com/r/LocalLLaMA/comments/1uqpxgp/can_you_trust_local_models_to_answer_accurately/) ⭐️ 9.0/10

一位开发者对本地 LLM（unsloth Gemma QAT、Apple Intelligence）进行了 7,648 道技术多选题的基准测试，发现没有 RAG 时准确率很低，但搭配 RAG 系统后准确率变得非常高。思维链模式仅提升约 1%准确率，但耗时显著增加。 这为构建本地 AI 应用的开发者提供了实证：要获得可靠的技术答案，RAG 集成至关重要，而思维链模式可能不值得付出延迟代价。该结果验证了将本地 LLM 与精心整理的知识库结合的实际价值。 基准测试使用了 7,648 道由 DeepSeek-V4-Flash 基于 GitHub 文档（Node、Langchain.js、TypeScript、Transformers.js 和 Vue）生成的多选题。RAG 系统从完整知识库中检索最相关文档，而非限制于正确答案集。Apple Intelligence（AFM 2 3b 模型）因上下文仅 4K 限制，只使用前 3 个检索结果，仍取得 86%的准确率。

reddit · r/LocalLLaMA · /u/Spiritual-Market-741 · 7月8日 11:28

**背景**: 检索增强生成（RAG）是一种技术，通过先从外部知识库检索相关文档，再基于这些文档生成答案，从而提升 LLM 的准确性。本地 LLM（如 Google 的 Gemma 4 QAT 系列）运行在用户自己的设备上，通常经过量化以提高效率。DeepSeek-V4-Flash 是一种快速且成本优化的 LLM，在此用于生成测试题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Retrieval-augmented_generation">Retrieval-augmented generation - Wikipedia</a></li>
<li><a href="https://unsloth.ai/docs/models/gemma-4/qat">Gemma 4 QAT | Unsloth Documentation</a></li>
<li><a href="https://deepseeksr1.com/v4-flash/">DeepSeek-V4-Flash | Fast, Low-Cost AI for Real-Time Apps</a></li>

</ul>
</details>

**标签**: `#local LLM`, `#RAG`, `#benchmark`, `#developer tools`, `#AI accuracy`

---

<a id="item-6"></a>
## [开发者将多个模型移植到 GGML，实现本地游戏资产生成管线](https://www.reddit.com/r/LocalLLaMA/comments/1ur1mim/complete_local_model_asset_generation_pipeline/) ⭐️ 9.0/10

一位开发者将 OpenMOSS（文本转语音）、thinksound.cpp（音效生成）和 trellis.cpp（3D 生成）移植到 GGML，为等距 RPG 游戏构建了完整的本地资产生成管线，并集成到 Lemonade SDK 中。 这展示了一个实用的全本地游戏资产生成管线，使用开源 AI 模型，减少了对云服务的依赖，使独立开发者能够离线开发。 该管线支持级联模型调用：通过 Lemonade 中的 stablediffusion.cpp 实现文生图，再通过 Trellis.2 实现图生 3D，外加 TTS 和音效生成，全部在 GGML 上运行，支持 CUDA、Vulkan 和 ROCm。

reddit · r/LocalLLaMA · /u/ilintar · 7月8日 18:42

**背景**: GGML 是一个机器学习张量库，能够在消费级硬件上高效推理大型模型，也是 llama.cpp 等工具的基础。OpenMOSS 是开源 TTS 模型家族，支持语音克隆和生成。Lemonade SDK 集成了多个本地 AI 引擎，用于创意工作流。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GGML">GGML</a></li>
<li><a href="https://github.com/ggml-org/ggml">GitHub - ggml-org/ggml: Tensor library for machine learning</a></li>
<li><a href="https://github.com/ServeurpersoCom/acestep.cpp/tree/master/">GitHub - ServeurpersoCom/acestep.cpp: Portable C++17 ...</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#ggml`, `#asset-generation`, `#game-dev`, `#pipeline`

---

<a id="item-7"></a>
## [字节跳动发布 Seedream 5.0 Pro，支持多语言与编辑](https://seed.bytedance.com/en/seedream5_0_pro) ⭐️ 9.0/10

字节跳动 Seed 团队推出了 Seedream 5.0 Pro，这是一个多模态图像生成模型，支持高密度信息图、交互式编辑、摄影级画质和原生多语言文字生成。该模型可以根据提示词生成十余种语言的文字，并支持通过空间标注和手绘草图进行精准编辑。 该模型解决了 AI 生成图像中长期存在的多语言文字准确渲染和精准编辑难题，对国际化设计、教育和专业内容创作极具实用价值。通过公开链接即可直接使用，降低了开发者和创作者利用先进图像生成能力的门槛。 Seedream 5.0 Pro 原生支持十余种语言（包括中文和英文）的提示词输入和图像内文字生成。它还可以通过空间标注和手绘草图进行编辑，并实现图层分离，同时实现具有自然光影、阴影和皮肤纹理的摄影级渲染。

telegram · zaihuapd · 7月8日 15:11

**背景**: 传统的 AI 图像生成模型在生成图像中的文字时，常常出现文字模糊、拼写错误或难以辨认的问题，尤其是在非英语语言上。多语言视觉文字生成和编辑仍然是活跃的研究领域。Seedream 5.0 Pro 通过将原生多语言文字能力和交互式编辑集成到一个模型中，解决了这些问题，为需要密集型文字图形或迭代设计流程的用户提供了更可控、更专业的输出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://seed.bytedance.com/en/seedream5_0_pro">Seedream 5.0 Pro - seed.bytedance.com</a></li>

</ul>
</details>

**标签**: `#image generation`, `#AI tool`, `#ByteDance`, `#multilingual`, `#editing`

---

<a id="item-8"></a>
## [用户设计技能将 Claude Code 和 AntiGravity 集成到 Codex](https://x.com/zjp1997720/status/2074848847453675754) ⭐️ 9.0/10

一位用户为 OpenAI 的 Codex 创建了两个自定义技能，使其能够以无头模式咨询 Claude Code 以及调用 AntiGravity 作为外部顾问，从而解决 GPT-5.5 在复杂决策中显得“呆板”的问题。 这种多模型集成技术通过利用专用工具增强了 Codex 的推理能力，有望提升复杂任务的表现，并激发 AI 代理生态系统中类似的流程优化。 这两个技能的设计思路是让 Codex 分别独立调研并调用 Claude Code 的无头模式（通过-p 标志）以及 Google 的 AntiGravity 平台，在遇到困难任务时进行咨询。

twitter · zjp1997720 · 7月8日 13:31

**背景**: OpenAI 的 Codex 支持用户自定义技能（skills），可通过显式或隐式方式调用以扩展其能力。Claude Code 的无头模式使用-p 标志以非交互方式运行代理。AntiGravity 是 Google 推出的以代理优先的集成开发环境，集成了自主 AI 代理用于代码生成和验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developers.openai.com/codex/skills">Agent Skills – Codex | OpenAI Developers</a></li>
<li><a href="https://antigravity.google/">Google Antigravity</a></li>
<li><a href="https://code.claude.com/docs/en/headless">Run Claude Code programmatically - Claude Code Docs</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Codex`, `#Claude Code`, `#workflow optimization`, `#multi-model integration`

---

<a id="item-9"></a>
## [新 AI 技能可制作高质量可编辑 PPT](https://x.com/zjp1997720/status/2074721821174456531) ⭐️ 9.0/10

一位 X（原 Twitter）用户推荐了一种新的“PPT 技能”，声称可以生成视觉丰富、完全可编辑的 PowerPoint 演示文稿，性能优于 PPT Master 等现有工具。 该技能可以显著提高专业人士和学生的生产力，通过 AI 辅助创建可完整编辑的演示幻灯片，弥合 AI 生成与手动精修之间的差距。 该技能基于 PptxGenJS（Node.js）构建，支持原生 OMML 数学公式、LaTeX 图片、Graphviz/Mermaid/TikZ 图表以及五种颜色主题，适用于学术和商务演示。

twitter · zjp1997720 · 7月8日 05:06

**背景**: 自定义“技能”是可重用的指令，用于指导 AI 编程助手（如 Codex、Claude Code 或 OpenClaw）执行特定任务。在此上下文中，PPT 技能指示 AI 通过代码生成.pptx 文件，确保输出在 PowerPoint 中可编辑。推荐的技能似乎是早期工具（如 PPT Master）常见问题的改进版本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Noi1r/powerpoint-skill">GitHub - Noi1r/powerpoint-skill: AI coding assistant skill ...</a></li>
<li><a href="https://github.com/ningzimu/codex-ppt-skill/blob/main/README.md">codex-ppt-skill/README.md at main · ningzimu/codex-ppt-skill</a></li>
<li><a href="https://slidespeak.co/blog/agent-skills-presentations-powerpoint-ai">Best AI Agent Skills for Creating Presentations in 2026</a></li>

</ul>
</details>

**标签**: `#PPT`, `#AI工具`, `#自动化`, `#办公效率`, `#干货`

---

<a id="item-10"></a>
## [Lazy Codex 插件通过子代理增强 Codex](https://x.com/zjp1997720/status/2074833298631930009) ⭐️ 9.0/10

一位推特用户推荐 Lazy Codex 插件，该插件通过提示词注入，让 Codex 自动将复杂任务委派给子代理，从而增强 Codex 处理多步骤工作流的能力。 该插件通过利用子代理，使 Codex 更加自主，能够处理更大、更复杂的代码库任务，减少了对人工监督的需求，实现了更高效的 AI 代理工作流程。 该插件在 GitHub 和官方网站上可用，它在 Codex 内部安装 OmO 代理框架，提供项目记忆、规划、并行代理、技能、钩子、路由和已验证的完成，该方法通过提示词注入来提醒 Codex 使用子代理。

twitter · zjp1997720 · 7月8日 12:29

**背景**: Codex 是一个代码生成 AI 模型，可以执行任务，但通常缺乏处理复杂多步骤项目的自主性。子代理是专门的 AI 代理，可以委派特定任务，而 Lazy Codex 插件通过一个框架在 Codex 内部编排它们。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/code-yeongyu/lazycodex">GitHub - code-yeongyu/lazycodex: The one and only agent ...</a></li>
<li><a href="https://lazycodex.ai/">LazyCodex — Codex agent harness for complex codebases</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Codex`, `#subagents`, `#tool recommendation`, `#plugin`

---

<a id="item-11"></a>
## [用户展示高可玩性 PPT 技能，计划开源](https://x.com/zjp1997720/status/2074765327574172040) ⭐️ 9.0/10

一位用户兴奋地分享了一个高可玩性的 PPT 技能，可用于设计品牌主题模板，并宣布将在企业培训后开源该模板设计技能。 这凸显了 AI 驱动演示设计工具的增长趋势，使非设计人员也能进行专业级定制。开源的承诺可能使开发人员在此基础上进行构建，促进模板创作的创新。 该 PPT 技能可能基于 ChatGPT for PowerPoint 或类似的 AI 扩展，可直接在 PowerPoint 内进行模板设计。用户计划在企业培训中使用后开源该技能。

twitter · zjp1997720 · 7月8日 07:59

**背景**: ChatGPT for PowerPoint 是微软批准的 AI 助手，作为 PowerPoint 内的侧边栏运行，帮助用户创建、编辑和完善演示文稿，同时保留可编辑的幻灯片结构。可以在此基础上构建自定义 GPT 或技能来自动执行特定任务，如模板设计。用户的技能似乎是一个自定义配置，用于简化品牌模板创建。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://help.openai.com/en/articles/20001242-chatgpt-for-powerpoint">ChatGPT for PowerPoint - OpenAI Help Center</a></li>
<li><a href="https://chatgpt.com/apps/powerpoint/">ChatGPT for PowerPoint | Create and edit presentations with ...</a></li>

</ul>
</details>

**标签**: `#PPT技能`, `#AI工具`, `#模板设计`, `#开源`

---

<a id="item-12"></a>
## [GitLost：通过提示注入攻击泄露 GitHub 私有仓库的 AI 代理](https://noma.security/blog/gitlost-how-we-tricked-githubs-ai-agent-into-leaking-private-repos/) ⭐️ 8.0/10

Noma Security 的研究人员演示了对 GitHub AI 代理的提示注入攻击，通过在公共问题或评论中嵌入恶意指令，诱使其泄露私有仓库中的数据。 此攻击突显了自主 AI 系统中系统性的漏洞类别，类似于 Web 应用中的 SQL 注入，并强调了在基于 LLM 的代理中建立强大安全边界的紧迫性。 该攻击使用像“Additionally”这样的简单提示前缀绕过 GitHub 的防护，表明任何在 LLM 上下文窗口内强制硬性安全性的尝试本质上都存在缺陷。该漏洞已负责任地披露给 GitHub，但披露时间线未确认是否已修复。

hackernews · ColinEberhardt · 7月8日 05:25 · [社区讨论](https://news.ycombinator.com/item?id=48827858)

**背景**: 提示注入是一种网络安全利用方式，攻击者通过构造输入，利用 LLM 无法区分开发者定义的指令和用户提供内容的弱点，导致模型产生意外行为。在此案例中，能够访问私有仓库的 GitHub AI 代理通过公共仓库讨论中的间接提示注入被欺骗。随着 AI 代理获得网页浏览和文件访问等能力，可信指令与不可信数据之间的界限变得模糊，这一攻击向量变得日益关键。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Prompt_injection_attack">Prompt injection attack</a></li>
<li><a href="https://github.blog/ai-and-ml/github-copilot/how-githubs-agentic-security-principles-make-our-ai-agents-as-secure-as-possible/">How GitHub's agentic security principles make our AI agents ...</a></li>

</ul>
</details>

**社区讨论**: 评论者将提示注入比作 SQL 注入，指出这是一种系统性的漏洞，需要系统性的防御。有人认为该攻击并非 GitHub 的过错，因为代理被授予了私有仓库的访问权限，而另一些人则强调在当前 LLM 架构中此类利用是不可避免的。

**标签**: `#AI security`, `#prompt injection`, `#GitHub`, `#agent vulnerabilities`, `#LLM risks`

---

<a id="item-13"></a>
## [Nully：使用 OpenRouter 的极简开源 AI 聊天界面](https://nully.chat/) ⭐️ 8.0/10

Nully 是一款新发布的开源 AI 聊天界面，使用 Go 和原生 HTML/CSS/JS 构建，专注于简洁与性能。它通过 OpenRouter 发送消息，并将聊天记录存储在本地，避免了主流 AI 服务的臃肿。 它为只需要基本 AI 聊天功能而无需高级特性（如代理模式或图像生成）的用户提供了一个轻量级、注重隐私的替代方案。作为开源且可自托管的软件，Nully 让用户完全掌控自己的数据，并减少对功能臃肿平台的依赖。 Nully 使用 Go 和原生 HTML/CSS/JS 编写，支持通过 OpenRouter API 发送附件和进行基础网络搜索。它无账户、无订阅，支持将聊天导出为 JSON 格式；所有数据均保留在用户本地设备上。

rss · Show HN (self-made tools) · 7月8日 20:25

**背景**: OpenRouter 是一个统一 API，提供对来自不同提供商的多种 AI 模型的访问，简化了集成过程。Nully 利用该 API 处理消息路由，因此用户无需为每个提供商分别申请 API 密钥或账号，即可与多种文本模型交互。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openrouter.ai/docs/api/reference/overview">OpenRouter API Reference - Complete Documentation</a></li>

</ul>
</details>

**标签**: `#AI chat`, `#OpenRouter`, `#FOSS`, `#minimal UI`, `#self-hosted`

---

<a id="item-14"></a>
## [NVIDIA 与 Hugging Face 推出 AI 智能体开放数据计划](https://huggingface.co/blog/nvidia/open-data-for-agents) ⭐️ 8.0/10

NVIDIA 与 Hugging Face 推出了一项开放数据计划，提供精选数据集和资源，用于训练和评估 AI 智能体。该博客重点介绍了用于工具调用、网络导航和编码基准的实用数据集。 该计划解决了构建可靠 AI 智能体对结构化高质量数据的关键需求，而 AI 智能体在自主系统中正变得至关重要。开发者现在可以访问标准化数据集，加速智能体开发，并推动行业基准测试。 这些数据集涵盖工具调用、网络交互和多步规划，包括 SWE-bench 和 WebArena 等基准。资源在 Hugging Face 上开放获取，便于微调和评估。

rss · Hugging Face Blog · 7月8日 17:16

**背景**: AI 智能体是自主软件实体，能够感知环境并采取行动以实现目标。训练它们需要大量结构化数据，这些数据教会它们工具使用和网络导航等行为。像这样的开放数据计划通过提供标准化基准和数据集，有助于推动智能体开发的民主化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opendatascience.com/15-datasets-for-training-and-evaluating-ai-agents/">15 Datasets for Training and Evaluating AI Agents</a></li>
<li><a href="https://odsc.medium.com/15-datasets-for-training-and-evaluating-ai-agents-c171dde4e0ce">15 Datasets for Training and Evaluating AI Agents | by ODSC ...</a></li>
<li><a href="https://www.analyticsvidhya.com/blog/2025/02/open-source-datasets-for-generative-and-agentic-ai/">20 Open-Source Datasets for Generative and Agentic AI Datasets for Training and Fine-tuning | jim-schwoebel/awesome ... Khang-9966/Computer-Browser-Phone-Use-Agent-Datasets - GitHub 20 Open-Source Datasets for Generative AI and Agentic AI 50+ Best AI Model Training Datasets for 2026: Free & Premium</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#datasets`, `#open data`, `#agent frameworks`

---

<a id="item-15"></a>
## [Hugging Face Transformers 原生速度 vLLM 后端](https://huggingface.co/blog/native-speed-vllm-transformers-backend) ⭐️ 8.0/10

Hugging Face 宣布为 Transformers 推出一个新的原生速度推理后端，集成了 vLLM，只需极少代码更改即可实现高达 2 倍的 LLM 推理加速。 这一整合弥合了 Hugging Face Transformers 的易用性与 vLLM 的高性能之间的差距，使最先进的推理优化对更广泛的用户群体触手可及。 该后端利用 vLLM 的 PagedAttention 和 continuous batching 来加速支持模型的推理，并与标准 Transformers API 无缝配合。

rss · Hugging Face Blog · 7月8日 00:00

**背景**: Hugging Face Transformers 是一个广泛使用的自然语言处理库，但其默认推理后端在处理大型语言模型时速度较慢。vLLM 是一个高吞吐推理引擎，采用先进的内存管理和批处理技术。这个新后端将两者结合，使用户无需离开 Transformers 生态系统即可获得 vLLM 的速度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.vllm.ai/en/latest/configuration/optimization/">Optimization and Tuning - vLLM</a></li>
<li><a href="https://docs.vllm.ai/">vLLM</a></li>

</ul>
</details>

**标签**: `#LLM`, `#inference`, `#vLLM`, `#Hugging Face`, `#performance`

---