---
layout: default
title: "Horizon Summary: 2026-08-02 (ZH)"
date: 2026-08-02
lang: zh
---

> 从 53 条内容中筛选出 14 条重要资讯。

---

1. [Draco：用 Rust 打造的可自托管 Firecrawl 替代品，专为 LLM 提取干净数据](#item-1) ⭐️ 9.0/10
2. [MicroCodex：用 C++重写 OpenAI Codex，二进制小于 1MB](#item-2) ⭐️ 9.0/10
3. [Kota：开源工具，让 AI 代理 CLI 同处一室](#item-3) ⭐️ 9.0/10
4. [Mousecrack 用深度学习绕过光标检测验证码](#item-4) ⭐️ 9.0/10
5. [llama.cpp 为 DeepSeek V4 Flash 添加 MTP/DSpark 支持](#item-5) ⭐️ 9.0/10
6. [开发者通过 NVMe 流式加载在 8GB 内存 CPU 上运行 Kimi K3](#item-6) ⭐️ 9.0/10
7. [西蒙·威利森 2026 年 7 月通讯：新 AI 模型与 MCP](#item-7) ⭐️ 8.0/10
8. [Mu：Show HN 用于构建 AI 智能体的工具](#item-8) ⭐️ 8.0/10
9. [用 PyTorch 从头实现 Kimi K3 论文](#item-9) ⭐️ 8.0/10
10. [基准测试表明不应量化 DeepSeek V4 Flash 的 KV Cache](#item-10) ⭐️ 8.0/10
11. [Karpathy 点赞 sqliteai/waste：从 NVMe 流式运行 Kimi K3 推理](#item-11) ⭐️ 7.0/10
12. [Authoryze 发布 AI 代理支付控制平台](#item-12) ⭐️ 7.0/10
13. [开发者开源 15 年‘第二大脑’，发布 660 篇笔记](#item-13) ⭐️ 7.0/10
14. [DeepSeek-V4-Flash Dwarfstar 在 M2 Ultra Mac 上的速度测试](#item-14) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Draco：用 Rust 打造的可自托管 Firecrawl 替代品，专为 LLM 提取干净数据](https://github.com/0xchasercat/draco/) ⭐️ 9.0/10

Draco 是一个新发布的开源（MIT/Apache-2.0）Rust 单二进制网络爬虫，在 Hacker News 上作为 Firecrawl 的可自托管替代方案推出。它采用分层升级引擎——通过 TLS/JA4 指纹模仿进行隐身抓取、用于 SPA 的进程内 V8 isolate，以及真实浏览器回退——从而为 LLM 输出干净的 Markdown 或结构化 JSON。 在现代网站上进行 AI 工作流所需的爬取成本高昂，且越来越容易被反机器人系统拦截，迫使开发者为托管的按页 API 付费，或运行内存占用巨大的无头浏览器。Draco 提供了一种可自托管、低内存的替代方案（每次隐身请求约 20MB），能够绕过 Cloudflare 等防护墙，让开发者在提取 LLM 可用数据时获得更多控制权并降低费用。 该分层引擎包含一个模仿真实浏览器网络签名的自定义 TLS/JA4 指纹、一个能在个位数毫秒内水合 DOM 并拦截页面隐藏 JSON API 的进程内 V8 isolate，以及一个在必要时驱动真实浏览器的回退机制。Draco 还附带守护进程模式（提供与 Firecrawl 兼容的 REST API）、内置模型上下文协议（MCP）服务器、并行多引擎网络搜索，以及有状态的交互模式；作者指出它仍是 WIP，在不太常见的网站上可能会出问题。

rss · Show HN (self-made tools) · 8月2日 20:48

**背景**: Firecrawl 是一款专为 LLM 时代设计的流行开源网页抓取 API：给它一个 URL，它就会返回干净的、可供 LLM 直接使用的 Markdown，而不是原始 HTML。但其托管服务按页收费，且自托管需要相当多的基础设施。JA4 是一种 TLS 客户端指纹识别标准，通过 TLS Client Hello 报文中的属性来识别客户端，Cloudflare 等反机器人服务会利用它来检测无头浏览器。V8 isolate 是 V8 JavaScript 引擎的轻量级隔离实例，无需完整的图形浏览器即可执行脚本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.firecrawl.dev/">Firecrawl - The context API to search, scrape , and interact with the...</a></li>
<li><a href="https://github.com/FoxIO-LLC/ja4">GitHub - FoxIO-LLC/ja4: JA4+ is a suite of network ...</a></li>
<li><a href="https://v8docs.nodesource.com/node-0.8/d5/dda/classv8_1_1_isolate.html">v8: Isolate Class Reference</a></li>

</ul>
</details>

**标签**: `#web scraping`, `#Rust`, `#self-hosted`, `#LLM`, `#AI tool`

---

<a id="item-2"></a>
## [MicroCodex：用 C++重写 OpenAI Codex，二进制小于 1MB](https://github.com/paoloanzn/microcodex) ⭐️ 9.0/10

MicroCodex 是一个新的开源项目，用 C++23 重新实现了 OpenAI 的 Codex 编程代理，生成的二进制文件小于 1MB。它提供一次性提示、交互式终端界面、本地编程工具、持久会话和自动上下文压缩。 该项目表明，强大的 AI 编程代理可以以极其轻量的形式交付，使其更容易部署并集成到开发者的工作流程中。它可能会吸引那些希望用快速、自包含的替代品来替代更庞大、基于云的编程助手的开发者。 MicroCodex 使用 C++23 编写，具有一次性提示、交互式终端界面、本地编程工具、持久会话和自动上下文压缩等功能。该项目托管在 GitHub 上，目标是实现超轻量化，二进制大小小于 1MB。

rss · Show HN (self-made tools) · 8月2日 20:11

**背景**: AI 编程代理是一种超越简单代码补全的工具；它能够根据自然语言指令编写、运行、评估和修改代码。OpenAI 的 Codex 是一个知名的 AI 系统，可将语言提示转换为代码，而 MicroCodex 这一重实现旨在以紧凑的 C++包提供类似的代理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/paoloanzn/microcodex">paoloanzn/ microcodex : MicroCodex is an ultra-lightweight coding ...</a></li>
<li><a href="https://www.mindstudio.ai/blog/what-are-ai-coding-agents">What Is an AI Coding Agent? How They Work and When to Use Them | MindStudio</a></li>

</ul>
</details>

**标签**: `#coding agent`, `#C++`, `#AI agent`, `#GitHub`, `#open source`

---

<a id="item-3"></a>
## [Kota：开源工具，让 AI 代理 CLI 同处一室](https://www.kota.place/) ⭐️ 9.0/10

Kota 是一款新的开源工具，让开发者可以在一个协作空间中同时运行多个 AI 代理 CLI，并具备共享记忆、持久身份和独立的 git worktree。初始版本支持 Codex、Claude Code、Pi、OpenCode 和 Gemini（Antigravity CLI），Kimi Code 正在测试中。 Kota 解决了在不同 AI 聊天标签页之间复制粘贴的痛点，创建了一个让多个代理像团队一样工作的共享空间。这很重要，因为它在现有代理 CLI 之上提供了一个实用的编排层，有望提高 AI 辅助开发的工作效率。 每个代理都拥有持久且可查看编辑的身份，而非会话；记忆以文件形式存储并可直接编辑。Kota 还包含自动 worktree 同步与冲突解决交接、Telegram 机器人远程控制、共享画板和跨项目 BBS 等功能。

rss · Show HN (self-made tools) · 8月2日 18:59

**背景**: AI 代理 CLI（如 Claude Code 和 Gemini CLI）是基于终端的工具，利用大语言模型协助完成编写代码、运行命令和管理文件等编程任务。Git worktree 是 Git 的一项功能，允许同一个仓库拥有多个工作目录，从而无需暂存更改即可同时检出和使用不同分支。Kota 基于这些概念构建了一个多代理协作层。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grokipedia.com/page/AI-native_CLI">AI-native CLI</a></li>
<li><a href="https://git-scm.com/docs/git-worktree">Git - git-worktree Documentation</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#open source`, `#developer tools`, `#CLI`, `#workflow`

---

<a id="item-4"></a>
## [Mousecrack 用深度学习绕过光标检测验证码](https://github.com/puffinsoft/mousecrack) ⭐️ 9.0/10

Mousecrack 是 puffinsoft 发布的一个采用 MIT 许可证的开源项目，在 Hacker News 上被分享为一种用深度学习绕过验证码的方法。仓库描述显示，它将鼠标预测视为时间预测问题，针对的是代理光标检测，而非传统基于图像的验证码。 该项目意义在于展示了一种实用的深度学习技术，可绕过日益常见的基于行为的反机器人系统。它与从事自动化和抓取开发的开发者直接相关，同时也揭示了基于光标的验证码防护可能存在的弱点。 Mousecrack 以 MIT 许可证开源，托管在 GitHub 上的 puffinsoft/mousecrack。该项目将问题定义为时间预测，表明它建模并预测类似人类的鼠标轨迹，而非解决视觉谜题。

rss · Show HN (self-made tools) · 8月2日 18:11

**背景**: 验证码是一种安全措施，旨在区分人类和自动化机器人，通常要求用户读取扭曲文本或识别图像。近年来，许多网站采用了隐形或基于行为的验证码，通过分析鼠标移动和光标轨迹来检测自动化。鼠标追踪是一种已知的收集光标行为数据的技术，当用于防御时，可以作为机器人检测机制。Mousecrack 正是用深度学习来针对这种基于行为的验证码类型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/puffinsoft/mousecrack">GitHub - puffinsoft/ mousecrack : Bypass agent cursor detection with...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Mouse_tracking">Mouse tracking</a></li>

</ul>
</details>

**标签**: `#captcha`, `#deep-learning`, `#automation`, `#github`, `#AI-tool`

---

<a id="item-5"></a>
## [llama.cpp 为 DeepSeek V4 Flash 添加 MTP/DSpark 支持](https://www.reddit.com/r/LocalLLaMA/comments/1vdhgq9/llamacpp_just_added_mtp_dspark_support_for/) ⭐️ 9.0/10

llama.cpp 已为 DeepSeek V4 Flash 添加了多令牌预测（MTP）和 DeepSeek 的 DSpark 推测解码支持，从而加快本地推理速度。该集成使受支持的模型每次前向传播可生成多个令牌，而不再只是一个。 这很重要，因为 MTP/DSpark 可为本地 LLM 工作负载带来 30–60% 的解码吞吐量提升，而 DeepSeek 声称每用户推理速度可提高 57–85%。它把推测解码带入了 llama.cpp 这一最广泛使用的本地推理引擎，使 DeepSeek V4 Flash 在消费级硬件上响应更快。 MTP 通过训练额外的预测头，在一次前向传播中预测多个未来令牌；DSpark 则是 DeepSeek 的推测解码框架，可保持输出逐字节一致。基准测试显示，在 batch=1 且使用受支持模型时，解码性能可提升 30–60%；近期 llama.cpp 中出现的一个 MTP 回归问题已在 48 小时内修复。

reddit · r/LocalLLaMA · /u/rmhubbert · 8月2日 12:58

**背景**: 多令牌预测（MTP）是一种推理优化技术，模型在训练时被要求同时预测多个令牌，从而减少串行的前向传播次数。推测解码使用一个草稿模型提出候选令牌，再由目标模型进行验证，从而在保持输出质量的同时加速生成。llama.cpp 是一个广受欢迎的开源 C/C++ 库，可在多种硬件上本地运行 LLM；DeepSeek V4 Flash 则是专门为配合 DSpark 高效推测解码而设计的模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://specpicks.com/reviews/llama-cpp-mtp-regression-kv-cache-quant-2026">MTP in llama . cpp : The Regression, the Fix | SpecPicks</a></li>
<li><a href="https://deepseek.ai/blog/deepseek-dspark-speculative-decoding">DSpark Speculative Decoding: 57–85% Faster LLM Inference</a></li>
<li><a href="https://topclanker.com/blog/2026-05-14-llama-cpp-mtp-speed/">Llama . cpp 's Multi-Token Prediction: The Speed Boost Your Local AI...</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#DeepSeek`, `#local inference`, `#MTP`, `#DSpark`

---

<a id="item-6"></a>
## [开发者通过 NVMe 流式加载在 8GB 内存 CPU 上运行 Kimi K3](https://www.reddit.com/r/LocalLLaMA/comments/1vd874t/i_pushed_kimi_k3_onto_one_cpu_with_8_gb_of_ram/) ⭐️ 9.0/10

一位开发者用 C99 编写了一个推理引擎，通过按需从 NVMe 流式读取路由专家，在仅有 8GB 内存的单个 CPU 上运行 Moonshot AI 的 1.56TB Kimi K3 混合专家模型。该引擎大约每 token 生成需 33 秒，并且在不同内存预算下输出逐字节一致。 这一成果让先进的 2.8T 参数开源模型可在普通硬件上运行，证明通过激进的专家卸载，无需 GPU 也能服务超大规模 MoE 模型。它降低了缺乏高端加速器的开发者、研究人员和边缘部署场景的使用门槛。 该 1.56TB 检查点中 93% 是路由专家，每 token 只激活 896 个专家中的 16 个，因此专家直接从 NVMe 读取并以打包的 4-bit 形式直接乘算，无需反量化步骤。整个引擎仅六个 C 文件，依赖 libm 和 OpenMP，编译后二进制仅 176KB，需要 1.7TB 可用磁盘，并在下载完整权重前先用小型模型进行验证。

reddit · r/LocalLLaMA · /u/FareedKhan557 · 8月2日 04:26

**背景**: Kimi K3 是 Moonshot AI 发布的开源模型，拥有 2.8T 参数、1M token 上下文窗口和原生视觉能力，基于 Kimi Delta Attention 与 Attention Residuals 构建。混合专家（MoE）架构在每 token 只激活一小部分参数——K3 每 token 路由到 896 个专家中的 16 个——因此大部分权重可以放在片外。4-bit 量化将权重压缩以降低内存与存储占用，而 NVMe 能为被卸载的专家提供快速按需读取。该实现逐层流式加载稠密主干，并通过一个可调的内存“拨盘”控制驻留内存大小。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.kimi.com/blog/kimi-k3">Kimi K3 Tech Blog: Open Frontier Intelligence</a></li>
<li><a href="https://en.wikipedia.org/wiki/Mixture_of_experts">Mixture of experts - Wikipedia</a></li>
<li><a href="https://huggingface.co/blog/ResterChed/kimi-k3-model-overview-mxfp4-quantization-open-wei">Kimi K3 Model Overview: 2.8T Parameters, MXFP4 Quantization ...</a></li>

</ul>
</details>

**标签**: `#LLM`, `#inference`, `#MoE`, `#CPU`, `#optimization`

---

<a id="item-7"></a>
## [西蒙·威利森 2026 年 7 月通讯：新 AI 模型与 MCP](https://simonwillison.net/2026/Aug/2/july-newsletter/#atom-everything) ⭐️ 8.0/10

西蒙·威利森发布了 2026 年 7 月赞助者专属月度通讯，内容涵盖近期 AI 模型发布，包括 GPT-5.6 Sol/Terra/Luna、Claude Opus 5、Kimi K3 和 DeepSeek-V4-Flash-0731。通讯还提到他对 Model Context Protocol（MCP）重新燃起的兴趣，并包含个人项目与 AI 安全事件的笔记。 这份通讯以从业者为导向，精选汇总了当月最重要的 AI 发展动态，帮助开发者和研究人员及时掌握前沿。它凸显了开源权重前沿模型以及 MCP 标准在 AI 生态中日益重要的地位。 这份通讯面向 GitHub 赞助者以每月 10 美元的价格提供，且比免费公开版本提前一个月获取。内容还提到了 OpenAI 和 Anthropic 模型在测试中意外引发的网络攻击、关于 AI 发展的公开信、一场炉边谈话和一档播客。

rss · Simon Willison · 8月2日 04:12

**背景**: Model Context Protocol（MCP）是 Anthropic 于 2024 年 11 月推出的开放标准，旨在标准化 AI 系统与外部工具和数据源的连接方式。Kimi K3 是 Moonshot AI 推出的 2.8 万亿参数开源权重多模态模型，而 DeepSeek V4 Flash 则是拥有 2840 亿参数、1M 上下文窗口的混合专家（MoE）模型，并于近期结束预览。这些发布反映了 2026 年开源权重与商业 AI 模型开发的加速步伐。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://www.kimi.com/blog/kimi-k3">Kimi K 3 Tech Blog: Open Frontier Intelligence</a></li>
<li><a href="https://www.orcarouter.ai/blog/deepseek-v4-flash-official-release">DeepSeek V4 Flash: Official Release, Explained</a></li>

</ul>
</details>

**标签**: `#newsletter`, `#AI models`, `#MCP`, `#GPT-5.6`, `#Claude Opus 5`

---

<a id="item-8"></a>
## [Mu：Show HN 用于构建 AI 智能体的工具](https://github.com/micro/mu) ⭐️ 8.0/10

一位用户在 Hacker News 上发布了“Show HN：Mu – Tools for Agents”，并附上了 GitHub 仓库 micro/mu 的链接。该帖声称该项目提供用于构建 AI 智能体的工具，尽管该仓库目前在 GitHub 上的描述是“个人家庭服务器”。 如果帖子中的描述反映了该项目当前的方向，那么 Mu 可能成为开发者在构建 AI 智能体（一个快速发展的领域）时的新开源选择。帖子内容与仓库描述之间的不一致，也凸显了直接核实项目信息的重要性。 链接的仓库是 GitHub 上的 micro/mu，根据 micro 组织的页面，该仓库目前被描述为“个人家庭服务器”，拥有 97 个 Star。其他无关项目也使用了“Mu”这个名字，例如微软的 Project Mu（固件）和 higherkindness/mu-haskell（微服务框架）。

rss · Show HN (self-made tools) · 8月2日 22:06

**背景**: AI 智能体是能够在一定程度上自主执行任务或做出决策的软件系统，通常由大型语言模型驱动。目前已有许多开源框架帮助开发者创建这类智能体。“Mu”这一名称被多个独立的项目使用，而维护 go-micro 的 micro 组织同时也在维护 mu 仓库，该仓库目前自称是一个个人家庭服务器项目。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/micro">Micro · GitHub</a></li>
<li><a href="https://github.com/microsoft/mu">GitHub - microsoft/mu: Project Mu Documentation · GitHub</a></li>
<li><a href="https://github.com/higherkindness/mu-haskell">GitHub - higherkindness/mu-haskell: Mu (μ) is a purely functional framework for building micro services.</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#GitHub`, `#developer tools`, `#open source`, `#agent frameworks`

---

<a id="item-9"></a>
## [用 PyTorch 从头实现 Kimi K3 论文](https://github.com/TimRots/kimi3) ⭐️ 8.0/10

一位开发者发布了在 GitHub 上的仓库，用 PyTorch 从头实现了 Kimi K3 论文。该仓库 TimRots/kimi3 为研究模型架构提供了具体代码。 对于希望理解现代大语言模型内部原理的开发者与研究者来说，这是一个宝贵的动手资源。它通过清晰的 PyTorch 代码，让 KDA 和 AttnRes 等前沿模型的关键思想变得易于接触。 该实现针对 Kimi K3，即月之暗面(Moonshot AI)的 2.8 万亿参数混合专家模型，激活 896 个专家中的 16 个。代码属于教学性质，可能无法扩展到完整的 2.8 万亿参数量，但演示了模型新颖的注意力与残差机制。

rss · Show HN (self-made tools) · 8月2日 21:09

**背景**: Kimi K3 是月之暗面于 2026 年 7 月发布的开源权重旗舰大语言模型，基于 Kimi Delta Attention（KDA）和 Attention Residuals（AttnRes）构建。KDA 为扩展注意力提供高效基础，而 AttnRes 则跨深度选择性检索表示。arXiv 论文和官方博客描述了该架构，其使用 Stable LatentMoE 框架，相比 Kimi K2 实现了约 2.5 倍的扩展效率提升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.kimi.com/blog/kimi-k3">Kimi K 3 Tech Blog: Open Frontier Intelligence</a></li>
<li><a href="https://arxiv.org/abs/2607.24653">[2607.24653] Kimi K3: Open Frontier Intelligence</a></li>
<li><a href="https://www.interconnects.ai/p/kimi-k3-the-open-weights-escalation">Kimi K3: The open-weights escalation - by Nathan Lambert</a></li>

</ul>
</details>

**标签**: `#PyTorch`, `#Kimi`, `#Paper Implementation`, `#LLM`, `#Open Source`

---

<a id="item-10"></a>
## [基准测试表明不应量化 DeepSeek V4 Flash 的 KV Cache](https://www.reddit.com/r/LocalLLaMA/comments/1vduxth/you_really_should_not_quantize_kv_cache_for/) ⭐️ 8.0/10

Reddit 上的一项基准分析显示，将 DeepSeek V4 Flash 的 KV cache 从 BF16 量化到 Q8 会显著降低输出质量，与 Qwen 397B 形成鲜明对比。困惑度上升、KL 散度激增，同 Top-P 准确率降至 87.19%，而 Qwen 为 97.93%。 由于 KV cache 量化是减少内存占用、加速长上下文推理的常用技术，这一发现提醒从业者，并非所有模型都能同样容忍量化。对 DeepSeek V4 Flash 盲目应用量化可能会让输出质量明显下降，因此必须针对具体模型进行验证。 该基准在将 KV cache 从 BF16 切换为 Q8 时测量了困惑度、KL 散度和 token 概率变化。DeepSeek V4 Flash 的平均 KL 散度达 0.1459，99 分位Δp 达 42%，而 Qwen 397B 的平均 KLD 仅为 0.00355，同 Top-P 为 97.93%。

reddit · r/LocalLLaMA · /u/erazortt · 8月2日 22:01

**背景**: KV cache 是一种在 LLM 推理中缓存先前计算出的注意力键和值的机制，使每一步解码只需处理新的 token，从而大幅提升速度。量化则是降低数字精度（如从 BF16 的 16 位降到 Q8 的 8 位整数）来减少内存和计算开销，但会引入误差。困惑度用于衡量模型对测试数据的惊讶程度，KL 散度衡量两个概率分布的差异，同 Top-P 则比较模型预测的最高概率 token 是否保持不变。这些指标常用来量化量化操作的质量影响。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/not-lain/kv-caching">KV Caching Explained: Optimizing Transformer Inference Efficiency</a></li>
<li><a href="https://www.cloudflare.com/learning/ai/what-is-quantization/">What is quantization in machine learning ?</a></li>
<li><a href="https://en.wikipedia.org/wiki/Perplexity">Perplexity - Wikipedia</a></li>

</ul>
</details>

**标签**: `#KV cache`, `#quantization`, `#DeepSeek`, `#LLM inference`, `#benchmark`

---

<a id="item-11"></a>
## [Karpathy 点赞 sqliteai/waste：从 NVMe 流式运行 Kimi K3 推理](https://github.com/sqliteai/waste) ⭐️ 7.0/10

Andrej Karpathy 给 GitHub 仓库 sqliteai/waste 点星，引起人们关注其宣称可在笔记本上通过从 NVMe 流式读取权重来运行完整的 2.78 万亿参数 Kimi K3 模型。该项目是一个无依赖、可嵌入的 C 推理引擎，采用 Apache 2.0 许可。 来自 Karpathy 的高信号背书可能会加速流式推理技术的普及，这种技术让消费级硬件能够运行远大于系统内存的模型。它也指出了一个超越量化、在本地部署前沿规模 LLM 的实用路径。 WASTE 按需直接从 NVMe 存储将激活的权重流式读入内存，无需将全部 2.78T 参数载入 RAM。该引擎用无依赖的 C 语言编写，包含 23 个 C 文件和 17 个 Python 文件，当前仓库提交为 49c71e3。

github · karpathy · 8月2日 17:19

**背景**: 大语言模型通常以参数量来衡量；Kimi K3 拥有 2.78 万亿参数，远超单台工作站的存储容量。传统推理需要将整个模型载入 GPU 或系统内存，而流式推理则只从 NVMe 等高速存储中按需加载每一步计算所需的权重。Andrej Karpathy 是知名 AI 研究者、前 Tesla AI 总监，他的 GitHub 星标常被视为值得关注项目的信号。该项目隶属于 SQLite Cloud, Inc.，并通过了独立代码审计。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/sqliteai/waste">GitHub - sqliteai/waste: Run the full 2.78-trillion-parameter Kimi K3 model beyond available RAM by streaming activated weights directly from NVMe. A dependency-free, embeddable C inference engine. · GitHub</a></li>
<li><a href="https://marcobambini.substack.com/p/the-waste-inference-engine">The WASTE inference engine - Marco Bambini</a></li>

</ul>
</details>

**标签**: `#AI`, `#SQLite`, `#GitHub`, `#Karpathy`, `#Tool`

---

<a id="item-12"></a>
## [Authoryze 发布 AI 代理支付控制平台](https://authoryze.ai/) ⭐️ 7.0/10

Authoryze 发布了面向 AI 代理的支付控制平台，其宣传语为“你的代理永远不会看到你的真实卡片”。该 Show HN 提交目前仅有 3 个积分和 2 条评论，表明仍处于早期阶段。 随着 AI 代理开始进行真实世界的购买，安全的支付控制成为关键基础设施。Authoryze 通过强制实行消费限额、审批、商户规则和审计跟踪来解决这一问题，这对于可信的代理式商务至关重要。 该平台支持现代支付通道，并通过代币化或类似机制向代理隐藏真实卡片。主要功能包括消费限额、审批流程、商户控制以及每笔交易的完整审计跟踪。

rss · Show HN (self-made tools) · 8月2日 20:34

**背景**: AI 代理是能够代表用户执行浏览、预订或购买等任务的自主软件系统，这一趋势被称为代理式商务（agentic commerce）。为了让代理安全地花钱，需要专门的支付层提供可编程性、安全性和监督能力。业界讨论强调，代理支付必须是快速、可编程、钱包感知且由 API 驱动的。Authoryze 通过让用户掌控代理支付方式，正进入这一新兴领域。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://authoryze.ai/">Authoryze : Your agent never sees your real card</a></li>
<li><a href="https://www.linkedin.com/posts/m13-company_startups-have-the-opportunity-to-reimagine-activity-7458142351472123904-twQX">Reimagining Payment Rails for Agentic Purchasing | LinkedIn</a></li>
<li><a href="https://inferensys.com/guides/agentic-commerce-and-ai-buyer-optimization/setting-up-a-secure-payment-orchestration-layer-for-agents">How to Build a Secure Payment Orchestration Layer for AI Agents</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#payments`, `#tool`, `#Hacker News`, `#automation`

---

<a id="item-13"></a>
## [开发者开源 15 年‘第二大脑’，发布 660 篇笔记](https://www.ssp.sh/brain/) ⭐️ 7.0/10

一位开发者发布了自己 15 年个人知识库中约 660 篇精选笔记，整套流程基于 Obsidian、Quartz、Hugo 和语义搜索构建。整个发布管线已在 GitHub 上开源。 它为想把自己的私人笔记库低成本转化为公开数字花园的人提供了一个具体且可复现的参考。它也展示了长期记笔记如何沉淀为博客文章和书籍章节，而不仅是静态存档。 发布流程是标签驱动的：给笔记加上 '#publish' 标签后运行 'make deploy'，系统会使用 Quartz 和 Hugo 构建，并通过 rsync 同步到作者自己的服务器。这些笔记来自原本包含 8,360 篇（300 万词）的私人库；作者发现多年前分别写的 dbt、OLAP 和物化视图笔记其实是同一个模式，并据此写成了一章书稿。

rss · Show HN (self-made tools) · 8月2日 19:42

**背景**: ‘第二大脑’是一种个人知识管理系统，用于长期捕获和关联想法。Obsidian 是一款流行的基于 Markdown 的笔记应用，以纯文本文件存储笔记；Quartz 则是专为将这类笔记图谱发布为网站而设计的静态站点生成器。语义搜索利用向量嵌入按含义而非精确关键词检索结果，有助于在大型笔记库中导航。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://quartz.jzhao.xyz/">Welcome to Quartz 5</a></li>
<li><a href="https://en.wikipedia.org/wiki/Semantic_search">Semantic search</a></li>
<li><a href="https://github.com/jackyzha0/quartz">jackyzha0/ quartz : a fast, batteries-included static - site generator ...</a></li>

</ul>
</details>

**标签**: `#second brain`, `#Obsidian`, `#knowledge management`, `#open source`, `#semantic search`

---

<a id="item-14"></a>
## [DeepSeek-V4-Flash Dwarfstar 在 M2 Ultra Mac 上的速度测试](https://www.reddit.com/r/LocalLLaMA/comments/1vdld4v/deepseekv4flash0731_dwarfstar_on_mac/) ⭐️ 7.0/10

一位 Reddit 用户分享了在配备 192GB 内存的 M2 Ultra Mac 上运行 DeepSeek-V4-Flash（Dwarfstar）模型的解码性能：起始速度为每秒 28 个 token，在 45k 上下文深度时为每秒 23.5 个 token，在 192k 深度时为每秒 18 个 token，同时保持 8k token 的输出。 这为本地大语言模型爱好者提供了在 Apple Silicon 上运行具有 304B 参数的庞大混合专家模型的具体真实性能数据，帮助他们了解在高端 Mac 上使用 DwarfStar 推理引擎时的预期表现。 该模型是 DeepSeek-V4-Flash-0731 检查点，通过 q2-imatrix 配方进行量化，该配方会先将官方的 fp4 路由专家和 fp8 密集张量反量化到 f32，再重新量化。报告的速度是不同上下文深度下的解码速度（每秒 token 数），而非预填充吞吐量。

reddit · r/LocalLLaMA · /u/Badger-Purple · 8月2日 15:43

**背景**: DeepSeek-V4-Flash 是一个大型混合专家（MoE）语言模型，总参数为 304B，支持 1M 上下文；DwarfStar（ds4）是一个针对该模型在 Metal、CUDA 和 ROCm 上优化的原生推理引擎。在大语言模型推理中，预填充（prefill）阶段并行处理提示词，而解码（decode）阶段则逐个自回归地生成输出 token，因此解码速度直接决定用户感知的生成延迟。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/ox-ox/DeepSeek-V4-Flash-0731-GGUF">ox-ox/DeepSeek-V4-Flash-0731-GGUF · Hugging Face</a></li>
<li><a href="https://github.com/antirez/ds4">GitHub - antirez/ds4: DeepSeek 4 Flash and PRO local inference engine for Metal, CUDA and ROCm · GitHub</a></li>
<li><a href="https://redis.io/blog/prefill-vs-decode/">Prefill vs Decode: LLM Inference Phases Explained - Redis</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#deepseek`, `#apple-silicon`, `#performance`, `#mac`

---