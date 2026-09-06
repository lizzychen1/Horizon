---
layout: default
title: "Horizon Summary: 2026-09-06 (ZH)"
date: 2026-09-06
lang: zh
---

> 从 56 条内容中筛选出 10 条重要资讯。

---

1. [MaskShift：拥有 148 个工具、零依赖的本地编码代理](#item-1) ⭐️ 9.0/10
2. [本地 vibeblending：用 Qwen 3.8 27B 和 Blender MCP 生成 3D 羊驼](#item-2) ⭐️ 9.0/10
3. [Quiz-UI 为测验漏斗带来 Shadcn 风格组件](#item-3) ⭐️ 8.0/10
4. [8 款无审查 Qwen 3.8 27B 变体实测对比，耗时 167 个 GPU 小时](#item-4) ⭐️ 8.0/10
5. [llama.cpp 新增 Spark-X2.5 GGUF 模型支持](#item-5) ⭐️ 8.0/10
6. [16GB 显存运行 Qwen3.8-27B 量化模型打造村民模拟游戏原型](#item-6) ⭐️ 8.0/10
7. [meclaw：用单个 Rust Linux 二进制文件实现的智能体操作系统，每个实体配备一个 SQLite 与一个沙箱](#item-7) ⭐️ 7.0/10
8. [Notifyd：基于 Postgres 的单二进制通知服务，通过 MCP 操作](#item-8) ⭐️ 7.0/10
9. [Program-Bench 与 SRE-Bench 展现更深入的大模型编程能力测评](#item-9) ⭐️ 7.0/10
10. [开发者为 llama.cpp 添加 MoE 模型专家扩展支持](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [MaskShift：拥有 148 个工具、零依赖的本地编码代理](https://github.com/nafeeur/MaskShift) ⭐️ 9.0/10

MaskShift 是一个新发布的本地优先编码代理框架，无需任何 npm 运行时依赖，并支持不具备原生工具调用 API 的模型。它集成了 148 个原生工具、惰性 MCP 加载、36 项技能，以及通往流行 CLI 代理的桥接，并可通过 Web 驾驶舱进行管理。 这很重要，因为它推动编码代理生态走向更透明、更可移植的本地优先模式，让即使不支持函数调用的模型也能获得高级代理能力。凭借多供应商兼容性和零依赖安装，它降低了开发者想要亲手控制且不被厂商锁定的门槛。 MaskShift 不使用原生工具调用，而是将工具模式注入系统提示词，并解析模型回复中专门的代码块，将其还原为工具调用。它使用仅追加的审计日志、运行前检查点和 Git stash 引用进行恢复，并且仅使用 Node 22 内置模块运行基于 WebSocket 的守护进程。

rss · Show HN (self-made tools) · 9月6日 21:39

**背景**: 编码代理是能够自主浏览代码库、执行 shell 命令和编辑文件的 AI 工具。模型上下文协议（MCP）是一个开放标准，常被比作 AI 的 USB-C 接口，它让模型能够连接外部数据源和工具。语言服务器协议（LSP）为自动补全、跳转定义等 IDE 功能提供了标准化。npm 是 Node.js 的默认包管理器，因此没有运行时 npm 依赖意味着安装更简单，供应链风险也更少。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro">What is the Model Context Protocol (MCP)? - Model Context ...</a></li>
<li><a href="https://microsoft.github.io/language-server-protocol/">Official page for Language Server Protocol</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agent`, `#GitHub`, `#developer tools`, `#open source`

---

<a id="item-2"></a>
## [本地 vibeblending：用 Qwen 3.8 27B 和 Blender MCP 生成 3D 羊驼](https://www.reddit.com/r/LocalLLaMA/comments/1w8rxwg/vibeblending_locally_with_qwen_38_27b/) ⭐️ 9.0/10

一位 Reddit 用户分享了一套完整的本地工作流，让名为 Qwen 3.8 27B 的 Qwen 模型能够通过 Blender MCP 扩展控制 Blender。帖子给出了具体配置命令，并成功生成了一只风格化的 3D 羊驼。 它提供了一个可直接复制的本地化自然语言驱动 3D 建模方案，无需依赖云端。这表明开源权重 LLM 结合 MCP 标准，已经能在 Blender 中自动完成复杂的场景搭建，让普通开发者和爱好者更容易上手 AI 辅助建模。 该方案需要 Blender 5.x 和 Blender MCP 扩展，并在.mcp.json 中配置通过 uvx 启动 blender-mcp 的命令，包含`--with mcp[cli]<2.0.0`和`--from git+https://projects.blender.org/lab/blender_mcp.git@v1.0.0#subdirectory=mcp`等参数。使用 pi 的用户还需先执行`pi install npm:pi-mcp-adapter`；演示中模型通过多步 MCP 调用，用基础几何体拼装出一只 Q 版羊驼。

reddit · r/LocalLLaMA · /u/jacek2023 · 9月6日 09:54

**背景**: MCP（Model Context Protocol）是 Anthropic 于 2024 年 11 月推出的开放标准，用于让 AI 应用连接外部工具和数据源。Blender MCP 是一个服务器，向 LLM 暴露 Blender 的 Python API，使其能够添加物体、指定材质并调整场景。uvx 可在临时隔离环境中运行 Python 命令行工具，因此无需常驻安装即可启动 blender-mcp。该示例说明这样的配置能让本地模型完成一项多步骤的 3D 资产创建任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.blender.org/lab/mcp-server/">MCP Server — Blender</a></li>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://pydevtools.com/handbook/reference/uvx/">uvx: Run Python CLI Tools in Isolated Environments</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#blender`, `#MCP`, `#3D-modeling`, `#workflow`

---

<a id="item-3"></a>
## [Quiz-UI 为测验漏斗带来 Shadcn 风格组件](https://github.com/kalpovskii/quiz-ui) ⭐️ 8.0/10

Quiz-UI 是 kalpovskii 发布的一个新 GitHub 项目，提供用于构建测验漏斗（quiz funnel）的 Shadcn 风格 React 组件。它还提供了一个机器可读的 registry JSON，开发者可以把它交给 AI 代理来快速生成测验。 该项目让营销技术（martech）开发者可以自行构建测验漏斗，而无需为商业测验构建工具支付每月数百美元的费用。它也顺应了将组件注册表交给 AI 代理来自动生成 UI 代码这一日益流行的趋势。 每个组件都带有自己的描述和依赖项，因此可以直接把注册表传给 AI 编程代理使用。入门指南和示例注册表均托管在 quiz-ui-phi.vercel.app。

rss · Show HN (self-made tools) · 9月6日 19:03

**背景**: 测验漏斗是一种营销工具，通过交互式测验或问卷来吸引用户、收集数据并推荐产品，通常用来替代静态表单。Quiz-UI 模仿的 Shadcn/ui 是一套 React 组件集合，它不通过 npm 包分发，而是以可复制粘贴的源码形式提供给开发者，让开发者完全拥有组件代码。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://heyflow.com/blog/quiz-funnel-examples/">16 Quiz funnel examples for creative marketers | Heyflow</a></li>
<li><a href="https://www.optimonk.com/quiz-funnel-examples">15 Successful Quiz Funnel Examples to Inspire You</a></li>
<li><a href="https://ui.shadcn.com/docs">Introduction - shadcn / ui</a></li>

</ul>
</details>

**标签**: `#GitHub`, `#UI components`, `#AI agent`, `#quiz funnel`, `#react`

---

<a id="item-4"></a>
## [8 款无审查 Qwen 3.8 27B 变体实测对比，耗时 167 个 GPU 小时](https://www.reddit.com/r/LocalLLaMA/comments/1w8vx6w/8_uncensored_qwen_38_27b_variants_one_base_167/) ⭐️ 8.0/10

Abliterlitics 发布了对 8 个基于同一基础模型的 Qwen 3.8 27B 无审查变体的对比测试，按 HarmBench 攻击成功率排名；测试耗时 11 天、约 167 个 GPU 小时。orcarouter 变体以 82.2% 的成功率排在首位，而编辑最激进的 obliteratus 仅排在倒数第二。 对本地 LLM 用户和微调者来说，这份报告提供了关于哪些无审查变体真正可用、不同 abliteration 方法效果如何的实用数据。一个关键结论是“轻量编辑优于重型干预”，这可能会改变社区处理模型去审查的方式。 评测流程包括权重比较、KL 散度测量、13 项基准测试，以及基于 HarmBench 400 条经典提示词的拒绝行为测试；完整报告发布在 ablerlitics.dev/models/qwen38-27b。值得注意的是，没有任何变体在版权相关解锁上超过 39%，而最激进的几个变体在 HarmBench 中多达 45%的回答因未结束的思考循环而无法完整输出。

reddit · r/LocalLLaMA · /u/nathandreamfast · 9月6日 13:15

**背景**: Abliteration 是一种训练后处理技术：先找出模型在激活空间中的“拒绝方向”，再通过修改权重将其中和，使已经对齐的大语言模型可以回应原本会拒绝的请求。HarmBench 是一个标准化的自动化红队评测框架，用于衡量模型在越狱式攻击下对有害指令的遵循程度。Qwen 3.8 27B 会先在思考痕迹中推理再作答，而这份报告考察的正是经过 abliteration 后这些模型的合规性与推理表现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/mlabonne/abliteration">Uncensor any LLM with abliteration</a></li>
<li><a href="https://arxiv.org/abs/2402.04249">[2402.04249] HarmBench: A Standardized Evaluation Framework ...</a></li>
<li><a href="https://webdecoy.com/blog/wtf-are-abliterated-models-uncensored-llms-explained/">WTF Are Abliterated Models? Uncensored LLMs Explained</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#qwen`, `#abliteration`, `#benchmarks`, `#uncensored-models`

---

<a id="item-5"></a>
## [llama.cpp 新增 Spark-X2.5 GGUF 模型支持](https://www.reddit.com/r/LocalLLaMA/comments/1w90zdc/model_support_for_spark2_5forcausallm/) ⭐️ 8.0/10

KnightYao 提交的 llama.cpp 拉取请求(#27868)新增了 Spark2_5ForCausalLM 实现，使 Spark-X2.5-4B 和 Spark-X2.5-1.7B 的 GGUF 量化版本可在本地运行。这款紧凑型模型支持原生 100 万 token 上下文及超过 200 种语言。 这扩展了设备端和自托管 AI 的实用工具集，因为这些小型模型无需大显存 GPU 就能提供强劲的编程、工具调用和智能体能力。llama.cpp 集成使长上下文及多语言推理对个人爱好者和企业都更加易用。 Spark-X2.5 采用混合注意力架构，将一层全注意力与三层滑动窗口注意力交替组合，以降低长上下文场景下的计算开销。模型兼容 llama.cpp、vLLM、SGLang、MLX 等推理框架以及 LLaMA-Factory 等微调框架，训练依托华为昇腾集群，并通过大规模强化学习及 MOPD 后训练技术增强能力。

reddit · r/LocalLLaMA · /u/jacek2023 · 9月6日 16:36

**背景**: 大型语言模型通常使用全量自注意力，即每个 token 都关注序列中的所有其他 token，因此计算量随序列长度呈二次增长。滑动窗口注意力则将每个 token 的关注范围限制在固定大小的相邻窗口内，使复杂度近似线性，但可能丢失全局信息。混合注意力架构通过组合全注意力层和滑动窗口注意力层来兼顾质量与效率，Spark-X2.5 也采用了这种设计。GGUF 是面向 llama.cpp 优化的一种文件格式，可让量化模型在消费级 CPU 和 GPU 上高效运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/XHToken/Spark-X2.5">GitHub - XHToken/Spark-X2.5: Spark-x2.5 open model series ...</a></li>
<li><a href="https://cyrilzakka.github.io/llm-playbook/nested/swa.html">Sliding-Window Attention (SWA) - The Large Language Model Playbook</a></li>
<li><a href="https://arxiv.org/abs/2502.18845">[2502.18845] Sliding Window Attention Training for Efficient Large Language Models</a></li>

</ul>
</details>

**标签**: `#LLM`, `#Open-Source Model`, `#Local Inference`, `#GGUF`, `#llama.cpp`

---

<a id="item-6"></a>
## [16GB 显存运行 Qwen3.8-27B 量化模型打造村民模拟游戏原型](https://www.reddit.com/r/LocalLLaMA/comments/1w8r0t9/villager_simulation_game_poc_created_with/) ⭐️ 8.0/10

一位开发者分享了一个由 Qwen3.8-27B 模型（Q3_K_XL GGUF 量化格式）驱动的村民模拟游戏概念验证，完全运行在 16GB RTX 5070 Ti 上，视觉部分由 CPU 处理。在线演示最高可达每秒 75 个 token，并使用了 KVarN 量化的 KV 缓存与 MTP 草稿缓存。 这一实战案例表明，激进量化的本地模型配合量化 KV 缓存，可以在消费级 16GB 显卡上实现流畅的、由智能体驱动的游戏交互。它可能激励更多开发者构建本地、注重隐私的 AI 体验，并为长时间运行的 AI 会话提供了实用的生产级技巧。 作者使用了 beellama.cpp 分支，主 KV 缓存采用 KVarN kvarn3/kvarn3，MTP 草稿缓存采用 kvarn2/kvarn2，上下文为 96,256 个 token，并借助 pi harness 的 pi-observational-memory 等扩展来防止上下文溢出。开发过程采用大量渐进式功能提示而非一次性完成，作者建议不要畏惧 Q3 量化或 KV 量化，因为更快的生成速度可以避免 CPU 卸载。

reddit · r/LocalLLaMA · /u/Fancy-Snow7 · 9月6日 09:02

**背景**: GGUF 量化可以压缩大型语言模型，使其能在显存有限的消费级 GPU 上运行，以少量输出质量换取更高的速度。KV 缓存保存生成过程中的注意力键和值，对其进行量化可进一步降低内存占用；MTP（多 token 预测）头则一次预测多个 token 以加速解码。pi agent harness 是一个可扩展的工具包，提供智能体循环以及观测记忆等工具，帮助模型管理长上下文。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Anbeeld/beellama.cpp">GitHub - Anbeeld/beellama. cpp : KVarN , KV cache precision tail...</a></li>
<li><a href="https://github.com/earendil-works/pi">GitHub - earendil-works/pi: AI agent toolkit: unified LLM API, agent loop, TUI, coding agent CLI · GitHub</a></li>
<li><a href="https://anbeeld.com/articles/kvarn-kv-cache-implementation-and-benchmarks">KVarN KV Cache: Implementation and Benchmarks - Anbeeld</a></li>

</ul>
</details>

**标签**: `#local-LLM`, `#quantization`, `#Qwen`, `#game-development`, `#VRAM-optimization`

---

<a id="item-7"></a>
## [meclaw：用单个 Rust Linux 二进制文件实现的智能体操作系统，每个实体配备一个 SQLite 与一个沙箱](https://github.com/mmeyerlein/meclaw) ⭐️ 7.0/10

Hacker News 的“Show HN”帖子发布了 meclaw，这是一个开源的 Rust 项目，可编译为单个 Linux 二进制文件并实现一个智能体操作系统。它为每个实体提供独立的 SQLite 数据库和沙箱，并以目录树的形式组织智能体群。 meclaw 为构建 AI 智能体系统的开发者提供了一种轻量、以文件系统为原生的替代方案，将持久化状态隔离与按实体沙箱化结合起来。Gartner 预测到 2026 年底，40% 的企业应用将集成面向特定任务的 AI 智能体，因此更安全、可复现的智能体编排工具正变得越来越重要。 该项目采用 Apache-2.0 许可证，自称是“一棵可运行的目录树——每个文件夹都是一个执行单元（actor），每条边都是一条路由”，设计上强调守护进程优先、文件系统原生。它还包含 meclaw-os，一个在运行时于这一基底上生长出来的小型实验性智能体操作系统。

rss · Show HN (self-made tools) · 9月6日 20:07

**背景**: 智能体操作系统（agentic OS）是一种协调层，为 AI 智能体提供记忆、工具访问、决策逻辑和监督，使它们能够在真实系统中完成多步骤任务。按实体进行沙箱隔离是一项关键安全实践，因为这能限制被攻陷智能体可能造成的破坏，并帮助控制其可消耗的计算与内存资源。Rust 让这个项目能够交付单个内存安全的二进制文件，而每个实体一个 SQLite 数据库则提供轻量且互相隔离的持久化状态，无需单独的数据库服务器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/mmeyerlein/meclaw">GitHub - mmeyerlein/ meclaw : Where agents build agents. An agentic...</a></li>
<li><a href="https://meclaw.ai/">meclaw · agentic harness swarms as a directory tree</a></li>
<li><a href="https://www.make.com/en/blog/agentic-operating-system">What Is an Agentic Operating System? 2026 Guide | Make</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Rust`, `#sandboxing`, `#developer tools`, `#Hacker News`

---

<a id="item-8"></a>
## [Notifyd：基于 Postgres 的单二进制通知服务，通过 MCP 操作](https://github.com/rmzlb/notifyd) ⭐️ 7.0/10

Notifyd 已作为开源项目发布在 GitHub 上，它是一个基于 Postgres 的单二进制通知服务，可通过模型上下文协议（MCP）进行操作。该仓库作为 Show HN 帖子分享，提供了用于管理通知的 MCP 接口，使其可直接被兼容 MCP 的 AI 应用使用。 Notifyd 将基于 Postgres 的通知以 MCP 服务器形式暴露，从而连接了数据库事件与 AI 代理，使 Claude 或 ChatGPT 等大语言模型能够以标准化方式订阅并响应数据库变化。这对构建事件驱动型 AI 工作流的开发者很有价值，因为它降低了将通知直接集成到 AI 工具链中的摩擦。 该服务特意做成单个静态二进制文件，简化了部署和操作——除了 Postgres 和 MCP 之外，不需要单独的运行时或依赖。虽然 GitHub 链接使其立即可用，但该项目看起来仍处于早期阶段，在 Hacker News 上没有任何社区讨论且仅获得 1 个积分，因此生产就绪性和功能完整性仍不确定。

rss · Show HN (self-made tools) · 9月6日 19:48

**背景**: 模型上下文协议（MCP）是 Anthropic 于 2024 年 11 月推出的开放标准，用于规范 AI 系统（如大语言模型）与外部工具和数据源的集成方式；随后 OpenAI 和 Google DeepMind 也采用了该协议。PostgreSQL 还内置了一种称为 LISTEN/NOTIFY 的进程间通信机制，可向在特定频道上注册的客户端会话发送通知事件。Notifyd 很可能利用这些 Postgres 原语，将通知暴露给 MCP 客户端，使 AI 模型能够监控数据库变化，例如新行、更新或自定义事件。可以把 MCP 想象成“AI 的 USB-C 接口”——它将与数据和工具的连接标准化，而 Notifyd 则把 Postgres 通知插入这个接口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://www.postgresql.org/docs/current/sql-notify.html">PostgreSQL: Documentation: 18: NOTIFY</a></li>
<li><a href="https://oneuptime.com/blog/post/2026-01-25-use-listen-notify-real-time-postgresql/view">How to Use Listen/Notify for Real-Time Updates in PostgreSQL</a></li>

</ul>
</details>

**标签**: `#notification`, `#Postgres`, `#MCP`, `#open-source`, `#developer-tools`

---

<a id="item-9"></a>
## [Program-Bench 与 SRE-Bench 展现更深入的大模型编程能力测评](https://www.reddit.com/r/LocalLLaMA/comments/1w8us6t/coding_benchmarks_that_are_quickly_showcasing/) ⭐️ 7.0/10

一位 Reddit 用户推荐了 Program-Bench、SRE-Bench 和 Code Migration 三个进阶编程基准，认为它们比常见基准更能检验大模型的深层软件工程能力。帖中给出的示例显示，GPT-6 Astra 在 Program-Bench 上仅获 5.5%，却在 SRE-Bench 上拿到 88%。 这些基准把评估从常规代码修改转向逆向工程和跨语言重实现，更接近对系统的深层理解。它们可能有助于揭示哪些前沿模型能胜任恶意软件分析、固件检查和遗留代码迁移等真实任务，也让基准分数不容易迅速饱和。 Program-Bench 要求智能体在仅有编译后二进制和文档、且不能使用反编译器或互联网的情况下复现程序行为；SRE-Bench 则由 19 个平均超过 16,000 行代码的净室（clean-room）自研程序构成。帖中数据还出现明显倒挂，例如 GPT-6 Astra 在 Program-Bench 上只有 5.5%，在 SRE-Bench 上却高达 88%，说明这些基准衡量的是差异很大的技能。

reddit · r/LocalLLaMA · /u/Informal-Trouble2183 · 9月6日 12:23

**背景**: 很多主流编程基准（如 LiveCodeBench、Terminal-Bench、DeepSWE）通常让模型修改源代码或修复 Bug，前沿模型在这些测试上的分数已非常接近。Program-Bench 和 SRE-Bench 则测试更难的反向工程场景：智能体只能从编译后的程序或二进制出发，理解其行为并重新实现。SRE-Bench 由领域专家投入超过 5,000 小时进行净室开发，避免了模型从常见源码库或记忆样例中获取答案，覆盖网络协议、恶意软件、固件、游戏和文件格式恢复等领域。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://llm-stats.com/benchmarks/program-bench">Program Bench Leaderboard | LLM Stats</a></li>
<li><a href="https://www.vals.ai/benchmarks/srebench">SRE Bench - Vals AI</a></li>
<li><a href="https://daplab.cs.columbia.edu/projects/sre-bench/">SRE-Bench | DAPLab</a></li>

</ul>
</details>

**标签**: `#benchmarks`, `#coding`, `#LLM`, `#AI agents`, `#software engineering`

---

<a id="item-10"></a>
## [开发者为 llama.cpp 添加 MoE 模型专家扩展支持](https://www.reddit.com/r/LocalLLaMA/comments/1w9404e/expert_expansion_with_llamacpp/) ⭐️ 7.0/10

一位开发者发布了自定义的 llama.cpp 分支，为混合专家（MoE）模型支持专家扩展，并在构建时借助了 GLM-5.3-Flash。作者仅在 Apple Metal 上测试过，并称效果优于他们之前的 DS4 版本，目前正请求社区在其他平台和模型上提供反馈。 由于 llama.cpp 是本地 LLM 推理事实上的标准，这一改动为在本地硬件上对 MoE 模型进行更灵活的专家级定制打开了大门。如果能在多平台得到验证，它可以帮助开发者实验性地调整专家数量、路由或专门的专家模块。 作者只在 Metal 平台上进行了测试，而且原帖中没有提供代码仓库链接，因此其他人目前无法直接克隆该分支。该实现针对的是专家扩展而非常规 MoE 推理；作者特别希望其他平台和不同 MoE 模型上进行测试。

reddit · r/LocalLLaMA · /u/Specific-Tax-6700 · 9月6日 18:27

**背景**: 混合专家（MoE）架构会将稠密的前馈层替换为多个专门的专家网络，并由一个路由器决定每个 token 激活哪些专家，从而让大模型更高效地扩展规模。llama.cpp 是一个开源的 C/C++推理库，已成为几乎所有本地推理工具（如 Ollama 和 LM Studio）的核心。GLM 是 Z.ai 开发的开源权重大语言模型系列，GLM-5.3-Flash 是 GLM-5 系列中首个原生多模态模型。专家扩展是指改变 MoE 模型中专家的数量或组成的操作，而上游 llama.cpp 目前并未向任意模型开放这一能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Llama.cpp">Llama.cpp</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp">GitHub - ggml-org/llama.cpp: LLM inference in C/C++</a></li>
<li><a href="https://www.guvi.in/blog/what-is-mixture-of-experts-moe/">Mixture of Experts ( MoE ) Architecture Explained | HCL GUVI Blog</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#MoE`, `#expert expansion`, `#LocalLLaMA`, `#LLM engineering`

---