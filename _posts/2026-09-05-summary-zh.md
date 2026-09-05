---
layout: default
title: "Horizon Summary: 2026-09-05 (ZH)"
date: 2026-09-05
lang: zh
---

> 从 57 条内容中筛选出 12 条重要资讯。

---

1. [在 macOS 上用编码智能体与 Blender 协作](#item-1) ⭐️ 9.0/10
2. [♻️ 英伟达发布 PAIR 软件，闲置家用电脑可组本地 AI 集群](#item-2) ⭐️ 9.0/10
3. [Fast Cut Video：面向 AI 智能体的 Codex 构建轻量视频剪辑工具](#item-3) ⭐️ 8.0/10
4. [Claude 技能：用三个“实习评审”代理对抗式批判你的设计决策](#item-4) ⭐️ 8.0/10
5. [Ditch：在 macOS 上同时管理多个 Codex 代理的开源桌面应用](#item-5) ⭐️ 8.0/10
6. [Qwen3.8 Flash Next 模板对比：Sharp 稳定，Fixed 随推理强度提升](#item-6) ⭐️ 8.0/10
7. [Otaku：支持 Web 与终端界面的开源 LLM 前端](#item-7) ⭐️ 8.0/10
8. [GPT-6 Astra 在鹈鹕 SVG 对比网格中胜过 GPT-5.6](#item-8) ⭐️ 7.0/10
9. [Twinrun：以相同输入对比新旧代码输出](#item-9) ⭐️ 7.0/10
10. [PHNTM-One：基于树莓派 5 的本地 AI 桌面助手](#item-10) ⭐️ 7.0/10
11. [ChatPanel 推出 Firefox 版，让 AI 智能体翻阅会议记录](#item-11) ⭐️ 7.0/10
12. [Qwen3.8-27B 推理引擎对比：NInfer 速度领先，质量旗鼓相当](#item-12) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [在 macOS 上用编码智能体与 Blender 协作](https://simonwillison.net/2026/Sep/5/blender-coding-agents-macos/) ⭐️ 9.0/10

西蒙·威利森（Simon Willison）发布了一篇 TIL 教程，展示如何在 macOS 上用编码智能体驱动 Blender：从 blender.org 安装完整的 Blender 应用后，ChatGPT Codex 只需根据自然语言提示（例如“一只骑自行车的鹈鹕”），就能编写并运行 Blender Python API 脚本来渲染完整的三维场景。他还通过“添加背景和大量点缀”“让它好得多”等后续提示不断迭代完善画面。 这是把 AI 智能体用于创意三维工作的一条具体且低成本的技巧——无需手动建模，只需自然语言请求就能得到渲染好的场景。它演示了一种更广泛的模式：编码智能体正在充当大语言模型与桌面创意应用之间的桥梁，有望让非专业人士更容易进行三维原型创作。 关键要求是把 Blender 作为常规 macOS 应用安装，使智能体可以通过 /Applications/Blender 调用它；之后智能体借助 Blender 内嵌的 Python 解释器和 bpy 模块来构建场景。西蒙公开了相关产物：这篇 TIL 页面，以及存放最终脚本 work/pelican_final.py 的 GitHub 仓库 simonw/gpt-6-astra-blender-pelican-bicycle。

rss · Simon Willison · 9月5日 15:51

**背景**: 编码智能体（coding agents）是 AI 开发者工具，能力远超自动补全：它们不仅“建议”，更会“行动”——可以根据自然语言描述实现功能、调试问题，并在开发者的指导下驱动“编辑—测试—修复”的循环。Blender 是一款内嵌 Python 解释器的免费开源三维创作套件，其 bpy 模块暴露了 Blender 的数据、类和函数，因此几乎任何建模或渲染操作都可以用脚本完成。由于 Blender 可以像普通 macOS 应用一样从命令行启动，它自然成为智能体易于操控的目标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.openhands.dev/blog/what-are-coding-agents">What Are Coding Agents? A Developer's Guide to Agentic Coding (2026)</a></li>
<li><a href="https://agentic.ai/best/coding-agents">20 Best AI Coding Agents in 2026 — Agentic.ai</a></li>
<li><a href="https://docs.blender.org/api/current/info_overview.html">API Overview - Blender Python API</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Blender`, `#ChatGPT Codex`, `#prompt engineering`, `#creative coding`

---

<a id="item-2"></a>
## [♻️ 英伟达发布 PAIR 软件，闲置家用电脑可组本地 AI 集群](https://www.techspot.com/news/113742-nvidia-pair-software-turns-idle-home-computers-local.html) ⭐️ 9.0/10

英伟达的开源 PAIR 软件可将配备 RTX GPU、DGX Spark 或 Mac 的闲置家用电脑连接成本地 AI 集群，支持 Ollama/LM Studio，实现私有化本地推理。

telegram · zaihuapd · 9月5日 02:55

**标签**: `#AI infrastructure`, `#Local AI`, `#NVIDIA`, `#Open-source tool`, `#Self-hosting`

---

<a id="item-3"></a>
## [Fast Cut Video：面向 AI 智能体的 Codex 构建轻量视频剪辑工具](https://github.com/modecir/fast-cutvid) ⭐️ 8.0/10

Fast Cut Video 是一个新发布在 GitHub 上的开源工具，用于在不使用重型编辑器的情况下快速剪辑视频，并专为 AI 智能体驱动的视频工作流而设计。作者表示，该工具借助 OpenAI Codex 在几小时内开发完成，目前仅在 Apple Silicon Mac 上测试过。 它解决了一个常见痛点：AI 智能体可以处理转录，但无法自行做出精确的剪辑和节奏判断。通过提供一个轻量、便于智能体对接的剪辑工具，它可以让人不必再打开 Premiere 或 DaVinci Resolve 这类功能完善的大型软件，从而更容易构建自动化视频工作流。 该项目托管在 github.com/modecir/fast-cutvid，属于早期发布的演示作品；作者明确表示目前仅在 Silicon Macs 上测试过，并欢迎反馈。该应用可将一个或多个视频加载到时间轴上，并导出智能体能读取的剪辑片段，以便继续后续流程。

rss · Show HN (self-made tools) · 9月5日 21:06

**背景**: OpenAI Codex 是 OpenAI 推出的 AI 编程智能体，于 2025 年 4 月以 Codex CLI 形式发布，可根据自然语言指令编写和修复代码、运行命令并完成软件工程任务。类似 Codex 这样的工具让开发者能够快速搭建小型实用程序。在 AI 驱动的视频工作流中，大型语言模型智能体往往负责转录和素材选择等任务，但仍难以完成时间轴上的精确剪辑，因此一个专门的轻量级剪辑工具正好填补了这一缺口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent)">OpenAI Codex (AI agent) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenAI_Codex_(language_model)">OpenAI Codex (language model) - Wikipedia</a></li>

</ul>
</details>

**标签**: `#video-editing`, `#AI-agents`, `#open-source`, `#workflow`, `#GitHub`

---

<a id="item-4"></a>
## [Claude 技能：用三个“实习评审”代理对抗式批判你的设计决策](https://github.com/alpbahadur/interns-review-plugin) ⭐️ 8.0/10

这篇 Show HN 帖子介绍了一款名为“interns-review-plugin”的 Claude Skill，它会自动产生三个对抗性代理来批评用户的设计决策。作者建议用户把问题背景写入文件，让这些代理阅读，然后把它们的反馈当作没有经验的新手实习生意见，而不是权威判断。 它为 AI 辅助设计中的对抗性自我审查提供了一个具体、可复用的工作流，对想要发现自身盲点的构建者很有价值。随着 Claude Skills 和多代理工作流的发展，这种模式展示了一种无需重型基础设施就能挑战自己设计假设的轻量方法。 该工作流特意告诉用户不要过度工程化（over-engineer），只需记录批评意见并据此进行批判性自我评估。这个 Skill 通过 GitHub 仓库 alpbahadur/interns-review-plugin 分发，但帖子本身没有提供代码或实现细节。

rss · Show HN (self-made tools) · 9月5日 19:27

**背景**: Claude Skills 是包含指令、脚本和资源的文件夹，Claude 可以在任务相关时按需加载，将专业知识打包用于专门任务。这个帖子的想法与更广泛的“多代理辩论”（multi-agent debate）和自我反思研究方向一致：通过让多个 LLM 代理对输出进行批判或辩论来提升推理能力并发现错误。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/blog/skills">Introducing Agent Skills | Claude by Anthropic</a></li>
<li><a href="https://arxiv.org/html/2510.01295">The Social Laboratory: A Psychometric Framework for Multi - Agent ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Claude Skill`, `#design review`, `#workflow`, `#GitHub`

---

<a id="item-5"></a>
## [Ditch：在 macOS 上同时管理多个 Codex 代理的开源桌面应用](https://theditch.dev/) ⭐️ 8.0/10

Ditch 是一款面向 macOS 的开源本地桌面应用，帮助开发者同时管理运行在不同项目中的多个 OpenAI Codex 代理。社区版已连同源码发布在 GitHub 上，无需账号或邮箱即可下载使用。 同时运行多个编码代理很容易变得混乱，因此一个专门的管理层可以帮助开发者保留上下文并减少手动开销。像 Ditch 这样的工具让 AI 代理工作流在多任务开发中真正可用，而不是迫使开发者手动切换多个终端会话。 Ditch 目前专注于 macOS 上的本地 Codex 工作流，作者还在尝试远程控制、跨代理共享上下文以及更高级的编排功能。本地运行时保持开源，以便在官方应用之外被扩展和集成到其他工作流中。

rss · Show HN (self-made tools) · 9月5日 17:48

**背景**: Codex 代理是构建在大语言模型之上的 AI 编程助手，能够阅读代码仓库、执行命令并在版本控制下修改代码。OpenAI 的 Codex CLI 是一种在开发者本机运行的轻量级编码代理，仓库中的 AGENTS.md 文件可以指导 Codex 如何浏览代码库以及运行测试。当开发者在多个项目中同时运行多个这类代理时，用于跟踪会话和关注请求的管理工具就变得越来越必要。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-codex/">Introducing Codex | OpenAI</a></li>
<li><a href="https://github.com/openai/codex">GitHub - openai/codex: Lightweight coding agent that runs in ...</a></li>
<li><a href="https://www.verdent.ai/guides/codex-agents-md-explained">Codex AGENTS .md Explained: How Team... - Verdent Guides</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Codex`, `#agent management`, `#open source`, `#dev tools`

---

<a id="item-6"></a>
## [Qwen3.8 Flash Next 模板对比：Sharp 稳定，Fixed 随推理强度提升](https://www.reddit.com/r/LocalLLaMA/comments/1w84mod/qwen38_flash_next_templates_comparison/) ⭐️ 8.0/10

一位 Reddit 用户使用 mini-SWE-agent 2.4.6，在 SWE-bench Verified 的 100 任务切片上，以 medium 和 xhigh 两种推理强度测试了 Qwen3.8 Flash Next 的三种提示词模板：Stock、Fixed 和 Sharp。Sharp 在两种设置下均解决 94 个任务，而 Fixed 从 87 个升至 98 个，Stock 从 91 个升至 99 个。 结果显示出提示词模板与推理预算之间存在明显的交互作用：Sharp 在 medium 推理强度下是最强的模板，但启用 xhigh 推理后 Stock 和 Fixed 反而反超。这为开发者在 SWE-bench 类场景中运行编码模型时，如何权衡准确率与延迟、成本提供了实用的经验法则。 Sharp 在两种推理强度下均解决 94/100 任务，但在 xhigh 下其中位推理 token 增加 46.5%，中位墙钟时间增加 53.4%，说明其在 medium 强度下已接近饱和。Stock 从 xhigh 中获益最大（增加 8 个任务，从 91 升至 99），但总墙钟时间飙升至 4 小时 31 分；在 xhigh 下按每个解决任务计算，Sharp 的 token 效率仍然最高（14,541 个输出 token），而 Stock 和 Fixed 约为 17,000 个。

reddit · r/LocalLLaMA · /u/HeDo88TH · 9月5日 16:02

**背景**: SWE-bench Verified 是一个被广泛使用的基准测试，由 OpenAI 整理，用于评估大语言模型解决真实 GitHub 议题的能力。本次推理使用了 SGLang（一个开源推理服务框架）和 NVFP4（一种面向 NVIDIA GPU 的 4 位浮点量化格式，可降低模型内存占用）。推理强度（reasoning effort）控制模型在给出答案前进行多少内部思维链计算，代价是速度和算力消耗增加。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.swebench.com/SWE-bench/">Overview - SWE-bench</a></li>
<li><a href="https://docs.sglang.io/">Welcome to SGLang - SGLang Documentation</a></li>
<li><a href="https://sovgrid.org/blog/nvfp4-quantization-explained/">NVFP 4 Quantization Explained (For Engineers Who Skipped the Paper)</a></li>

</ul>
</details>

**标签**: `#LLM`, `#prompting`, `#SWE-bench`, `#Qwen`, `#benchmark`

---

<a id="item-7"></a>
## [Otaku：支持 Web 与终端界面的开源 LLM 前端](https://www.reddit.com/r/LocalLLaMA/comments/1w85blf/otaku_an_llm_frontend/) ⭐️ 8.0/10

Otaku 是一款由个人开发者发布的免费开源 LLM 前端，提供 Web 界面和终端界面。它支持 Ollama、LM Studio 等本地后端，也支持 OpenRouter、NanoGPT 等云服务商。 作为 SillyTavern 和 Open WebUI 的替代品，Otaku 让用户在一个工具中完成角色扮演和通用聊天，且可对接本地或云端模型。其 MIT 许可证和简便安装方式，使它成为开发者探索 LLM 界面的易用选择。 该项目可通过“uv tool install otaku”安装，Web 界面默认地址为 http://localhost:9600。首次启动时会自动检测 Ollama、oMLX、LM Studio、llama.cpp 和 KoboldCpp，并导入两个示例故事。

reddit · r/LocalLLaMA · /u/Fickle_Tradition4491 · 9月5日 16:29

**背景**: LLM 前端是让用户无需编写代码即可与大语言模型聊天的用户界面。SillyTavern 专注于角色扮演场景，而 Open WebUI 则是一个面向 Ollama 及 OpenAI 兼容 API 的通用自托管聊天平台。Otaku 试图兼顾这两种用途；lore extraction（世界观抽取）是角色扮演功能，可在普通聊天时关闭。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/SillyTavern/SillyTavern">GitHub - SillyTavern/SillyTavern: LLM Frontend for Power ...</a></li>
<li><a href="https://docs.openwebui.com/">Home / Open WebUI</a></li>

</ul>
</details>

**标签**: `#LLM frontend`, `#Open Source`, `#Ollama`, `#Chat UI`, `#AI tool`

---

<a id="item-8"></a>
## [GPT-6 Astra 在鹈鹕 SVG 对比网格中胜过 GPT-5.6](https://simonwillison.net/2026/Sep/4/astra-pelicans/) ⭐️ 7.0/10

西蒙·威利森获得了 GPT-6 Astra 的访问权限，并用它分别以低、中、高、极高和最高五个推理档位生成“骑自行车的鹈鹕”SVG，与 GPT-5.6 Sol、Terra、Luna 的结果进行网格对比。Astra 从低到极高的每一档输出都优于 GPT-5.6 Sol 的最佳输出，其中 Astra 低档结果仅需 9.55 美分，却胜过所有档位的 GPT-5.6 Sol 模型。 这类动手对比提供了一种可复用的 LLM 评测方法，通过划分推理档位来衡量输出质量，并显示出 GPT-6 Astra 在单位成本质量上的明显优势。它还提出了一个耐人寻味的问题：Astra 与 Luna 之间可能存在更紧密的技术关联，这可能影响开发者的模型选型和成本规划。 测试中，Astra 和 Luna 均只用了 16 个输入 token，而 Sol 和 Terra 用了 26 个，这暗示它们在分词或提示处理上可能有共通之处。GPT-6 Astra 不支持 reasoning=none，价格约为每百万输入 token 10 美元、每百万输出 token 50 美元，几乎是 Sol（5/30 美元）的两倍，但 Astra 更低的 token 消耗使实际价差缩小。

rss · Simon Willison · 9月4日 23:59

**背景**: 推理模型（Reasoning LLM）是能够在输出最终答案前，先把复杂问题拆解为中间“链式思考”步骤的大语言模型，从而提升数学、编程等任务的准确性。推理时间扩展（又称测试时计算）指在生成答案时投入更多算力来换取更好的输出质量。GPT-6 Astra 是 OpenAI 最新旗舰模型，提供从 low 到 max 共五个推理强度档位。西蒙·威利森一直使用“骑自行车的鹈鹕”SVG 作为统一的创意测试题，用来跨模型比较绘图能力与成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GPT-6_Astra">GPT-6 Astra - Wikipedia</a></li>
<li><a href="https://developers.openai.com/api/docs/models/gpt-6-astra">GPT-6 Astra Model | OpenAI API</a></li>
<li><a href="https://magazine.sebastianraschka.com/p/understanding-reasoning-llms">Understanding Reasoning LLMs - by Sebastian Raschka, PhD</a></li>

</ul>
</details>

**标签**: `#GPT-6 Astra`, `#model comparison`, `#reasoning levels`, `#SVG generation`, `#LLM evaluation`

---

<a id="item-9"></a>
## [Twinrun：以相同输入对比新旧代码输出](https://github.com/prian3003/twinrun) ⭐️ 7.0/10

Twinrun 是一个在 GitHub 上发布的新开源工具，它能用相同的输入分别运行修改前和修改后的代码，并报告输出结果在哪些地方不同。它主要面向重构和回归测试场景。 手动确认重构或 AI 生成的补丁是否保持原有行为，既耗时又容易出错。Twinrun 将输出比对自动化，帮助开发者在合并前发现非预期的行为变化。 Twinrun 的仓库介绍是：用相同的输入分别运行修改前后的代码，并报告输出在哪些地方不同。在 Show HN 发布时，该项目获得 1 分且有 0 条评论，表明它仍处于早期阶段并希望获得开发者反馈。

rss · Show HN (self-made tools) · 9月5日 22:08

**背景**: 重构指的是在不改变代码外部行为的前提下调整代码结构，因此开发者需要通过回归测试来确认重构没有破坏功能。Twinrun 将“用相同输入运行新旧版本并比对输出”这一常见验证步骤自动化。在审查大型补丁或由 AI 编程工具生成的改动时，这种方法尤其有用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/prian3003/twinrun">GitHub - prian3003/twinrun: Run the old and the new version ...</a></li>

</ul>
</details>

**标签**: `#developer-tools`, `#testing`, `#refactoring`, `#github`

---

<a id="item-10"></a>
## [PHNTM-One：基于树莓派 5 的本地 AI 桌面助手](https://www.phntmcore.com/) ⭐️ 7.0/10

作者打造了 PHNTM-One，一个运行在 8GB 树莓派 5 上的自包含本地 AI 助手，通过 Ollama 运行 Gemma 3 4B，并集成了 whisper.cpp 语音识别、Piper 语音合成、本地 RAG 和持久化记忆。该项目定位为类似家电的个人助理，而非普通的树莓派演示项目。 该项目展示了一种以所有权为先的云端 AI 助手替代方案，让用户掌控硬件、记忆、文件与恢复路径。同时，它展示了应对小模型局限性的实用工程手段，与本地 AI 和边缘 AI 日益增长的趋势密切相关。 该系统运行在 8GB 内存的树莓派 5 上，通过 Ollama 使用 Gemma 3 4B 模型，采用 whisper.cpp 做语音转文字、Piper 做语音合成、本地 RAG 处理文档查询，并用 SQLite 存储持久化记忆。作者指出其权衡包括树莓派 5 上冷模型加载较慢，以及 4B 模型的推理和知识局限；为此，系统通过如实表达不确定性、基于文档的可靠回答、有界记忆和可恢复故障设计来弥补。

rss · Show HN (self-made tools) · 9月5日 21:03

**背景**: Ollama 是一个开源平台，用于在本地计算机上运行和管理大语言模型，提供命令行界面和 REST API。whisper.cpp 是 OpenAI Whisper 模型的 C/C++移植版，用于语音识别；Piper 则是一个快速的本地神经语音合成系统。RAG（检索增强生成）让模型利用检索到的文档来回答问题，树莓派则是一种低成本单板计算机。Gemma 3 4B 是体积较小的开放权重模型，使得完全本地的助手运行成为可能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Ollama">Ollama</a></li>
<li><a href="https://github.com/ggml-org/whisper.cpp">GitHub - ggml-org/ whisper . cpp : Port of OpenAI's Whisper model in...</a></li>
<li><a href="https://github.com/rhasspy/piper">GitHub - rhasspy/piper: A fast, local neural text to speech ...</a></li>

</ul>
</details>

**标签**: `#AI assistant`, `#local AI`, `#Raspberry Pi`, `#Gemma`, `#RAG`

---

<a id="item-11"></a>
## [ChatPanel 推出 Firefox 版，让 AI 智能体翻阅会议记录](https://chatpanel.net/) ⭐️ 7.0/10

ChatPanel 是一款主打隐私的 AI 智能体浏览器扩展，此前已支持 Chrome 和 Edge，现已正式支持 Firefox。该扩展可捕获 Zoom、Teams、Google Meet 和 Webex 等浏览器内会议的转录内容，并通过 MCP 服务器将其提供给 Codex、Claude 等 CLI 智能体。 这种集成将日常会议和笔记数据直接连接到强大的 CLI 编程智能体，使开发者可以在 Codex、Claude 等工具内部直接查询自己的会议历史。随着 MCP 逐渐成为 AI 模型与外部数据之间的标准桥梁，ChatPanel 展示了一种实用模式：在保持个人生产力数据本地化的同时，仍能让 AI 智能体使用这些数据。 该扩展支持任何模型提供商以及 webllm，并以隐私优先的方式在本地保存笔记、聊天和会议内容。要让外部 CLI 智能体访问这些数据，用户需要安装 bridge 或 gateway 组件，由这些组件暴露一个 MCP 服务器，用于查询已捕获的内容。

rss · Show HN (self-made tools) · 9月5日 19:30

**背景**: 模型上下文协议（Model Context Protocol，简称 MCP）是一个开源标准，最初由 Anthropic 推出，允许 Claude 等 AI 应用连接外部数据源、工具和工作流，常被比喻为“AI 的 USB-C 接口”。CLI 智能体则是运行在终端中的 AI 工具，它们接收自然语言任务，规划修改、执行 shell 命令和测试，并不断迭代直到任务完成。ChatPanel 正是利用 MCP 将个人浏览器数据（如会议记录或聊天日志）与这些驻留在终端里的编程智能体连接起来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro">What is the Model Context Protocol (MCP)? - Model Context ...</a></li>
<li><a href="https://copilot-alternatives.com/cli-agents/">CLI Agents - Copilot Alternatives</a></li>

</ul>
</details>

**标签**: `#AI Agent`, `#MCP`, `#Browser Extension`, `#Meeting Transcription`, `#Privacy`

---

<a id="item-12"></a>
## [Qwen3.8-27B 推理引擎对比：NInfer 速度领先，质量旗鼓相当](https://www.reddit.com/r/LocalLLaMA/comments/1w821fg/ninfer_vs_llamacpp_vs_vllm_quality_speed/) ⭐️ 7.0/10

一位开发者在单块 RTX 5090 上，用一个真实 HVAC 内容管线中的自定义长上下文生产任务，对 NInfer、llama.cpp 和 vLLM 运行 Qwen3.8-27B 进行了基准测试。在可比的质量测试中三者在统计上没有差异，而 NInfer 的 prefill 和长上下文 decode 速度分别比 llama.cpp 最多快 4.7 倍和 2.8 倍。 单卡本地推理正从实验性玩法走向生产级服务，并发请求处理与长上下文保留能力已成为不可或缺的功能。这项测试提供了实用的参考信号：在真实负载下，专用推理引擎可以带来大幅速度提升，同时不损害输出质量。 参与对比的引擎包括 llama.cpp（Q5_K_M GGUF、q5_1 KV、parallel=1）以及 vLLM/NInfer（NVFP4、FP8 KV）；上下文窗口分别为 196K、262K、240K，GPU 是放在 OCuLink eGPU 坞中的 RTX 5090。需要注意：NInfer 因不支持 json_mode 跳过了结构化抽取项，vLLM 的速度数据因 perf probe 使用 wall-clock 计时而未被纳入主对比表。

reddit · r/LocalLLaMA · /u/bengizmoed · 9月5日 14:20

**背景**: NInfer 是一个从零编写的 C++/CUDA 推理引擎，专为在 NVIDIA RTX 5090 上运行特定 Qwen checkpoint 并实现最大单卡性能而设计。NVFP4 是 NVIDIA 的 4 位浮点量化格式，用于在 Blackwell GPU 上实现高效的低精度推理，通常只带来有限的精度损失。多 token 预测（MTP）是一种投机解码技术：模型一次性预测多个未来 token，无需单独的 draft model 即可提升生成速度。llama.cpp 和 vLLM 则是广泛使用的开源推理与服务框架，在兼容性、批处理与并发性上各有取舍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Neroued/ninfer">GitHub - Neroued/ ninfer : High-performance single-GPU inference for...</a></li>
<li><a href="https://developer.nvidia.com/blog/introducing-nvfp4-for-efficient-and-accurate-low-precision-inference/">Introducing NVFP4 for Efficient and Accurate Low-Precision ...</a></li>
<li><a href="https://arxiv.org/abs/2502.09419">[2502.09419] On multi-token prediction for efficient LLM ... On multi-token prediction for efficient LLM inference - arXiv.org Multi-Token Prediction for Faster and Efficient LLMs Awesome Multi-Token Prediction (MTP!) - GitHub MTP (Multi-Token Prediction) - vLLM How Multi-Token Prediction Makes Local LLMs Faster – Without ... Multi-Token Prediction (MTP) | Sebastian Raschka, PhD</a></li>

</ul>
</details>

**标签**: `#Local LLM`, `#Inference Benchmark`, `#vLLM`, `#llama.cpp`, `#RTX 5090`

---