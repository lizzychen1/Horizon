---
layout: default
title: "Horizon Summary: 2026-07-15 (ZH)"
date: 2026-07-15
lang: zh
---

> 从 65 条内容中筛选出 15 条重要资讯。

---

1. [Inkling：开源权重多模态模型，支持音频](#item-1) ⭐️ 9.0/10
2. [适用于编码代理的开源内存系统，通过 SSH 同步](#item-2) ⭐️ 9.0/10
3. [多智能体编排的 Python SDK 发布](#item-3) ⭐️ 9.0/10
4. [Pullboard：一款用于管理 AI 代理集群的工作队列工具](#item-4) ⭐️ 9.0/10
5. [Gate.cat 阻止 AI 编码代理的危险 rm -rf 命令](#item-5) ⭐️ 9.0/10
6. [Grok 构建在 Apache 2.0 下开源](#item-6) ⭐️ 9.0/10
7. [德国 AI 联合体发布开源 30B 模型 Soofi S](#item-7) ⭐️ 9.0/10
8. [全球 14 台 Mac 上的强化学习后训练](#item-8) ⭐️ 9.0/10
9. [Telegram 推出无服务器机器人平台](#item-9) ⭐️ 9.0/10
10. [Gemma 4 26B CPU 推理：5t/s](#item-10) ⭐️ 8.0/10
11. [构建 Shippy AI agent 的经验教训](#item-11) ⭐️ 8.0/10
12. [模型路由复杂性深度剖析](#item-12) ⭐️ 8.0/10
13. [谷歌更新 Gemma 4，修复工具调用并引入 Flash Attention 4](#item-13) ⭐️ 8.0/10
14. [ComfyUI v0.28.0 添加字节跳动音频支持与安全修复](#item-14) ⭐️ 7.0/10
15. [misa77：比 LZ4 解压快 2 倍的编解码器](#item-15) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Inkling：开源权重多模态模型，支持音频](https://thinkingmachines.ai/news/introducing-inkling/) ⭐️ 9.0/10

Thinking Machines 发布了 Inkling，这是一个开源权重的多模态模型，支持文本、图像和音频，旨在本地部署和微调。 Inkling 是少数拥有音频功能的大型开源权重模型之一，使开发者无需依赖专有 API 即可构建自定义 AI 应用。 Inkling 支持长上下文窗口，可在 GitHub 和 Hugging Face 上获取以进行本地使用，并可通过 Tinker 平台进行微调，社区提供了 llama.cpp 和 Unsloth 的链接。

hackernews · vimarsh6739 · 7月15日 18:12 · [社区讨论](https://news.ycombinator.com/item?id=48924912)

**背景**: 开源权重模型发布训练好的神经网络权重，允许用户在本地运行和微调模型。与完全开源模型不同，开源权重模型通常不包含训练代码或数据。多模态模型在单一框架中处理多种数据类型，如文本、图像和音频。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ai21.com/glossary/open-weights-model/">What is an Open - Weights Model ? | AI21</a></li>
<li><a href="https://zilliz.com/learn/top-10-best-multimodal-ai-models-you-should-know">Top 10 Multimodal AI Models of 2024 - Zilliz Learn</a></li>

</ul>
</details>

**社区讨论**: 社区成员称赞 Inkling 的音频能力和高效推理，有人指出它可能是面向代理应用的良好基础。一位用户表示它可能成为美国的 'DeepSeek'，其他人则强调了现代模型设计的复杂性。

**标签**: `#open-weights`, `#multimodal`, `#AI model`, `#audio`, `#local deployment`

---

<a id="item-2"></a>
## [适用于编码代理的开源内存系统，通过 SSH 同步](https://github.com/vshulcz/deja-vu/) ⭐️ 9.0/10

Deja-vu 是一个新的开源内存层，适用于编码代理，支持搜索、MCP 召回、自动上下文、秘密编辑、统计，并通过 SSH 同步 Claude Code、Codex 和 OpenCode 的会话日志。 这解决了 AI 编码代理持久内存的关键挑战，使其能够在不同会话之间保持上下文，而无需依赖托管服务，这对于构建基于代理的复杂工作流的开发者来说非常有价值。 它是一个零依赖的单一二进制文件，在本地运行并通过 SSH 同步，具有语义搜索、自动上下文注入和生产环境下的秘密编辑功能。

hackernews · vshulcz · 7月15日 16:15 · [社区讨论](https://news.ycombinator.com/item?id=48923111)

**背景**: Claude Code 和 Codex 等编码代理通常只有有限的内置内存，常常只是便签。Deja-vu 通过提供一个可搜索的持久内存层来扩展这一功能，该层适用于不同的代理和会话，并使用 SSH 进行安全同步。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/vshulcz/deja-vu/">GitHub - vshulcz/deja-vu: Memory layer for coding agents ...</a></li>
<li><a href="https://github.com/rohitg00/agentmemory">GitHub - rohitg00/agentmemory: #1 Persistent memory for AI coding ...</a></li>

</ul>
</details>

**社区讨论**: 社区分享了对超过 140 个类似内存系统的审查、构建自定义解决方案的个人经验，以及对仅本地操作的兴趣。关于内存复杂性和代理内存可靠性存在争论。

**标签**: `#coding agents`, `#memory`, `#open-source`, `#AI tools`, `#GitHub`

---

<a id="item-3"></a>
## [多智能体编排的 Python SDK 发布](https://github.com/h5i-dev/h5i-python) ⭐️ 9.0/10

h5i-python SDK 已发布，允许开发者使用普通 Python 程序定义和执行跨 Claude Code、Codex 和其他 AI 运行时的多智能体编码工作流。 该 SDK 为编排多个 AI 编码智能体提供了可编程、可审计的层，满足了软件开发中对可重现和可管理的多智能体系统日益增长的需求。 该 SDK 基于 h5i orchestra 引擎构建，使用基于 Git 事件日志的嵌入式领域特定语言（eDSL），确保每次更改都被记录并可审计；它内置支持集成、管道和竞技场等模式。

rss · Show HN (self-made tools) · 7月15日 22:25

**背景**: h5i（发音为 high-five）是一个为 AI 编码智能体设计的可审计工作区，为每个智能体提供沙盒化的 Git 工作树，并记录提示、命令、日志、策略和审查。多智能体编排协调多个 AI 智能体协作完成复杂任务，h5i-orchestra 提供了可编程的 eDSL 来定义此类工作流，无需依赖图引擎或 actor 系统。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/h5i-dev/h5i">GitHub - h5i-dev/h5i: Auditable workspaces for AI coding ...</a></li>
<li><a href="https://h5i.dev/blog/programmable-agent-orchestration-edsl/">Programmable Agent Orchestration: the h5i-orchestra eDSL</a></li>
<li><a href="https://h5i.dev/blog/orchestration-patterns-beyond-ensemble/">Orchestration Patterns Beyond Ensemble: arena, pipeline ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#multi-agent orchestration`, `#Python SDK`, `#developer tools`, `#GitHub`

---

<a id="item-4"></a>
## [Pullboard：一款用于管理 AI 代理集群的工作队列工具](https://pullboard.dev/) ⭐️ 9.0/10

Pullboard 是一款新发布的工作队列工具，专门用于协调多个 AI 代理的协作，最初是为量化交易团队开发的。它让代理能够共享上下文、追踪任务依赖关系，并在无需手动重复解释的情况下接取工作。 随着多代理系统日益普及，如何在复杂项目中保持多个代理的协调一致成为关键挑战。Pullboard 通过提供一个共享的工作队列来解决这一问题，使代理保持同步，减少在量化金融等高要求环境中的重复劳动和错误。 Pullboard 支持通过一个 curl 命令匿名访问，可作为远程 MCP 服务器集成，且仅用三天即达到可用状态。它经受了超过 40 万行代码库的实战考验，用于美国期权交易。

rss · Show HN (self-made tools) · 7月15日 21:51

**背景**: AI 代理通常需要协作完成复杂任务，但缺乏协调会导致工作重复或上下文丢失。工作队列模式通过分配任务、保留执行历史和启用重试来提供帮助。Pullboard 专门为代理集群实现了这一模式，让代理能够看到之前的尝试和依赖关系。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.logrocket.com/ai-agent-task-queues/">Why your AI agent needs a task queue (and how to build one)</a></li>
<li><a href="https://arxiv.org/html/2601.13671v1">The Orchestration of Multi-Agent Systems: Architectures ...</a></li>
<li><a href="https://gerred.github.io/building-an-agentic-system/second-edition/part-iv-advanced-patterns/chapter-10-multi-agent-orchestration.html">Multi-Agent Orchestration - The Agentic Systems Series</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent orchestration`, `#work queue`, `#coding agents`, `#quant trading`

---

<a id="item-5"></a>
## [Gate.cat 阻止 AI 编码代理的危险 rm -rf 命令](https://gate.cat/) ⭐️ 9.0/10

Gate.cat 是一个新工具，它能拦截并阻止 AI 编码代理执行像 rm -rf 这样的危险 shell 命令，防止意外数据丢失。 随着 AI 编码代理变得越来越自主，意外执行破坏性命令构成了严重风险。Gate.cat 提供了一个简单的安全层，让开发者在使用自主编码工具时更放心。 该工具可能通过包装或监控 shell 环境，在允许任何命令执行之前扫描危险模式。公告中未提供关于支持哪些 shell 或集成方法的具体细节。

rss · Show HN (self-made tools) · 7月15日 20:13

**背景**: AI 编码代理是能自主编写、审查和编辑代码的 AI 系统，通常与终端交互执行命令。rm -rf 命令递归删除文件且无确认，如果代理误将其应用于错误目录，可能导致灾难性数据丢失。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grokipedia.com/page/Coding_agent">Coding agent</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#tool`, `#safety`, `#coding`

---

<a id="item-6"></a>
## [Grok 构建在 Apache 2.0 下开源](https://www.reddit.com/r/LocalLLaMA/comments/1uxi5mf/grok_build_open_sourced_under_apache_20_license/) ⭐️ 9.0/10

xAI 已将 Grok 构建以宽松的 Apache 2.0 许可证发布，使其代码可供自由使用、修改和分发。 此次开源发布允许开发者独立运行和定制 Grok，加速实时 AI 聊天机器人的创新，并促进社区贡献。 此次发布包括 Grok 模型的构建脚本和基础设施，使其他人能够复制或扩展 xAI 的工作。Apache 2.0 许可证允许在适当署名的情况下进行商业使用。

reddit · r/LocalLLaMA · /u/FreemanDave · 7月15日 20:59

**背景**: Grok 是 xAI 开发的生成式 AI 聊天机器人，由埃隆·马斯克于 2023 年 11 月推出。它因能够实时访问 X（原 Twitter）数据而与众不同。Apache 2.0 许可证是一种宽松的开源许可证，允许用户自由使用、修改和分发代码，甚至用于商业目的，只需包含原始版权声明。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Grok_(chatbot)">Grok (chatbot) - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Apache_License">Apache License - Wikipedia</a></li>
<li><a href="https://www.apache.org/licenses/LICENSE-2.0.html">Apache License, Version 2.0 | Apache Software Foundation</a></li>

</ul>
</details>

**标签**: `#open source`, `#AI model`, `#Grok`, `#Apache 2.0`, `#LLM`

---

<a id="item-7"></a>
## [德国 AI 联合体发布开源 30B 模型 Soofi S](https://www.reddit.com/r/LocalLLaMA/comments/1uxao7y/german_ai_consortium_releases_soofi_s_an_open_30b/) ⭐️ 9.0/10

德国 AI 联合体 Soofi 发布了 Soofi S，这是一个开源 300 亿参数的语言模型，在英语和德语基准测试中均取得了最高分。 此次发布增强了欧洲 AI 主权，提供了一个在多语言基准测试中表现优异的开源模型，使开发者能够微调或用于推理，无需依赖专有 API。 该模型是一个 300 亿参数的基础模型，同时提供了指令版本。一些社区成员指出它可能是 Qwen 的微调版本，但联合体声称其在基准测试中领先。

reddit · r/LocalLLaMA · /u/yogthos · 7月15日 16:21

**背景**: 大型语言模型通常由大型科技公司开发且闭源。开源模型允许更广泛的访问和定制。Soofi S 是欧洲创建自主 AI 能力努力的一部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://wiot-group.com/think/en/news/soofi-s-european-ai-foundation-model-for-industry-unveiled/">European AI Foundation Model Soofi S for Industry Unveiled</a></li>
<li><a href="https://digg.com/tech/y7ac3158">German consortium releases Soofi S 30B open-source AI model · Digg</a></li>

</ul>
</details>

**社区讨论**: 在 Reddit 讨论中，许多用户称赞 Soofi S 是欧洲 AI 主权和开源进步的胜利，而其他人则认为它只是 Qwen 的微调版本，并非前沿规模。

**标签**: `#open source model`, `#LLM`, `#benchmarks`, `#German AI`, `#30B`

---

<a id="item-8"></a>
## [全球 14 台 Mac 上的强化学习后训练](https://www.reddit.com/r/LocalLLaMA/comments/1uxb3zn/rl_posttraining_on_14_macs_across_4_countries/) ⭐️ 9.0/10

Pluralis Research 的研究人员首次使用横跨 4 个国家的 14 台消费级 Mac 生成 rollout，完成了强化学习（RL）后训练，由单个 B200 GPU 负责梯度更新。他们开源了代码库 Stoa，并采用 PULSE 和 DPPO 风格的概率门控技术来控制量化 rollout 模型与全精度训练器之间的 off-policy 差距。 这表明 AI 智能体的分布式 RL 训练可以在普通的消费级硬件上通过公共互联网进行，大大降低了进入门槛。由于 rollout 生成约占智能体 RL 计算量的 80%，在闲置的消费级 Mac 上运行可以推动 RL 训练的民主化，并保持模型开发的开放性。 所有 Mac 使用 Apple 的 MLX 框架进行 int8 推理，而 B200 训练器使用 bf16 精度。PULSE 仅发送版本间变化的 int8 值（约 0.5%），将权重更新压缩至约 82 MB；DPPO 门控则丢弃概率漂移过大的约 0.3%的 token。在 PaperSearchQA 基准测试中，cover pass@1 从 29%提升至 63%。

reddit · r/LocalLLaMA · /u/erfan_mhi · 7月15日 16:36

**背景**: 强化学习（RL）后训练通过奖励信号微调预训练模型，通常需要模型与环境交互生成 rollout。Apple 的 MLX 是一个针对 Apple 芯片优化的数组框架，支持 Mac 上的高效推理和训练。Off-policy 差距是指生成 rollout 的模型与正在训练的模型在权重或量化方式上存在差异，从而降低性能。权重增量压缩和概率门控等技术有助于弥合这一差距。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ml-explore/mlx">GitHub - ml-explore/mlx: MLX: An array framework for Apple ... Exploring LLMs with MLX and the Neural Accelerators in the M5 ... MLX MLX — MLX 0.31.2 documentation - GitHub Pages mlx · PyPI GitHub - frankgmail/apple-mlx: MLX: An array framework for ...</a></li>
<li><a href="https://opensource.apple.com/projects/mlx/">Apple Open Source</a></li>

</ul>
</details>

**标签**: `#RL`, `#distributed training`, `#open source`, `#Mac`, `#post-training`

---

<a id="item-9"></a>
## [Telegram 推出无服务器机器人平台](https://core.telegram.org/bots/serverless) ⭐️ 9.0/10

Telegram 正式推出无服务器平台，开发者无需自建服务器即可将机器人和 Mini App 的后端代码直接部署在 Telegram 的基础设施上，只需通过一条命令 `npx tgcloud push` 即可完成部署，使用标准 JavaScript 模块。 这极大地降低了 Telegram 机器人开发者的复杂性和成本，消除了服务器管理和扩容的需求，有望通过降低准入门槛加速 Telegram 机器人生态系统的发展。 代码运行在紧邻 Bot API 的隔离 V8 沙箱中，并附带内置的 SQLite 数据库。该平台目前仅支持 JavaScript，未来有望支持 TypeScript。

telegram · zaihuapd · 7月15日 16:00

**背景**: 无服务器计算允许开发者无需部署或管理服务器即可运行代码，自动根据需求扩展。Telegram 的新平台类似于 AWS Lambda，但与其 Bot API 紧密集成。V8 沙箱是一种安全机制，用于隔离 JavaScript 执行环境以保护宿主系统。这一举措顺应了云服务商为 Telegram 机器人提供无服务器模板的趋势。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://juejin.cn/post/7433218776982126618">【V8引擎blog翻译-192】V8 Sandbox在最初的设计文档和数百个CL发布近...</a></li>
<li><a href="https://whu-telegram.com/blogs/325-telegram/">Telegram 机器人指令自动化配置与部署全流程指南 | Telegram 中文官网</a></li>

</ul>
</details>

**标签**: `#telegram`, `#serverless`, `#bots`, `#developer-tools`, `#javascript`

---

<a id="item-10"></a>
## [Gemma 4 26B CPU 推理：5t/s](https://www.neomindlabs.com/2026/06/08/running-gemma-4-26b-at-5-tokens-sec-on-a-13-year-old-xeon-with-no-gpu/) ⭐️ 8.0/10

NeoMind Labs 的一篇博文展示了在没有 GPU 的情况下，在 13 年前的至强 CPU 上以每秒 5 个 token 的速度运行 Google 的 Gemma 4 26B 混合专家模型。 这表明大型 MoE 模型可以在老旧、低成本的硬件上运行，使本地推理更易获取，并减少对昂贵 GPU 的依赖。这也引发了关于本地推理与云端推理成本效益的讨论。 Gemma 4 26B 是一种 MoE 变体，总参数量为 260 亿，但每个 token 仅激活 40 亿参数，从而减少了计算量。每秒 5 个 token 的速度是通过量化（很可能是 8 位或 4 位）和 CPU 优化推理框架（如 llama.cpp）实现的。

hackernews · neomindryan · 7月15日 15:34 · [社区讨论](https://news.ycombinator.com/item?id=48922434)

**背景**: Gemma 4 是 Google 最新开源的语言模型系列，提供密集和混合专家（MoE）架构。像 26B A4B 这样的 MoE 模型每个 token 仅激活部分参数，从而提高了效率。CPU 推理依赖量化（降低权重的数值精度）来将模型放入内存并加速计算，但与 GPU 相比吞吐量仍然较低。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/google/gemma-4-26B-A4B">google/gemma-4-26B-A4B · Hugging Face</a></li>
<li><a href="https://ai.google.dev/gemma/docs/core">Gemma 4 model overview | Google AI for Developers</a></li>
<li><a href="https://www.techplained.com/run-llms-without-gpu">Run LLMs Without GPU: CPU Benchmarks... | TechPlained</a></li>

</ul>
</details>

**社区讨论**: 评论者意见不一：有人庆祝其可行性（例如 dwa3592 预测到 2027 年消费级硬件可运行 >200B MoE 模型），而另一些人指出本地推理的电费可能比使用云 API 更贵（hagen8、Aurornis）。hparadiz 分享了自己的基准测试，throwaway2027 报告在类似硬件上达到 8-12 t/s，表明结果存在差异。总体而言，讨论凸显了成本、速度和硬件需求之间的权衡。

**标签**: `#local LLM`, `#inference`, `#Gemma 4`, `#CPU inference`, `#cost analysis`

---

<a id="item-11"></a>
## [构建 Shippy AI agent 的经验教训](https://huggingface.co/blog/allenai/shippy-tech-blog) ⭐️ 8.0/10

Ai2 的 Skylight 项目发布了一篇博文，分享了开发 Shippy（一个用于海事分析的 AI agent）的关键经验，表明可靠的 agent 更多地取决于确定性的工具和护栏，而不是模型本身。 这些经验为构建生产级 AI agent 的开发者提供了实用的、经过实战检验的见解，将焦点从模型选择转移到系统设计、工具和评估上。 该博文强调，确定性的工具、明确的护栏、隔离的基础设施以及基于真实工作流和实时数据的评估对于 agent 的可靠性至关重要。

rss · Hugging Face Blog · 7月15日 17:29

**背景**: Shippy 是一个基于 Ai2 的 Skylight 平台构建的免费 AI agent，可以回答关于实时船舶数据的自然语言问题。Skylight 项目是一个海洋监测平台，供海事分析师使用。构建此类 agent 需要将大型语言模型（LLMs）与工具和安全措施结合起来。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://allenai.org/blog/shippy-deep-dive">What building Shippy taught us about building agents | Ai2</a></li>
<li><a href="https://www.geekwire.com/2026/ai2s-skylight-project-launches-shippy-an-ai-agent-that-dives-into-ocean-data/">Ai2’s Skylight project launches ‘Shippy,’ an AI agent that ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent development`, `#LLM`, `#best practices`

---

<a id="item-12"></a>
## [模型路由复杂性深度剖析](https://huggingface.co/blog/ibm-research/model-routing-is-simple-until-it-isnt) ⭐️ 8.0/10

IBM Research 在 Hugging Face 上发布了一篇博客文章，揭示了 AI 应用中模型路由隐藏的复杂性，挑战了其简单任务的观念。 随着多模型和基于代理的 AI 系统的发展，理解路由细微差别对于开发者有效平衡成本、延迟和质量至关重要。 文章强调了成本与延迟、质量与速度等实际权衡，并指出由于模型强弱不同和资源限制，动态模型选择充满困难。

rss · Hugging Face Blog · 7月15日 17:27

**背景**: 模型路由是指动态选择哪个语言模型（LLM）来处理给定请求，以优化成本、延迟或质量的过程。虽然看似直接，但实际部署引入了异质模型能力、波动工作负载和冲突用户期望等挑战。行业分析师预测，到 2028 年，大多数顶级 AI 企业将采用复杂的路由架构。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://medium.com/google-cloud/a-developers-guide-to-model-routing-1f21ecc34d60">A Developer’s Guide to Model Routing - Medium</a></li>
<li><a href="https://inworld.ai/resources/what-is-an-ai-router">What Is an AI Router? LLM Model Routing Explained (2026)</a></li>
<li><a href="https://www.idc.com/resource-center/blog/the-future-of-ai-is-model-routing/">The future of AI is model routing - IDC</a></li>

</ul>
</details>

**标签**: `#model routing`, `#AI agents`, `#LLM`, `#practical techniques`, `#Hugging Face`

---

<a id="item-13"></a>
## [谷歌更新 Gemma 4，修复工具调用并引入 Flash Attention 4](https://www.reddit.com/r/LocalLLaMA/comments/1uxfu4k/google_is_updating_gemma_4s_chat_templates/) ⭐️ 8.0/10

谷歌更新了 Gemma 4 的聊天模板，对工具调用进行了重大修复以减轻模型“懒惰”问题，并在 Hopper GPU 上启用了 Flash Attention 4 以加速推理。此外，还发布了一个交互式指南，帮助用户使用和改进 Gemma 4 的视觉能力。 这些改进直接提升了 Gemma 4 在智能体 AI 应用中的可靠性和性能，使其对构建工具调用 LLM 的开发者更加实用。视觉指南也降低了集成多模态能力的门槛。 此次更新包括一个 'preserve_thinking' 参数，并通过 Flash Attention 4 优化了注意力机制，利用 NVIDIA Hopper GPU 架构实现更高效、更快速的自注意力计算。Hugging Face 上的交互式视觉 token 预算指南帮助用户调整视觉性能。

reddit · r/LocalLLaMA · /u/Iwaku_Real · 7月15日 19:26

**背景**: Flash Attention 是一种加速 Transformer 中自注意力机制的技术，通过减少内存访问来使训练和推理更快、更节省内存。Hopper GPU 架构（用于 NVIDIA H100/H200 GPU）为大型语言模型提供了所需计算能力。工具调用允许 LLM 与外部函数交互，从而使它们能够执行现实任务，但许多模型存在“懒惰”问题，即它们在适当情况下拒绝调用工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/FlashAttention">FlashAttention</a></li>
<li><a href="https://en.wikipedia.org/wiki/Hopper_(microarchitecture)">Hopper (microarchitecture) - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Gemma 4`, `#tool calling`, `#model update`, `#LLM`, `#vision`

---

<a id="item-14"></a>
## [ComfyUI v0.28.0 添加字节跳动音频支持与安全修复](https://github.com/Comfy-Org/ComfyUI/releases/tag/v0.28.0) ⭐️ 7.0/10

ComfyUI v0.28.0 集成了字节跳动的 Seed Audio 1.0 用于 AI 音频生成，并修复了四个安全漏洞。 此次更新扩展了 ComfyUI 的多模态能力，使用户能够在图像和视频之外生成全场景音频，同时提升了平台安全性。 字节跳动合作伙伴节点支持 Seed Audio 1.0 和 Seedream 5 Pro 模型；安全修复解决了编号为 GHSA-779p-m5rp-r4h4 的漏洞。

github · github-actions[bot] · 7月15日 15:37

**背景**: ComfyUI 是一个流行的基于节点的 AI 图像生成界面，常与 Stable Diffusion 等模型一起使用。字节跳动的 Seed Audio 1.0 是一个多模态音频模型，能够从文本和参考音频一次性生成对话、音乐和音效。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://seeddance.ai/seed-audio-1-0">Seed Audio 1.0 —ByteDance Full-Scene AI Audio Generation ...</a></li>
<li><a href="https://fal.ai/learn/tools/how-to-use-seed-audio">How to Use Seed Audio 1.0: Prompts & Workflows | fal</a></li>
<li><a href="https://github.com/QwenLM/Qwen3-VL">GitHub - QwenLM/Qwen3-VL: Qwen3-VL is the multimodal large language model series developed by Qwen team, Alibaba Cloud. · GitHub</a></li>

</ul>
</details>

**标签**: `#ComfyUI`, `#release`, `#AI tool`, `#image generation`, `#audio generation`

---

<a id="item-15"></a>
## [misa77：比 LZ4 解压快 2 倍的编解码器](https://github.com/welcome-to-the-sunny-side/misa77) ⭐️ 7.0/10

Misa77 是一种新的无损压缩编解码器，在 Silesia 语料库上实现了比 LZ4 快 2 倍的解压速度，同时提供相当或更好的压缩比。该项目以 v0.x.y 版本在 GitHub 上开源发布。 该编解码器针对一次写入、多次读取的场景，这对数据分发、游戏资产和大规模存储至关重要。其性能提升可以减少数据密集型应用中的 I/O 瓶颈。 解码器假设输入有效，对格式错误的流可能产生未定义行为；该项目仍处于实验阶段，未经加固。压缩速度慢于 LZ4，但通过减少分支和利用乱序执行优化了解压吞吐量。

hackernews · nonadhocproblem · 7月15日 15:58 · [社区讨论](https://news.ycombinator.com/item?id=48922838)

**背景**: LZ4 等无损压缩编解码器在压缩速度和比率之间权衡以换取解压速度。Silesia 语料库是衡量无损压缩的标准基准。Misa77 采用基于 LZ 的格式，通过精简布局最大化 memcpy 操作，从而实现高速解压。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/welcome-to-the-sunny-side/misa77">GitHub - welcome-to-the-sunny-side/misa77: Ridiculously fast decompression at good ratios. misa77 is 1.5-3x faster than LZ4 for decompression on x86 and ARM (with better ratios!). · GitHub</a></li>
<li><a href="https://en.wikipedia.org/wiki/Silesia_corpus">Silesia corpus - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者指出了较慢压缩速度换取更快解压的权衡，有用户询问背后的设计思路。另有人强调该项目仍处于实验阶段且未经加固。建议添加代码集成示例以方便开发者使用。

**标签**: `#compression`, `#codec`, `#open-source`, `#performance`

---