---
layout: default
title: "Horizon Summary: 2026-07-13 (ZH)"
date: 2026-07-13
lang: zh
---

> 从 52 条内容中筛选出 15 条重要资讯。

---

1. [PlanWright：AI 编程智能体的控制平面](#item-1) ⭐️ 9.0/10
2. [Sql4json：用 SQL 语法查询 JSON 文件](#item-2) ⭐️ 9.0/10
3. [像情报分析师一样分析新闻的克劳德技能](#item-3) ⭐️ 9.0/10
4. [开源工具利用 Claude Code 自动化 After Effects 视频制作](#item-4) ⭐️ 9.0/10
5. [对 15 款电子垃圾 GPU 进行现代 AI 工作负载基准测试](#item-5) ⭐️ 9.0/10
6. [开源编排器技能让 Codex MultiAgent 实现模型分配](#item-6) ⭐️ 9.0/10
7. [Codex 桌宠定制最简单赚钱方法](#item-7) ⭐️ 9.0/10
8. [使用 SPM 和 xtool 无需 Xcode 构建 iOS 应用](#item-8) ⭐️ 8.0/10
9. [DOM-docx：开源 HTML 转可编辑 Word 文档工具](#item-9) ⭐️ 8.0/10
10. [开源工具检测智能体评估作弊](#item-10) ⭐️ 8.0/10
11. [Fleet Deck：Claude Code 会话仪表板](#item-11) ⭐️ 8.0/10
12. [AgentsProof：追踪与评估 AI 代理的工具](#item-12) ⭐️ 8.0/10
13. [Phlox-GW：无企业付费墙的开源 LLM 网关](#item-13) ⭐️ 8.0/10
14. [YouTube 吉他谱解析器：AI 视觉提取指法谱](#item-14) ⭐️ 8.0/10
15. [用 Xarray-SQL 在 SQL 中实现神经网络](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [PlanWright：AI 编程智能体的控制平面](https://planwright.tools/) ⭐️ 9.0/10

PlanWright 是一个由 MCP 驱动的控制平面，用于协调 AI 编程智能体在规划、实施和审查阶段的工作，它使用 Claude Desktop、Codex 和自定义分类智能体。 它为智能体工程提供了结构化工作流，能够更好地协调不同 AI 智能体并记录决策，从而提高 AI 辅助开发的可靠性和透明度。 该工具使用 MCP（模型上下文协议）集成多个智能体，记录所有决策并跟踪整个过程。它支持从 Claude Desktop 进行规划、在 Codex 中实施，并通过自定义分类智能体进行审查。

rss · Show HN (self-made tools) · 7月13日 19:59

**背景**: MCP（模型上下文协议）是一个开放标准，允许 AI 智能体连接到工具和数据源。它区分了 MCP 主机（AI 智能体）、客户端和服务器。该协议实现了不同 AI 智能体和服务之间的互操作性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://medium.com/@elisowski/mcp-explained-the-new-standard-connecting-ai-to-everything-79c5a1c98288">MCP Explained: The New Standard Connecting AI to... | Medium</a></li>
<li><a href="https://modelcontextprotocol.io/">What is the Model Context Protocol ( MCP )? - Model Context Protocol</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#MCP`, `#coding agents`, `#agentic engineering`, `#tool`

---

<a id="item-2"></a>
## [Sql4json：用 SQL 语法查询 JSON 文件](https://github.com/mnesimiyilmaz/sql4json) ⭐️ 9.0/10

Sql4json 是一款新的命令行工具，允许用户使用类似 SQL 的语法查询 JSON 文件，无需数据库即可进行筛选、聚合和选择操作。 该工具简化了处理 JSON 的开发者的数据探索过程，无需设置数据库即可在结构化查询和非结构化数据之间搭建桥梁。 该工具支持与 SQL SELECT 查询几乎相同的语法，包括 WHERE、GROUP BY、ORDER BY 以及对 JSON 数组的连接操作。

rss · Show HN (self-made tools) · 7月13日 19:44

**背景**: JSON 是 API、日志和配置文件的常见数据格式，但查询它通常需要自定义脚本或导入数据库。Sql4json 提供了熟悉的 SQL 接口，降低了临时分析的门槛。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/mnesimiyilmaz/sql4json">GitHub - mnesimiyilmaz/sql4json: Filter, aggregate and select data from json using SQL like query.</a></li>

</ul>
</details>

**标签**: `#JSON`, `#SQL`, `#developer-tools`, `#query`, `#open-source`

---

<a id="item-3"></a>
## [像情报分析师一样分析新闻的克劳德技能](https://github.com/Vadiml1024/signal-analysis) ⭐️ 9.0/10

一名开发者在 GitHub 上发布了 Signal Analysis，这是一种克劳德技能，允许用户使用类似情报分析师的方法论来分析新闻文章。 该技能在 GitHub 上免费提供，可添加到克劳德项目中；它指导克劳德检查新闻中的信号、偏见和潜在叙事。

rss · Show HN (self-made tools) · 7月13日 19:35

**背景**: 克劳德技能是可复用的流程文档，用于教导 AI 一致地执行特定任务，例如遵循公司品牌指南或分析数据。信号情报分析师接受过从电子辐射和通信中提取和解读信息的培训——该技能将这些分析技术应用于新闻阅读。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.claude.com/en/articles/12512176-what-are-skills">What are skills? | Claude Help Center</a></li>
<li><a href="https://chrislema.com/what-is-a-claude-skill">What Is a Claude Skill? A Walkthrough of My Expert Profiler</a></li>
<li><a href="https://www.airforce.com/careers/intelligence/signals-intelligence-analyst">Signals Intelligence Analyst - U.S. Air Force</a></li>

</ul>
</details>

**标签**: `#AI`, `#Claude`, `#skill`, `#news`, `#analysis`

---

<a id="item-4"></a>
## [开源工具利用 Claude Code 自动化 After Effects 视频制作](https://github.com/Arman-Luthra/aftr) ⭐️ 9.0/10

一个名为'aftr'的新开源项目利用 Anthropic 的 Claude Code，直接在 Adobe After Effects 中自动化创建生产就绪的视频。 该工具弥合了 AI 驱动代码生成与专业视频制作之间的差距，使开发者能够以编程方式生成视频，无需手动编辑。 该项目将 Claude Code 集成作为代理编码工具，该工具能理解 After Effects 代码库、编辑文件并运行命令以生成最终视频。

rss · Show HN (self-made tools) · 7月13日 19:26

**背景**: Claude Code 是 Anthropic 推出的一款代理编码工具，位于终端中，帮助开发者编写和编辑代码。Adobe After Effects 是运动图形和视觉效果领域的行业标准软件。'aftr'通过使用 Claude Code 以编程方式控制 After Effects，将两者结合起来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://docs.anthropic.com/en/docs/claude-code/overview">Claude Code overview - Anthropic</a></li>

</ul>
</details>

**标签**: `#AI tool`, `#video production`, `#open source`, `#Claude Code`, `#After Effects`

---

<a id="item-5"></a>
## [对 15 款电子垃圾 GPU 进行现代 AI 工作负载基准测试](https://www.reddit.com/r/LocalLLaMA/comments/1uvcjd0/i_benchmarked_15_ewaste_gpus_with_modern_workloads/) ⭐️ 9.0/10

作者对 15 款已退役的 NVIDIA 企业 GPU（包括 K80、P100、V100 等）进行了现代工作负载（如大语言模型、计算机视觉和 Whisper）的基准测试。结果发现，V100（16GB）是性价比最佳的选择，售价不到 200 美元，性能却接近更昂贵的 T40。 这为爱好者和开发者提供了使用廉价企业 GPU 构建经济实惠的 AI 家庭实验室的实用指南。它挑战了电子垃圾 GPU 无法用于现代 AI 的观点，可能降低本地 AI 实验的门槛。 P40 在运行大语言模型方面优于 P100，而 M60 在 Whisper 音频转录上表现出色，甚至超过 V100。在一个机箱内堆叠多张 GPU 可实现线性扩展，但混用不同代产品会导致慢卡拖累快卡。软件兼容性问题可通过从源码编译 llama.cpp 等旧工具来解决。

reddit · r/LocalLLaMA · /u/eso_logic · 7月13日 14:05

**背景**: NVIDIA Tesla 系列（如 P100、V100）是企业级 GPU，专为数据中心设计，没有显示输出接口，因此在二手市场上价格低廉。llama.cpp 是一个开源的大语言模型推理引擎，可以从源码编译以支持旧的 GPU 架构。基准测试表明，通过合适的软件适配，这些电子垃圾 GPU 在现代 AI 任务中仍然可行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Llama.cpp">Llama.cpp</a></li>
<li><a href="https://en.wikipedia.org/wiki/Nvidia_Tesla">Nvidia Tesla - Wikipedia</a></li>
<li><a href="https://www.nvidia.com/en-gb/data-center/tesla-v100/">NVIDIA Tesla V 100 | NVIDIA</a></li>

</ul>
</details>

**标签**: `#GPU benchmarking`, `#homelab`, `#LLM inference`, `#cost-effective AI`, `#enterprise GPUs`

---

<a id="item-6"></a>
## [开源编排器技能让 Codex MultiAgent 实现模型分配](https://x.com/zjp1997720/status/2076605089523876191) ⭐️ 9.0/10

一位开发者开源了一个针对 Codex MultiAgentV2 的编排器技能，允许为子代理分配不同模型（如 Sol、Luna）和推理强度，克服了当前所有子代理继承主模型的限制。 这使得多代理编排更加灵活高效，用户可以通过为每个子代理匹配适合其任务的模型和推理强度来优化成本和性能，这对复杂的并行工作流至关重要。 该技能将 Sol 设为编排器，由 Luna 或 Sol Worker 执行任务；它与 Codex 原生的 MultiAgentV2 系统兼容，用户导入开源技能文件后即可使用。

twitter · zjp1997720 · 7月13日 09:50

**背景**: Codex 是一个 AI 编程平台，通过 MultiAgentV2 支持多代理工作流，允许并行子代理拥有独立的上下文窗口。OpenAI 的 GPT-5.6 提供三个模型层级：Sol（旗舰）、Terra（均衡）和 Luna（最快/最便宜）。原生的 MultiAgentV2 目前强制所有子代理使用相同模型，而该编排器技能解决了这一问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.reddit.com/r/codex/comments/1rt6314/a_codex_delegation_skill_that_enables_multiagent/">r/codex on Reddit: A Codex delegation skill that enables "multi-agent orchestration" in Codex Desktop</a></li>
<li><a href="https://www.firecrawl.dev/blog/codex-multi-agent-orchestration">Multi-Agent Orchestration With Codex</a></li>
<li><a href="https://github.com/am-will/swarms">GitHub - am-will/swarms: Multi-agent orchestration skills for Claude Code and Codex · GitHub</a></li>

</ul>
</details>

**标签**: `#multi-agent`, `#orchestration`, `#open-source`, `#Codex`, `#AI agents`

---

<a id="item-7"></a>
## [Codex 桌宠定制最简单赚钱方法](https://x.com/zjp1997720/status/2076580748308693399) ⭐️ 9.0/10

有用户分享了一种基于技能（skill）的简单 Codex 桌宠定制方法，声称可以在闲鱼上以每个 200 元的价格出售，交付时只需将文件夹发给买家即可。 这种方法降低了利用 AI 工具赚钱的门槛，使任何人都能无需复杂编程就能创建和销售定制桌宠，有望在闲鱼等平台上开辟新的副业机会。 该定制使用单个“skill”，适用于动作不多的简单需求。对于复杂定制，作者建议还是老老实实做素材。

twitter · zjp1997720 · 7月13日 08:13

**背景**: Codex 桌宠是出现在 Codex AI 编程环境桌面的动画角色。闲鱼是阿里巴巴旗下的二手交易平台，也提供副业服务市场。这篇帖子展示了一种利用 AI 定制技能赚钱的实用方法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://toolin.ai/blog/openai-codex-desktop-pet">OpenAI Codex 桌 面悬浮 宠 物：自定义玩法全攻略 | Toolin AI</a></li>
<li><a href="https://www.alizila.com/alibaba-resale-platform-xianyu-beyond-bargains-young-china-users-side-jobs/">Alibaba Resale Platform Xianyu Moves Beyond Bargains to Power Young Users’ Side Hustles</a></li>

</ul>
</details>

**标签**: `#AI tool`, `#customization`, `#monetization`, `#skill`, `#desk pet`

---

<a id="item-8"></a>
## [使用 SPM 和 xtool 无需 Xcode 构建 iOS 应用](https://scottwillsey.com/building-and-shipping-mac-and-ios-apps-without-ever-opening-xcode/) ⭐️ 8.0/10

一位开发者介绍了一种完全从命令行使用 Swift Package Manager 和 xtool 工具构建和发布 Mac 及 iOS 应用的工作流程，全程无需打开 Xcode。这种方法甚至可以从 Linux 构建 iOS 应用并通过 USB 本地安装。 该技术为偏好命令行或 AI 辅助开发的开发者提供了一种替代方案，减少了对 Xcode IDE 的依赖。它还开辟了跨平台开发的可能性，例如从 Linux 构建 iOS 应用，这可能降低贡献者的门槛。 该工作流程使用 Swift Package Manager 的 build 命令和 xtool 来归档、签名、公证和钉选应用。对于 iOS，应用可以通过 USB 本地安装，无需上传到 TestFlight 或 App Store，甚至可以从 Linux 进行。

hackernews · speckx · 7月13日 18:22 · [社区讨论](https://news.ycombinator.com/item?id=48896665)

**背景**: Xcode 是苹果为 macOS、iOS、watchOS 和 tvOS 开发应用的官方 IDE，传统上构建和签名应用需要使用它。Swift Package Manager（SPM）是管理 Swift 代码分发和构建过程的工具，可以独立于 Xcode 使用。提到的 xtool 工具很可能是一个社区工具，用于在没有 Xcode GUI 的情况下自动化构建和签名任务，从而实现命令行工作流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://decode.agency/article/ios-app-development-tools/">In this article, we'll talk about 10 crucial tools for iOS app development.</a></li>

</ul>
</details>

**社区讨论**: 评论者指出在宿主机上运行代理存在安全隐患，可能会暴露 SSH 密钥和主目录，类似于 xAI 事件。有人成功使用 xtool 从 Linux 构建了 iOS 应用，证实了其可行性。其他人建议将整个应用设置为 Swift 包，以完全避免 Xcode 项目。

**标签**: `#iOS development`, `#Swift`, `#CI/CD`, `#GitHub repo`, `#agent`

---

<a id="item-9"></a>
## [DOM-docx：开源 HTML 转可编辑 Word 文档工具](https://github.com/floodtide/dom-docx) ⭐️ 8.0/10

Floodtide 发布了 DOM-docx，这是一个采用 MIT 许可的库，可将 HTML 片段转换为原生、可编辑的 Word 文档（DOCX），且保真度高。 这解决了后端文档生成中的常见痛点，使开发者能够使用现代 JS 框架制作报告模板，并生成真正可编辑的 DOCX 输出。 该库采用视觉回归循环：在 Chromium 中渲染 HTML，转换为 DOCX，通过 LibreOffice 光栅化，并针对人工验证的指标评分布局保真度。它支持表格、列表、样式表，且无需上传。

hackernews · fishbone · 7月13日 11:51 · [社区讨论](https://news.ycombinator.com/item?id=48891267)

**背景**: 将 HTML 转换为 Word 文档具有挑战性，因为大多数开源库生成的输出在编辑时结构不合法。开发者常常求助于复杂的模板引擎或手动调整。DOM-docx 旨在生成原生 OOXML，可以像普通文档一样在 Word 中打开和编辑。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/floodtide/dom-docx">floodtide/dom-docx: Convert semantic HTML fragments to native ...</a></li>
<li><a href="https://dom-docx.com/">dom - docx — HTML to Word converter in the browser</a></li>
<li><a href="https://dev.to/blair_googer_8e41a7d338d2/brute-forcing-my-way-to-better-html-docx-conversion-4ffj">Brute forcing my way to better HTML > DOCX ... - DEV Community</a></li>

</ul>
</details>

**社区讨论**: 作者强调了维护后端 docx 生成的烦恼，更倾向于使用 JS 渲染 HTML。评论者赞赏该工具采用 TypeScript 实现以及使用截图到 docx 评分循环进行布局验证。一些人指出这可能有助于提高浏览器打印/保存为 PDF 的保真度。

**标签**: `#HTML-to-docx`, `#document generation`, `#open-source`, `#developer tools`

---

<a id="item-10"></a>
## [开源工具检测智能体评估作弊](https://github.com/sebuzdugan/agent-eval-harness) ⭐️ 8.0/10

一个新的 GitHub 仓库 agent-eval-harness（由 sebuzdugan 开发）提供了一个可复现的测试框架，用于检测 AI 智能体评估中的作弊行为。 随着 AI 智能体能力增强，确保基准测试的诚实性对于信任至关重要；该工具帮助开发者和研究人员在不操纵指标的情况下验证智能体性能。 该工具实现了反作弊检查，例如审查对话记录和任务分解分析，借鉴了 NIST 指南和自我评估偏差研究的实践。

rss · Show HN (self-made tools) · 7月13日 22:11

**背景**: 评估工具（harness）是在测试 AI 智能体时提供上下文、记忆和工具的执行层。智能体评估中的作弊可能通过自我评估偏差或利用固定任务发生。NIST 等机构已概述了检测此类作弊的方法，该工具则以可复现的方式实现了这些方法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://medium.com/@JiazhenZhu/i-ran-one-ai-task-through-4-harness-architectures-heres-what-broke-0758b68229dc">I Ran One AI Task Through 4 Harness Architectures. | Medium</a></li>
<li><a href="https://www.nist.gov/caisi/cheating-ai-agent-evaluations/4-practices-detecting-and-preventing-evaluation-cheating">4. Practices for detecting and preventing evaluation cheating | NIST</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#evaluation`, `#harness`, `#anti-cheating`, `#reproducibility`

---

<a id="item-11"></a>
## [Fleet Deck：Claude Code 会话仪表板](https://github.com/lacion/fleet-deck) ⭐️ 8.0/10

Fleet Deck 是一款新的本地守护进程和 Web 界面，可将机器上的所有 Claude Code 会话汇总到一个仪表板中，显示排队、工作中、需要你输入和空闲等状态列。 对于同时运行多个 Claude Code 会话的开发者来说，Fleet Deck 消除了在多个终端标签页间切换的需要，提高了生产力并减轻了认知负担。 Fleet Deck 利用 Claude Code 挂钩来获取会话状态，运行在 localhost:4711 上。它还支持直接在 tmux 窗口中启动新会话以及管理工作树。

rss · Show HN (self-made tools) · 7月13日 20:56

**背景**: Claude Code 是 Anthropic 推出的 AI 驱动的编码助手，作为终端中的代理工具运行。开发者经常为不同任务同时运行多个会话，但追踪这些会话可能很混乱。Fleet Deck 提供了一个确定性仪表板，而不增加任何 AI 开销。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://code.claude.com/docs/en/overview">Overview - Claude Code Docs</a></li>
<li><a href="https://code.claude.com/docs/en/hooks">Hooks reference - Claude Code Docs</a></li>
<li><a href="https://medium.com/write-a-catalyst/one-terminal-many-worlds-mastering-tmux-5c0b77ab6266">One Terminal , Many Worlds: Mastering tmux | by Sajid Khan | Medium</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#AI agents`, `#developer tools`, `#session management`, `#GitHub`

---

<a id="item-12"></a>
## [AgentsProof：追踪与评估 AI 代理的工具](https://www.agentsproof.dev/) ⭐️ 8.0/10

AgentsProof 是一个新的副业项目，能够追踪 AI 代理的运行、创建评估案例并生成可公开分享的报告，用于分析代理的成功与失败。 随着 AI 代理的使用日益增长，开发者需要实用的可观测性和评估工具；AgentsProof 提供了一种简单、可共享的方式来调试和评估代理行为，满足了生态中的关键需求。 该工具为代理运行创建可公开分享的报告，便于团队协作评估代理性能，但该项目被描述为一个复杂度有限的小型副业项目。

rss · Show HN (self-made tools) · 7月13日 20:23

**背景**: AI 代理评估是对执行涉及推理、规划和工具使用的多步骤任务的自主 AI 系统进行的系统评估。代理可观测性是指监控和理解这些代理的内部状态和行为，包括提示、推理链和工具调用。像 AgentsProof 这样的工具帮助开发者了解代理成功或失败的原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/engineering/demystifying-evals-for-ai-agents">Demystifying evals for AI agents \ Anthropic</a></li>
<li><a href="https://docs.cloud.google.com/stackdriver/docs/observability/agent-observability">Agent observability | Google Cloud Observability | Google Cloud Documentation</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent evaluation`, `#observability`, `#testing`, `#tool`

---

<a id="item-13"></a>
## [Phlox-GW：无企业付费墙的开源 LLM 网关](https://robert-mcdermott.github.io/phlox-gw/) ⭐️ 8.0/10

Phlox-GW 是一款开源的 LLM 网关，已在 Hacker News 上发布，提供 SSO、成本核算、预算控制、速率限制、智能路由和安全护栏等功能，无需企业授权费用。 它提供了一种免费、自托管的替代方案，替代昂贵的企业级 LLM 网关，使小型团队和个人开发者能够更好地管理和控制多个 LLM 提供商，并提高成本效益。 该网关支持单点登录、成本核算、预算控制、速率限制、跨提供商的智能路由以及安全使用护栏，所有这些都包含在一个自托管的开源软件包中。

rss · Show HN (self-made tools) · 7月13日 20:16

**背景**: LLM 网关充当多个大型语言模型提供商的统一 API 层，处理 API 密钥管理、速率限制和请求路由。许多商业网关需要企业授权费用，对小团队构成障碍。像 Phlox-GW 这样的开源替代品提供了类似功能，且无需付费，填补了这一空白。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.databasemart.com/blog/best-llm-api-gateways-in-2026">7 Best LLM API Gateways in 2026</a></li>

</ul>
</details>

**标签**: `#LLM`, `#gateway`, `#open-source`, `#AI tool`

---

<a id="item-14"></a>
## [YouTube 吉他谱解析器：AI 视觉提取指法谱](https://github.com/marcelpanse/youtube-guitar-tab-parser) ⭐️ 8.0/10

一位开发者发布了一个 CLI 工具，它可以下载 YouTube 吉他教学视频，使用 Claude Vision 定位并裁剪谱例区域，通过小节号去重，然后将不同的谱例行拼接成单个 PDF 文件。 该工具解决了吉他学习者手动转录的常见痛点，提供了利用 AI 视觉自动提取吉他谱的流程，展示了多模态 AI 在创意小众任务中的实际应用。 该工具下载视频、采样帧，使用 Claude Vision 识别谱例区域，然后根据每行打印的小节号裁剪和去重帧。开发者指出未在大量视频上测试，预计会出现问题。

rss · Show HN (self-made tools) · 7月13日 20:13

**背景**: 吉他指法谱（tab）是一种吉他乐谱，表示手指在指板上的位置而非音高。Claude Vision 是一种多模态 AI 模型，能够理解和分析图像，包括读取文本和识别截图中的区域。该工具结合了这些技术，自动化了原本需要手动转录或依赖不可靠服务的流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://learn-prompting.fr/blog/claude-vision-guide">Claude Vision : Analyzing Images, Charts & Visual Documents</a></li>
<li><a href="https://www.songsterr.com/howtoreadtab.pdf">How to read tab | Songsterr Tabs with Rhythm</a></li>

</ul>
</details>

**标签**: `#AI tool`, `#GitHub`, `#computer vision`, `#music transcription`, `#CLI`

---

<a id="item-15"></a>
## [用 Xarray-SQL 在 SQL 中实现神经网络](https://github.com/xqlsystems/xarray-sql/blob/claude/xarray-sql-mnist-demo/benchmarks/nn.py) ⭐️ 8.0/10

作者使用 Xarray-SQL 库在 SQL 中完整实现了一个神经网络，表明线性代数、自动求导等神经网络操作均可表示为关系查询。 这项工作将 AI 与数据库相连，有望直接在 SQL 数据库中实现机器学习，无需移动数据，从而简化分布式训练并利用数据库优化功能。 该实现依赖将矩阵乘法表达为带聚合求和的 SQL 连接，以及将自动求导表达为 Jacobian 矩阵对角线上的逐行操作，这些都基于 Xarray-SQL 的关系数组模型。

rss · Show HN (self-made tools) · 7月13日 20:00

**背景**: SQL 传统上用于查询结构化数据，而非数值计算。Xarray-SQL 将 N 维数组映射为关系表，使 SQL 能够处理数组操作。作者扩展了这一概念，实现了自动求导和神经网络，表明神经网络训练可以是一个纯关系过程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/alxmrs/xarray-sql">GitHub - alxmrs/ xarray - sql : An experiment to query Xarray datasets...</a></li>
<li><a href="https://deepwiki.com/alxmrs/xarray-sql">alxmrs/ xarray - sql | DeepWiki</a></li>

</ul>
</details>

**标签**: `#neural network`, `#SQL`, `#database`, `#AI`, `#implementation`

---