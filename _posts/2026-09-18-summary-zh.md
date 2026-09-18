---
layout: default
title: "Horizon Summary: 2026-09-18 (ZH)"
date: 2026-09-18
lang: zh
---

> 从 67 条内容中筛选出 11 条重要资讯。

---

1. [Show HN：Cactus Needle 3：8-29MB 的自动化模型可与 DeepSeek V4 Flash 相媲美](#item-1) ⭐️ 8.0/10
2. [CRT：面向 AI 生成代码的本地代码审查工具](#item-2) ⭐️ 8.0/10
3. [OnPanda：面向 LLM 与 Agent 的 Token 级操控与检查工具](#item-3) ⭐️ 8.0/10
4. [MiniMax 以 MIT 协议开源终端版编程智能体 MiniMax Code](#item-4) ⭐️ 8.0/10
5. [Dan Abramov 用大模型 "氛围式" 完成 Conway 猜想证明](#item-5) ⭐️ 7.0/10
6. [Claude Code v2.1.277 支持回退读取 AGENTS.md，并以首个内置 mod 形式发布](#item-6) ⭐️ 7.0/10
7. [Agentgit：面向 AI 代理的免账号、免令牌、免密钥 Git 托管](#item-7) ⭐️ 7.0/10
8. [TypeSeer 为 macOS 全局文本框带来端侧 AI 自动补全](#item-8) ⭐️ 7.0/10
9. [Show HN：Lodestar 以共享洞察为核心来组织多个编程智能体](#item-9) ⭐️ 7.0/10
10. [InclusionAI 发布 Realtime-Venus：9B 全双工音视频开源模型](#item-10) ⭐️ 7.0/10
11. [智谱发布 GLM-5.3-FlashX，最高输出 200 tokens/s](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Show HN：Cactus Needle 3：8-29MB 的自动化模型可与 DeepSeek V4 Flash 相媲美](https://cactuscompute.com/needle) ⭐️ 8.0/10

Cactus Needle 3 发布了体量仅 8-29MB、低于 2 比特的模型，专精于工具调用和结构化 JSON 输出，HN 用户正在测试其在真实场景中的指令遵循能力极限。

hackernews · HenryNdubuaku · 9月18日 00:11 · [社区讨论](https://news.ycombinator.com/item?id=49748553)

**标签**: `#ai-agents`, `#tool-calling`, `#small-language-models`, `#structured-output`, `#llm-inference`

---

<a id="item-2"></a>
## [CRT：面向 AI 生成代码的本地代码审查工具](https://github.com/imron/crt) ⭐️ 8.0/10

一位开发者发布了 CRT（github.com/imron/crt），这是一个本地运行的代码审查工具，可以列出某个 commit 之后所有改动的文件及其 diff，让开发者逐个批准满意的文件，并对仍需修改的代码片段留下评论。该工具通过 MCP（Model Context Protocol）服务器把这些评论暴露给编码智能体，智能体即可读取反馈、修复被标记的部分，之后 diff 会刷新为只显示最近一次批准之后的改动。 随着越来越多的代码由 AI 智能体编写，人工审查这些产物已成为主要瓶颈，也是责任归属的关键所在，因为“这是智能体写的”在面向生产的软件中并不能作为借口。CRT 正是针对这一瓶颈，把审查评论变成智能体可直接消费的结构化输入，形成比把 diff 复制粘贴进聊天窗口更紧密的反馈闭环。 作者明确表示 CRT 仍是开发中的项目，但他自己已经连续使用并改进数月。它围绕“以某个 commit 作为 diff 基线”加“逐文件批准状态”来设计。其核心价值依赖智能体能够访问该 MCP 端点，因此这套流程默认你已经在使用支持 MCP 的编码智能体，而不是普通的聊天模型。

rss · Show HN (self-made tools) · 9月18日 23:09

**背景**: Vibe coding（氛围编程）指由 AI 辅助的开发方式：开发者用自然语言描述需求，由大语言模型生成源代码，有时开发者并不会完整阅读生成结果。Model Context Protocol（MCP）是 Anthropic 推出的开放标准，用于让 AI 应用连接外部工具与数据源，常被用来让编码智能体访问文件、代码仓库和其他开发工具。CRT 把这两者结合起来：一侧是智能体生成的改动集，另一侧是支持 MCP 的审查界面，从而让审查反馈能够自动回流给智能体。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/model-context-protocol">Introducing the Model Context Protocol \ Anthropic</a></li>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#code review`, `#developer tools`, `#MCP`, `#GitHub`

---

<a id="item-3"></a>
## [OnPanda：面向 LLM 与 Agent 的 Token 级操控与检查工具](https://onpanda.diyer22.com/) ⭐️ 8.0/10

作者从 2024 年 9 月起持续开发的交互式开源工具 OnPanda 正式上线了在线试用页面和可自托管的 GitHub 仓库，用于对 LLM 输出进行 token 级可视化与操控。用户可以悬停在任意 token 上、点击候选替换或自由编辑，然后继续生成；同样的编辑能力也覆盖推理过程、工具调用和提示词，并支持通过树状结构记录分支的工具调用历史。 Token 级修正能提供带精确位置、且天然成对的正负样本，从而实现细粒度监督，作者认为这可能成为未来 LLM 对齐与数据标注的一种高效实用范式。对于正在构建 Agent 的开发者来说，它还提供了一种可直接上手的途径，用来对比和调试 Claude Code、Codex、OpenCode 等流行 harness 的工具集、系统提示词、技能与记忆机制。 OnPanda 是「on-Policy Alignment Data Annotator」（在策略对齐数据标注器）的缩写，支持图像、视频、音频等多种模态，并可连接 MCP 服务器在真实环境中执行任务。它还内置了一个无需安装的浏览器 Agent，以浏览器作为其 harness，具备 JavaScript 执行、信息检索、界面交互、多媒体输入输出、本地文件访问和持久化记忆能力；网页版可在移动端使用，项目另附有论文与基准测试。

rss · Show HN (self-made tools) · 9月18日 19:26

**背景**: Token 是大型语言模型实际逐个预测的文本小片段（大致相当于词的一部分），因此 token 级操控意味着直接干预模型的原始输出决策，而不仅仅是重写提示词或修改最终答案。「Agent harness」（也称 Agent 脚手架）是包裹在模型外面的一整套软件基础设施，负责管理工具调用、记忆、状态持久化、执行环境与反馈循环，从而使模型能够作为 Agent 行动；Claude Code、Codex 和 OpenCode 就是面向编码 Agent 的几款竞争性 harness。MCP（Model Context Protocol，模型上下文协议）最初由 Anthropic 提出的开放标准，用于让 AI 应用连接外部数据源、工具和工作流，OnPanda 对 MCP 的支持意味着其 Agent 可以调用这类外部工具。提示词工程（prompt engineering）指的是通过反复设计并调整模型输入来获得更好输出的实践，而细粒度的 token 检查与编辑正是为这一工作流服务的。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://modelcontextprotocol.io/">What is the Model Context Protocol ( MCP )?</a></li>
<li><a href="https://en.wikipedia.org/wiki/Agent_harness">Agent harness - Wikipedia</a></li>
<li><a href="https://www.anthropic.com/news/model-context-protocol">Introducing the Model Context Protocol \ Anthropic</a></li>

</ul>
</details>

**标签**: `#LLM tooling`, `#prompt engineering`, `#AI agents`, `#MCP`, `#developer tools`

---

<a id="item-4"></a>
## [MiniMax 以 MIT 协议开源终端版编程智能体 MiniMax Code](https://www.reddit.com/r/LocalLLaMA/comments/1wjs62f/minimax_code_goes_open_source/) ⭐️ 8.0/10

MiniMax 已在 github.com/MiniMax-AI/minimax-code 开源其编程智能体 MiniMax Code 的终端版本，并按照自有代码默认采用 MIT 许可证发布智能体层。该仓库包含交互式 TUI 与无头（headless）执行能力，可用于代码编辑、shell 命令、diff 对比和测试验证，同时支持计划模式、可恢复会话、子智能体、插件、技能、MCP，以及兼容 OpenAI 与 Anthropic 接口的 BYOK。 编程智能体正越来越多地与云服务绑定，因此公开一个可审查的智能体层，对于希望自托管或核实工具真实行为的开发者而言，是迈向可审计性的重要一步。这也让 MiniMax 的智能体可以直接与其他开源编程智能体进行对比，并让社区有具体代码可用来检查网络行为、文件访问边界与遥测情况。 MiniMax 将该版本标记为 0.4.12 源码预览版，且不包含桌面应用的源码；仓库自身也提醒，版本号一致并不能证明已发布安装包与源码检出之间具有相同的构建来源。此外，它还支持面向兼容编辑器与客户端的 ACP，使该智能体能够走出终端场景。

reddit · r/LocalLLaMA · /u/No_Issue_8224 · 9月18日 14:44

**背景**: 编程智能体是一种由大语言模型驱动的工具，能够在开发者本机上读取与编辑文件、运行 shell 命令并验证测试，通常通过终端界面（TUI）或以无头模式用于自动化。MCP（模型上下文协议）由 Anthropic 于 2024 年 11 月推出，是一项开放标准，用于让 AI 应用连接外部工具与数据源；BYOK（自带密钥）则指用户提供自己的 API 凭证，而不是通过厂商付费调用。ACP（智能体客户端协议）是相关的另一项工作，旨在让智能体在不同 IDE 与编辑器之间通用；子智能体则是主智能体可以委派子任务的辅助智能体。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://medium.com/vibecodingpub/from-autocomplete-to-autonomous-how-acp-is-powering-ai-coding-agents-in-modern-ides-032faf48b883">From Autocomplete to Autonomous: How ACP Is Powering... | Medium</a></li>
<li><a href="https://docs.vexlynk.app/byok/">BYOK — Bring Your Own Key | Vexlynk Docs</a></li>

</ul>
</details>

**社区讨论**: 讨论聚焦于编码代理与智能体究竟读取、发送和存储了哪些内容；发帖者认为，开源本身并不能自动回答所有隐私或安全问题，但至少给了社区一个可以实际审查的对象。发帖人与参与者呼吁在采用前进一步审视其网络行为、文件访问边界、遥测机制以及可复现构建方案。

**标签**: `#ai-agents`, `#open-source`, `#coding-agent`, `#mcp`, `#github-repo`

---

<a id="item-5"></a>
## [Dan Abramov 用大模型 "氛围式" 完成 Conway 猜想证明](https://overreacted.io/how-i-vibed-a-proof-of-conways-conjecture/) ⭐️ 7.0/10

以 React 创造者身份闻名的 Dan Abramov（网名 gaearon）发表了一篇博文，讲述他如何借助大语言模型 "氛围式"（vibe）地推进 Conway 猜想的证明，并将成果公开在 GitHub 仓库（gaearon/conway-refinement）中，同时在 Hacker News 上引发了一场关于 AI 辅助数学的热烈讨论。 它提供了一个具体、可复现的案例，说明大语言模型可以用于真正的数学推理，而非停留在炒作层面，展示了一套他人可以借鉴的实操工作流。随着 AI 辅助证明从实验走向主流数学实践，这类案例有助于澄清当前模型究竟能做什么、不能做什么。 该仓库专门有一节说明作者为何认为证明是正确的，而这篇博文并非即插即用的工具，而是一段反复提示与迭代的叙事。在 HN 讨论中，一位受过专业训练的数学家建议把证明拆解，并让 AI 检查各个子论证是否已存在于文献中，作者表示自己正在采纳这一做法。

hackernews · m-hodges · 9月18日 14:36 · [社区讨论](https://news.ycombinator.com/item?id=49755024)

**背景**: John Horton Conway 是一位以提出众多重要未解问题而著称的数学家，其中最著名的一个是 thrackle 猜想——即 thrackle（一种任意两条边恰好相交一次的图绘制方式）的边数不会超过顶点数。"氛围式编程"（vibe coding）一词由 Andrej Karpathy 于 2025 年 2 月提出，指让大语言模型生成内容，作者依据结果与后续提示来迭代，而非逐行审查。这一现象属于 AI 辅助数学与计算机辅助证明的大趋势，模型正越来越多地参与研究级别的论证工作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Thrackle">Thrackle - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding</a></li>
<li><a href="https://en.wikipedia.org/wiki/Computer-assisted_proof">Computer-assisted proof - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者总体上表示赞赏但态度审慎：有人把这种方法类比为奇幻设定中 "巫师之学"（深入研究）与 "术士召唤"（驱使外力）的区别；一位自称受过专业训练的数学家认可这一方向，并建议拆解证明、检查各子论证是否已存在于别处。也有人援引无限猴子定理，认为在无限 token 预算下，有限数量的 LLM 智能体几乎必然能找到所有定理；还有读者推荐了一个 Hackenbush 视频，作为了解超实数与组合博弈论的入门材料。

**标签**: `#LLM-reasoning`, `#AI-assisted-math`, `#GitHub-repo`, `#AI-workflow`, `#prompting-techniques`

---

<a id="item-6"></a>
## [Claude Code v2.1.277 支持回退读取 AGENTS.md，并以首个内置 mod 形式发布](https://simonwillison.net/2026/Sep/18/thariq-shihipar/) ⭐️ 7.0/10

Anthropic 工程师 Thariq Shihipar 宣布，从 Claude Code 2.1.277 版本开始，如果某个文件夹中没有 CLAUDE.md，Claude 就会转而查找并使用 AGENTS.md。该功能是作为首个内置“mod”实现的，其源代码已发布在 anthropics/claude-code 仓库的 mods/agents-md 目录下。 这让 Claude Code 与其他编码智能体已采用的跨工具 AGENTS.md 约定实现互操作，开发者只需维护一份项目说明文件，不必在 CLAUDE.md 与 AGENTS.md 中重复内容。同时这也低调预告了即将推出的“mods”定制系统，让开发者能够自行扩展这一编码工具的运行框架，而不必完全依赖 Anthropic 内置的行为。 该回退机制有先后顺序：只有在没有 CLAUDE.md 时才会读取 AGENTS.md，因此已有的 CLAUDE.md 仍保持优先地位且不受影响。该 mod 以源代码形式公开在仓库中，意味着开发者可以阅读它，并且据公告所述，在 mods 系统开放后还能构建自己定制版本的项目说明逻辑。

rss · Simon Willison · 9月18日 19:09

**背景**: CLAUDE.md 是 Claude Code 从项目仓库中读取的 Markdown 文件，用于在动手改代码之前了解代码库的约定、命令和风格规则。AGENTS.md 则是一种平行的、与工具无关的约定——本质上是写给 AI 智能体的 README——由 agents.md 推广，同时也被 OpenAI 的 Codex CLI 使用，因此同一个文件可以指导多种不同的编码智能体。“mods”是 Claude Code 即将推出的自定义自身运行框架的机制，像这样的内置 TypeScript 模块会运行在 Claude Code 自身进程内以改变其行为。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://agents.md/">AGENTS . md</a></li>
<li><a href="https://grokipedia.com/page/AGENTSmd">AGENTS.md</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>

</ul>
</details>

**标签**: `#claude-code`, `#ai-agents`, `#coding-agents`, `#agents-md`, `#dev-tools`

---

<a id="item-7"></a>
## [Agentgit：面向 AI 代理的免账号、免令牌、免密钥 Git 托管](https://agentgit.co/) ⭐️ 7.0/10

Agentgit（agentgit.co）以 Show HN 项目的形式发布在 Hacker News 上：这是一个专为 AI 代理打造的 Git 托管服务，使用它不需要注册账号、不需要个人访问令牌（token），也不需要 SSH 密钥。该提交目前处于非常早期的阶段，在本分析进行时仅获得 1 分、0 条评论。 凭据配置是自主代理面临的最大实际摩擦之一：它们很难完成交互式 OAuth 授权流程，也往往无法安全地长期持有密钥。如果一个无摩擦、免密钥的 Git 托管服务能够稳定运行，就会显著降低代理提交、拉分支和推送真实代码的门槛，这也契合 2026 年诸如 Cursor Origin 等“代理原生”Git 基础设施兴起的趋势。 除了落地页链接之外，该提交几乎没有提供任何技术细节，因此在任何用户（或任何代理）都能无凭据推送的情况下，身份识别、仓库归属、滥用防范和垃圾回收如何实现尚不明确。读者还应注意，GitHub 上一个名字相似的项目 Samian89/agentgit 是另一款本地优先的工具，它把 LLM 调用记录为提交，而不是一个托管的 Git 服务。

rss · Show HN (self-made tools) · 9月18日 23:14

**背景**: GitHub、GitLab、Bitbucket 等 Git 托管平台负责存储仓库并承载协作，但它们通常要求每次推送都必须有账号，外加 SSH 密钥对或个人访问令牌（GitHub 官方的认证文档就是这么描述的）。这套模型假设操作者是人：能够注册账号、点击授权页面、定期轮换密钥——而当操作者是在循环中无人值守运行的自主代理时，这些假设就不再成立。云基础设施领域已经出现了“免密钥”方案（例如工作负载身份联合）以避免长期密钥，如今类似思路正被应用到面向代理的代码托管上。Agentgit 正处在这一交叉点上：把凭据这一步直接从 Git 托管中去掉。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://alphasignal.ai/news/cursor-s-origin-takes-on-github-with-ai-agent-scale-git-hosting">Cursor's Origin Takes on GitHub With AI Agent-Scale Git Hosting - AlphaSignal</a></li>
<li><a href="https://www.reddit.com/r/AI_Agents/comments/1uw24y1/gitnative_agent_workflows_are_starting_to_look/">Git-native agent workflows are starting to look less like a gimmick and more like the only sane option - Reddit</a></li>
<li><a href="https://docs.github.com/en/authentication/connecting-to-github-with-ssh/generating-a-new-ssh-key-and-adding-it-to-the-ssh-agent">Generating a new SSH key and adding it to the ssh-agent - GitHub Docs</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Git hosting`, `#developer tools`, `#Show HN`, `#agent infrastructure`

---

<a id="item-8"></a>
## [TypeSeer 为 macOS 全局文本框带来端侧 AI 自动补全](https://typeseer.com/) ⭐️ 7.0/10

TypeSeer 是一款新的 macOS 应用，通过 Show HN 帖子发布并链接到 typeseer.com，它为整个操作系统中的所有文本框提供 AI 自动补全，而不是局限于某一个应用内部。该发布帖在 Hacker News 上热度不高，采集时仅有 2 分和 1 条评论。 大多数 AI 写作助手要么绑定于单一应用，要么把用户的键入内容发送到云端，因此“系统级 + 端侧运行”的方案指向了一种更注重隐私、延迟更低的 Mac 日常文本输入模式。如果它运行足够稳定，AI 辅助就会变得无处不在——在邮件、聊天、代码编辑器和网页表单中都能直接使用，而无需为每个应用单独做集成。 要在任意应用中生效，此类工具通常必须依赖 macOS Accessibility API 来读取和修改其他进程中被聚焦的文本框，而这一技术会因目标应用不同而失效或表现不一致。本地运行模型还必须在模型规模和生成质量之间做出权衡；此外，所提供的资料中并未包含模型细节、定价、系统要求或版本信息。

rss · Show HN (self-made tools) · 9月18日 21:35

**背景**: macOS Accessibility API（在 Swift 中通过 kAXFocusedUIElementAttribute 等属性暴露）是让一个应用读取和写入其他应用文本框的标准机制，基本上也是在 Mac 上实现全局写作辅助的唯一途径。端侧 AI 推理指语言模型完全运行在本地硬件上——通常是 Mac 的 Apple Silicon 芯片——因此用户文本不会离开本机；PyTorch 的 ExecuTorch 等运行时正是为支持这类本地推理而生。文本自动补全本身是一种机器学习任务，模型根据前文上下文预测接下来的 token、词或字符。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theodorehq.com/charm/blog/what-is-accessibility-api-mac">What Is the Mac Accessibility API for Writing Tools?</a></li>
<li><a href="https://executorch.ai/">ExecuTorch - On - Device AI Inference Powered by PyTorch</a></li>
<li><a href="https://aiportalx.com/models/task/text-autocompletion">Text Autocompletion AI Models in 2026 – Capabilities & Comparisons</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#macOS`, `#autocomplete`, `#on-device AI`, `#productivity`

---

<a id="item-9"></a>
## [Show HN：Lodestar 以共享洞察为核心来组织多个编程智能体](https://www.try-lodestar.com/) ⭐️ 7.0/10

Lodestar 在 Show HN 上发布，它是一个面向 Claude Code 和 Codex 的 Mac 工作空间，目标不是做一个“仪表盘”，而是围绕共享的“实质内容”——理解、决策与洞察——来阅读、回应并管理多个编程智能体。其具体功能包括：在文本、文档和 HTML 文件上做行内评论，由智能体主动生成图表与标注来解释想法，用自然语言描述回忆几天甚至几周前的消息，以及自动生成带实时状态的层级化或图形化会话地图。 当开发者越来越多地在同一个想法上并行运行三个甚至更多编程智能体时，真正的瓶颈已从“如何调用智能体”转向“如何让各智能体的洞察、决策和未完成线索保持连贯”——而这恰恰是终端窗口和仪表盘难以解决的问题。Lodestar 是较早把多智能体编排当作上下文与知识管理问题来处理的一种尝试，如果这一思路成立，就能降低并行智能体协作的协调成本。 该工具定位为仅支持 Mac 的工作空间，并且专门面向 Claude Code 和 Codex；作者也坦言它“距离我设想的愿景还很远”，属于早期粗糙版本。值得注意的是，这篇 Show HN 帖子在抓取时仅获得 1 分和 0 条评论，帖子中也没有提供公开代码仓库、演示视频或定价信息。

rss · Show HN (self-made tools) · 9月18日 19:14

**背景**: Claude Code、Codex 这类编程智能体是能够代替开发者在终端中自主阅读、修改并运行代码的 AI 系统，如今开发者同时在问题的不同部分上运行多个此类智能体已相当常见。多智能体编排（multi-agent orchestration）正是研究如何协调多个此类智能体的子领域，通常借助一个中心化的编排者，让复杂的多步骤工作流高效完成。Show HN 是 Hacker News 上供开发者直接向社区展示新项目的栏目，通常也是一个小型开发者工具首次公开亮相的地方。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.try-lodestar.com/">Lodestar · Keep the thread.</a></li>
<li><a href="https://github.com/Kgard/lodestar-releases">GitHub - Kgard/ lodestar -releases: Lodestar documents your coding ...</a></li>
<li><a href="https://grokipedia.com/page/Multi-agent_orchestration">Multi-agent orchestration</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#developer tools`, `#agent orchestration`, `#Show HN`

---

<a id="item-10"></a>
## [InclusionAI 发布 Realtime-Venus：9B 全双工音视频开源模型](https://www.reddit.com/r/LocalLLaMA/comments/1wjtav9/inclusionairealtimevenus_hugging_face/) ⭐️ 7.0/10

InclusionAI 在 Hugging Face 上发布了两款 Realtime-Venus 检查点：9B 的音视频交互模型 Realtime-Venus-Omni，以及基于同一流式骨干网络的音频侧重版本 Realtime-Venus-Audio。两者都包含模型权重与自定义的 Hugging Face Transformers 代码，异步的 Realtime-Venus-Harness 及其外部工具集成则放在配套的 GitHub 仓库中。 可开放权重、支持全双工的音视频模型仍然稀缺，而一个能在本地运行和微调的 9B 检查点，为本地 LLM 社区提供了对标 Google、字节跳动等闭源实时 API 的具体替代方案。主动发起回应、语义打断处理以及免训练长视频记忆等能力，也让语音助手从“轮流对话”迈向始终在线的交互式智能体。 Omni 检查点改编自 MiniCPM-o 4.5，借助内置的 Token2wav 资源和参考音色在生成回复文本的同时合成原生语音；长视频记忆则通过归档视觉信息丰富的片段、检索与查询相关且不冗余的证据来实现，无需额外训练。执行委派任务需要单独运行 Realtime-Venus-Harness，因此仅靠 Hugging Face 上的开箱代码并不能获得完整的工具集成能力。

reddit · r/LocalLLaMA · /u/jacek2023 · 9月18日 15:27

**背景**: MiniCPM-o 4.5 是一个端到端的 9B 全模态模型，视觉部分基于 SigLip2，音频部分基于 Whisper-medium，语音合成基于 CosyVoice2，语言主干为 Qwen3-8B，其在视觉、语音和全双工实时流式交互上接近 Gemini 2.5 Flash 的水平。所谓“全双工”是指模型在说话时仍持续收听和观看，而不是等用户说完；“主动交互”则指它能自行判断何时对观察到的事件作出回应，而不是只对提示作出反应。免训练长视频记忆指的是用检索式处理而非微调来记住长视频流中的相关片段。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/openbmb/MiniCPM-o-4_5">openbmb/ MiniCPM - o - 4 _ 5 · Hugging Face</a></li>
<li><a href="https://github.com/OpenBMB/MiniCPM-V">GitHub - OpenBMB/ MiniCPM -V: A Pocket-Sized MLLM for...</a></li>
<li><a href="https://www.orcarouter.ai/blog/seedrealtime-launch">SeedRealtime: ByteDance's Full - Duplex AV Model, No API Yet</a></li>

</ul>
</details>

**标签**: `#open-source-model`, `#multimodal`, `#local-llm`, `#audio-visual`, `#huggingface`

---

<a id="item-11"></a>
## [智谱发布 GLM-5.3-FlashX，最高输出 200 tokens/s](https://mp.weixin.qq.com/s/ZJHhQrDeiwOGkkaqHw7kqA) ⭐️ 7.0/10

智谱今日正式发布 GLM-5.3-FlashX 模型，宣称最高输出速度可达 200 tokens/s，API 已上线，模型标识为 GLM-5.3-FlashX。官方表示，此次在 10 万张国产芯片的推理算力基础上进一步做了推理优化，以在智能、价格、速度三个维度形成全面竞争力。 输出速度正成为中国大模型厂商的重要竞争点，因为生成越快，就越能支撑 Agent、实时编程辅助和高并发批处理等对延迟敏感的场景。对于已经在使用智谱 API 的开发者而言，一个即刻可用的更高速端点意味着低成本的升级路径，而对国产推理芯片的强调也呼应了中国 AI 基础设施自主化的整体趋势。 公告确认，此前的 GLM-5.3-Flash 曾以 "Ox Alpha" 这一代号面向全球开发者开放，之后才揭晓真实身份，并提到该模型的调用量持续攀升。值得注意的是，此次并未公布具体价格、基准测试成绩或代码示例，因此 200 tokens/s 目前仍是厂商口径的数据，而非第三方实测结果。

telegram · zaihuapd · 9月18日 06:48

**背景**: GLM 是 General Language Model 的缩写，是中国 "AI 六小虎" 之一智谱（Zhipu AI，亦称 Z.ai）的旗舰模型系列；该公司于 2023 年 3 月推出首个 ChatGLM 聊天机器人，并多以 MIT 或 Apache 2.0 协议开放 GLM 权重，可本地或云端部署。"Ox Alpha" 是此前匿名出现在模型路由平台 OpenRouter 上的隐身模型，后被揭晓为 GLM 系列，这是正式发布前低调收集真实调用数据与社区反馈的常见做法。tokens/s 表示模型每秒生成的文本单元数（大致对应词片段），是决定大模型应用响应速度与成本的核心指标之一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Ox_Alpha">Ox Alpha</a></li>
<li><a href="https://upxuu.com/posts/ox-alpha/">0元首发？ 匿名 模 型 Ox Alpha 空降 OpenRouter... - UpXuu's blog</a></li>
<li><a href="https://tokenra.io/zh/docs/ox-alpha">Ox Alpha 模 型 API 文档 | TokenRa</a></li>

</ul>
</details>

**标签**: `#LLM`, `#智谱`, `#模型发布`, `#API`, `#推理加速`

---