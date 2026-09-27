---
layout: default
title: "Horizon Summary: 2026-09-27 (ZH)"
date: 2026-09-27
lang: zh
---

> 从 51 条内容中筛选出 11 条重要资讯。

---

1. [Blender Copilot：让大模型直接在你打开的场景里写并执行 Python](#item-1) ⭐️ 9.0/10
2. [KoboldCpp 内置智能体框架，自带 9 个工具](#item-2) ⭐️ 9.0/10
3. [Show HN：Reladraw——让你自己决定元素位置的关系图语言](#item-3) ⭐️ 8.0/10
4. [Drawgent：在实时 Excalidraw 画布上工作的编程智能体](#item-4) ⭐️ 8.0/10
5. [Withmcp：可系统级开关 MCP 服务器的开源启动器](#item-5) ⭐️ 7.0/10
6. [Leftovers：一个用于清理编码代理遗留进程的开源 macOS 命令行工具](#item-6) ⭐️ 7.0/10
7. [开发者用 ffmpeg.wasm 打造免上传的浏览器视频剪辑工具](#item-7) ⭐️ 7.0/10
8. [Grabbit 推出面向智能体的截图 API，支持 MCP 与一行 CLI](#item-8) ⭐️ 7.0/10
9. [修复版 GPT-OSS Jinja 模板：保留思考轮次并修补 Unsloth 引入的缺陷](#item-9) ⭐️ 7.0/10
10. [ishizuki 仓库让 Qwen3.8 Flash-Next 与小型模型在 Apple Silicon 上提速最高 3 倍](#item-10) ⭐️ 7.0/10
11. [4 张 RTX 3060 Ti 跑 27B 模型达到 120 t/s](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Blender Copilot：让大模型直接在你打开的场景里写并执行 Python](https://github.com/XEonAX/blender-copilot) ⭐️ 9.0/10

一个名为 Blender Copilot 的开源 Blender 插件在 3D 视口侧边栏中加入了一个聊天面板，用户输入一句自然语言，大模型就写出 Python 代码并直接在当前屏幕上打开的那个 Blender 场景中执行。作者称整套工作流只用一天就搭好，花费 7.18 美元的 Deepseek token，并用五句提示词、52 次工具调用、约 15 分钟生成了带后掠翼、尾翼、玻璃座舱、四组 RCS 推进器、22 个动画尾焰及完整飞行动画的科幻飞船。 它展示了一种极易复制的模式：不必微调模型，只要把宿主应用自身的脚本 API 包装成工具接口交给现成的编程大模型，让它直接操作实时状态即可。Blender 成熟的 Python API 使其成为容易下手的目标，但同样的配方适用于任何可脚本化的应用；而 7 美元这个数字也具体说明了构建 agent 工作流已经变得多么便宜。 作者给出的成本数据是 3,833 次请求、6.13 亿 token，其中 97% 命中缓存，生成一艘飞船约花费七分之一美分；值得注意的是，模型还主动检查了自己放置的推进器，发现尾部推进器正对着船体喷射，于是未经要求就重建并再次校验。作者明确表示这只是一个工具框架，并不能替代艺术家——他没有手动建模哪怕一个顶点，也没读过 Blender 插件开发文档——而他的分享中流露出的与其说是兴奋，不如说是一种矛盾心态。

rss · Show HN (self-made tools) · 9月26日 18:06

**背景**: Blender 是一款免费开源的 3D 创作套件，其功能通过 Python API（即 bpy 模块）对外开放，脚本可以据此创建物体、修改场景数据，并在 3D 视口中绘制自定义 UI 面板。这里的“Copilot”模式意味着大模型不只是给出代码让人类去粘贴，而是调用工具直接在被运行的 Blender 进程内执行 Python，因此改动落在真正打开的那个文件上，而不是需要另一个进程同步的副本上。RCS（反应控制系统）推进器是真实航天器用于控制姿态与平移的小型微调发动机，对应横滚、俯仰、偏航三个旋转轴加上三个方向的平移，合起来就是六自由度（6DoF），也是太空飞行类游戏常用的操控方式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.blender.org/api/current/index.html">Blender Python API</a></li>
<li><a href="https://en.wikipedia.org/wiki/Reaction_control_system">Reaction control system - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/6DoF">6DoF</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#GitHub repo`, `#Blender`, `#LLM automation`, `#code generation`

---

<a id="item-2"></a>
## [KoboldCpp 内置智能体框架，自带 9 个工具](https://www.reddit.com/r/LocalLLaMA/comments/1wqlyp8/introducing_koboldcpp_agent_and_a_plea_for_help/) ⭐️ 9.0/10

KoboldCpp 现已内置集成的 KoboldCpp Agent Harness，只需在 GUI 启动器的 Admin 标签页勾选一个复选框，或添加 --agent 启动参数（会打开一个新终端）即可启用。它自带 9 个内置工具，包含全部工具定义的系统提示词仅约 2k token，作者 concedo / LostRuins 将其定位为 Opencode、Codex、Claude Code 的极轻量本地替代方案。 这为本地大模型用户提供了一条几乎零配置的智能体使用路径，免去了许多人觉得繁琐的外部智能体工具链搭建过程。由于该框架体积小且直接捆绑在已在消费级硬件上运行 GGUF 模型的软件中，它降低了普通本地模型用户做基础代码编写、文件整理和自动化任务的门槛。 要有效运行，KoboldCpp Agent 至少需要 28k 上下文和 8k 生成长度（建议使用更大值），并且最好拥有至少 12GB 显存；它提供 on、auto、off 三种工具调用确认模式。它还能连接第三方后端或任何兼容 OpenAI Chat Completions 的端点，支持 AGENTS.md 和上下文压缩，并可通过加载 mcp.json 扩展工具——但需注意 MCP 工具在 KoboldCpp 服务端执行，而 Agent 工具在智能体客户端执行。

reddit · r/LocalLLaMA · /u/HadesThrowaway · 9月26日 09:13

**背景**: KoboldCpp 是一款自包含的单文件 AI 文本生成软件，用于运行 GGML 和 GGUF 模型，构建在 llama.cpp 之上，并采用 KoboldAI 风格的界面，用户几乎无需安装即可运行本地量化模型。所谓智能体框架（agent harness，又称 agent scaffolding），是指围绕大语言模型的一层软件基础设施——包括工具、记忆、状态持久化、执行环境和反馈循环——它把只会输出文本的无状态模型变成能够分多步执行动作、调用外部工具的智能体。目前流行的同类框架包括 Anthropic 的 Claude Code、OpenAI 的 Codex，以及开源的 OpenCode，后者能把大模型与软件项目连接起来，让模型按自然语言指令检查、修改代码并运行命令。同一条公告中，作者还呼吁社区帮忙对抗一个冒充 KoboldCpp 的钓鱼网站，该站点通过黑帽 SEO 在 Google 上排名靠前，诱导访客下载恶意软件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/lostruins/koboldcpp">GitHub - LostRuins/koboldcpp: Run GGUF models easily with a KoboldAI UI. One File. Zero Install. · GitHub</a></li>
<li><a href="https://en.wikipedia.org/wiki/Agent_harness">Agent harness</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenCode">OpenCode</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#local LLM`, `#KoboldCpp`, `#open source tools`, `#agent frameworks`

---

<a id="item-3"></a>
## [Show HN：Reladraw——让你自己决定元素位置的关系图语言](https://github.com/reladraw/reladraw) ⭐️ 8.0/10

Reladraw 是一门新的开源关系图（diagram）语言，作者可以自己指定元素放置的位置，而不是交给引擎自动排版，目标是把 Draw.io 这类图形工具的控制力与 Mermaid 这类文本格式的便捷性结合起来。它提供了浏览器内的 playground、简单的 npm 安装方式，以及一个兼容 Claude 的 “skill”，让人和 AI 智能体都能生成图表。 图表工具长期存在一个两难：Mermaid、Graphviz 这类自动排版语言书写快捷，但放弃了对外观的控制；Draw.io 这类编辑器精确，却耗时且不便于智能体操作。随着图表逐渐成为开发者与编码智能体之间高带宽对齐的共同媒介，一种既对智能体友好、又保留手动定位能力的格式，可能填补开发者工具链中的一块真实空白。 其语法使用 `node name ["text"] [placements] [key: value …]` 和 `edge a -> b` 这类语句，支持相对定位（例如 `from: left to: right`），并提供样式与主题选项，如 `theme: nord` 和自定义背景色。早期反馈指出一个小 bug：一条从左到右的边没有被渲染成曲线箭头；还有评论者建议，布局指令最终可被编译为绝对坐标，再对接可插拔的多种渲染后端，而不必自带单一渲染器。

hackernews · jpwalsh234 · 9月26日 17:10 · [社区讨论](https://news.ycombinator.com/item?id=49858513)

**背景**: “图表即代码”（diagram-as-code）工具让你用文本描述图形、再由软件绘制，最知名的 Mermaid 和 Graphviz 会通过布局算法自动决定节点位置。Draw.io 这类图形界面编辑器能提供像素级控制，但需要手动拖拽，对人来说繁琐，对 AI 智能体来说也难以编程操作。Reladraw 用显式的相对定位切入这一中间地带，同时还附带了一个 Claude “skill”——即基于 SKILL.md 的指令包，Claude Code 等智能体加载后即可获得这项新能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/reladraw/reladraw">GitHub - reladraw/reladraw · GitHub</a></li>
<li><a href="https://news.ycombinator.com/item?id=49858513">Show HN: Reladraw – A diagram language where you decide where to place things | Hacker News</a></li>
<li><a href="https://code.claude.com/docs/en/skills">Extend Claude with skills - Claude Code Docs</a></li>

</ul>
</details>

**社区讨论**: 评论者总体持欢迎态度，有人称其“在 AI 编码时代非常必要”，认为图表是把心智模型与智能体对齐的关键瓶颈。多位用户认同 Mermaid 适合时序图、甘特图等固定布局，却不适合作流程图这类“位置为王”的场景，而直接在 Markdown 中内嵌 SVG 很快会变得难以维护；其中一人表示相对定位大概已足够满足需求。也有人提出保留意见：有人报告了曲线箭头的渲染 bug，有人建议把渲染器与语言解耦，还有用户表示需更仔细地研读语法后才能判断其能力与便利性。

**标签**: `#ai-agents`, `#developer-tools`, `#github-repo`, `#diagramming`, `#claude-skills`

---

<a id="item-4"></a>
## [Drawgent：在实时 Excalidraw 画布上工作的编程智能体](https://tangled.org/yanndegat.tngl.sh/drawgent) ⭐️ 8.0/10

Drawgent 是一个新项目，它把一个编程智能体（coding agent）直接放到实时的 Excalidraw 画布上，让智能体可以解读、绘制并修改人类正在使用的同一块共享白板。它的 Hacker News 讨论帖很快又带来了相关成果，包括 Excalidraw 官方的 MCP 端点与服务器、一个基于 Mermaid 做智能体白板的 Obsidian 插件，以及另一个开源项目 whiteboard-agents。 这反映了一个更广泛的趋势：智能体不再局限于终端和文本文件，而是获得了共享的可视化工作空间，人与模型可以在其中共同编辑产物并相互校验改动。随着基于 MCP 的工具链逐渐成熟，白板类界面有可能成为团队与智能体一起讨论架构的标准方式。 有实际使用经验的评论者提醒说，图形格式对智能体影响很大：使用 Excalidraw 的 MCP 时，模型需要处理大量 JSON，并推算边界框和像素坐标，容易出错；而 Mermaid 或纯 HTML 能给智能体更自然的语义。也有人指出该项目仍处于早期且基本未经过充分测试，因此更适合作为比较实现思路的实验，而非生产级工具。

hackernews · parasitid · 9月26日 15:56 · [社区讨论](https://news.ycombinator.com/item?id=49857729)

**背景**: Excalidraw 是一款免费的开源虚拟白板，以手绘风格的图表、流程图和插画著称，并且可以直接在浏览器中使用、无需注册。Model Context Protocol（MCP）是 Anthropic 于 2024 年 11 月开源的一套开放标准，用于规范 Claude、ChatGPT 等 AI 应用与外部工具和数据源之间的连接方式。而编程智能体（coding agent）指的是既能生成代码又能执行代码的 AI 系统，因此可以在较少人工干预的情况下自行测试并迭代产出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/model-context-protocol">Introducing the Model Context Protocol \ Anthropic</a></li>
<li><a href="https://excalidraw.com/">Excalidraw Whiteboard</a></li>
<li><a href="https://www.openhands.dev/blog/what-are-coding-agents">What Are Coding Agents? A Developer's Guide to Agentic Coding (2026) | Jun 02, 2026</a></li>

</ul>
</details>

**社区讨论**: 讨论整体上热情且具有建设性：有用户指出 Excalidraw 官方已提供第一方 MCP 端点与服务器；有人表示现有白板方案达不到自己的需求，于是用 Mermaid 这一对智能体最友好的媒介写了 Obsidian 插件；还有人开源了类似项目 whiteboard-agents 以便对比实现。也有持保留意见者认为，画图的真正价值在于它迫使团队思考；另一位评论者则主张 HTML 被低估了，而 JSON 的边界框计算反而让智能体表现更差。

**标签**: `#ai-agents`, `#github-repos`, `#mcp`, `#excalidraw`, `#dev-tools`

---

<a id="item-5"></a>
## [Withmcp：可系统级开关 MCP 服务器的开源启动器](https://github.com/lava/withmcp) ⭐️ 7.0/10

一位开发者在 GitHub 上发布了 Withmcp，这是一个开源的工具启动器（harness launcher），可以让用户在整个系统范围内统一启用或禁用 MCP 服务器，而不必逐个修改每个工具的配置。其目的是避免 Claude Code 等智能体被未使用或已失效的 MCP 连接所干扰，从而节省上下文窗口与注意力预算。 对于需要访问需鉴权服务的智能体来说，MCP 仍是最简便的接入方式之一，但像 Claude Code 这样的主流工具却不支持临时禁用一个已配置的服务器。Withmcp 正好填补了这一空白，让同时使用多个服务的开发者无需反复删除、重加配置，就能保持上下文干净。 Withmcp 以自定义启动器的形式工作，可以为任何“看起来还算有意思”的服务配置 MCP，从而避免因登录过期等警告挤占智能体的上下文。它属于小型实用工具而非重大版本发布，发布时在 Hacker News 上仅获得 1 分且没有评论，尚未经过社区验证。

rss · Show HN (self-made tools) · 9月26日 22:35

**背景**: 模型上下文协议（MCP）是一个开放标准，最初由 Anthropic 提出，用于让 AI 应用通过标准化的“MCP 服务器”连接外部数据源、工具和工作流。由于已配置的服务器会被加载进智能体的工作上下文中，那些凭证已过期或当前用不到的连接就会制造噪音、浪费 token。Claude Code 是 Anthropic 推出的终端智能体编程工具，作者指出其 MCP 管理相当简陋，没有内置方式临时禁用一个已配置的服务器。作者还认为，尽管 MCP 的热度有所下降，但对许多需要鉴权的服务而言它仍是最直接的选择，尤其是在不希望凭证与智能体共处同一主机的情况下。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://modelcontextprotocol.io/">What is the Model Context Protocol ( MCP )? - Model Context Protocol</a></li>
<li><a href="https://github.com/modelcontextprotocol">Model Context Protocol · GitHub</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>

</ul>
</details>

**标签**: `#MCP`, `#AI agents`, `#developer tools`, `#Claude Code`, `#open source`

---

<a id="item-6"></a>
## [Leftovers：一个用于清理编码代理遗留进程的开源 macOS 命令行工具](https://github.com/arpwal/leftovers) ⭐️ 7.0/10

一位开发者在 GitHub 上发布了名为 "Leftovers" 的项目，并以 Show HN 的形式提交到 Hacker News：这是一个小型开源 macOS 工具，用于扫描那些在编码代理退出后仍在后台运行的进程。该帖子本身非常新且内容极简，抓取时仅有 2 分、0 条评论。 像 Claude Code、Codex CLI 这类本地编码代理会频繁启动 shell 命令、开发服务器、测试运行器和文件监听进程；一旦会话意外中断，这些子进程就可能变成孤儿进程继续存活。对于整天使用代理的开发者来说，这意味着 CPU 被占用、端口被霸占，下次运行时还会遇到莫名其妙的报错，因此一个专门用于清理的工具正好解决了代理式编程工作流中反复出现的真实痛点。 从现有信息来看，Leftovers 只被描述为一个带命令行界面的小型开源 macOS 工具，因此其实现细节并不明确——例如它能识别哪些代理、是通过父进程 PID、进程名启发式规则还是命令行特征来匹配进程，以及它只能列出进程还是可以直接结束它们，这些都需要去仓库中确认。它的定位是一个单一用途的窄众开发者工具，而非框架；且仅支持 macOS，在 Linux 或 Windows 上无法使用。

rss · Show HN (self-made tools) · 9月26日 22:27

**背景**: 所谓“编码代理”（coding agent），指的是一类 AI 系统，它不只是给出代码建议，而是自主地循环执行规划、修改文件和运行终端命令，Claude Code、Codex CLI 等工具就是这样工作的。由于这套循环建立在 shell 执行之上，代理可能启动长生命周期的子进程——本地 Web 服务器、数据库、测试监听器——正常退出时它们会被回收，但当会话被强杀、超时或崩溃时就未必如此。在类 Unix 系统中，这些幸存者会成为被 init 进程收养的孤儿进程，继续占用资源却没有明显归属。Leftovers 针对的正是 macOS 上的这一盲区，因为系统自带的进程监视器很难分辨某个残留进程究竟来自哪个代理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sumguy.com/what-is-an-ai-harness/">What Is an AI Harness? | SumGuy's Ramblings</a></li>
<li><a href="https://zalt.me/blog/picking-an-ai-coding-agent-vibecoders-handbook">The Vibecoder's Handbook on Picking an AI Coding Agent | zalt.me</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#macOS`, `#coding agents`, `#developer tools`, `#CLI`

---

<a id="item-7"></a>
## [开发者用 ffmpeg.wasm 打造免上传的浏览器视频剪辑工具](https://clipyouredit.com/) ⭐️ 7.0/10

一位开发者发布了一款名为 clipyouredit.com 的免费、免注册浏览器视频剪辑工具，支持裁剪、循环查找、裁切、旋转、倾斜、修补、去除音频和批量导出，且主要由 Claude 协助构建。所有处理都通过 ffmpeg.wasm 在浏览器本地完成，因此文件永远不会离开用户的电脑。 它展示了 AI 辅助开发如何让非专业人士也能快速做出真正实用、无需安装的网页工具，同时为需要上传或注册的云端视频编辑器提供了一个保护隐私的替代方案。作者还公开主张不要在剪辑环节中引入 AI，而是把 AI 当作构建工具的助手，而非内容生成器。 直线剪切采用 stream copy，因此无需重新编码即可在几秒内完成；同时提供一个可选启用的服务器选项，用于在性能较弱的机器或大文件场景下重新编码，但若访问量过大可能会崩溃。作者坦言工具远非完美，目前也尚未开源，不过他表示用 Claude 重建并不困难。

rss · Show HN (self-made tools) · 9月26日 20:19

**背景**: ffmpeg.wasm 是 FFmpeg 的 WebAssembly/JavaScript 移植版本，让这个广受欢迎的多媒体工具集能够直接在浏览器内运行，处理前会先下载约 25MB 的核心文件；它比原生 FFmpeg 慢，但能让文件留在本地、无需上传。stream copy 是一种直接沿用原有音视频流、不重新编码的技术，因此简单的裁剪能保持画质像素级一致且几乎瞬间完成，而完整的重新编码则更慢且可能降低画质。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://jeromewu.github.io/ffmpeg-wasm-a-pure-webassembly-javascript-port-of-ffmpeg/">FFmpeg . wasm , a pure WebAssembly / JavaScript port of FFmpeg</a></li>
<li><a href="https://www.solveigmm.com/blog/en/direct-stream-copy-for-mp4-and-other-videos/">Direct Stream Copy for MP4 and other videos - Blog</a></li>

</ul>
</details>

**标签**: `#browser-tools`, `#video-editing`, `#ffmpeg`, `#AI-assisted-development`, `#web-app`

---

<a id="item-8"></a>
## [Grabbit 推出面向智能体的截图 API，支持 MCP 与一行 CLI](https://www.grabbit.live/) ⭐️ 7.0/10

Grabbit 是一个新的面向智能体的截图 API，用户只需发送一个简单的 POST 请求并附带 URL，即可获得托管好的截图链接，同时提供 MCP 服务器和面向 AI 智能体的一行式 CLI 安装命令。它主打低价，标价为每次抓取 0.002 美元，采用按年统一计费、没有每月最低消费。 截图能力是 AI 智能体的常见需求——它们需要验证网页、检查渲染后的界面或获取视觉上下文，而 MCP 支持让 Claude、ChatGPT 之类的客户端无需编写定制集成代码即可调用该服务。廉价且原生面向智能体的截图服务，降低了开发者构建浏览器操作与质量检查类智能体工作流的门槛。 Grabbit 公开的价格对比声称，每次抓取 0.002 美元的价位上只有 Browserless 和 Thum.io 报价更低，而这两家都没有配套的智能体优先 CLI 与 MCP 服务器、按年统一计费以及零月度浪费。该服务可从 URL 返回像素级精确的托管图片，一行式安装命令的目的就是让智能体快速获得截图能力。

rss · Show HN (self-made tools) · 9月26日 19:46

**背景**: Model Context Protocol（MCP）是一套开放标准，用于把 AI 应用连接到外部系统，例如数据源、工具和工作流；在 MCP 出现之前，开发者必须为每个应用、每个工具编写一次性的集成代码。传统截图 API 的做法是用无头浏览器渲染网页并返回图片，广泛用于视觉回归测试、数据抓取和页面监控。Grabbit 把这两者结合起来，将截图能力封装为智能体可直接调用的 MCP 工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.grabbit.live/">Grabbit: the agent - first screenshot API</a></li>
<li><a href="https://modelcontextprotocol.io/">What is the Model Context Protocol ( MCP )? - Model Context Protocol</a></li>
<li><a href="https://www.foundrlist.com/product/grabbit-2">Grabbit — Send a URL, get a hosted screenshot . | FoundrList</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#MCP`, `#developer tools`, `#screenshot API`, `#CLI`

---

<a id="item-9"></a>
## [修复版 GPT-OSS Jinja 模板：保留思考轮次并修补 Unsloth 引入的缺陷](https://www.reddit.com/r/LocalLLaMA/comments/1wr0wki/improved_and_fixed_template_for_gptoss_again/) ⭐️ 7.0/10

LocalLLaMA 用户 u/arbv 在 Hugging Face 上发布了修正版 GPT-OSS 聊天模板（arbv/gpt-oss-fixed-jinja-template），修复了从 Unsloth 模板继承而来的严重缺陷，并新增了 preserve_thinking 选项。该缺陷使得消息渲染循环在历史助手消息同时包含 content 和 thinking 时只输出推理（analysis 通道）内容，从而在重放聊天历史时静默丢掉模型真正的回答。 由于在许多本地推理工具中保留此前的推理轮次已成为默认行为，并且 API 层面也可能出现这种情况，该缺陷会静默降低所有使用 GPT-OSS 20B 或 120B 的用户的多轮对话质量。这一修复恢复了正确的上下文，使模型不再丢失对话脉络，因此对本地大模型用户和工具开发者都有直接价值。 出问题的 Jinja 分支取自 Unsloth 的模板，对于同时含有 thinking 和 content 的助手轮次，它只渲染 message.thinking 却从不渲染 message.content，而且注释中“推理内容会被丢弃”的说法也是错误的；OpenAI 的参考模板中并不存在这个分支。作者表示 GPT-OSS 20B 有时会彻底跑偏，而 120B 模型足够聪明，仅凭推理轨迹就能恢复上下文；同时指出 preserve_thinking 有望通过前缀缓存加快多轮推理，代价是更高的 token 消耗。

reddit · r/LocalLLaMA · /u/arbv · 9月26日 20:35

**背景**: GPT-OSS 是 OpenAI 推出的开放权重推理模型系列（gpt-oss-20b 与 gpt-oss-120b），它会把内部的 analysis 推理通道与 final 回答通道交错输出。聊天模板是用 Jinja2 编写的程序，负责把带角色标记的消息列表转换成模型期望的精确 token 序列，Hugging Face transformers、Ollama、llama.cpp 等工具都依赖它来格式化提示词。Unsloth 是一个广受欢迎的开源库，用于在本地运行和微调大模型，其 GPT-OSS 模板被大量复用——这也正是这个复制粘贴式缺陷得以扩散的原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/openai/gpt-oss">GitHub - openai/ gpt - oss : gpt - oss -120b and gpt - oss -20b are two...</a></li>
<li><a href="https://github.com/unslothai/unsloth">GitHub - unslothai/ unsloth : Local UI to run and train LLMs and...</a></li>
<li><a href="https://github.com/jndiogo/LLM-chat-templates">GitHub - jndiogo/ LLM - chat - templates : Jinja2 chat templates for...</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#gpt-oss`, `#chat-template`, `#jinja`, `#reasoning-models`

---

<a id="item-10"></a>
## [ishizuki 仓库让 Qwen3.8 Flash-Next 与小型模型在 Apple Silicon 上提速最高 3 倍](https://www.reddit.com/r/LocalLLaMA/comments/1wr1qlz/run_qwen38flashnext_and_tiny_models_on_apple/) ⭐️ 7.0/10

一位 LocalLLaMA 用户（u/VagabondTruffle）发布了名为 ishizuki 的 GitHub 仓库（struffl/ishizuki），它通过 MLX 让 Qwen3、Qwen3.8-Flash-Next 及其他小型模型在 Apple Silicon 上运行速度最高提升 3 倍，并公开邀请他人继续贡献优化。 任何在 Mac 上跑本地模型的人，都可能在不换硬件的情况下获得显著提速，这也让 Apple Silicon 这条本地大模型推理路线在面对基于 CUDA 的方案时更具竞争力。 作者声称自己曾长期位居 MLX.fast 排行榜首位，并且在 M5 以下的芯片上仍保持第一，不过原帖内容很短，并未详细说明具体的技术手段或可复现的基准测试数据。

reddit · r/LocalLLaMA · /u/VagabondTruffle · 9月26日 21:10

**背景**: MLX 是苹果为 Apple Silicon 打造的开源数组计算框架，针对苹果芯片的统一内存架构设计，并提供与 NumPy 类似、开发者容易上手的 API。Qwen3 和 Qwen3.8-Flash-Next 是阿里巴巴通义千问（Qwen）系列的模型，在本地推理场景中被广泛使用。在 Mac 上本地运行这类模型，意味着性能要靠 Metal 与统一内存来挖掘，而非独立显卡，因此像本文这类框架层与算子层的优化会直接体现为每秒生成 token 数的提升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://mlx-framework.org/">MLX</a></li>
<li><a href="https://huggingface.co/Qwen/Qwen3.8-Flash-Next">Qwen/Qwen3.8- Flash - Next · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#apple-silicon`, `#mlx`, `#github-repo`, `#inference-optimization`

---

<a id="item-11"></a>
## [4 张 RTX 3060 Ti 跑 27B 模型达到 120 t/s](https://www.reddit.com/r/LocalLLaMA/comments/1wqv9o8/getting_stupidly_good_results_on_my_4x3060ti_setup/) ⭐️ 7.0/10

一位 LocalLLaMA 用户分享了自己用闲置挖矿用 RTX 3060 Ti（每张 8GB，功耗限制在 110W）搭建的四卡机器：在放弃 llama.cpp、改用张量并行的推理方案后，EXL3 量化模型上以约 70 t/s 跑 196k 上下文，而在 HyperQwen + vLLM 的 W4A16 方案上以约 120 t/s 跑 150k 上下文。帖子里还给出了每一步所用的 HuggingFace 模型与 GitHub 仓库链接。 这说明张量并行可以把一堆便宜的二手 8GB Ampere 显卡变成真正可用的本地推理服务器，成为购买单张 24GB 3090/4090 之外的另一条路。由于帖子给出了具体的仓库与模型链接，这套方案对其他在普通硬件上跑本地模型的爱好者来说可以直接复现。 把 KV cache 量化为 kv8 后可以解锁完整的 262k 上下文，但吞吐会回落到约 70 t/s；作者还提到同时运行两个 agent 几乎不会造成降速。四张卡每张都被限制在 110W，因此这些数据来自一个刻意压低功耗的配置，而非火力全开的机器。

reddit · r/LocalLLaMA · /u/DontWinFrensWthSalad · 9月26日 16:47

**背景**: 张量并行会把单个模型的层和矩阵乘法切分到多张 GPU 上，从而让装不进单卡显存的模型也能被服务。llama.cpp 不支持这一特性，因此这位用户转向了 ExLlamaV3——其 EXL3 量化格式是 QTIP 的精简变体，目标是让消费级硬件也能用上最前沿的量化——随后又用上了针对 Ampere 架构 GPU 优化的推理栈 HyperQwen。W4A16 指 4 比特权重配 16 比特激活，是低显存场景中常见的量化方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/turboderp-org/exllamav3">GitHub - turboderp-org/ exllamav 3 : An optimized quantization and...</a></li>
<li><a href="https://github.com/syv-ai/HyperQwen">GitHub - syv-ai/ HyperQwen : Serve large Qwen models fast on the...</a></li>
<li><a href="https://huggingface.co/Ar4ikov/Qwen3.8-27B-AWQ-W4A16-ASYM-HyperQwen">Ar4ikov/ Qwen 3.8-27B-AWQ-W4A16-ASYM- HyperQwen · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#inference-optimization`, `#tensor-parallelism`, `#github-repo`, `#multi-gpu`

---