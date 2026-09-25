---
layout: default
title: "Horizon Summary: 2026-09-25 (ZH)"
date: 2026-09-25
lang: zh
---

> 从 67 条内容中筛选出 15 条重要资讯。

---

1. [Public Browser v3.0 发布：开源 MCP 服务器宣称比 Playwright MCP 省 61% token](#item-1) ⭐️ 8.0/10
2. [用户用本地 Qwen-3.8-27B 编码智能体替代 API](#item-2) ⭐️ 8.0/10
3. [自制 CUDA 引擎让 Qwen3.8-Flash-Next 在 12GB 显卡上跑到 65 tok/s](#item-3) ⭐️ 8.0/10
4. [CLM：面向 Qwen3-8B 的开源权重投影头，宣称与 Jev 功能完全对齐](#item-4) ⭐️ 8.0/10
5. [Claude Code 云会话正式上线，Pro/Max 可领最高 250 美元额度](#item-5) ⭐️ 8.0/10
6. [Whiteboard（YC W26）：面向人机协作设计软件的开源画布式 IDE](#item-6) ⭐️ 7.0/10
7. [Opus 5.5 用约 4 美元把提示词变成解说视频](#item-7) ⭐️ 7.0/10
8. [jev-browse：为编码智能体提供更低成本的浏览器子任务](#item-8) ⭐️ 7.0/10
9. [Jev-pilot 为每个提示自动挑选 Claude Code 的模型、推理强度与技能](#item-9) ⭐️ 7.0/10
10. [Grev：把 grep 与 Jev 模型结合的“会思考的 grep”](#item-10) ⭐️ 7.0/10
11. [Canary（YC）发布 CLI，用智能体集群独立验证 AI 编写的代码](#item-11) ⭐️ 7.0/10
12. [Dunara：面向 Expo/React Native 的开源本地构建器，通过 MCP 接入自有 AI](#item-12) ⭐️ 7.0/10
13. [MemoryNotch 发布常驻 MacBook 刘海的离线录音与转写应用](#item-13) ⭐️ 7.0/10
14. [Liquid AI 发布 DSpark 草稿模型，加速 LFM2.5-VL-3B 推理](#item-14) ⭐️ 7.0/10
15. [UkisAI 发布 Swift 推理模型系列，思考 token 最多减少 63.4%](#item-15) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Public Browser v3.0 发布：开源 MCP 服务器宣称比 Playwright MCP 省 61% token](https://github.com/Silbercue/public-browser/releases/tag/v3.0.0) ⭐️ 8.0/10

一位来自汉堡的独立开发者发布了 "Public Browser" v3.0.0，这是一个免费开源的 MCP 服务器，通过 Chrome DevTools Protocol 直接驱动真实 Chrome 浏览器（使用用户自己的配置文件，因此无需重复登录），安装命令为 `claude mcp add public-browser -- npx -y public-browser@latest`。该版本提供完整的工具集、多标签页处理和脚本 API，并附有自测基准：相比 Playwright MCP 减少 61% 的 token、54% 的成本和 47% 的时间，相比 Chrome DevTools MCP 和 browser-use 的节省幅度更大。 浏览器自动化是 AI 智能体工作流中最消耗 token 的环节之一，因此减少上下文和调用次数能直接降低每次长时间智能体会话的成本与延迟。如果这些数据站得住脚，这个复用用户真实 Chrome 配置文件的开源方案，有可能成为 Playwright MCP 以及商业浏览器智能体服务的实用替代品。 该基准使用同一套测试框架共 30 项测试，Public Browser 3.0 与 agent-browser 各跑 5 次，其余竞品只跑 3 次；结果例如 Public Browser 为 79 次调用 / 3.02M token / 2.40 美元 / 261 秒，而 Playwright MCP 为 162 次调用 / 7.84M token / 5.22 美元 / 494 秒，browser-use 为 384 次调用 / 63.68M token / 36.06 美元 / 2187 秒。需要注意：这些数字完全由作者自报、没有第三方验证；Public Browser、agent-browser 和 Chrome DevTools 都在同一项测试（T5.2，navigator.webdriver 检测）上失败；作者也承认 agent-browser 单次响应体积仍小约 28%，只是总体需要更多轮次。

rss · Show HN (self-made tools) · 9月24日 21:20

**背景**: MCP（Model Context Protocol，模型上下文协议）是 Anthropic 于 2024 年 11 月推出的开放标准，用于规范 LLM 应用与外部工具和数据源的连接方式，此后已被 OpenAI、Google DeepMind 等主要厂商采用。Chrome DevTools Protocol（CDP）是用于检测、调试和控制 Chrome 及其他 Blink 内核浏览器的底层接口。Public Browser 所处的竞争领域已相当拥挤，同类工具包括 Playwright MCP、Vercel Labs 的 agent-browser 以及 browser-use 项目，它们都致力于让 AI 智能体在网页上点击、输入和导航。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://chromedevtools.github.io/devtools-protocol/">DOMSnapshot - DevTools Protocol</a></li>
<li><a href="https://github.com/vercel-labs/agent-browser">vercel-labs/agent-browser: Browser automation CLI for AI agents - GitHub</a></li>

</ul>
</details>

**标签**: `#MCP`, `#browser-automation`, `#AI-agents`, `#open-source`, `#developer-tools`

---

<a id="item-2"></a>
## [用户用本地 Qwen-3.8-27B 编码智能体替代 API](https://www.reddit.com/r/LocalLLaMA/comments/1wp0z3i/qwen3827b_is_good_enough_that_i_stopped_using_api/) ⭐️ 8.0/10

一位 r/LocalLLaMA 用户发帖称，在 Pi 智能体框架中完全本地运行 Qwen-3.8-27B 作为编码智能体已经足够好用，因此他不再使用付费 API。他的配置是 Q4_K_S 量化模型、上下文缓存量化为 Q8_0，并估算在自己的硬件上每 100 万 token 的输入成本约 2.4 美分、输出成本约 70 美分。 这是一个具体的实战数据点：一个中等规模（27B）的开源权重模型在 4 比特量化下，已经能够承担真正的智能体编码工作——自主完成多步骤重构，而不只是聊天。如果这类配置能够稳定复现，那么在成本、隐私与离线可用性方面都会强化自托管智能体的理由，也会对 nano-gpt.com 等 API 供应商的定价形成压力。 该用户提醒说这个模型「想得太多」，盯着它干活很痛苦，必须让它无人监督地自主运行；他还指出 Pi 的编辑工具是最薄弱环节，模型经常因为缩进出错而需要重试。他也试过 Swift-Qwen，速度确实更快但会陷入循环（原生 Qwen 很少出现这种情况）；他的 Pi 智能体不接 MCP，只保留最少工具（bash 加上 read、write、edit），用 Docker 做沙箱，而且跑在一台树莓派上。

reddit · r/LocalLLaMA · /u/Training-Respect8066 · 9月24日 12:59

**背景**: GGUF 是本地推理中广泛使用的模型文件格式，支持 GPU 卸载与 CPU 推理，其量化名称直接表示精度：Q4_K_S 是约 4 比特的「small」k-quant，以一定质量损失换取更小显存占用，而 Q8_0 通常被认为接近无损。Pi 是一个极简、token 效率高的编码智能体框架，定位为 Claude Code、Cursor 等 harness 的替代方案；MCP（模型上下文协议）则是 Anthropic 提出的开放标准，用于把 AI 助手连接到外部工具与数据——而这位用户刻意不用它，只保留极小的内置工具集。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pristren.com/blog/gguf-quantization-guide-2026/">GGUF Quantization Explained: Q4_K_M vs Q8_0 and When Each Matters</a></li>
<li><a href="https://github.com/earendil-works/pi">GitHub - earendil-works/pi: AI agent toolkit: unified LLM API, agent loop, TUI, coding agent CLI · GitHub</a></li>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#qwen`, `#ai-agents`, `#coding-agent`, `#quantization`

---

<a id="item-3"></a>
## [自制 CUDA 引擎让 Qwen3.8-Flash-Next 在 12GB 显卡上跑到 65 tok/s](https://www.reddit.com/r/LocalLLaMA/comments/1wp7zyb/qwen38flashnext_on_12gb_vram_65_tokens_per_second/) ⭐️ 8.0/10

一位开发者（GitHub 用户 Niko1221）发布了专为 Qwen3.8-Flash-Next 打造的自定义 CUDA 推理引擎 "Strata"，把此前在 llama.cpp 上用 IQ3_XXS 量化取得的 15 tok/s 生成、100-120 tok/s 提示处理提升到约 65 tok/s 生成和 430 tok/s 以上提示处理（12GB 显存的 RTX 5070）。帖子还给出了 128K 上下文下各量化的实测数据（Q2_0：65.1 tok/s 生成、543 tok/s 提示；IQ2_XS：52.0 / 472；IQ3_XXS：44.8 / 414）以及精确的 RAM+VRAM 合计需求，并提供了 GitHub 一键安装方式。 这说明像 Qwen3.8-Flash-Next 这样的巨型 MoE 模型，只要推理引擎针对单一模型专门优化（而非通用实现），就能在主流消费级配置上（12GB RTX 5070 + 64GB DDR5、Windows 系统）变得可用。对本地大模型社区而言，这是一个具体证据：llama.cpp 等通用引擎仍有大量性能没有被榨出来，而且这次给出的是可直接安装的产物，而不只是跑分。 该引擎目前只针对 CUDA 且只针对这一个模型做了优化，需要 37.6GB（Q2_0）、39.2GB（IQ2_XS）或 47GB（IQ3_XXS）的 RAM+VRAM 合计内存，另外视觉编码器还要额外占用 0.91GB；作者把自己用的量化大致对应到 Unsloth 的 Q3/Q4/Q5，并表示采用 RCO-GSQ 量化的 2-bit 版本速度更快。需要注意的是，帖子正文所说 IQ3_XXS 约 65 tok/s 高于基准表中 IQ3_XXS 的 44.8 tok/s，表里最快的是 Q2_0 配置。

reddit · r/LocalLLaMA · /u/KnownAd4832 · 9月24日 17:30

**背景**: Qwen3.8-Flash-Next 是阿里巴巴 Qwen 团队发布的大型开源多模态模型——Unsloth 将其描述为拥有 262K 上下文窗口的 125B 参数混合专家（MoE）模型——其权重远超 RTX 5070 的 12GB 显存，必须在显存和系统内存之间分层放置（offloading）。量化可以压缩这些权重："IQ3_XXS"、"Q2_0" 是 llama.cpp 推广的低比特 GGUF 格式，而 GSQ 与 RCO 是 ISTA-DASLab 提出的较新方法，先对每个张量做高精度的低比特标量量化，再在总大小预算下为每个张量分配量化类型。llama.cpp 是本地运行这类 GGUF 模型最主流的开源引擎，作者此前 15 tok/s 的结果就来自它；GitHub 上的 "Strata" 是他手写的 CUDA 替代实现，模型文件则来自 Hugging Face 上 ISTA-DASLab 的 GSQ-RCO GGUF 仓库。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF">ISTA-DASLab/Qwen3.8-27B- GSQ - RCO -GGUF · Hugging Face</a></li>
<li><a href="https://unsloth.ai/docs/models/qwen3.8-next">Qwen3.8-Flash-Next: How to Run Locally | Unsloth Documentation</a></li>
<li><a href="https://gist.github.com/Artefact2/b5f810600771265fc1e39442288e8ec9">GGUF quantizations overview · GitHub</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#llm-inference`, `#quantization`, `#llama.cpp`, `#github-repo`

---

<a id="item-4"></a>
## [CLM：面向 Qwen3-8B 的开源权重投影头，宣称与 Jev 功能完全对齐](https://www.reddit.com/r/LocalLLaMA/comments/1wouby6/jev_almost_dead_clm_vs_jev/) ⭐️ 8.0/10

一个名为 CLM（Contrastive Language Models）的 Qwen3-8B 开源权重投影头发布，代码托管在 GitHub（Contrastive-LM/CLM），权重发布在 HuggingFace，定位为 TypeSafe AI 的 Jev 决策接口的可自托管替代方案。作者声称这不是子集而是完整功能对齐：CLM 实现了相同的“System One”接口以及全部三种原语（Choice、Noul、Score），为 TypeSafe Jev 客户端编写的代码可以通过 `from clm import CLMClient, Choice, Noul, Score` 直接指向 clm-serve 端点。 Jev 是按调用计费的专有云模型，因此一个开源权重的即插即用替代品能让智能体开发者在其循环的决策层彻底去掉 API 成本与延迟。如果这一功能对齐的说法成立，它会把新兴的“System One”决策接口类别推向开放权重——用户可以基于自己的智能体轨迹进行微调，而不再被托管厂商锁定。 CLM 将状态头与动作头分离，对持久的工具与动作只需嵌入并缓存一次，作者在交互式浏览器与游戏智能体上测得比 Jev 快 4 到 13 倍；在智能体轨迹上微调后，它报告在 Terminal-Bench 2.1 上达到 87.6%、在 DeepSWE 验证器上达到 81.6%（而 Jev 在 DeepSWE 上零样本仅约 71%）。但权衡确实存在：Jev 在零样本开放域边界案例上仍占优（Berkeley Function Calling Leaderboard v4：99.2% 对 CLM-8B 的 95.2%；WikiRacing：30/30 对 26/30）；Jev 开箱支持 64K 上下文，而 CLM-8B 只在 2K 到 8K 上做标定；CLM 的概率由点积与 softmax 在当前请求传入的候选上计算，因此是相对于候选集的，而 Jev 的评分是针对绝对标准内部标定的。

reddit · r/LocalLLaMA · /u/R_Duncan · 9月24日 06:40

**背景**: TypeSafe AI 的 Jev 是一个“System One”模型：智能体不必为每一步都跑一次完整的大模型调用，而是把非结构化状态加一个问题发送出去，在约 70 到 500 毫秒内得到类型化的概率决策（候选选择分布、经过标定的真/假概率，或针对评分标准的打分）。投影头是挂在基础语言模型上的一个小模块，负责把模型的隐藏状态映射成特定输出格式，也就是说繁重的工作由现成的主干模型（如 Qwen3-8B）完成，新增且可训练的只有约 75 MB 的小型头。CLM 的主张正是：这些被训练来模仿 Jev 原语的小头，可以在本地复现同一套接口，并且可以按用户需求微调。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://typesafe.ai/blog/introducing-system-one-models-and-jev">Introducing System One Models & Jev - TypeSafe AI Blog</a></li>
<li><a href="https://www.langchain.com/blog/building-a-harness-with-jev">What Is Jev? A Guide to TypeSafe AI’s System One Model</a></li>
<li><a href="https://jevtypesafeai.com/">Jev/typesafe</a></li>

</ul>
</details>

**标签**: `#LocalLLM`, `#open-weights`, `#Qwen3`, `#GitHub repo`, `#LLM tools`

---

<a id="item-5"></a>
## [Claude Code 云会话正式上线，Pro/Max 可领最高 250 美元额度](https://code.claude.com/docs/en/claude-code-on-the-web) ⭐️ 8.0/10

Claude Code 云会话已结束研究预览并正式上线，面向 Pro、Max、Team 和 Enterprise 用户开放，合上笔记本后任务仍可在云端继续运行，并可从浏览器、手机、桌面应用或终端查看和接管。现有订阅用户可一次性领取 100 美元（Pro）或 250 美元（Max）额度，通过官方领取页或直接在 Claude Code 中执行 /claim-credit 获取。 这意味着编程代理从受限于本地笔记本的终端会话，转向可持久运行的云端基础设施，付费 Claude 订阅实际上等于附带了用于异步代理任务的云端算力。对需要并行处理多个任务的开发者而言，这带来了并行执行与长时间运行任务的能力；但中国大陆、香港和澳门不在 Anthropic 支持地区名单内，该地区用户的可用性受限。 额度需在太平洋时间 10 月 7 日 23:59 前领取，并在 11 月 4 日 23:59 到期，且仅可用于 Cloud sessions。资格需登录后按账号及条款判定，并非所有用户都能领取；会话还可通过 --cloud 与 --teleport 命令迁移，并内置 GitHub 工具、支持自动修复 pull request。

telegram · zaihuapd · 9月24日 02:45

**背景**: Claude Code 是 Anthropic 的代理式编程工具，能够代替用户编辑文件、运行测试和执行命令，传统上运行在本地终端会话中，一旦关机任务就会中断。云会话则把代理放到 Anthropic 托管的机器上运行，其云环境内置 GitHub 集成，可直接读取 issue、列出 pull request、获取 diff 并发表评论，无需额外配置。运行这类代理会消耗大量 token 与算力，因此发布时配套了推广额度；同时可用范围受 Anthropic 的《支持国家与地区》政策约束，目前不包含中国大陆、香港和澳门。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://code.claude.com/docs/en/claude-code-on-the-web">Use Claude Code in the cloud</a></li>
<li><a href="https://www.reddit.com/r/ClaudeCode/comments/1wojd4c/cloud_sessions_are_officially_available_and_out/">Cloud sessions are officially available and out of research preview! They ...</a></li>
<li><a href="https://www.anthropic.com/supported-countries">Supported countries and regions \ Anthropic</a></li>

</ul>
</details>

**社区讨论**: r/ClaudeCode 子版块上的讨论集中在云会话结束研究预览以及额度金额上，有用户指出 Claude 订阅如今实际上相当于附带了供代理使用的云端计算机。整体情绪偏正面且务实，关注点主要在于如何领取和使用这笔额度，而非技术层面的质疑。

**标签**: `#AI福利`, `#Claude Code`, `#AI Agents`, `#Coding Tools`, `#Cloud Sessions`

---

<a id="item-6"></a>
## [Whiteboard（YC W26）：面向人机协作设计软件的开源画布式 IDE](https://github.com/devdotfast/whiteboard) ⭐️ 7.0/10

由 Sid、Alex、Ketan 和 Milan 四人组成的团队发布了 Whiteboard——一款基于 CodeOSS 构建、以 MIT 许可证开源发布的桌面应用，让人类与编码智能体在同一工作空间中共同设计软件架构。它可以接入 Claude Code、Codex 等工具，为智能体提供 SDK，使其能在应用内画布上绘制并流式输出图表（时序图、ER 图、trace 片段），同时内置了用 Rust 编写的 AST 级语义 diff 查看器，以及可将智能体 trace 关联回需求的 Decision Log（决策日志）。 智能体编程让代码生成速度远超人类审查速度，从而产生创始人所称的“认知债务”——即大量无人真正理解的 PR 被合并。Whiteboard 正是针对这一缺口，把人的参与环节上移到架构与规格层面，并将自身定位为 Greptile 等自动化审查工具的补充；同时它以免自托管模式开源，并规划了付费托管版本。 目前 Whiteboard 中还不能直接编辑文件，因此“IDE”这个称呼存在争议；另一个早期担忧是图表准确性——有 HN 评论者发现示例图中某个迁移标签与底层 diff 并不吻合。语义 diff 查看器采用了一些合理默认值：新增的大函数会被总结成伪代码，单元测试和大段文档变更则被折叠隐藏，并且这一切都可通过基于 WASM 的插件系统自定义。

hackernews · sidharthkmenon · 9月24日 17:21 · [社区讨论](https://news.ycombinator.com/item?id=49833867)

**背景**: CodeOSS 是微软 Visual Studio Code 所基于的开源仓库，因此构建在其之上的 Whiteboard 能直接继承 VS Code 的快捷键和用于代码导航的语言服务器协议（LSP）支持。Claude Code 和 OpenAI 的 Codex 属于智能体式编程工具，可以代开发者阅读代码库、修改文件并执行命令。语义化的 AST diff 作用于代码的抽象语法树而非原始文本行，因而能按语义总结或隐藏变更，而不必逐行展示；文中提到的“认知债务”指的是当智能体交付代码的速度超过人类队友的理解速度时，所积累起来的理解鸿沟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Visual_Studio_Code">Visual Studio Code - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenAI_Codex_(AI_agent)">OpenAI Codex (AI agent) - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论整体偏正面：有人认为“边生成边流式绘制图表”这种动效是“12 个月内会到处都是”的技术，也有人称赞语义 diff 查看器填补了多数编程工具做得不够好的环节。主要质疑集中在 LLM 生成图表的准确性——有读者把示例图与 diff 对照后发现了没有依据的“wait for release”标签——以及一个连文件都不能编辑的工具是否真的配叫 IDE。

**标签**: `#ai-agents`, `#open-source`, `#developer-tools`, `#github`, `#ide`

---

<a id="item-7"></a>
## [Opus 5.5 用约 4 美元把提示词变成解说视频](https://launchvideo.io/) ⭐️ 7.0/10

围绕 launchvideo.io 的一条 Hacker News 讨论帖，聚焦 Claude Opus 5.5 生成完整解说视频的能力，评论区还给出了实打实的证据：两条 r/ClaudeAI 帖子显示，用 Claude Code 工作流制作完整视频分别只花了约 3.21 美元和 4 美元的 OpenRouter API 费用。帖子中分享的提示词还让其他用户能在自己的项目上复现类似效果。 这条新闻为端到端的 AI 视频制作给出了一个具体的价格标签——只需几美元的 API 开销，这对正在权衡 AI 自动化与传统内容生产流程的人很有参考价值，也说明智能体式编程工具正从软件任务扩展到创意媒体产出。讨论本身也折射出一个日益明显的矛盾：自动化内容生成正变得又便宜又快，但质量与原创性的疑问依然悬而未决。 评论区的质疑者指出，其底层做法——先做一个带转场动画的 HTML 演示文稿，再用 Playwright/ffmpeg 录屏——在此前的模型（如 Opus 4.6）上就已经可行，因此这套工作流对 Opus 5.5 的依赖可能没有标题所暗示的那么大。此外，链接站点本身只是一个宣传落地页，没有代码仓库或可下载的工具，读者只能借助第三方 Reddit 提示词来复现，而没有官方的成品可用。

hackernews · iacguy · 9月24日 20:28 · [社区讨论](https://news.ycombinator.com/item?id=49836374)

**背景**: Claude Opus 5.5 是 Anthropic 的旗舰模型，主打长时间运行的智能体式编程和专业知识工作；Anthropic 表示它在智能体式编程方面处于领先，且在典型工作负载下的运行成本比上一代 Opus 5 低约 40%。Claude Code 是 Anthropic 的智能体式命令行工具，能够规划并执行写文件、跑脚本等多步骤任务。OpenRouter 是一个统一的 API 网关，可将请求路由到多种模型并给出每次请求的费用。解说视频——用旁白动画讲解某个主题的短片——是常见的营销与科普形式；帖中所说的成本仅指模型 API 的直接开销，并不包含剪辑、托管或人工审核的时间成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/claude-opus-5-5">Introducing Claude Opus 5.5 \ Anthropic</a></li>
<li><a href="https://platform.claude.com/docs/en/models/opus-5-5/overview">Claude Opus 5.5 - Claude Platform Docs</a></li>
<li><a href="https://www.anthropic.com/claude/opus">Claude Opus \ Anthropic</a></li>

</ul>
</details>

**社区讨论**: 评论区观点两极分化。一些人对结果十分惊艳，直接把分享的提示词用在自己项目上，每次约花 4 美元；另一些人则认为这类产出不过是低投入的自动化内容，指出 Reddit 和 X 上有远比这更惊艳的作品，还有人认为这套技术并非某一模型独有的能力。也有评论者借此反思了套壳 LLM 的 SaaS 产品究竟价值何在。

**标签**: `#AI video generation`, `#Claude/Opus`, `#prompts`, `#AI workflow`, `#creative AI`

---

<a id="item-8"></a>
## [jev-browse：为编码智能体提供更低成本的浏览器子任务](https://github.com/danielnc/jev-browse) ⭐️ 7.0/10

一个 Show HN 帖子发布了 jev-browse（github.com/danielnc/jev-browse），这是一个开源工具，用于把浏览器子任务从编码智能体中剥离出来，并声称成本大约只有替代方案的三分之一。该帖子仅有 1 分、0 条评论，提交内容除仓库链接外没有任何说明、基准测试或版本信息。 Token 与推理成本是编码智能体访问网页时最主要的现实瓶颈之一，因此任何声称能把成本降到约三分之一的方案，对构建智能体工作流的开发者都直接相关。如果该说法成立，那么表单填写、文档查询和端到端测试等浏览器密集型任务就能以更低的成本大规模运行。 帖子没有提供基准测试、对比方法，也没有说明那三分之一成本数字是如何测得的，因此该说法目前未经验证。它同样没有说明实现语言、许可证、支持的模型或浏览器运行时，而且仅有 1 分和 0 条评论，基本没有经过社区审视。

rss · Show HN (self-made tools) · 9月24日 23:08

**背景**: Claude Code、GitHub Copilot 等编码智能体可以把特定任务委派给子智能体，从而避免大量工具输出挤占主上下文窗口。当这些任务涉及网页时，智能体通常会驱动 Playwright 之类的浏览器自动化框架，而每一次抓取页面或 DOM 快照都会消耗 token。jev-browse 似乎把自己定位为一个专门层，用比主智能体亲自浏览更低廉的方式处理这些浏览器子任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://playwright.dev/">Web automation and testing for apps, scripts, and AI agents</a></li>
<li><a href="https://code.claude.com/docs/en/sub-agents">Create custom subagents - Claude Code Docs</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#browser automation`, `#GitHub repo`, `#developer tools`

---

<a id="item-9"></a>
## [Jev-pilot 为每个提示自动挑选 Claude Code 的模型、推理强度与技能](https://github.com/Akramovic1/jev-pilot) ⭐️ 7.0/10

一位开发者在 Hacker News 的 Show HN 板块发布了 Jev-pilot，这是一个开源 GitHub 项目（作者为 Akramovic1），能够针对每一条提示自动选择 Claude Code 的推理强度（effort）、模型和技能（skill）。开发者不再需要为每个任务手动决定用哪套配置，该工具会代替用户完成这一路由决策。 像 Claude Code 这样的编码智能体如今提供了越来越多的模型、推理强度档位和可复用技能组合，手动挑选这些配置会给日常工作带来额外的操作负担和成本。按提示自动路由的机制顺应了一个更大的趋势，即在智能体工作流之上增加一层编排层，以便在质量、延迟和 token 开销之间取得平衡，这对所有正在构建或使用编码智能体的人都具有现实意义。 这条 Hacker News 帖子几乎没有获得关注——仅有 2 分和 0 条评论——说明该项目非常早期，尚未经过外部验证。从命名来看，路由决策似乎由 “Jev” 完成；第三方报道将 Jev 描述为 TypeSafe AI 提供的托管模型，专门用于有边界的判断任务，例如选择类别或给某个命题打分，这意味着提示分类可能被委托给外部托管服务，而非完全在本地完成。

rss · Show HN (self-made tools) · 9月24日 22:21

**背景**: Claude Code 是 Anthropic 推出的智能体式编码工具，可在终端、IDE、桌面应用或浏览器中运行，能够读取代码库、编辑文件、执行命令并与开发者现有的工具链集成。该产品近年来的版本允许用户在不同模型档位和推理强度之间进行选择，并支持 “skills”（技能），即智能体可以调用的可复用指令包。Jev-pilot 是一个第三方封装工具，试图自动完成上述选择，因此理解它既需要知道 Claude Code 是什么，也需要了解像 Jev 这类分类/判定模型通常用来做什么。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Claude_Code">Claude Code</a></li>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://medium.com/@adnanmasood/jev-and-the-return-of-the-classifier-490ce05e5d3d">Jev and the Return of the Classifier | by Adnan Masood, PhD. - Medium</a></li>

</ul>
</details>

**标签**: `#claude-code`, `#ai-agents`, `#developer-tools`, `#github`, `#llm-workflow`

---

<a id="item-10"></a>
## [Grev：把 grep 与 Jev 模型结合的“会思考的 grep”](https://github.com/aurorainfra/grev) ⭐️ 7.0/10

aurorainfra 在 GitHub 上以 Show HN 的形式发布了 Grev，把它描述为 grep 的“会思考”版本——把传统的命令行文本搜索与 AI 模型 Jev 结合起来。该项目已经发布到 v0.2.0 版本，以公开仓库的形式提供，读者可以直接安装试用。 它体现了一种正在兴起的做法：把面向机器的 AI 模型挂到人们熟悉的 Unix 工具上，这可能让终端搜索从字面模式匹配转向基于意图的查询。如果这种思路站得住脚，长期泡在 shell 里的开发者无需离开命令行，就能用上一类全新的 AI 增强版 coreutils。 根据公开资料，Jev 并不是生成自然语言文本的 LLM：它提供 66k token 的上下文窗口，定位于智能体、分类以及 JSON/工具调用等用途。Grev 的 v0.2.0 更新日志提到按 token 而非字节来计算请求大小，并修复了在密集日志上的 pickv 问题；该仓库由 magik6k 在 aurorainfra 组织下维护，该组织同时维护 aurora-skills。

rss · Show HN (self-made tools) · 9月24日 21:46

**背景**: grep 是已有数十年历史的 Unix 命令行文本搜索工具，开发者常用它通过正则表达式扫描源代码和日志。Jev 是旧金山公司 TypeSafe AI 开发的专有模型，于 2026 年 9 月 15 日随 4000 万美元种子轮融资一同开放有限早期访问，官方称其为 “System One Model”，它不生成自然语言文本，而是在软件内部做决策。Grev 把两者结合起来，目标是理解搜索意图，而不仅仅是做字面模式匹配。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Jev_(AI_model)">Jev (AI model) - Wikipedia</a></li>
<li><a href="https://typesafe.ai/blog/introducing-system-one-models-and-jev">Introducing System One Models & Jev - TypeSafe AI Blog</a></li>
<li><a href="https://github.com/aurorainfra/grev/releases/tag/v0.2.0">Release v0.2.0 · aurorainfra/grev</a></li>

</ul>
</details>

**社区讨论**: 讨论非常冷清——Hacker News 上只有 2 分和 1 条评论——因此还没有形成任何真正的共识。在这条评论中，作者表示这个工具起初只是觉得做出来好玩，但实际用下来确实对自己有帮助。

**标签**: `#ai-tools`, `#developer-tools`, `#grep`, `#github`, `#cli`

---

<a id="item-11"></a>
## [Canary（YC）发布 CLI，用智能体集群独立验证 AI 编写的代码](https://www.runcanary.ai/) ⭐️ 7.0/10

创始人 Aakash 和 Viswesh 发布了 Canary，这是一个可用 `npm i -g @runcanary/cli` 安装的命令行工具，它会对代码仓库做一次冷快照，然后在远程沙箱中部署智能体集群，专门排查 AI 所写变更集中的运行时缺陷。Claude、Codex 等编码智能体把变更集、预期行为和团队知识交给 Canary，Canary 再返回带有证据的发现结果，让智能体据此修复并申请对失败场景的再次验证。 随着编码智能体编写的代码在生产代码中占比越来越高，静态评审和现有测试套件无法覆盖仅表现为行为异常的缺陷，因此独立的验证层有可能成为 AI 辅助开发流程的标准环节。如果它确实有效，团队对智能体生成代码的信任依据将从“diff 看起来没问题”转向可复现的运行时证据，这会影响到所有用 Claude Code、Codex 等工具交付代码的团队。 Canary 会把用户提供的意图和团队知识与来自 Notion、Linear 等工具的需求、决策和历史问题结合起来，对比变更前后的代码，并沿调用方、依赖和状态迁移追踪影响；针对每个可疑故障，它会选择运行时验证、静态分析、单元测试或集成测试等手段，并能通过编码智能体把澄清性问题回传给开发者。官方表示产品仍处于早期阶段，未提供基准测试或独立的有效性数据，因此实际效果尚未得到验证。

rss · Show HN (self-made tools) · 9月24日 20:57

**背景**: 编码智能体是由大模型驱动、可以自主修改并提交代码的工具，如何验证其产出已成为瓶颈。“智能体集群（agent swarms）”指多个专用智能体协同完成同一任务，通常会利用不同模型家族各自的优势。沙箱是隔离的虚拟环境，可以安全地执行不受信任或实验性的代码，在其中灌入数据、配置权限、模拟第三方集成都不会影响生产环境。Canary 将自己定位为构建在通用智能之上的专用验证框架，把能产生不同类型证据和保证的多种验证手段组合起来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.runcanary.ai/">Canary · AI writes your code. Canary tests it.</a></li>
<li><a href="https://swarmai.site/">OpenCode Swarm - Production-Ready AI Code That Actually Works</a></li>
<li><a href="https://fly.io/learn/agent-sandbox/">Agent Sandboxes: Isolated Runtimes for Testing AI Agent Behavior · Learn</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#code verification`, `#developer tools`, `#LLM`, `#CLI`

---

<a id="item-12"></a>
## [Dunara：面向 Expo/React Native 的开源本地构建器，通过 MCP 接入自有 AI](https://dunara-studio.com/) ⭐️ 7.0/10

一位开发者发布了 Dunara，这是一个面向 Expo 和 React Native 应用的开源本地构建器，允许用户接入自己的 AI 提供商，在名为 Studio 的界面中不断打磨应用，最后导出完整源代码。该工具支持通过 Model Context Protocol（MCP）或直接在 Studio 中与应用交互，作者将其发布到 Hacker News 并明确寻求反馈。 它契合了日益流行的一类工具形态：可自托管、自带模型的开发工具，让 AI 辅助的应用开发掌握在开发者手中，而不是被锁在某个厂商的托管平台里。如果它能逐渐成熟，就可能降低以自然语言驱动的方式产出真实可导出的 Expo/React Native 代码库的门槛；但作为一个全新项目，它尚未得到验证。 Dunara 被描述为本地运行且开源，需要用户自备 AI 连接，而不是内置模型或 API Key，并且强调可以导出“完整源代码”，以免项目被锁死在工具之中。此次发布处于非常早期的阶段——在 Hacker News 上仅获得 1 分和 1 条评论，帖子正文也没有附仓库链接，因此其成熟度、许可证和维护状况都未经验证。

rss · Show HN (self-made tools) · 9月24日 20:07

**背景**: Expo 是一个被广泛使用的框架和工具链，用于基于 React 和 React Native 构建 iOS、Android 与 Web 原生应用，它提供托管式工作流，让开发者主要编写 JavaScript 而无需接触原生代码。Model Context Protocol（MCP）是 Anthropic 于 2024 年 11 月发布的一项开放标准，用于规范 AI 模型如何连接外部工具、文件和数据源，此后已被 OpenAI、Google DeepMind 等主要厂商采纳。Dunara 把这两者结合在一起：一个支持 MCP 的 AI 客户端在本地驱动对 Expo/React Native 项目的修改，最终生成的源码可以像普通代码库一样被导出。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://expo.dev/">Expo</a></li>

</ul>
</details>

**标签**: `#ai-agents`, `#mcp`, `#open-source`, `#react-native`, `#dev-tools`

---

<a id="item-13"></a>
## [MemoryNotch 发布常驻 MacBook 刘海的离线录音与转写应用](https://memorynotch.app/) ⭐️ 7.0/10

一位开发者在 Hacker News 的 Show HN 板块发布了 MemoryNotch：一款常驻 MacBook 刘海区域的应用，可完全离线录制并转写音频，并声称其准确率高于 Whisper 等商业转写工具。该应用发布在 memorynotch.app，作者表示这最初只是自己日常使用的项目，后来在朋友建议下才决定产品化。 这反映出市场对「隐私优先、完全本地」语音转写方案的旺盛需求——无需云 API、无需订阅、音频不出本机，而 Whisper Notes 以及各类离线转写应用已经在这一领域布局。如果其准确率声称属实，这种常驻刘海的录音工具可以显著降低在 macOS 上记录会议与笔记的操作门槛。 这次发布几乎没有提供技术细节：没有公开代码仓库、没有基准测试，也没有说明底层使用的是哪种模型或方案，因此「比 Whisper 更准」的说法目前缺乏证据支撑。截至撰写时，该 HN 帖子仅有 4 分、0 条评论，尚无任何独立验证或用户反馈。

rss · Show HN (self-made tools) · 9月24日 20:01

**背景**: Whisper 是 OpenAI 开源的自动语音识别系统，使用了约 68 万小时的多语言网络音频训练，如今已成为大多数本地转写应用所依赖或被比较的事实基准。由于 Whisper 可以完全在设备端运行，一批 Mac 和 iPhone 应用开始提供全离线听写与会议转写功能，以牺牲部分准确率和速度换取隐私。与此同时，MacBook 的刘海（屏幕顶部摄像头缺口区域）也已成为 macOS 上常驻小工具青睐的界面位置。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Whisper_(speech_recognition_system)">Whisper ( speech recognition system) - Wikipedia</a></li>
<li><a href="https://openai.com/index/whisper/">Introducing Whisper | OpenAI</a></li>
<li><a href="https://whispernotes.app/">Whisper Notes - Offline Whisper Transcription App | iPhone & Mac</a></li>

</ul>
</details>

**标签**: `#transcription`, `#offline-ai`, `#macos-app`, `#speech-to-text`, `#ai-tools`

---

<a id="item-14"></a>
## [Liquid AI 发布 DSpark 草稿模型，加速 LFM2.5-VL-3B 推理](https://huggingface.co/blog/LiquidAI/lfm2-5-vl-dspark) ⭐️ 7.0/10

Liquid AI 在 Hugging Face 博客上发布了 DSpark——一个针对其视觉语言模型 LFM2.5-VL-3B 的实验性草稿模型，通过投机解码（speculative decoding）在不改变输出质量的前提下加速推理。官方公布的数据显示，解码速度在端侧（Apple M5 Max 搭配 MLX）最高提升 3.13 倍，在 GPU 上提升 2.66 倍。 推理成本和延迟是部署视觉语言模型的主要瓶颈，在算力与内存受限的端侧设备上尤其如此。一个即插即用、能在不降低质量的情况下带来数倍解码加速的草稿模型，降低了在本地运行多模态模型的门槛，而这正是 Liquid AI 所瞄准的端侧场景。 DSpark 为 3B 的目标模型额外增加了 2.8 亿参数，参数量增幅约 8.9%，官方明确将其定位为实验性模型。公布的加速数据是在特定硬件与运行时上测得的（Apple M5 Max 搭配 MLX，以及某种 GPU 配置），因此实际加速比会因设备、批大小和解码设置的不同而变化。

rss · Hugging Face Blog · 9月24日 14:08

**背景**: 投机解码（speculative decoding）将一个小而快的“草稿”模型与一个较大的“目标”模型配对：草稿模型先预测后面的若干 token，目标模型在一次前向传播中批量校验这些 token，接受其中正确的部分，从而在保持目标模型输出分布不变的前提下加速生成。Liquid AI 是一家 2023 年从 MIT 分拆出来的美国 AI 公司（创始人包括 Ramin Hasani、Mathias Lechner、Alexander Amini 和 Daniela Rus），专注于可在设备本地运行、无需联网的紧凑型“液态”基础模型。LFM2.5-VL-3B 是一个约 30 亿参数的视觉语言模型，可以同时接受图像和文本输入。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/LiquidAI/lfm2-5-vl-dspark">Accelerating vision-language models with LFM2.5-VL-DSpark</a></li>
<li><a href="https://github.com/hanzhad/squelch-news-engine/issues/1102">Accelerating vision-language models with LFM2.5-VL-DSpark · Issue #1102 · hanzhad/squelch-news-engine</a></li>
<li><a href="https://en.wikipedia.org/wiki/Liquid_AI">Liquid AI</a></li>

</ul>
</details>

**标签**: `#vision-language models`, `#inference acceleration`, `#model release`, `#Hugging Face`, `#LLM engineering`

---

<a id="item-15"></a>
## [UkisAI 发布 Swift 推理模型系列，思考 token 最多减少 63.4%](https://www.reddit.com/r/LocalLLaMA/comments/1wp6gal/ukisai_swift_series_27b_flash_next_and_bonsai_2/) ⭐️ 7.0/10

UkisAI 发布了基于 Qwen 的高效推理模型系列 Swift，包括 Swift1.5 27B、Swift Flash Next 和 Swift Bonsai 2，并同时提供了呼声很高的 27B 与 Flash Next 的 GSQ-RCO 量化版本。此前发布的 Swift Qwen 3.8 27B 据称在 13 天内下载量突破 35 万次。 在现代推理模型中，"过度思考"是推高成本与延迟的最大元凶之一；在准确率基本持平甚至略有提升的前提下把思考 token 削减 39%–63%，直接意味着消费级硬件上更便宜、更快的本地推理。对本地大模型社区而言，这是一套可直接下载、并附带多种量化格式的模型家族，而不只是一篇研究论文。 UkisAI 公布的数据是：Swift1.5 27B 思考 token 减少 58.5% 且得分比基座高 0.35%；Flash Next 思考 token 减少 63.4%、速度提升 1.8 倍，但在 xhigh 档位比基座低 0.2%；Bonsai 2 思考 token 减少 39.8%、准确率提升 0.19%，但仍被标注为实验性。量化格式涵盖 GGUF、NVFP4、MLX 和 W4A16，基准测试在 GPQA、AIME26、LiveCodeBench、ERQA 与 Terminal Bench 2.1 上以五个随机种子各跑五次，后续还将推出 9B 版本，并提供免费的 Research API 和 HuggingFace Spaces 试用入口。

reddit · r/LocalLLaMA · /u/Secure_Recording_472 · 9月24日 16:32

**背景**: 推理型大模型在作答前会生成很长的思维链，而模型容易陷入"过度思考循环"，白白消耗 token 却不改善答案。UkisAI 表示，Swift 的训练方式是对与这类病态模式相关的 token 施加惩罚，再通过强化学习恢复准确率：所用 GSPO 是 Qwen 团队提出的序列级算法，是 GRPO 的变体，在序列而非 token 粒度上做裁剪与优化；同时使用 OPD（在策略蒸馏），即让模型从自己生成的轨迹中学习。GSQ-RCO 则来自 ISTA-DASLab 的量化方案：GSQ 对每个张量做精确的低比特标量量化，RCO 则在总大小预算约束下为各张量分配合适的量化类型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://qwenlm.github.io/blog/gspo/">GSPO: Towards Scalable Reinforcement Learning for Language Models | Qwen</a></li>
<li><a href="https://verl.readthedocs.io/en/latest/algo/opd.html">On-Policy Distillation (OPD) — verl documentation</a></li>
<li><a href="https://huggingface.co/ISTA-DASLab/Qwen3.8-27B-GSQ-RCO-GGUF">ISTA-DASLab/Qwen3.8-27B- GSQ - RCO -GGUF · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#reasoning-models`, `#quantization`, `#qwen`, `#model-release`

---