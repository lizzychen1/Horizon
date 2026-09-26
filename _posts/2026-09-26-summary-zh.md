---
layout: default
title: "Horizon Summary: 2026-09-26 (ZH)"
date: 2026-09-26
lang: zh
---

> 从 52 条内容中筛选出 9 条重要资讯。

---

1. [Show HN：KISS——受 Pi 启发、用 Rust 编写的高性能 Agent 框架](#item-1) ⭐️ 8.0/10
2. [OOMU：免费的原生 macOS AI 执行框架，支持本地与云端模型](#item-2) ⭐️ 8.0/10
3. [Mica v0.1 4B 零输出 token 通关《我的世界》铁镐目标](#item-3) ⭐️ 8.0/10
4. [MyA11yReport MCP：让 AI 编程工具在本地执行 WCAG 无障碍审计](#item-4) ⭐️ 7.0/10
5. [Show HN：Recurse——更快开发和部署专用 AI 智能体的平台](#item-5) ⭐️ 7.0/10
6. [Swift1.5-Qwen3.8-Flash-Next 推理 token 较基座 Flash 减少约 60%](#item-6) ⭐️ 7.0/10
7. [开源 Kev 4B 准确率追平 Jev，但隐藏的 token 开销使 Jev 短请求贵达 12 倍](#item-7) ⭐️ 7.0/10
8. [Qwen3.8-27B：用 KV cache 移植提升输出质量](#item-8) ⭐️ 7.0/10
9. [开发者训练 50MB 小模型，替代内部应用中的 Gemini Flash 调用](#item-9) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Show HN：KISS——受 Pi 启发、用 Rust 编写的高性能 Agent 框架](https://github.com/racetozero/kiss) ⭐️ 8.0/10

一位开发者在 Hacker News 的 Show HN 板块发布了 KISS：一个用 Rust 编写、深受 Pi agent harness 启发的高性能 agent 框架，额外加入了可选的子代理（sub-agents）、动态工作流、MCP/ACP/WebMCP 支持，以及可选的 Jev 集成，用于动态压缩上下文和在一轮对话中途动态调整推理/努力程度。它提供 Rust、Python、TypeScript 和 WASM 的 SDK，并为其他语言提供 JSONL RPC 与 WebSocket RPC，还有一个可在浏览器中脱离服务器运行完整 agent 循环的 WASM 构建版本。 该项目瞄准了一个具体的痛点：开发者喜欢 Pi 的极简设计，却对其性能不满意，而 KISS 用 Rust 内核加上公开的性能基准页面来回应这一问题。由于它提供四种语言的 SDK 以及无需服务器的浏览器端构建，它降低了把 agent 循环直接嵌入现有应用的门槛，而不必引入重型框架；同时它对 MCP/ACP/WebMCP 的支持，也让它与正在逐步标准化“agent 如何调用工具、如何互相通信”的这些协议绑定在一起。 作者表示 Jev 支持是可选开启的，用于动态压缩上下文以及在一轮对话中途动态切换推理强度/努力程度，而 WASM 构建可在客户端运行完整的 agent 循环；仓库中专设的性能章节为性能宣称提供了依据。需要注意的局限是：这是一个个人项目，由其作者在工作和日常中自用，目前尚无社区验证，发布帖在撰写时仅有 1 分和 0 条评论，因此它在真实场景中的成熟度和基准可复现性都还未得到证明。

rss · Show HN (self-made tools) · 9月26日 00:05

**背景**: Agent harness（代理框架）是包裹语言模型的那一层，负责提供 agent 循环、工具调用和上下文管理，让模型能够真正完成多步任务；Pi 是 Mario Zechner 开发的极简终端 agent harness，以体积小、可扩展著称。MCP（Model Context Protocol）是一种把工具和数据暴露给模型的标准；ACP（Agent Communication Protocol）是 IBM BeeAI 团队提出、现由 Linux 基金会治理的开放标准，用于跨不同框架的代理间通信；WebMCP 则是 W3C Web Machine Learning 社区组正在推进的规范，旨在把网页变成类似 MCP 服务器的存在。来自 TypeSafe AI 的 Jev 是一个小型的“System One”决策模型，只输出数字而不生成文本，用于在 agent 循环中回答路由、风险与审批类问题。KISS 正是用 Rust 重新实现了 Pi 的设计原则，并把上述这些组件整合进来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/earendil-works/pi">GitHub - earendil-works/pi: AI agent toolkit: unified LLM API, agent loop, TUI, coding agent CLI · GitHub</a></li>
<li><a href="https://www.ibm.com/think/topics/agent-communication-protocol">What is Agent Communication Protocol (ACP)? | IBM</a></li>
<li><a href="https://nearform.com/digital-community/webmcp-turning-web-pages-into-tools-for-ai-agents/">WebMCP: Turning web pages into tools for AI agents | Nearform</a></li>

</ul>
</details>

**标签**: `#ai-agents`, `#agent-framework`, `#rust`, `#github`, `#mcp`

---

<a id="item-2"></a>
## [OOMU：免费的原生 macOS AI 执行框架，支持本地与云端模型](https://oomu.ai/download.html) ⭐️ 8.0/10

一位开发者发布了 OOMU（oomu.ai），这是一个用 Rust 和 AppKit 编写的免费原生 macOS AI 执行框架（AI harness），目前处于 Beta 2（版本 0.2.16），可直接下载或通过 Homebrew 命令 'brew install --cask oomu-ai/tap/oomu' 安装。它可以操作系统应用、执行终端任务，并生成 Word、Excel、PowerPoint 和 PDF 文档，默认使用本地运行的 Gemma 4 E2B QAT 模型，同时支持用户自带密钥（BYOK）接入 OpenAI、Gemini、DeepSeek、Grok 和 Mistral 等云端 API。 它为使用者提供了一个具体且可立即上手的方案，用来替代 OpenClaw 等更笨重的开源执行框架；其逐轮智能自动路由功能（针对每条提示判断应本地还是云端处理）很可能被其他智能体工具效仿，因为用户希望在控制 token 成本的同时不牺牲能力。由于该应用完全免费、没有订阅分层，它降低了 macOS 用户进行桌面自动化和文档生成的门槛，无需为云端 token 付费，也不必把文件交给网络服务处理。 OOMU 宣称零遥测、使用加密的本地数据库，提供可彻底切断网络访问的 Air-Gap（气隙）模式，空闲时 CPU 占用为 0.0%，且不使用 Electron 也没有后台 Web 服务；智能自动路由功能默认关闭，需要在聊天窗口中手动启用。作者说明目前仍是 beta 版本，可能偶尔出现 bug，建议通过内置的 bug 反馈表单提交问题；该应用开箱即支持 12 种语言本地化，其中包括简体中文和繁体中文。

rss · Show HN (self-made tools) · 9月25日 22:16

**背景**: 所谓“AI 执行框架”（AI harness）是在语言模型外面包裹的一层工具层，赋予模型调用应用、执行 shell 命令或写文件的能力，使智能体能够真正干活而不只是聊天。作者提到的 OpenClaw 是一个知名的免费开源自主智能体，以消息平台作为主要交互界面，而作者表示长期维护这类项目令人疲惫。Gemma 4 E2B 是谷歌的小型开放模型，QAT（量化感知训练）在训练过程中模拟量化，使压缩后的模型质量损失大幅降低；据谷歌介绍，面向移动端的量化格式把 Gemma 4 E2B 的内存占用降到约 1GB，使其在设备本地运行变得可行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/innovation-and-ai/technology/developers-tools/quantization-aware-training-gemma-4/">Gemma 4 with quantization-aware training - The Keyword</a></li>
<li><a href="https://huggingface.co/google/gemma-4-E2B-it-qat-mobile-transformers">google/gemma-4-E2B-it-qat-mobile-transformers · Hugging Face</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenClaw">OpenClaw - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#macOS app`, `#local LLM`, `#AI tools`, `#desktop automation`

---

<a id="item-3"></a>
## [Mica v0.1 4B 零输出 token 通关《我的世界》铁镐目标](https://www.reddit.com/r/LocalLLaMA/comments/1wqahbz/mica_v01_4b_got_an_iron_pickaxe_in_real_minecraft/) ⭐️ 8.0/10

Mica v0.1 4B 是一个在 RTX 3090 上以 llama.cpp + Q5_K_M 量化运行的本地 4B 参数模型，它在一个真实的《我的世界》1.20.4 服务器上从空背包开始，仅用 23 次决策就自主合成出了铁镐。它并不生成文本，而是通过读取答案标签 token 的概率来为候选指令打分，因此输出 token 数为零，每次决策约耗时 90 到 150 毫秒，被选中的指令再经由 Mindcraft 技能库交给 Mineflayer 机器人执行。 这个演示说明智能体控制完全可以不依赖文本生成：小型本地模型只要充当固定动作词表上的打分器，就能可靠地驱动真实游戏环境。其意义在于大幅降低了具身智能体的延迟与成本，也表明在消费级 GPU 上运行的 4B 级本地模型，只要配合优秀的技能库，已足以完成结构化的工具调用任务。 每一步都会先把机器人的实时游戏状态（背包、附近方块、实体、上一次结果）序列化为文本，Mica 为候选指令打分，选中的指令再在游戏中执行；这 23 步依次经过原木、木板、工作台、木镐、石头、石镐、熔炉、铁矿石、熔炼，最终得到铁镐。需要注意的局限是：这只是一个单一项目的演示，摘录中并未明确给出仓库链接；此外视频里的行走、挖矿、熔炼等长动作被加速处理，而画面中的 HUD 与合成、熔炉界面是根据机器人记录的背包日志绘制的。

reddit · r/LocalLLaMA · /u/Top-Evidence174 · 9月25日 22:55

**背景**: 《我的世界》智能体通常由大语言模型逐 token 生成文本指令来驱动，速度慢且容易出错。Mindcraft 是一个开源智能体框架，它提供技能库来封装挖矿、合成、移动等底层游戏操作，底层则建立在 Mineflayer 这一稳定、易用的 JavaScript 机器人 API 之上。Logit 是语言模型为每个 token 给出的原始未归一化分数，经 softmax 转换为概率分布；Mica 正是利用这一点，直接比较一小组预定义答案标签 token 的概率，而不是采样解码出完整回复。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepwiki.com/mindcraft-bots/mindcraft/2.2-skills-library">Skills Library | mindcraft-bots/mindcraft | DeepWiki</a></li>
<li><a href="https://ai-tldr.dev/learn/llm-fundamentals/text-generation/logits-explained/">Logits Explained: The Logits Probability Distribution | AI/TLDR</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#local LLM`, `#llama.cpp`, `#agent frameworks`, `#Minecraft`

---

<a id="item-4"></a>
## [MyA11yReport MCP：让 AI 编程工具在本地执行 WCAG 无障碍审计](https://mya11y.report/mcp/) ⭐️ 7.0/10

一个名为 MyA11yReport MCP 的 Show HN 项目在 mya11y.report/mcp/ 上线，它提供了一个本地 MCP 服务器，让 Claude Desktop、Cursor 等 AI 开发工具能够在本地运行 WCAG 无障碍审计并生成符合规范的代码。该帖在 Hacker News 上仅获得 1 分且没有任何评论。 无障碍合规正日益成为 Web 团队的法律与产品硬性要求，而把 WCAG 检查直接嵌入 AI 编码流程，意味着问题可以在代码生成阶段就被发现，而不必等到后期人工审计。这也表明 MCP 生态正从通用的文件与搜索工具，向垂直领域的专业开发工具演进。 关键的技术特点在于审计以 MCP 服务器的形式在本地运行，无需把代码发送给第三方无障碍检测服务，这对处理专有代码或受监管代码的团队尤为重要。与任何自动化检查工具一样，它很可能只能捕捉基于规则的违规项，而无法覆盖需要人工判断的全部无障碍问题；此外，该项目目前没有任何社区讨论为其质量背书。

rss · Show HN (self-made tools) · 9月25日 22:27

**背景**: Model Context Protocol（MCP）是 Anthropic 于 2024 年 11 月推出的开放标准，为 AI 应用提供统一的方式去连接外部工具、数据源与工作流，常被形容为「AI 的 USB-C 接口」。WCAG（Web 内容无障碍指南）是 W3C 制定的国际标准，规定了如何让网页内容对视障、听障、肢体及认知障碍人士可用，并在 2.0、2.1、2.2 各版本中给出了可测试的成功标准。Cursor 是一款 AI 辅助的代码编辑器与开发环境，允许开发者用自然语言指令编写代码；Claude Desktop 则是 Anthropic 的 Claude 桌面客户端，两者都可作为 MCP 客户端加载此类第三方服务器。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://www.w3.org/WAI/standards-guidelines/wcag/">WCAG 2 Overview | Web Accessibility Initiative (WAI) | W3C</a></li>
<li><a href="https://en.wikipedia.org/wiki/Cursor_(code_editor)">Cursor (code editor)</a></li>

</ul>
</details>

**标签**: `#MCP`, `#AI agents`, `#accessibility`, `#developer tools`, `#AI coding`

---

<a id="item-5"></a>
## [Show HN：Recurse——更快开发和部署专用 AI 智能体的平台](https://recurse.run/) ⭐️ 7.0/10

Recurse 通过 Hacker News 的 Show HN 帖子发布，定位为一个让开发者更快构建和部署专用 AI 智能体的平台。该提交指向其线上站点 recurse.run，但目前附带信息极少——仅 2 分、1 条评论，帖子本身也没有列出功能细节或文档。 智能体开发是应用型 AI 中发展最快的领域之一，Microsoft、Google、LangChain 等大厂都在推出构建与部署智能体的框架，因此一个旨在缩短“从开发到部署”路径的新玩家，对正在交付智能体产品的开发者而言直接相关。如果 Recurse 真能减少打包、托管和运维专用智能体所需的样板工作，它可能吸引那些认为通用智能体框架过于笨重或过度绑定单一云厂商的团队。 目前可确认的具体信息只有网址（recurse.run）和一句话定位；帖子没有说明支持的编程语言、模型供应商、托管方式、定价，也没有说明智能体是本地运行还是云端运行。在官网文档或后续讨论澄清技术范围之前，读者应将这些宣称视为未经证实。

rss · Show HN (self-made tools) · 9月25日 22:06

**背景**: AI 智能体是指利用大语言模型进行规划并执行动作（调用工具、API 和外部系统）的系统，而不仅仅是回答单个问题。“专用”智能体则被限定在某个狭窄任务或工作流上，例如文档撰写智能体或安全审计智能体，拥有各自的提示词、模型选择和工具权限。构建智能体相对容易，难的是可靠地部署它——这通常涉及容器化或无服务器托管、记忆与状态管理、与现有系统的集成，以及对性能漂移和回归的持续监控。Recurse 瞄准的正是这一运维侧的难题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opencode.ai/docs/agents/">Configure and use specialized agents . | OpenCode</a></li>
<li><a href="https://www.ibm.com/think/topics/ai-agent-deployment">How to Deploy AI Agents Across the Enterprise | IBM</a></li>
<li><a href="https://www.langchain.com/resources/ai-agent-frameworks">The best AI agent frameworks in 2026</a></li>

</ul>
</details>

**标签**: `#ai-agents`, `#agent-framework`, `#dev-tools`, `#show-hn`, `#deployment`

---

<a id="item-6"></a>
## [Swift1.5-Qwen3.8-Flash-Next 推理 token 较基座 Flash 减少约 60%](https://www.reddit.com/r/LocalLLaMA/comments/1wq56pf/swift15qwen38flashnext_is_phenomenal_vs_base/) ⭐️ 7.0/10

r/LocalLLaMA 用户 returnity 用同一套 Aider agentic 编程基准，在 xhigh 推理档位下对比了 UkisAI 的 Swift-1.5-Qwen3.8-Flash-Next（Q5_K_L，配合 Q8_0 engrams）与 Unsloth 的基座 Qwen3.8-Flash-Next（Q5_K_XL）。结果显示 Swift 版本首次通过率 41.1%、重试后通过率 86.9%，基座为 40.2% 和 90.7%；但 Swift 每题中位 token 用量仅 6,991、耗时 608 秒，而基座为 17,646 token 和 1,542 秒。 对于在本地跑模型做 agentic 编程的用户来说，这说明经过后训练变体的模型可以在基本保持任务质量的同时，消除大部分“过度思考”的无效循环，把实际耗时和 token 成本都削减约 60%。由于冗长的推理链一直是本地 agent 工作流最现实的瓶颈之一，一个“更省但同样好”的模型会直接改变可用的硬件门槛与上下文预算。 帖子称两者质量几乎一致，差异在统计上不显著：在 n=107 的配对比较中，99 例结果相同，Swift 仅 2 例胜、6 例负（McNemar 精确检验 p ≈ 0.29），格式良好的 diff 比例分别为 100.0%（Swift）与 98.1%（基座）。差距主要集中在最难的任务上——基座能挽回 84% 的重试样本，Swift 只有 78%；在基座最耗 token 的 20 个样本中，Swift 只用了 29% 的 token 并解出 16/20（基座 17/20），Swift 单例最高消耗 44k token，而基座高达 203k。C++ 代码压缩最明显，仅占基座 token 量的 29%，Python 与 JavaScript 约为 46%。

reddit · r/LocalLLaMA · /u/returnity · 9月25日 19:16

**背景**: Aider 是一款开源的 AI 结对编程工具，运行在终端中，让语言模型直接修改本地 Git 仓库里的文件；由于它会走真实的“多步编辑—测试—修复”循环，社区常把它当作 agentic 编程的评测工具。这里的“量化”指 llama.cpp 量化器生成的 GGUF 权重格式，Q8_0、Q5_K_M、Q4_K_M 等预设是在文件体积／显存占用与精度之间做权衡；文中出现的 Q5_K_L、Q5_K_XL 属于非标准的动态混合量化变体，而非 llama.cpp 的原生预设，而“Q8_0 engrams”指的是量化时用来保护敏感权重的校准／重要性数据。所谓“过度思考（overthinking）”指推理模型在难题上反复自我验证、动辄多烧几万 token 的现象，因此能抑制这种循环的变体就可以在精度不变的前提下大幅提速。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://aider.chat/">Aider - AI Pair Programming in Your Terminal</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp/blob/master/tools/quantize/README.md">llama.cpp/tools/quantize/README.md at master · ggml-org/llama.cpp</a></li>
<li><a href="https://qwen.readthedocs.io/en/latest/quantization/llama.cpp.html">llama.cpp - Qwen</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#qwen`, `#agentic-coding`, `#model-benchmark`, `#quantization`

---

<a id="item-7"></a>
## [开源 Kev 4B 准确率追平 Jev，但隐藏的 token 开销使 Jev 短请求贵达 12 倍](https://www.reddit.com/r/LocalLLaMA/comments/1wq2hfc/jev_vs_kev_opensource_jev_alternative_tested_side/) ⭐️ 7.0/10

一位开发者将开源模型 Kev 4B（Jared Palmer 基于 Qwen3.5-4B 的 Apache-2.0 微调版本）与 TypeSafe 的闭源模型 Jev 部署在同一端点上进行对比测试，使用 362 条在两个模型发布之后才出现的新样本（新的 arXiv 论文、Stack Exchange 问题和 GitHub issue），答案取自原始来源。结果显示两者在所有任务上的准确率差距都在 2 个百分点以内，属于该样本量下的噪声范围；但基准测试同时发现 Jev 会在每次请求中暗中多计算约 257 个固定输入 token，导致在标价相同的情况下，短请求的成本最高可达前者的 12 倍。 对于构建基于 LLM 的分类和路由流水线的团队来说，这项测试提供了一个可复现的理由去重新审视闭源 API：一个开放权重的 4B 模型就能在准确率上追平一家拿到融资的初创公司的旗舰决策模型，而仅 token 计算方式的差异就足以让实际账单成倍增长。这一发现还表明，按每百万 token 标出的价格可能具有误导性，因为未公开的提示词或系统开销同样会被计为输入 token。 Jev 在置信度校准和复述检测任务上领先（PAWS 上为 87.0% 对 74.5%），而 Kev 模型在知识类问题上的表现因其更依赖基础模型而落后。Kev 4B 本身并不是文本生成模型：它是 Qwen3.5-4B-Base 之上的一个 LoRA 适配器（秩为 16，3380 万个可训练参数）加一个指针头，在一次前向传播中为每个结构化问题输出概率分布；OpenRouter 上其定价为每百万输入 token 0.042 美元，输出免费。

reddit · r/LocalLLaMA · /u/facethef · 9月25日 17:30

**背景**: Jev 是总部位于旧金山的 TypeSafe AI 推出的专有“System One Model”，于 2026 年 9 月 15 日随 4000 万美元种子轮融资一起开放限量早期访问；与常规大语言模型不同，它不生成自然语言文本，而是以约 70–500 毫秒的速度返回经过校准的、类型安全的决策结果。Kev 是由 Jared Palmer 创建的开源（Apache-2.0）小型决策模型系列，对外提供与 Jev 相同的 /v1/systemone 接口契约，因此两者可以在同一端点上互换。PAWS 是复述检测领域的标准基准数据集，要求模型判断两个经过词语打乱的句子是否表达相同含义。作者通过自己创办的初创公司 Opper 路由调用这两个模型，并在 GitHub 上公开了基准测试代码、测试样本和结果，以便他人复现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/jaredpalmer/kev">GitHub - jaredpalmer/kev: Jev-like family of decision models ...</a></li>
<li><a href="https://github.com/jaredpalmer/kev/blob/main/docs/model-cards/kev-4b.md">kev/docs/model-cards/kev-4b.md at main · jaredpalmer/kev</a></li>
<li><a href="https://en.wikipedia.org/wiki/Jev_(AI_model)">Jev (AI model) - Wikipedia</a></li>
<li><a href="https://ukgovernmentbeis.github.io/inspect_evals/evals/reasoning/paws/index.html">PAWS : Paraphrase Adversaries from Word Scrambling</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#model-benchmark`, `#open-source`, `#qwen-finetune`, `#llm-inference`

---

<a id="item-8"></a>
## [Qwen3.8-27B：用 KV cache 移植提升输出质量](https://www.reddit.com/r/LocalLLaMA/comments/1wq76f6/qwen3827b_using_kv_cache_transplants_to_boost/) ⭐️ 7.0/10

一位本地大模型爱好者用数十个 NIAH（大海捞针）长上下文任务，对 Qwen3.8-27B 的三种 unsloth 量化版本（UD-Q6_K、UD-Q4_K_XL、UD-IQ3_S）进行了对比测试，并验证了一种“动态量化”策略：先用高精度量化开始推理，在运行中通过 llama.cpp 热重载分支切换到更低精度的模型，同时把 KV cache 从 f16 转换为 q8_0。他表示，同一模型不同量化版本之间的 KV cache 复用无需训练转换网络即可实现，且这种“由高到低”的分阶段策略优于一开始就使用低精度量化。 如果同一模型的不同量化版本之间的 KV cache 可以互换，那么显存受限的消费级 GPU 用户（本实验中为 24 GiB）就可以先用高精度启动任务，随着显存紧张再平滑降级到更省资源的量化版本，而不必整轮推理都锁定在单一量化上。这也为多智能体系统中提出的跨模型“缓存融合”提供了一条更廉价的路径——即把某个智能体的工作记忆直接嫁接到另一个模型上，而不再通过交接消息来序列化上下文。 所引用的 Cache-to-Cache（C2C）论文需要训练一个 3 层 MLP，把源模型（如 Qwen3-4B）的 KV cache 投影到目标模型（如 Qwen3-0.6B）的表示空间中；而本次实验押注的是：同一架构、同一训练流程的不同量化版本本身就已兼容，无需额外转换器。实验中各策略的上下文窗口按 24 GiB 显存设计（IQ3_S 最大 196,096 token，Q4_K_XL 最大 183,296，Q6_K 最大 175,104），f16 与 q8_0 之间的缓存转换由同一个 llama.cpp 分支完成。该文章属于探索性记录而非可直接使用的工具，且作者的基准测试结果尚未完整公布。

reddit · r/LocalLLaMA · /u/wadeAlexC · 9月25日 20:35

**背景**: 在 Transformer 推理中，KV cache 保存了已处理每个 token 对应的 key 和 value 张量，使模型在生成下一个 token 时不必重新计算整段上下文，相当于模型在生成过程中的“工作记忆”。量化则把模型权重（有时也包括 KV cache）压缩成更少的比特数，用少量精度换取显著降低的内存占用——Q6_K、Q4_K_XL 与 IQ3_S 就是 llama.cpp 体系中压缩程度依次提高的 GGUF 量化方案。NIAH（大海捞针）任务把某个特定值藏在很长的输入中，让模型把它找出来，因此常被用来压力测试长上下文能力。发表于 ICLR 2026 的 Cache-to-Cache（C2C）表明，大模型可以通过直接投影并融合彼此的 KV cache 来通信，其报告称准确率比单模型高 8.5–10.5%，比文本通信方式高 3.0–5.0%，延迟约降低到 1/2。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2510.03215">[2510.03215] Cache-to-Cache: Direct Semantic Communication ... Cache-to-Cache: Direct Semantic Communication Between Large ... Direct Semantic Communication Between Large Language Models Paper page - Cache-to-Cache: Direct Semantic Communication ... Cache-to-Cache: Direct Semantic Communication Between Large ... Cache-to-Cache Cache-to-Cache: Direct Semantic Communication Between Large ...</a></li>
<li><a href="https://github.com/thu-nics/C2C">Direct Semantic Communication Between Large Language Models</a></li>
<li><a href="https://huggingface.co/Qwen/Qwen3.8-27B">Qwen/ Qwen 3 . 8 - 27 B · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#kv-cache`, `#multi-agent`, `#llm-inference`, `#technique`

---

<a id="item-9"></a>
## [开发者训练 50MB 小模型，替代内部应用中的 Gemini Flash 调用](https://www.reddit.com/r/LocalLLaMA/comments/1wq3wn6/trained_my_first_small_language_model/) ⭐️ 7.0/10

一位开发者在 r/LocalLLaMA 上分享了自己第一次训练小语言模型的经历：模型体积约 50MB，用来替代内部高频团队应用中对字符串对做布尔分类判断的 Gemini Flash 调用。他从约 550 条真实用例出发，借助两个前沿模型生成相似样本来扩增到约 2500 条，在 RTX A6000 16GB 显卡上训练约 15 分钟，最终得到一个在 CPU 上仅需 0.06 秒、准确率 97% 的小模型。 这是一个具体且可复用的模式：把高频、窄范围的 LLM 任务蒸馏成极小的定制模型，用约两个百分点的准确率损失，换取超过一个数量级的延迟下降，并免去按次调用的 API 成本。对于构建延迟敏感型交互流程的开发者来说，这说明针对特定任务训练的小模型，可以在真正影响用户体验的指标上胜过调用前沿 API。 对照数据很能说明问题：确定性的 Python/JavaScript 规则只需几毫秒就能给出答案，但准确率只有 66% 出头；Gemini Flash 准确率高达 99%，但每次调用要 0.9–1.2 秒。作者也提到，原帖在解释到一半时就中断了，没有提供仓库、模型或数据集链接，并且把推理放到服务端会带来少量额外延迟；他还计划持续记录准确率和对比结果，以便不断补充训练数据。

reddit · r/LocalLLaMA · /u/newz2000 · 9月25日 18:26

**背景**: 小语言模型（SLM）通常指为出色完成某一具体任务而设计的紧凑模型，其内存、算力和成本开销远低于大模型——"小"是一个相对概念，业界并无严格的分界线，正是这种特性让端侧或自托管推理变得可行。Gemini Flash 是 Google 面向低延迟场景的模型档位，而"thinking budget"（思考预算）是一项限制模型在给出最终答案前可以生成多少推理 token 的设置，是控制延迟的主要手段。本地 LLM 则指完全运行在自有硬件上的模型，数据不出本地，也无需按 token 支付云端费用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://agneya.medium.com/small-language-models-are-winning-db22c3fbf062">Small Language Models Are Winning | by Agneya Pathare | Medium</a></li>
<li><a href="https://docs.nvidia.com/nim/large-language-models/1.14.0/thinking-budget-control.html">Thinking Budget Control (Thinking-Token Limiter) — NVIDIA NIM for Large Language Models (LLMs)</a></li>
<li><a href="https://iternal.ai/local-llm">Local LLM: What It Is, Best Models & Hardware (2026) - Iternal Technologies</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#small-language-models`, `#model-training`, `#llm-latency`, `#practical-experience`

---