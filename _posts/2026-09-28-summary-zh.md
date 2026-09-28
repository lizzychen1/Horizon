---
layout: default
title: "Horizon Summary: 2026-09-28 (ZH)"
date: 2026-09-28
lang: zh
---

> 从 50 条内容中筛选出 11 条重要资讯。

---

1. [Show HN：AstraBox——Claude Managed Agents 的开源自托管替代方案](#item-1) ⭐️ 8.0/10
2. [在 llama.cpp 中对「模糊词」施加负 logit 偏置可提升 Qwen 准确率](#item-2) ⭐️ 8.0/10
3. [Qwen 27B 在单张 RTX 4090 上本地生成动态图形](#item-3) ⭐️ 8.0/10
4. [开发者用 Qwen 与自建 MCP 让大模型自动玩《魔兽世界》](#item-4) ⭐️ 8.0/10
5. [Simon Willison 发布 2026 年 LLM 发展回顾主题演讲](#item-5) ⭐️ 7.0/10
6. [Show HN：Vanish 让你的命令行任务在云端运行](#item-6) ⭐️ 7.0/10
7. [Squint：在屏幕上拖出一个选区，直接问 AI](#item-7) ⭐️ 7.0/10
8. [Naive-N0.5-Flash：309B MoE 编程模型，原生 1M 上下文](#item-8) ⭐️ 7.0/10
9. [LocalLLaMA 用户在 48GB M4 Pro 上以 131K 上下文运行 Qwen3.8-Flash-Next](#item-9) ⭐️ 7.0/10
10. [美团 LongCat-2.5-Preview 在 OpenCode 免费开放两周](#item-10) ⭐️ 7.0/10
11. [MiniMax M3.1-Flash-Preview 上线 MiniMax Code 平台](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Show HN：AstraBox——Claude Managed Agents 的开源自托管替代方案](https://github.com/Colton-z/AstraBox) ⭐️ 8.0/10

一条 Show HN 帖子发布了 AstraBox 的链接，这是用户 Colton-z 在 GitHub 上的一个仓库，定位为 Claude Managed Agents 的开源、自托管替代方案。帖子本身没有提供任何功能、架构或安装说明，只有仓库地址。 Claude Managed Agents 这类托管式 agent 平台把 agent harness 和基础设施都封装起来，用起来方便，但也让团队绑定在厂商的运行时和计费方式上；如果出现一个可靠的开源替代品，开发者就能在自己的机器上跑同样的 agent loop，并完全掌控数据和工具执行。当前开发者对可自行部署的 agent 工具需求很高，因此即便只是早期项目，也很容易获得关注。 这条提交几乎没有验证信号：在 Hacker News 上仅获得 2 分、0 条评论，其高分理由中也明确指出帖子缺少功能、架构或安装说明，读者只能自己点进仓库盲看。另外，“AstraBox”这个名字与至少一个无关项目重名（同名 Chrome DevTools 扩展），因此搜索该词时结果比较杂乱。

rss · Show HN (self-made tools) · 9月27日 20:31

**背景**: Claude Managed Agents 是 Claude 平台上的服务，把预置且可配置的 agent harness 与托管的生产级基础设施结合在一起。实际运行时，托管会话在服务端执行 agent loop：保存对话记录、在沙箱中执行工具，并把事件流式返回给前端，因此很适合长时间运行或异步的自主任务。所谓“开源替代方案”通常意味着重新实现这套 loop——包括会话状态、工具沙箱和事件流——从而让用户自行部署和掌控，而不依赖 Anthropic。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://platform.claude.com/docs/en/managed-agents/overview">Claude Managed Agents overview - Claude Platform Docs</a></li>
<li><a href="https://grokipedia.com/page/Claude_Managed_Agents">Claude Managed Agents</a></li>
<li><a href="https://platform.claude.com/docs/en/managed-agents/quickstart">Get started with Claude Managed Agents - Claude Platform Docs</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent frameworks`, `#open-source`, `#GitHub`, `#self-hosted`

---

<a id="item-2"></a>
## [在 llama.cpp 中对「模糊词」施加负 logit 偏置可提升 Qwen 准确率](https://www.reddit.com/r/LocalLLaMA/comments/1wromzr/adding_logit_penalty_for_wait_maybe_and_perhaps/) ⭐️ 8.0/10

Reddit 用户 u/am17an 在 llama.cpp 中对约 49 个 token ID 施加 -2 的负 logit bias，这些 token 对应一篇被引用的 Meta 论文所称的「过度思考标记」，即 " wait"、" maybe"、" perhaps"、" alternatively"、" however" 等词；他在 bartowski 的 Qwen3.5-4B GGUF 的多个量化版本上，用 MATH-500 的 50 道随机题做了测试。所有配置的准确率都有提升：BF16 从 74% 升到 84%，Q8_0 从 76% 升到 80%，Q4_K_M 从 60% 升到 66%，Q3_K_M 从 52% 升到 66%，Q2_K 从 12% 升到 24%。 这是一个纯推理期技巧，不需要微调或重新训练：在 llama.cpp 里多加一个参数、填上若干 token ID 即可，而且对通常退化最严重的 2-bit 极限量化模型同样有效。对于越来越多在消费级硬件上跑本地大模型的用户来说，这是一个成本极低、值得在自己的任务上试一试的准确率提升手段。 所用惩罚值为每个 token -2，报告中推理 token 数下降了 11%–19%，说明收益可能来自抑制无效的自我纠错循环，而不是模型知识本身发生了变化。需要注意的局限：这只是单个模型上的单次 50 题测试；帖子正文被截断，完整的 bias 列表和 token ID 并不齐全；而且 Q2_K 即使提升之后也只有 24% 的准确率。

reddit · r/LocalLLaMA · /u/am17an · 9月27日 16:29

**背景**: logit bias 是一种解码参数，它在采样前给某个 token 的分数加上一个固定值，从而提高或降低该 token 被生成的概率；负偏置就是压制它。面向推理的模型常在解题中途冒出犹豫和自我怀疑的词（如 "wait"、"maybe"、"let me reconsider"），被引论文把这类词称为「过度思考标记」。实验在 llama.cpp 中进行，这是应用广泛的 C/C++ 本地推理引擎，测试对象是 GGUF 格式的低精度量化模型（BF16、Q8_0、Q4_K_M、Q3_K_M、Q2_K），数字越小表示每个权重占用的比特越少、内存占用越低，但通常精度也越低。MATH-500 则是衡量推理准确率的标准竞赛数学基准，共 500 道题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.vellum.ai/llm-parameters/logit-bias">Logit Bias - LLM Parameter Guide - Vellum</a></li>
<li><a href="https://github.com/abetlen/llama-cpp-python/issues/827">Support logit _ bias outside of server · Issue #827...</a></li>
<li><a href="https://bentoml.com/llm/model-preparation/llm-quantization">LLM quantization | LLM Inference Handbook</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#local-llm`, `#quantization`, `#llm-inference`, `#prompt-techniques`

---

<a id="item-3"></a>
## [Qwen 27B 在单张 RTX 4090 上本地生成动态图形](https://www.reddit.com/r/LocalLLaMA/comments/1wrjlls/the_opus_55_posts_about_motion_graphics_are_cool/) ⭐️ 8.0/10

r/LocalLLaMA 用户 u/speedb0at 发帖展示了一段动态图形作品，称其由 Qwen 27B 在单张 RTX 4090 上本地生成，并明确将其作为对大量「让 Opus 5.5 生成动态图形视频」推文的本地化回应。帖子附上了用于提示和构建的 GitHub 仓库 mkultraware/accuretta，以及托管在 X 上带声音的高清版本。 这是一个具体且可复现的案例：消费级显卡加开放权重模型，产出了此前被归功于前沿托管模型的那类动态图形效果——这正是本地 AI 实践者在判断「一张 4090 够不够用」时最需要的证据。它也凸显出在视觉与生成媒体任务上，闭源前沿模型与可本地运行的开放权重之间的感知差距正在迅速缩小。 作者说明帖子里的 GIF 显得卡顿只是因为 Reddit 的 .gif 文件大小限制，并给出了 X 上带声音的完整高清版本；提示与构建流程放在 accuretta 仓库中，该仓库被描述为一个「主权化、零信任」的本地 AI 工作台，通过 llama.cpp 驱动本地模型，将聊天历史、文件工具、持久化 shell、实时 HTML 预览和审批机制整合在同一个界面里。

reddit · r/LocalLLaMA · /u/speedb0at · 9月27日 12:58

**背景**: Opus 5.5 是 Anthropic 当前的旗舰 Claude Opus 模型，属于托管式、需通过 API 访问的系统，用户按 token 付费且无法在自己的硬件上运行。帖子中的「Qwen 27B」指的是 Qwen3.6/Qwen3.8 世代中 270 亿参数的稠密 Qwen 模型，它采用开放权重，因而可以下载并本地运行。RTX 4090 拥有 24GB 显存，27B 模型只有在量化后才能装进单张卡，因此像 accuretta 这类基于 llama.cpp 的运行时是运行它的常见方式。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/mkultraware/accuretta">GitHub - mkultraware/accuretta: A sovereign, zero-trust local ...</a></li>
<li><a href="https://qwen.ai/blog?id=qwen3.6-27b">Qwen3.6-27B: Flagship-Level Coding in a 27B Dense Model</a></li>
<li><a href="https://platform.claude.com/docs/en/models/opus-5-5/overview">Claude Opus 5.5 - Claude Platform Docs</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#qwen`, `#ai-video`, `#github-repo`, `#generative-ai`

---

<a id="item-4"></a>
## [开发者用 Qwen 与自建 MCP 让大模型自动玩《魔兽世界》](https://www.reddit.com/r/LocalLLaMA/comments/1wry136/qwen_plays_world_of_warcraft/) ⭐️ 8.0/10

一位开发者（u/professormunchies）用 vibe coding 的方式搭建了一个私有的《魔兽世界》服务器、带移动端操作的浏览器版 WoW 客户端，并写了一个自定义的 MCP 服务器和 agent 执行框架，让本地或云端的 LLM（如 Qwen）能够自主游玩该游戏；公开的浏览器客户端演示已上线 jankcraft.xyz。不过 MCP 和 agent 框架目前只跑在作者自己的开发服务器上，尚未开源。 这是 MCP 驱动 agent 构建的一个具体落地案例，把大模型用于开放式、长周期的任务，说明标准化工具接口能让 LLM 走出聊天和写代码、去操作复杂软件。对本地 LLM 社区而言，这也意味着评测兴趣正从较简单的“宝可梦”类任务，转向更硬的挑战，比如在《巫妖王之怒》里把角色练到 80 级。 该框架通过自定义 MCP 而非通用浏览器 agent 向模型提供游戏状态，从而实现更精细的操作控制；系统完全不使用视觉/截图输入，作者认为未来加入视觉可能有帮助，但会增加延迟。为了获得最佳效果，驱动游戏的模型输出速度最好超过每秒 50 token，这对本地或云端推理的速度都有要求。

reddit · r/LocalLLaMA · /u/professormunchies · 9月27日 22:46

**背景**: MCP（Model Context Protocol，模型上下文协议）是 Anthropic 在 2024 年 11 月推出的开放标准，为 LLM 提供了读取文件、执行函数、连接外部工具与数据源的统一方式，此后被 OpenAI、Google DeepMind 等厂商采用。Qwen 是阿里云推出的大模型家族，多数权重开放，常被用作本地部署和微调模型的起点。“Vibe coding”指由 AI 辅助的开发方式：开发者用自然语言描述意图，由 LLM 生成代码，通常很少逐行审查。而《魔兽世界》是一款长期运营的大型多人在线角色扮演游戏，其开放式的任务与升级流程使它对自主 agent 来说既有趣又颇具难度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://en.wikipedia.org/wiki/Qwen">Qwen - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#MCP`, `#LLM gaming`, `#local LLM`, `#vibe coding`

---

<a id="item-5"></a>
## [Simon Willison 发布 2026 年 LLM 发展回顾主题演讲](https://simonwillison.net/2026/Sep/27/2026-in-llms-so-far/) ⭐️ 7.0/10

2026 年 9 月 25 日，Simon Willison 在圣何塞举行的 WeAreDevelopers World Congress North America 上发表了闭幕主题演讲，并随之发布了带注释的幻灯片、讲稿笔记以及完整的 YouTube 视频，按时间顺序回顾了 2026 年迄今为止 LLM 领域发生的各项进展。 Willison 是 LLM 领域最受关注的实用派评论者之一，因此这样一份年度综合回顾能帮助开发者区分真正改变日常工作方式的转折点与频繁发版带来的噪音。这类演讲往往会成为团队在决定如何以及何时采用新模型和智能体工具时的重要参考资料。 整个叙述以 Willison 所称的 2025 年 11 月转折点为开端——Claude Opus 4.5 与 GPT-5.1 的发布——让编码智能体从“经常出错”变成“可靠到可以日常使用”。他还提到自己长期使用的非正式基准测试，即让模型生成“一只鹈鹕骑自行车”的 SVG 图片，当时的结果依然出现车架扭曲、鹈鹕几乎认不出的情况。

rss · Simon Willison · 9月27日 23:54

**背景**: Simon Willison 是 Datasette 和 LLM 命令行工具的创作者，也是 LLM 领域最广为阅读的持续观察者之一。WeAreDevelopers World Congress 是一个为期多天的大型开发者会议，在圣何塞 McEnery 会展中心举办，吸引数千名工程师和架构师参加。所谓“编码智能体框架（coding agent harness）”，指的是包裹在模型外层的脚手架，例如 2025 年 2 月推出的 Claude Code 或 OpenAI 的 Codex，它让模型能够自主读取文件、执行命令并修改代码。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://luma.com/5g07qyg5">WeAreDevelopers World Congress North America · Luma</a></li>
<li><a href="https://simonwillison.net/">Simon Willison ’s Weblog</a></li>
<li><a href="https://ai-tldr.dev/releases/simonw-six-months-llms/">Simon Willison — The Last Six Months in LLMs, in… | AI/TLDR</a></li>

</ul>
</details>

**标签**: `#LLM`, `#Simon Willison`, `#AI trends`, `#developer talk`, `#2026 retrospective`

---

<a id="item-6"></a>
## [Show HN：Vanish 让你的命令行任务在云端运行](https://vanishcompute.com/) ⭐️ 7.0/10

一位开发者发布了 Vanish，这是一个进程透明的命令行工具，只要在任意命令前加上前缀（例如 `vanish cargo test`）就能把命令放到云端执行。作者的动机是 AI agent 和重负载计算把笔记本电池耗干、机器变得无法使用。 随着 AI 编程 agent 越来越多地产生长时间、并行运行的任务（例如测试套件、编译和 lint），本地笔记本在续航、散热和响应速度上就成了瓶颈。与手动搭建远程开发环境或容器相比，一个无需改动现有命令、零配置的包装器大幅降低了使用门槛，对在本地运行 agent 的开发者具有很强的吸引力。 其核心技术主张是“进程透明”：加上前缀后，命令的表现应与本地执行一致，这意味着需要保留标准输入输出、退出码、环境变量和文件路径等语义。但发布说明在实用细节上非常单薄——价格、使用哪家云厂商或区域、延迟表现、本地文件与状态如何同步、失败时如何处理，在发布时都未披露。

rss · Show HN (self-made tools) · 9月27日 21:51

**背景**: 所谓“进程透明”的包装器，是指工具插在你的 shell 与程序之间，转发参数并把输出和退出码原样回传，从而使脚本、CI 步骤和交互式工具无需修改即可继续工作。远程执行本身并不新鲜——它延续了远程开发容器、GitHub Codespaces、distcc 式分布式编译以及基于 SSH 的工作流等思路——但 Vanish 的卖点在于无需任何项目配置或环境迁移。推动这一趋势的诱因是 AI 编程 agent：它们会并行触发大量 CPU 密集型命令，让普通开发者的笔记本发烫、卡顿并迅速耗电。

**标签**: `#CLI tools`, `#AI agents`, `#cloud compute`, `#developer tools`, `#remote execution`

---

<a id="item-7"></a>
## [Squint：在屏幕上拖出一个选区，直接问 AI](https://heysquint.com/) ⭐️ 7.0/10

Squint 在 Show HN 上发布，这是一款用 Rust 和 Tauri v2 构建的桌面应用：用户可以在屏幕任意区域拖出一个选区，随即让 OpenAI 模型对所选内容作答，从而替代“截图—切到聊天窗口—上传”的常规流程。目前支持 Windows 10/11 以及 Wayland 下的 Linux（GNOME 45+ 或 KDE Plasma 6），免费档为每天 3 次、每周最多 10 次截图，Plus 订阅为每月 10 美元或每年 99 美元。 它切入的是一个快速增长的“屏幕感知型 AI 工具”赛道：把“截图再对话”的循环压缩成一个动作，与系统级助手和其他截图问答应用正面竞争。对于经常就代码、报错弹窗、图表或界面元素向 AI 提问的开发者和知识工作者而言，每次查询省下的几秒钟会累积成可观效率，但它闭源、仅依赖 OpenAI 模型且暂不支持 macOS，限制了覆盖面。 免费档需要邮箱登录，因为用量按账号计量，且每天仅有 3 次截图额度，只能使用 Fast 模型；Plus 档每月提供 2,500 积分，可使用 Best 模型（每次回答 25 积分，追问计入其中，而 Fast 仅需 1 积分），每次截图的追问上限也从 2 次提高到 10 次。目前没有 macOS 版本，也不支持 X11，Fast 模型通常能在 1–2 秒内开始输出答案。

rss · Show HN (self-made tools) · 9月27日 19:29

**背景**: Tauri 是一个把 Web 前端与 Rust 后端配对的框架，生成的桌面应用体积和内存占用远低于同类 Electron 应用；v2 版本增加了移动端目标，并在 Linux 上使用 webkit2gtk 4.1。Wayland 是现代 Linux 显示服务器协议，被视为 X Window System（X11）的继任者，它对应用之间的隔离更严格，因此实现原生全屏截取比在 X11 上更棘手。像 Squint 这类工具依赖具备视觉能力的大语言模型，这类模型可以同时接收图像和文字提示，并就图像内容作答。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Tauri_(software_framework)">Tauri (software framework) - Wikipedia</a></li>
<li><a href="https://github.com/tauri-apps/tauri">GitHub - tauri-apps/tauri: Build smaller, faster, and more secure desktop and mobile applications with a web frontend. · GitHub</a></li>
<li><a href="https://wiki.archlinux.org/title/Wayland">Wayland - ArchWiki</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#desktop app`, `#screenshot Q&A`, `#Rust/Tauri`, `#productivity`

---

<a id="item-8"></a>
## [Naive-N0.5-Flash：309B MoE 编程模型，原生 1M 上下文](https://www.reddit.com/r/LocalLLaMA/comments/1wrs58t/naiven05flash_309ba155b/) ⭐️ 7.0/10

Naive.ai 发布了 Naive-N0.5-Flash：一个开放权重的混合专家（MoE）模型，总参数 309B、激活参数 15.5B，专门面向编程与 AI 研发场景，并原生支持 1M token 上下文窗口。该消息通过 r/LocalLLaMA 的一条链接帖传播，指向 Naive.ai 的研究页面，同时模型权重与代码仓库已托管在 Hugging Face 和 GitHub 上。 1M token 上下文加上每 token 仅 15.5B 的激活参数，正好契合智能体式编程工具和仓库级代码理解的需求：既能吞下整个代码库，又能把推理成本压得较低。如果开放权重确实可用，它就给开发者提供了一个可自行部署的长上下文编程模型，作为各大实验室闭源方案的替代品。 根据模型卡说明，Naive-N0.5-Flash 采用滑动窗口注意力（SWA）与轻量级 DeepSeek 稀疏注意力（DSA）的混合方案，完全没有全注意力层；Naive.ai 还宣称经过 AI 优化的推理速度可达每秒 2,000 token。原始 Reddit 帖子本身只包含链接和一行规格说明，因此发布时并未附带基准测试成绩、评测数据或实际使用反馈。

reddit · r/LocalLLaMA · /u/nullmove · 9月27日 18:48

**背景**: 混合专家（MoE）模型总参数量很大，但每个 token 只经过其中一小部分专家，因此 309B 的模型实际计算时可能只用到约 15.5B 激活参数，运行成本远低于同等规模的稠密模型。长上下文模型通常受限于 KV 缓存——一种随上下文长度增长的注意力状态存储；滑动窗口注意力（SWA）让每个 token 只关注局部窗口，从而大幅压缩缓存，而 DeepSeek 稀疏注意力（DSA）则通过基于内容的筛选保留远处的相关 token，而不是直接丢弃。Naive-N0.5-Flash 将两者结合，使 1M token 的上下文窗口在成本上可承受，这也顺应了 2025–2026 年向混合与稀疏注意力架构演进的趋势。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/NaiveAI/Naive-N0.5-Flash">NaiveAI/Naive-N0.5-Flash · Hugging Face</a></li>
<li><a href="https://github.com/NaiveAI-Labs/Naive-N0.5-Flash/tree/main">NaiveAI-Labs / Naive-N0.5-Flash Public - GitHub</a></li>
<li><a href="https://naive.ai/en/">NaiveAI</a></li>

</ul>
</details>

**标签**: `#LLM`, `#model-release`, `#MoE`, `#long-context`, `#coding-model`

---

<a id="item-9"></a>
## [LocalLLaMA 用户在 48GB M4 Pro 上以 131K 上下文运行 Qwen3.8-Flash-Next](https://www.reddit.com/r/LocalLLaMA/comments/1wrutx9/so_yeah/) ⭐️ 7.0/10

一位 r/LocalLLaMA 用户（u/JLeonsarmiento）报告称，他在 48GB 内存的 M4 Pro Mac 上用 llama.cpp 跑起了 ISTA-DASLab 的 Qwen3.8-Flash-Next GSQ-RCO GGUF 模型，并能在不爆内存（OOM）的情况下维持约 131K 的上下文。其可用配置为 --ctx-size 131072 搭配 --cache-type-k q4_0、--cache-type-v q4_0、--flash-attn on、--load-mode mmap 以及 --lazy-mode on；发帖者还表示加上这些参数后 Flash-Next 实际比稠密的 3.8-27B 版本更快。 这说明把激进的 KV 缓存量化与 flash attention 结合，可以让超长上下文在消费级统一内存设备上变得可用；在本地模型纷纷向 128K 以上上下文推进的当下，这是一个重要的实测参考。由于具体参数和 HuggingFace 上的 GGUF 仓库都已公开，其他拥有 32–64GB 内存 Mac 的用户可以直接复现或调整这套配置。 帖子粘贴的服务端日志相当零碎，其中数字字段也出现错乱（数值显示为类似 "0.36.940.283" 的字符串），并且没有任何 token/s 或内存占用的实测数据，作者本人也用 "maybe" 来弱化 131K 的说法，因此这只是一台机器上的个例报告而非基准测试。一个值得注意的技术限制是：在 llama.cpp 中量化 V 缓存必须开启 flash attention，所以 --flash-attn on 实际上是这套配置的必需项。

reddit · r/LocalLLaMA · /u/JLeonsarmiento · 9月27日 20:32

**背景**: GSQ（Gumbel Softmax Quantization，Gumbel 软最大化量化）与 RCO（Riemannian Constrained Optimization，黎曼约束优化）来自 ISTA 的 Das Lab，也就是 GPTQ 背后的同一个研究组；GSQ 在给定比特宽度下对每个张量做精确的标量量化，RCO 则在总大小预算内为各张量分配量化类型，最终生成非均匀的 GGUF 文件。GGUF 是 llama.cpp 的模型文件格式，而 llama.cpp 是目前最流行的开源本地大模型推理引擎，可在 CPU、GPU 与 Apple Silicon 上运行。模型的显存/内存占用来自两部分：静态的模型权重，以及随上下文长度线性增长的 KV（键值）缓存，因此把 KV 缓存量化到 4 比特正是让超长上下文塞进有限内存的关键。Flash attention 则把注意力计算融合为单个分块 kernel，将中间数据保留在高速片上存储中，从而降低峰值内存占用并加快长上下文下的注意力计算。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.mindstudio.ai/blog/what-is-gsq-rco-quantization">What Are GSQ and RCO? Das Lab's New LLM Quantization Method</a></li>
<li><a href="https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF">ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF · Hugging Face</a></li>
<li><a href="https://inventivehq.com/blog/flash-attention-llama-cpp-benchmark">Flash Attention in llama.cpp: -fa Is Free Because It's Already On</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#llama.cpp`, `#quantization`, `#qwen`, `#inference-optimization`

---

<a id="item-10"></a>
## [美团 LongCat-2.5-Preview 在 OpenCode 免费开放两周](https://x.com/Meituan_LongCat/status/2103844449550020816) ⭐️ 7.0/10

2026 年 9 月 26 日，美团 LongCat 团队宣布 LongCat-2.5-Preview 在开源 AI 编程智能体 OpenCode 中开放两周免费试用。该模型主打 100 万 token 上下文、多模态（图像）输入，并承诺零数据留存。 开发者可以在自己可能已在使用的工具里，零成本、无绑定风险地体验百万级上下文的多模态编程模型，这是挑战者模型快速获客的捷径。这也说明中国大模型团队正通过与第三方编程智能体合作来争夺用户心智，而不仅依赖自家的对话应用。 除 100 万 token 输入窗口外，该模型还支持最高 128K 的输出 token、工具调用、可选的扩展思考模式以及图像理解，在 OpenCode 中通过 models.dev 元数据登记表对外提供。零数据留存意味着提示词、文档和输出都不会被保存、记录或用于训练后续模型版本；不过至少有一家第三方站点称 OpenCode 中的免费条目“没有截止日期”，因此应以美团公布的这两周窗口作为安排试用时间的依据。

telegram · zaihuapd · 9月27日 01:41

**背景**: OpenCode 是由 Anomaly 开发的开源免费 AI 编程智能体，它把大语言模型与软件项目连接起来，用户可以在终端、桌面应用或 IDE 中用自然语言指令查看、修改和优化源代码，运行命令与测试，并支持来自 75 家以上厂商的模型。LongCat 是美团的大语言模型系列，2.5-Preview 版本定位于编程与智能体工作流，强调长上下文分析能力。零数据留存是一种架构模式：平台实时处理敏感数据后即丢弃，而不保存用于后续调用或训练。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://models.dev/models/meituan/longcat-2.5-preview/">LongCat - 2 . 5 - Preview pricing, providers, and specs | Models.dev</a></li>
<li><a href="https://nano-gpt.com/models/text/longcat-2.5-preview">LongCat 2 . 5 Preview model | NanoGPT</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenCode">OpenCode</a></li>

</ul>
</details>

**标签**: `#AI福利`, `#LLM`, `#免费模型`, `#多模态`, `#coding-agent`

---

<a id="item-11"></a>
## [MiniMax M3.1-Flash-Preview 上线 MiniMax Code 平台](https://x.com/MiniMaxAgent/status/2104079819881517400) ⭐️ 7.0/10

9 月 27 日，MiniMax 宣布最新文本模型 M3.1-Flash-Preview 正式上线 MiniMax Code 平台，并同步重置所有用户的 Token Plan 额度、发放额度重置卡，还提供免费领取 Token 等福利。面向新老用户的签到双倍积分活动于 9 月 28 日至 10 月 7 日期间开启。 已经在用或想尝试 MiniMax Code 的开发者可以立刻上手这一新编程模型，而额度重置和免费 Token 进一步降低了试用成本。这也加剧了快速、低成本编程模型赛道（如各家大模型的 Flash/mini 档位）的竞争，促使厂商在价格、延迟和日常开发体验上比拼，而不只是堆跑分。 该版本带有“Preview（预览）”标签，MiniMax 并未同步公布价格或基准测试成绩，因此实际能力尚待验证；第三方报道称它是 M3 的轻量版本，针对快速、低成本的日常编程做了调优，并支持可调节的推理强度。模型通过 MiniMax Code 交付——这是一个基于 Token Plan 订阅额度运行的开源终端编程 Agent——而不是独立可下载的仓库或明码标价的 API 端点。

telegram · zaihuapd · 9月27日 08:09

**背景**: MiniMax 是一家中国 AI 公司，自研基础模型并推出了一系列 AI 原生应用，包括 MiniMax Code、MiniMax Design、MiniMax Audio 和 Talkie。MiniMax Code 是其官方编程 Agent，以开源形式发布在 GitHub 上，是一个由 MiniMax 模型驱动的终端工具，消耗的正是面向个人开发者和高频编程负载的共享多模态额度 Token Plan。“Flash”类模型通常以牺牲深度多步推理换取更低的延迟与成本，更适合日常修 Bug 和常规功能开发，而非复杂的架构级难题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://alphasignal.ai/news/minimax-quietly-slips-m3-1-flash-preview-into-its-coding-tool">MiniMax Quietly Slips M3.1-Flash-Preview Into Its Coding Tool ...</a></li>
<li><a href="https://startupfortune.com/minimax-slips-a-new-coding-model-into-its-agent-tool-without-a-price-tag/">MiniMax Slips M3.1-Flash-Preview Coding Model Into Its Agent ...</a></li>
<li><a href="https://github.com/MiniMax-AI/minimax-code/">GitHub - MiniMax-AI/minimax-code: An open-source coding agent ...</a></li>

</ul>
</details>

**标签**: `#LLM`, `#Coding Agent`, `#AI 福利`, `#MiniMax`, `#Developer Tools`

---