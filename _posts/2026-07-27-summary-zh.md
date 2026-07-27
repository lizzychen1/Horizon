---
layout: default
title: "Horizon Summary: 2026-07-27 (ZH)"
date: 2026-07-27
lang: zh
---

> 从 65 条内容中筛选出 10 条重要资讯。

---

1. [Scout：通过 OpenAPI 规范理解企业平台的本地工具](#item-1) ⭐️ 9.0/10
2. [Graph Skill：用依赖图执行任务的编码代理](#item-2) ⭐️ 9.0/10
3. [Kimi K3 开源模型部署于多种 GPU](#item-3) ⭐️ 9.0/10
4. [Nifer 推理引擎在 RTX 5090 上实现 Qwen 3.6 每秒 700 token](#item-4) ⭐️ 9.0/10
5. [阿里巴巴推出'千问办公'AI 平台，支持 PPT、表格和电脑操控](#item-5) ⭐️ 9.0/10
6. [升级版 codex-model-routing-team 双路径路由器](#item-6) ⭐️ 9.0/10
7. [browser-use v0.13.7 发布，包含多项错误修复](#item-7) ⭐️ 7.0/10
8. [有主见的 AI 指南凸显智能体系统转变](#item-8) ⭐️ 7.0/10
9. [Lorraine：开源笔记工具，支持说话人识别](#item-9) ⭐️ 7.0/10
10. [Openvisor：一款面向 OpenCode 的本地优先会话浏览器](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Scout：通过 OpenAPI 规范理解企业平台的本地工具](https://github.com/prabhuavula7/scout) ⭐️ 9.0/10

Scout 是一款新发布的本地工具，通过摄入 OpenAPI 规范和文档，构建对企业平台的深入理解，提供架构图、入门代码、线程化 AI 聊天以及用于编码代理的 MCP 服务器。 这很重要，因为编码代理经常虚构端点；Scout 将其基于实际的 OpenAPI 规范，减少错误。它本地运行，无需账户，对开发者使用 AI 代理时既隐私又方便。 Scout 通过 npm 安装（`npm i -g @dotapk7/scoutcli`），采用 MIT 许可证，无需托管后端。它使用 OpenAPI 作为真实依据，防止代理虚构不存在的 API 端点。

rss · Show HN (self-made tools) · 7月27日 20:56

**背景**: OpenAPI 规范是描述 RESTful API 的标准，使工具能够生成文档、客户端 SDK 和服务器存根。模型上下文协议（MCP）是 Anthropic 推出的开放标准，规范了 LLM 等 AI 系统与外部工具和数据的集成方式。Scout 利用两者为 AI 编码代理提供对企业平台的准确理解。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/MCP_server">MCP server</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#OpenAPI`, `#MCP server`, `#developer tools`, `#GitHub repo`

---

<a id="item-2"></a>
## [Graph Skill：用依赖图执行任务的编码代理](https://github.com/gwaghmar/graph) ⭐️ 9.0/10

Graph Skill 是一个新的开源 GitHub 项目，它允许编码代理将任务结构化为依赖图并执行，从而将复杂工作流分解为有序的子任务。 这种方法通过确保任务按照依赖关系按正确顺序执行，提高了 AI 驱动代码生成中的可靠性和可追溯性，这是当前编码代理面临的一个关键挑战。 该项目托管在 GitHub 上的 github.com/gwaghmar/graph，旨在与现有的编码代理框架集成。

rss · Show HN (self-made tools) · 7月27日 19:52

**背景**: 编码代理是能够从高级指令自主规划、编写、测试和修改代码的 AI 系统。依赖图（通常是有向无环图）将任务表示为节点，将约束表示为边，确保任务只有在其前提条件满足后才能执行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cloud.google.com/discover/what-is-agentic-coding">What is agentic coding? How it works and use cases</a></li>
<li><a href="https://arstechnica.com/information-technology/2025/12/how-do-ai-coding-agents-work-we-look-under-the-hood/">How AI coding agents work—and what to remember if you use them</a></li>
<li><a href="https://engineersofai.com/docs/agentic-ai/long-horizon-planning/task-decomposition">01 - Task Decomposition | EngineersOfAI - Technical Education for AI...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#dependency graph`, `#GitHub`, `#agent framework`

---

<a id="item-3"></a>
## [Kimi K3 开源模型部署于多种 GPU](https://www.reddit.com/r/LocalLLaMA/comments/1v81qw0/kimi_k3_weights_drop_today_were_deploying_on/) ⭐️ 9.0/10

Kimi K3，一个拥有 2.8 万亿参数的 MoE 模型，采用 MXFP4 量化，于 2025 年 7 月 27 日以开源权重形式发布在 Hugging Face 上。公司 qubridInc 宣布计划在 A100、H200 和 B300 GPU 上部署该模型，其中 A100 和 H200 配置的内存需求超过单节点容量。 此次发布意义重大，因为它提供了一个具有原生视觉能力和 1M 上下文窗口的先进 2.8T MoE 模型，使开发者能够针对自己的数据进行微调和定制。部署分析为在当前和下一代硬件上运行超大规模模型提供了实际基准，有助于权衡成本与性能。 该模型使用 896 个专家，每个 token 激活 16 个专家，MXFP4 格式下需要约 1.4 TB 存储空间。在 8x A100（640 GB）上，需要三个节点才能容纳模型，且 Ampere 架构缺乏 FP4/FP8 张量核心，推理效率低下；8x H200（1.13 TB）勉强跨两个节点运行；只有 8x B300（2.3 TB）能在单节点内容纳模型并留出长上下文空间。

reddit · r/LocalLLaMA · /u/qubridInc · 7月27日 14:18

**背景**: Kimi K3 是一个混合专家（MoE）模型，总参数量达 2.8 万亿，但每个 token 仅激活部分参数，从而平衡了容量与计算成本。MXFP4 是一种 4 位浮点量化格式，能大幅减小模型体积，但需要硬件支持才能高效推理。B300 GPU 基于 NVIDIA 的 Blackwell 架构，提供 288 GB HBM3e 显存和原生 FP4 张量核心，非常适合运行该模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/moonshotai/Kimi-K3">moonshotai/Kimi-K3 - Hugging Face</a></li>
<li><a href="https://platform.kimi.ai/docs/guide/kimi-k3-quickstart">Kimi K3 - Kimi API Platform</a></li>
<li><a href="https://pantheon.run/learn/nvidia-hgx-b300-specs">NVIDIA HGX B 300 Specs & Datasheet (8- GPU Node) | Pantheon</a></li>

</ul>
</details>

**社区讨论**: 评论指出托管一个 3T MoE 模型成本不低，第三方提供商的价格将揭示服务成本。用户强调了开源权重对定制和数据主权的重要性，但有一位用户报告模型错误地自称为 Claude。许可证要求年收入超过 2000 万美元的提供商需签订商业协议。

**标签**: `#Kimi K3`, `#MoE`, `#model deployment`, `#quantization`, `#GPU memory`

---

<a id="item-4"></a>
## [Nifer 推理引擎在 RTX 5090 上实现 Qwen 3.6 每秒 700 token](https://www.reddit.com/r/LocalLLaMA/comments/1v8a7wb/nifer_is_insane_700ts_with_qwen_36_35b_no/) ⭐️ 9.0/10

一款名为 ninfer（或 Nifer）的全新定制推理引擎，在单张 RTX 5090 GPU 上，对 Qwen 3.6 35B 和 27B 模型实现了每秒 550-720 token 的推理速度，并支持完整的 25 万上下文长度和无思考模式。 这一性能可与 Cerebras 硬件相媲美，表明通过优化软件，在消费级 GPU 上也能实现极快的本地推理，从而可能赋能实时应用并减少对云 API 的依赖。 该引擎使用 C++和 CUDA 从头编写，专为 RTX 5090 的 Blackwell 架构调优，目前仅支持两个特定的 Qwen 3.6 检查点。GitHub 仓库位于 https://github.com/Neroued/ninfer，在 Windows 上构建需要额外工具。

reddit · r/LocalLLaMA · /u/BringTea_666 · 7月27日 19:17

**背景**: 本地 LLM 推理在消费级 GPU 上通常只能达到每秒几十到几百 token，例如 Ollama 在 RTX 5090 上对 Gemma 4 的推理速度约为 87 t/s。Nifer 的 700 t/s 是通过极低阶优化实现的巨大提升，包括自定义内核以及利用 NVFP4 和投机解码等硬件特定特性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Neroued/ninfer">GitHub - Neroued/ ninfer : High-performance single-GPU inference for...</a></li>
<li><a href="https://github.com/avifenesh/bw24">avifenesh/bw24: From-scratch Rust+CUDA LLM inference engine for ...</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#inference-engine`, `#RTX5090`, `#qwen`, `#speed-optimization`

---

<a id="item-5"></a>
## [阿里巴巴推出'千问办公'AI 平台，支持 PPT、表格和电脑操控](https://qwenwork.cn/) ⭐️ 9.0/10

阿里巴巴推出了千问办公的 Beta 版，这是一个 AI 办公平台，支持网页、Windows 和 macOS 客户端，并接入钉钉。用户可以通过自然语言生成和编辑文档、PPT、表格、网页、代码及多媒体内容，桌面端还能通过浏览器自动化和 Computer Use 功能操控电脑。 此举使阿里巴巴在竞争激烈的 AI 办公工具市场中占据一席之地，免费版降低了用户体验 AI 辅助生产力的门槛。电脑操控能力类似于新兴的 AI 代理，可能改变用户与桌面应用的交互方式。 定价包括免费版、标准版（78 元/月，2000 积分）和高级版（158 元/月，4000 积分），新用户限时获赠 2000 积分，有效期 90 天。桌面端要求 macOS 14 以上或 64 位 Windows 10 以上系统，部分功能仍标注'敬请期待'。

telegram · zaihuapd · 7月27日 05:45

**背景**: AI 驱动的办公工具如 Microsoft 365 Copilot 和 Google 的 Gemini 已将生成式 AI 集成到生产力套件中。Computer Use AI 由 Claude 等模型推广，允许 AI 直接控制电脑界面以实现任务自动化。千问办公基于阿里巴巴的通义千问大语言模型构建。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.youtube.com/watch?v=7TtuiNnhwmM">How to Install and Use Claude Computer Use : NEW Claude AI Model</a></li>
<li><a href="https://cn121.com/taizmzzczznb-dmtsjck-smsrh-phdnwgxz-kyyqzdzh-mfed-dysj.html">TuriX｜ AI ...</a></li>

</ul>
</details>

**标签**: `#AI办公`, `#千问办公`, `#阿里巴巴`, `#电脑操控`, `#免费AI工具`

---

<a id="item-6"></a>
## [升级版 codex-model-routing-team 双路径路由器](https://x.com/zjp1997720/status/2081676148040454262) ⭐️ 9.0/10

用户将开源的 codex-model-routing-team 升级为双路径路由器，支持原生 Subagent 和独立工作流两种模式，底层已支持给子任务指定模型和推理强度。 这一升级为多智能体系统开发者提供了灵活的子任务路由选择，通过原生 Subagent 和独立工作流两种路径，可分别优化快速并行执行和深度隔离场景，提升效率和降低成本。 原生 Subagent 启动快、结果直接返回主任务，适合短时边界清晰的并行工作；独立工作流则提供完全隔离环境。该路由器利用了 Codex Multi-Agent V2 的上下文传递机制。

twitter · zjp1997720 · 7月27日 09:40

**背景**: Codex 是一个开源的多智能体编码系统，父智能体可以生成子智能体（Subagent）作为独立线程运行。Multi-Agent V2 版本新增了为子任务指定模型和推理强度的能力。双路径路由器在此基础上提供两种路由选择：原生 Subagent（快速并行执行）和独立工作流（完全隔离的复杂操作）。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gist.github.com/serialx/f842f7b41d0f74ff5f64845e4afbc260">Codex Multi - Agent System Architecture · GitHub</a></li>
<li><a href="https://cloud.google.com/blog/topics/developers-practitioners/where-to-use-sub-agents-versus-agents-as-tools/">Where to use sub-agents versus agents as tools | Google Cloud Blog</a></li>
<li><a href="https://addyosmani.com/blog/code-agent-orchestra/">AddyOsmani.com - The Code Agent Orchestra - what makes multi-agent coding work</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#multi-agent`, `#codex`, `#routing`, `#open-source`

---

<a id="item-7"></a>
## [browser-use v0.13.7 发布，包含多项错误修复](https://github.com/browser-use/browser-use/releases/tag/0.13.7) ⭐️ 7.0/10

browser-use 版本 0.13.7 已发布，包含多项错误修复，例如不在 Gemini genconfig 中发送默认参数、处理 file:// URL、改进 React 受控输入处理，以及通过 CLI 实现更好的浏览器管理。 此更新提高了 browser-use AI 代理框架的稳定性和兼容性，该框架广泛用于通过 LLM 自动化浏览器任务。修复增强了跨域 iframe 处理和 DOM 状态管理的可靠性，使构建稳健 AI 代理的开发人员受益。 值得注意的技术修复包括限制 DOM 扇出以保留可恢复状态、保持选择器索引在 CDP 会话中的唯一性，以及在浏览器状态超时后停止重用缓存的 DOM。该版本还包含 Browser Harness 0.1.8。

github · laithrw · 7月27日 17:10

**背景**: browser-use 是一个开源框架，允许 AI 代理（例如由 Gemini 等 LLM 驱动的代理）以编程方式控制 Web 浏览器。它提供 CLI 并与浏览器自动化工具集成，用于执行网页抓取、表单填写和测试等任务。该项目使用 Chrome DevTools Protocol (CDP) 进行浏览器交互，并支持跨域 iframe 提取。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://geminicli.com/docs/cli/generation-settings/">Advanced Model Configuration | Gemini CLI</a></li>
<li><a href="https://stackoverflow.com/questions/42550341/react-trigger-onchange-if-input-value-is-changing-by-state">javascript - React: trigger onChange if input value is... - Stack Overflow</a></li>

</ul>
</details>

**标签**: `#browser-use`, `#AI agent`, `#browser automation`, `#CLI`

---

<a id="item-8"></a>
## [有主见的 AI 指南凸显智能体系统转变](https://simonwillison.net/2026/Jul/27/an-opinionated-guide-to-which-ai-to-use-to-do-stuff/#atom-everything) ⭐️ 7.0/10

Ethan Mollick 的 AI 使用指南现在更强调智能体系统而非简单聊天，比较了 ChatGPT Work、Claude Cowork 和 Codex 等模式。Gemini 已从列表中移除，因为 Gemini Spark 尚未证明自己。 这一转变反映了 AI 从对话工具迅速演进为能够完成数小时人类工作的自主智能体，引导从业者选择当前最强大的方案。同时也凸显了用户必须应对的混乱命名惯例。 该指南解释说，ChatGPT Work 和 Claude Cowork 让 AI 访问用户的计算机，移动端 ChatGPT Work 模式与桌面版不同，后者允许 Code Interpreter 容器访问互联网。Codex 和 Code 模式提供类似功能但命名不同。

rss · Simon Willison · 7月27日 21:55

**背景**: 智能体系统是能够自主执行复杂多步骤任务的 AI 模型，通常通过访问外部工具或用户计算机来实现。ChatGPT 和 Claude 分别来自 OpenAI 和 Anthropic，是领先的聊天机器人，各自提供专门的智能体使用模式。Gemini 是 Google 的对应产品，但其智能体产品 Gemini Spark 尚未广泛可用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Gemini_Spark">Gemini Spark</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_Opus">Claude Opus</a></li>
<li><a href="https://grokipedia.com/page/Codex_OpenAI">Codex (OpenAI)</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#agentic AI`, `#ChatGPT`, `#Claude`, `#model comparison`

---

<a id="item-9"></a>
## [Lorraine：开源笔记工具，支持说话人识别](https://github.com/trezm/lorraine) ⭐️ 7.0/10

Lorraine 是一款开源笔记应用，通过说话人识别技术将笔记内容归因到不同说话者，现已上线 GitHub。 该工具回应了闭源笔记应用可能滥用数据的隐私担忧，提供了一个透明且具备 AI 说话人归因能力的替代方案。 该项目受一条 Twitter 帖子启发，该帖子警告免费闭源笔记应用常利用用户数据盈利；Lorraine 旨在保护用户数据隐私。

rss · Show HN (self-made tools) · 7月27日 19:44

**背景**: 说话人识别是通过语音特征识别个体的技术。许多会议笔记工具（如 Fathom AI）为闭源，引发数据隐私担忧。Lorraine 等开源替代品让用户掌握数据控制权。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Speaker_recognition">Speaker recognition - Wikipedia</a></li>
<li><a href="https://www.fathom.ai/">Fathom AI Notetaker - Never Take Notes Again</a></li>

</ul>
</details>

**标签**: `#open source`, `#note-taking`, `#speaker recognition`, `#AI tool`

---

<a id="item-10"></a>
## [Openvisor：一款面向 OpenCode 的本地优先会话浏览器](https://openvisor.vercel.app/) ⭐️ 7.0/10

Openvisor 是一款全新的本地优先会话浏览器，专为 OpenCode AI 代理会话设计，受 LangSmith 追踪功能启发，能将导入的会话 JSON 存储在浏览器的 IndexedDB 中，并允许用户深入检查每一轮交互、工具调用及子代理使用情况。 Openvisor 为 OpenCode 用户带来了关键的观测能力，使他们无需将数据发送到外部服务器就能调试和分析代理行为，这对于 AI 辅助开发中的信任和隐私至关重要。 该工具完全在浏览器中运行；导入导出的 OpenCode 会话 JSON 后，数据仅存储在本地 IndexedDB 中，不会离开本机。它附带了一个示例会话供测试，并计划未来支持 Claude Code。

rss · Show HN (self-made tools) · 7月27日 19:08

**背景**: OpenCode 是一个开源的 AI 编码代理，运行在终端中，让开发者借助 AI 辅助编写代码。调试代理会话通常需要检查每一步，但 OpenCode 缺少内置的详细追踪功能。像 LangSmith 这样的工具为 LangChain 应用提供追踪，但不原生支持 OpenCode。Openvisor 通过提供本地优先的会话浏览器来填补这一空白。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opencode.ai/">OpenCode | The open source AI coding agent</a></li>
<li><a href="https://docs.langchain.com/langsmith/observability-quickstart">Add LangSmith tracing to an LLM application in minutes.</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#session explorer`, `#Opencode`, `#local-first`, `#developer tools`

---