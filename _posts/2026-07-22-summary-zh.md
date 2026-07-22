---
layout: default
title: "Horizon Summary: 2026-07-22 (ZH)"
date: 2026-07-22
lang: zh
---

> 从 71 条内容中筛选出 15 条重要资讯。

---

1. [Bento：一个 HTML 文件搞定完整 PPT（离线、协作、可编辑）](#item-1) ⭐️ 9.0/10
2. [微软发布 Fara1.5-27B：多模态网页代理](#item-2) ⭐️ 9.0/10
3. [Cactus Hybrid 让 Gemma 4 输出置信度分数](#item-3) ⭐️ 9.0/10
4. [开源技能让 WorkBuddy 一键切换 GPT、Grok、Gemini](#item-4) ⭐️ 9.0/10
5. [Gemini 3.6 Flash 在 codex 和 WorkBuddy 中速度惊人](#item-5) ⭐️ 9.0/10
6. [「智见 Skills」开源 AI 技能合集介绍](#item-6) ⭐️ 9.0/10
7. [Show HN：将安卓模拟器流式传输到浏览器供 AI 代理使用](#item-7) ⭐️ 8.0/10
8. [TrustLoop：AI 代理审批工作流与策略检查](#item-8) ⭐️ 8.0/10
9. [The Daily FM 将任何来源转化为个性化每日播客](#item-9) ⭐️ 8.0/10
10. [ClawLite：Telegram 上的本地优先 AI 助手](#item-10) ⭐️ 8.0/10
11. [粘贴职位描述，立刻得到一个破损的 Kubernetes 集群来修复](#item-11) ⭐️ 8.0/10
12. [奥地利推出基于 Mistral 模型和 Open WebUI 的 GovGPT 平台](#item-12) ⭐️ 8.0/10
13. [Claude Code 新增 iOS 模拟器支持](#item-13) ⭐️ 8.0/10
14. [四大 AI 编程代理曝沙箱逃逸漏洞](#item-14) ⭐️ 8.0/10
15. [Claude 推出“教授技能”功能，可录制操作复用](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Bento：一个 HTML 文件搞定完整 PPT（离线、协作、可编辑）](https://bento.page/slides/) ⭐️ 9.0/10

Bento 是一个独立的 HTML 文件，提供了完整的演示工具功能，包括编辑、查看、动画和实时协作，完全离线运行，无需安装或云登录。 这种方法挑战了传统的演示软件，提供了一种便携、零依赖的替代方案，可轻松与 Claude 或 ChatGPT 等 AI 工具编辑，可能改变幻灯片的创建和分发方式。 默认文件约 560KB，使用 base64 编码的 blob 配合 DecompressionStream 压缩，并包含加密盲中继（blind relay）支持共享编辑，中继无法看到任何数据。

hackernews · starfallg · 7月22日 15:19 · [社区讨论](https://news.ycombinator.com/item?id=49008211)

**背景**: 单 HTML 文件工具将所有代码和资源打包到一个文件中，支持离线使用和便携性。加密盲中继是一种密码学技术，服务器在不解密内容的情况下促进通信，保护隐私。Reveal.js 是一个流行的开源 HTML 演示框架，Bento 在此基础上构建。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Blinding_(cryptography)">Blinding (cryptography) - Wikipedia</a></li>
<li><a href="https://dev.to/iamjephter/building-a-blind-relay-in-rust-with-tauri-at-the-edge-57gp">Architecting a Blind Relay: E2EE Clipboard Sync with Rust and Tauri - DEV Community</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_(AI)">Claude (AI) - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 创建者解释了架构并鼓励贡献。用户称赞了这个概念，并指出其他类型软件的潜力。有评论报告称，当大量用户同时编辑留言板时，M1 Mac 会出现卡死，表明在高负载下可能存在限制。

**标签**: `#presentation tool`, `#HTML`, `#offline`, `#collaboration`, `#AI-editable`

---

<a id="item-2"></a>
## [微软发布 Fara1.5-27B：多模态网页代理](https://www.reddit.com/r/LocalLLaMA/comments/1v3ny84/microsoftfara1527b_hugging_face/) ⭐️ 9.0/10

微软发布了 Fara1.5-27B，这是一个多模态计算机使用代理，通过处理截图并发出结构化的工具调用（如点击、输入、滚动、访问 URL）来自动化网页浏览器任务。 Fara1.5-27B 代表了实用 AI 代理在真实网页自动化方面的重要一步，它提供了开源模型，能够端到端地执行多步骤任务，这有望减少重复性在线活动的手动工作量。 该模型在感知阶段仅依赖视觉，不使用 DOM 或无障碍树，它是从 Qwen3.5-27B 通过 FaraGen1.5 多智能体流水线生成的数据进行监督微调而成。已知局限包括易受欺骗性页面渲染影响以及长轨迹中的累积错误。

reddit · r/LocalLLaMA · /u/pmttyji · 7月22日 18:04

**背景**: 计算机使用代理（CUA）是多模态 AI 系统，它们通过解释 GUI 截图并执行操作来自动化软件任务。与依赖 DOM 解析的传统浏览器自动化不同，像 Fara1.5 这样的 CUA 纯粹基于像素级视觉输入，并使用结构化的工具调用来与界面交互，这使得它们更灵活，但也容易受到视觉歧义的影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.emergentmind.com/topics/computer-use-agents-cuas">Computer - Use Agents (CUAs)</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#multimodal`, `#web automation`, `#computer use agent`, `#Microsoft`

---

<a id="item-3"></a>
## [Cactus Hybrid 让 Gemma 4 输出置信度分数](https://www.reddit.com/r/LocalLLaMA/comments/1v3nw3j/cactus_hybrid_we_taught_gemma_4_to_know_when_its/) ⭐️ 9.0/10

Cactus 在 Gemma 4 上通过一个轻量级（6.8 万参数）探针层进行后训练，该探针在解码过程中读取中间隐藏状态以预测 0 到 1 之间的置信度分数。他们已在 HuggingFace 上发布权重，并提供了适用于 Transformers、MLX、llama.cpp 和 Cactus 的可运行代码。 该技术实现了高效的混合 AI 路由，允许开发者在置信度高时接受快速的设备端响应，仅在需要时切换到大型云端模型，从而在大多数基准测试中匹配或超越基线精度的同时，可能将查询成本降低 65-85%。 该探针在 12 个留出基准（文本、视觉、音频）上实现了平均 AUROC 0.814，而 token 熵启发式方法仅为 0.549。该方法目前仅限于单序列解码（最多 1024 个生成 token），且路由在按任务（而非按步骤）应用时效果最佳。

reddit · r/LocalLLaMA · /u/Henrie_the_dreamer · 7月22日 18:01

**背景**: 混合 AI 系统在小型设备端模型和大型云端模型之间路由查询，以平衡速度、隐私和成本。置信度评分对于路由决策至关重要，但现有方法（如让模型自我评估或使用 token 熵）往往不可靠。Cactus 使用机制可解释性技术，从 Gemma 4 的隐藏状态中提取了与模态无关的正确性信号。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/models/gemma/gemma-4/">Gemma 4 is a family of open models , purpose-built for advanced...</a></li>
<li><a href="https://arxiv.org/html/2602.11180v1">Mechanistic Interpretability for Large Language Model Alignment - arXiv</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#model confidence`, `#hybrid AI`, `#Gemma`, `#routing`

---

<a id="item-4"></a>
## [开源技能让 WorkBuddy 一键切换 GPT、Grok、Gemini](https://x.com/zjp1997720/status/2079843010649747678) ⭐️ 9.0/10

开发者 zjp1997720 开源了一个用于腾讯 WorkBuddy AI 助手的技能，使用户能够一键轻松切换 GPT、Grok 和 Gemini 模型，解决了高阶模型积分消耗快的问题。 该技能显著降低了需要使用不同 AI 模型的 WorkBuddy 用户的积分消耗，为成本管理提供了实用解决方案，同时保持了灵活性。它也展示了 AI 助手开源扩展生态系统的成长。 该技能是开发者在培训经历中遇到高积分消耗（一次消耗三四千积分）后创建的。它允许在 WorkBuddy 内部无缝切换 GPT、Grok 和 Gemini 模型。

twitter · zjp1997720 · 7月22日 08:16

**背景**: WorkBuddy 是腾讯云开发的 AI 原生助手，旨在通过自然语言指令处理复杂的办公任务。它使用基于积分的系统，高级 AI 模型（如 GPT-4、Grok、Gemini）消耗积分很快。Grok 是 xAI 开发的聊天机器人模型，Grok 3 号称是'地球上最聪明的 AI'。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.tencentcloud.com/act/pro/workbuddy">WorkBuddy · Your scenario-based AI all-in-one package - Tencent Cloud</a></li>
<li><a href="https://en.wikipedia.org/wiki/Grok_(chatbot)">Grok (chatbot) - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#WorkBuddy`, `#multi-model`, `#open source`, `#skill`

---

<a id="item-5"></a>
## [Gemini 3.6 Flash 在 codex 和 WorkBuddy 中速度惊人](https://x.com/zjp1997720/status/2079885809440727454) ⭐️ 9.0/10

用户报告称，在 AI 编程工具 codex 和 WorkBuddy 中使用 Google 的 Gemini 3.6 Flash 模型时，几乎能瞬间生成完整网页，吞吐量接近每秒 300 个 token。模型完成调研后，网页立即出现，调研完成到页面生成之间仅有一两秒延迟。 这一亲身经历凸显了 Gemini 3.6 Flash 卓越的速度和实时能力，使其非常适合需要快速迭代的实际编程工作流。这样的性能可能显著提升开发者的生产力，并为 AI 辅助代码生成树立新的标杆。 该模型实现了接近每秒 300 个 token 的吞吐量，使得从调研到完成网页的生成近乎瞬间完成。用户在 codex（AI 编程代理）和 WorkBuddy（AI 驱动的办公助手）中都配置了 Gemini 3.6 Flash，强调了其无缝集成能力。

twitter · zjp1997720 · 7月22日 11:06

**背景**: Gemini 3.6 Flash 是 Google DeepMind 最新推出的轻量级模型，旨在提供高速且成本高效的性能，其推理质量可与更大的 Pro 模型媲美。该模型已通过 Gemini API 发布，开发者可立即使用。codex 指代 OpenAI 的 Codex 或类似 AI 编程代理，帮助编写和调试代码。WorkBuddy 在此处是用于办公任务的 AI 代理，尽管也有同名的现场服务管理软件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/models/gemini/flash/">Gemini 3.6 Flash — Google DeepMind</a></li>
<li><a href="https://ai.google.dev/gemini-api/docs/models/gemini-3.6-flash">Gemini 3.6 Flash | Gemini API | Google AI for Developers</a></li>
<li><a href="https://www.stork.ai/en/codex">Codex Review (2026): Pricing & Alternatives | Stork. AI</a></li>

</ul>
</details>

**标签**: `#Gemini 3.6 Flash`, `#codex`, `#WorkBuddy`, `#AI model`, `#workflow`

---

<a id="item-6"></a>
## [「智见 Skills」开源 AI 技能合集介绍](https://x.com/zjp1997720/status/2079844411211735104) ⭐️ 9.0/10

作者 @zjp1997720 正式介绍了「智见 Skills」这个基于真实工作提炼的开源 AI 技能合集，其中第 10 个技能被重点提及。该合集内已有数个技能获得了数百个 GitHub 星标。 该合集提供了一种结构化的、任务驱动的方法来构建可复用的 AI Agent 技能，使开发者更容易创建可靠的 AI Agent。它通过提供经过实战检验的工作流，为日益增长的 Agent 技能生态系统做出了贡献。 作者的方法论是先在真实工作中跑通任务，然后将稳定路径、脚本、参考资料和验收方式固化为一个技能。技能是包含指令和资源的文件夹，AI Agent 可以发现并使用它们。

twitter · zjp1997720 · 7月22日 08:22

**背景**: AI Agent 技能是可复用的结构化程序，通过专门知识和工作流扩展 AI Agent 的能力。它们通常打包为包含 SKILL.md 文件和其他资源的文件夹。像 skills.sh 和 agentskills.io 等平台提供了发现和安装此类技能的生态系统。OpenAI 也有针对 Codex 的技能目录，表明行业对这一模式的认可。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.skills.sh/">Discover and install skills for AI agents.</a></li>
<li><a href="https://github.com/openai/skills">GitHub - openai/ skills : Skills Catalog for Codex · GitHub</a></li>
<li><a href="https://agentskills.io/">Agent Skills Overview - Agent Skills</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#open-source`, `#curated tools`, `#practical skills`, `#developer tools`

---

<a id="item-7"></a>
## [Show HN：将安卓模拟器流式传输到浏览器供 AI 代理使用](https://github.com/hsandhu/serve-avd) ⭐️ 8.0/10

该工具允许开发者托管安卓模拟器并将其流式传输到浏览器，使 Codex、Cursor 或 Claude Desktop 等 AI 代理框架能够远程与模拟器交互。 它弥合了无头 AI 代理与可视化应用交互之间的鸿沟，使自动化安卓应用测试和 UI 任务更加容易，加速了使用 AI 编码助手的安卓开发者的工作流程。 该工具可以在本地、局域网内或通过隧道在远程机器上运行，并通过 npx 作为简单命令分发，便于设置。

rss · Show HN (self-made tools) · 7月22日 21:30

**背景**: Codex、Cursor 和 Claude Desktop 等 AI 代理框架利用大型语言模型自动化软件工程任务，包括编写代码和与应用程序交互。安卓模拟器在计算机上模拟安卓设备，但通常需要直接屏幕访问。该工具将模拟器的显示流式传输到网页浏览器，使 AI 代理能够远程查看并与模拟器交互，从而实现自动化 UI 测试或应用导航等任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Codex_(AI_agent)">OpenAI Codex ( AI agent ) - Wikipedia</a></li>
<li><a href="https://cursor.com/agents">Agents | Cursor - The AI Code Editor</a></li>
<li><a href="https://juliangoldie.com/claude-desktop-agent/">The Claude Desktop Agent: How to Automate Your Computer with AI – Julian Goldie</a></li>

</ul>
</details>

**标签**: `#Android Emulator`, `#AI Agents`, `#Streaming`, `#Developer Tools`, `#Browser`

---

<a id="item-8"></a>
## [TrustLoop：AI 代理审批工作流与策略检查](https://gettrustloop.app/) ⭐️ 8.0/10

TrustLoop 为 AI 代理的动作提供审批工作流和策略检查，让管理者能够批准或拒绝工具调用，并管理 MCP 访问权限。它提供实时演示，且只需几行代码即可轻松集成。 随着 AI 代理变得越来越自主，像 TrustLoop 这样的治理机制对于防止生产环境中的不安全行为（例如超出支出上限或发表破坏性评论）至关重要。这有助于组织自信地部署代理。 TrustLoop 会接入任何代理工作流，拦截提议的工具调用，并将其升级给人类审批或自动应用策略检查。它在每次操作后签署收据，以创建审计追踪。

rss · Show HN (self-made tools) · 7月22日 21:03

**背景**: 模型上下文协议（MCP）是 Anthropic 于 2024 年推出的开放标准，旨在标准化 AI 代理如何连接外部工具和数据源。TrustLoop 在 MCP 基础上增加了治理层，控制代理可以调用哪些工具以及在什么条件下调用，填补了企业 AI 部署中的关键空白。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://www.anthropic.com/news/model-context-protocol">Introducing the Model Context Protocol \ Anthropic</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#governance`, `#MCP`, `#approval workflow`, `#tool calls`

---

<a id="item-9"></a>
## [The Daily FM 将任何来源转化为个性化每日播客](https://thedaily.fm/) ⭐️ 8.0/10

The Daily FM 是一款新工具，它能将博客、新闻、X 账号、Hacker News 故事、长播客和立法内容转化为每日播客节目，使用了 AI 文本转语音和前沿语言模型。 这款工具提供了一种高度可定制的方式来保持信息更新，能将任何内容源转化为音频摘要，可能改变人们随时随地获取信息的方式。 该服务基于 Cloudflare Workers、队列和浏览器渲染构建，通过 OpenRouter 使用 MAI-2 语音模型进行 TTS，并允许用户将多个来源合并到一个 RSS 订阅源中。

rss · Show HN (self-made tools) · 7月22日 20:50

**背景**: 文本转语音（TTS）技术将书面文字转换为口语，前沿模型指的是最新进的 AI 语言模型。RSS 订阅源使用户能够通过标准播客应用订阅播客。该工具利用 OpenRouter 的统一 API 来访问各种 AI 模型，包括微软的 MAI-2 语音模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/OpenRouter">OpenRouter</a></li>
<li><a href="https://evolutionaihub.com/microsoft-ai-models-mai-voice1-mai1-preview/">Microsoft AI Unveils First In House Models - MAI - Voice -1 And...</a></li>
<li><a href="https://qveris.ai/guides/openrouter-alternatives/">OpenRouter Alternatives: 9 LLM Gateways Compared</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#podcast`, `#news`, `#TTS`, `#content curation`

---

<a id="item-10"></a>
## [ClawLite：Telegram 上的本地优先 AI 助手](https://github.com/forgesynapseltd/ClawLite) ⭐️ 8.0/10

ClawLite 是一款全新的开源个人 AI 助手，直接在 Telegram 内运行，强调本地优先的数据存储和处理方式。 该项目通过提供将用户数据保存在本地的 AI 助手，减少对云服务器的依赖，从而应对日益增长的隐私和数据所有权担忧。 ClawLite 托管在 GitHub 的 forgesynapseltd 组织下，设计为可自托管，让用户完全掌控自己的数据和 AI 交互。

rss · Show HN (self-made tools) · 7月22日 20:33

**背景**: 本地优先软件是一种范式，应用程序主要将数据存储在用户设备上，而非远程服务器，从而支持离线访问并增强隐私保护。这一概念由 Ink & Switch 实验室的研究人员在 2019 年的一篇论文中正式提出，主张在云时代用户应拥有自己的数据。遵循本地优先原则的 AI 助手可以在本地运行语言模型，确保敏感对话的私密性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Local-first_software">Local-first software</a></li>
<li><a href="https://www.inkandswitch.com/essay/local-first/">Local-first software: You own your data, in spite of the cloud</a></li>

</ul>
</details>

**标签**: `#AI assistant`, `#local-first`, `#Telegram`, `#GitHub project`, `#agent framework`

---

<a id="item-11"></a>
## [粘贴职位描述，立刻得到一个破损的 Kubernetes 集群来修复](https://prepme.io/) ⭐️ 8.0/10

一个名为 PrepMe 的新工具让用户粘贴职位描述后，就能获得一个定制的、有问题的 Kubernetes 集群，用于模拟真实世界的故障排查场景进行面试练习。 这个工具填补了 Kubernetes 理论知识与实际调试技能之间的鸿沟，为开发者和 DevOps 工程师提供了一种可操作的方式来准备面试并提升故障排查能力。 破损集群是根据从职位描述中提取的关键词生成的，针对常见问题如配置错误、网络错误或资源限制。该平台基于网页，无需本地设置。

rss · Show HN (self-made tools) · 7月22日 20:12

**背景**: Kubernetes 是一个开源容器编排平台，广泛用于管理生产中的容器化应用。排除集群故障是 DevOps 岗位的关键技能，但真实的练习环境很难找到。PrepMe 自动从职位描述中创建这样的环境，让练习更加便捷。

**标签**: `#Kubernetes`, `#DevOps`, `#tool`, `#practice`

---

<a id="item-12"></a>
## [奥地利推出基于 Mistral 模型和 Open WebUI 的 GovGPT 平台](https://www.reddit.com/r/LocalLLaMA/comments/1v3hra4/austria_is_rolling_out_a_government_aiplatform/) ⭐️ 8.0/10

奥地利政府推出了“GovGPT”AI 平台，面向约 18 万名联邦雇员，采用 Mistral 开放权重模型和 Open WebUI 作为界面。 这是开放权重 AI 模型和开源聊天界面在政府领域最大规模的实际部署之一，为主权 AI 基础设施在公共部门的应用树立了先例。 该平台运行在 BRZ 联邦数据中心的自主基础设施上，计划用例包括文档聊天、内部知识库、电子文件分析、议会请求，以及未来的智能体工作流。

reddit · r/LocalLLaMA · /u/ClassicMain · 7月22日 14:28

**背景**: Mistral 等开放权重模型允许组织检查并部署 AI 而无需供应商锁定，而 Open WebUI 是一个自托管界面，用于管理和交互大语言模型。此次部署利用两者来维护数据主权和控制权。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.mistral.ai/models/overview">Models Overview - Mistral Docs</a></li>
<li><a href="https://mistral.ai/models/">Models - from cloud to edge | Mistral</a></li>
<li><a href="https://openwebui.com/">Open WebUI : Self-Hosted AI Platform</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#government AI`, `#Mistral`, `#Open WebUI`

---

<a id="item-13"></a>
## [Claude Code 新增 iOS 模拟器支持](https://www.macrumors.com/2026/07/21/claude-code-ios-simulator/) ⭐️ 8.0/10

Anthropic 宣布，桌面版 Claude Code 现已支持与苹果 iOS 模拟器联动，目前为公开测试版。它可根据构建、运行或检查应用的指令直接打开模拟器、实时观察界面并进行交互，反复修改直到项目完成。 此集成显著提升了 Claude Code 对 iOS 开发者的实用性，允许直接在模拟器中进行 AI 辅助的构建和测试。它简化了开发工作流程，减少了手动配置，加速了迭代周期。 该集成通过 Claude Code 内置面板直接控制模拟器，不依赖 computer use 功能，因此无需 macOS 辅助功能和屏幕录制权限。该功能仅限 macOS 本地会话，且需安装带 iOS 平台的 Xcode；模拟器截图会发送给 Anthropic 并按标准保留规则保存。

telegram · zaihuapd · 7月22日 02:55

**背景**: Claude Code 是 Anthropic 开发的智能编码工具，能够理解代码库、编辑文件并运行命令，帮助开发者更快交付。iOS 模拟器是一款 macOS 应用，允许开发者在没有物理设备的情况下测试 iOS 应用。此集成将两者连接起来，使 Claude Code 能够在其智能工作流中与模拟器交互。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://code.claude.com/docs/en/computer-use">Let Claude use your computer from the CLI - Claude Code Docs</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#iOS Simulator`, `#AI agent`, `#developer tool`

---

<a id="item-14"></a>
## [四大 AI 编程代理曝沙箱逃逸漏洞](https://www.bleepingcomputer.com/news/security/cursor-codex-gemini-cli-antigravity-hit-by-sandbox-escapes/) ⭐️ 8.0/10

Pillar Security 安全研究团队披露，Cursor、OpenAI Codex、Google Gemini CLI 及 Antigravity 四款主流 AI 编程代理存在沙箱逃逸漏洞。攻击者通过在项目文件中嵌入恶意提示，诱使沙箱外的系统执行任意代码，从而控制开发者本地环境。 该漏洞揭示了 AI 编程辅助工具中隔离机制的重大缺陷——攻击者无需正面突破沙箱即可实现代码执行。使用这些工具的开发者面临远程代码执行风险，事件警示需加强对本地工具盲目信任工作区生成物的监控。 漏洞利用间接提示注入技术，通过 README、Issues、依赖库或代码差异等文件植入恶意内容。厂商已推送修复版本（Cursor 升至 3.0.0，Codex CLI 升至 v0.95.0），但 Google 将 Antigravity 的两项漏洞降级处理，认为其利用需配合社工攻击。

telegram · zaihuapd · 7月22日 08:08

**背景**: AI 编程代理在沙箱环境中运行，以隔离其对主机系统的影响。但沙箱通常信任项目工作区内的文件。间接提示注入攻击中，攻击者在 AI 可能访问的外部内容（如文档、代码库）中嵌入恶意指令，诱导 AI 创建配置文件或脚本，随后被主机工具加载执行，从而绕过沙箱。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://forgeeks.dev/ai-coding-agent-sandbox-escapes/">Four AI coding agents hit by sandbox escapes — for(geeks)</a></li>
<li><a href="https://thenextweb.com/news/ai-coding-agents-sandbox-escapes-pillar">AI coding agents keep escaping their sandboxes , study finds</a></li>
<li><a href="https://genai.owasp.org/llmrisk/llm01-prompt-injection/">LLM01:2025 Prompt Injection - OWASP Gen AI Security Project</a></li>

</ul>
</details>

**标签**: `#security`, `#AI coding agents`, `#vulnerability`, `#sandbox escape`

---

<a id="item-15"></a>
## [Claude 推出“教授技能”功能，可录制操作复用](https://www.androidauthority.com/claude-cowork-record-skills-feature-3689919/) ⭐️ 8.0/10

Anthropic 为 Claude Cowork 桌面端推出了“教授技能”功能，用户可通过录制屏幕操作和语音讲解来创建可复用的技能，从而实现重复任务的自动化。 该功能将 Claude 从对话式 AI 转变为更自主的数字同事，弥合了大语言模型与实际工作流自动化之间的鸿沟，对于处理重复性工作的非技术用户尤为有价值。 该功能面向 Pro、Max 和 Team 订阅用户开放，通过点击 Cowork 聊天框中的“+”图标并选择“录制技能”来使用。后续只需一个提示即可触发技能，执行报表整理、电子表格处理或批量重命名文件等任务。

telegram · zaihuapd · 7月22日 09:09

**背景**: Claude Cowork 是 Anthropic 推出的新模式，它超越了简单的聊天，成为一个数字工作台，Claude 可以访问文件、规划并执行用户电脑上的复杂任务。它支持网页、桌面和移动端，即使在笔记本电脑关闭时也能继续运行。“教授技能”功能在此基础上，让用户将工作流捕捉为可复用的指令包，本质上无需编码即可创建自定义自动化宏。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/product/cowork">Claude Cowork | Claude by Anthropic</a></li>
<li><a href="https://www.bnext.com.tw/article/89996/claude-cowork-transforming-generative-ai-into-a-digital-colleague">Claude Cowork 是 什 麼？ Cowork ...</a></li>
<li><a href="https://claude.com/skills">Skills | Claude by Anthropic</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Claude`, `#automation`, `#skills`

---