---
layout: default
title: "Horizon Summary: 2026-09-17 (ZH)"
date: 2026-09-17
lang: zh
---

> 从 58 条内容中筛选出 6 条重要资讯。

---

1. [将 Qwen3.8-Flash-Next 的 KV cache 卸载到内存，3 张 3090 实现 100 万上下文](#item-1) ⭐️ 8.0/10
2. [Show HN：用于学习 Claude Code 的交互式思维导图](#item-2) ⭐️ 7.0/10
3. [OpenCode Mentor 配置让 AI 编程智能体扮演导师而非代写代码](#item-3) ⭐️ 7.0/10
4. [Vending Machine Lab：浏览器模拟让 AI 无人工干预经营 14 天](#item-4) ⭐️ 7.0/10
5. [Interakt：面向网站的开源自托管搜索与 AI 对话工具](#item-5) ⭐️ 7.0/10
6. [Qwen 3.8 27B 在单张 RTX 3090 上自主运行 63 小时挑战黎曼猜想](#item-6) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [将 Qwen3.8-Flash-Next 的 KV cache 卸载到内存，3 张 3090 实现 100 万上下文](https://www.reddit.com/r/LocalLLaMA/comments/1whx5xi/you_can_offload_most_of_qwen38flashnexts_kv_cache/) ⭐️ 8.0/10

r/LocalLLaMA 用户（u/sadnessdevil）称已让 vLLM 的补丁跑通，把 Qwen3.8-Flash-Next 的大部分 KV cache 卸载到系统内存，在不做 KV cache 量化的前提下，用 3 张 RTX 3090 跑到 100 万 token 上下文。实测短上下文解码约 80 tok/s，当 QSA 用满 2048 token 预算后降到约 60 tok/s 并随后保持平稳，248k token 预填充达 3,701 tok/s，4 路并发约 150 tok/s；补丁和模型已发布在作者的 HuggingFace 页面。 这说明对于采用稀疏注意力的混合架构，长上下文服务不再必然受显存容量和 GPU 内存带宽的限制，而这通常是本地推理的硬天花板。如果这一方法能推广到未来 Qwen 本地模型所基于的 qwen4exp 系列，那么只有中等规模多卡设备的自托管用户也能以较小的解码速度损失运行接近最大上下文长度。 这一技巧之所以成立，是因为该模型 48 层中只有 12 层带 KV cache：其余 36 层是门控 delta-net 线性注意力层，其循环状态大小固定；这 12 个注意力层使用 QSA，对池化/压缩后的 key 建索引（indexer_head_dim=128 除以 indexer_compress_ratio=4），并且只为至多 indexer_budget=2048 个被选中的位置读取主 KV 行，从而把每步 KV 读取量限制在约 48 MiB/token，而不是每层每 token 的 2048 B。需要注意的限制是：模型权重、一个 2 字节 slot 以及 64 B 的池化索引 key 必须留在 GPU 上，并且 QSA 的 indexer 状态与 KV cache 量化以及批处理 QSA 同时使用会出问题。

reddit · r/LocalLLaMA · /u/sadnessdevil · 9月16日 13:24

**背景**: KV cache 会保存已处理 token 的 key/value 张量，以免模型在每个解码步重复计算，但它随上下文线性增长，通常必须留在显存里。由于每个解码步只产生一个 token，却要读取该步所需的全部权重和注意力状态，解码是受带宽而非算力限制的；而 PCIe 4.0 x16 之类的主机链路（约 32 GiB/s）远不足以在每个步都搬运庞大的全注意力 KV cache。Qwen3.8-Flash-Next 沿用 Qwen3-Next/qwen4exp 的设计：以线性注意力层为主，混合少量使用 Qwen Sparse Attention（QSA）的全注意力层；QSA 用一个廉价的 indexer 选出有限数量的位置，这正是把 cache 卸载到系统内存可行的原因。vLLM 及 LMCache 等相关项目本就支持将 KV cache 放在 CPU 内存中，而这个补丁利用该架构每步读取量有界的特性，使这种做法变得足够快。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://vllm.ai/blog/2026-01-08-kv-offloading-connector">Inside vLLM ’s New KV Offloading Connector: Smarter... | vLLM Blog</a></li>
<li><a href="https://sebastianraschka.com/llm-architecture-gallery/qwen-sparse-attention/">Qwen Sparse Attention | Sebastian Raschka, PhD</a></li>
<li><a href="https://github.com/jundot/omlx/issues/3170">Support for qwen4_exp architecture (Qwen3.8-Flash-Next) · Issue #3170 · jundot/omlx</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#vllm`, `#kv-cache`, `#inference-optimization`, `#qwen`

---

<a id="item-2"></a>
## [Show HN：用于学习 Claude Code 的交互式思维导图](https://mikenikles.com/blog/learn-claude-code) ⭐️ 7.0/10

一篇 Show HN 投稿指向发布在 mikenikles.com 上的交互式思维导图，旨在帮助开发者学习和使用 Claude Code。该帖子目前几乎没有获得关注，抓取时仅有 1 分和 0 条评论。 Claude Code 已成为使用最广泛的智能体编码工具之一，因此能够缩短上手周期的结构化学习材料对采用它的开发者具有实际价值。社区整理的思维导图还能挖掘出官方文档往往埋没的隐性工作流与配置选项。 该投稿只提供了文章链接和 Hacker News 讨论链接，没有说明这份思维导图的深度、覆盖范围以及是否可免费访问。由于评论数为零，该资料的准确性与完整度也没有经过社区同行的验证。

rss · Show HN (self-made tools) · 9月16日 22:13

**背景**: Claude Code 是 Anthropic 推出的智能体编码工具，运行在终端中，能够读取并理解代码库、编辑文件、执行命令，并通过自然语言指令处理 git 工作流。它与单纯的自动补全式助手不同，因为它以自主循环的方式工作：规划多步任务、执行、观察结果，再决定下一步。思维导图是一种围绕中心主题分层组织概念的图示，而交互式版本允许用户展开、折叠和浏览各个分支，非常适合学习一个拥有大量命令、设置和工作流的工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://github.com/anthropics/claude-code">GitHub - anthropics/claude-code: Claude Code is an agentic coding tool that lives in your terminal, understands your codebase, and helps you code faster by executing routine tasks, explaining complex code, and handling git workflows - all through natural language commands. · GitHub</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#AI agents`, `#coding agents`, `#learning resource`, `#developer tools`

---

<a id="item-3"></a>
## [OpenCode Mentor 配置让 AI 编程智能体扮演导师而非代写代码](https://github.com/davejpeters/opencode-mentor) ⭐️ 7.0/10

一位开发者在 GitHub 上发布了 OpenCode Mentor，这是一份配置文件，把 OpenCode 这款 AI 编程智能体改造成"编程导师"，而不是只会盲目生成代码的工具。该项目明确以对抗"vibecoding"（氛围编程）为定位——即用自然语言提示大模型生成代码后不加审查就直接采用的做法。 随着 AI 编程智能体逐渐成为开发流程的标配，智能体的默认行为方式变得至关重要：一个会解释权衡、主动提出质疑的"导师型"智能体，有助于保住那些被纯代码生成所侵蚀的学习习惯与代码审查习惯。对于担心未经审查的 AI 代码带来可维护性问题和安全漏洞的团队而言，这是一个虽小但具体、可直接克隆使用的应对方案。 该产物是 OpenCode 的一份配置。OpenCode 采用 MIT 许可证、不绑定单一模型厂商，可在终端、IDE 或桌面端运行，因此使用者需先安装 OpenCode，然后克隆该仓库即可启用。它属于小众的社区配置而非正式工具发布，其在 Hacker News 上的提交仅获得 3 分和 1 条评论。

rss · Show HN (self-made tools) · 9月16日 21:15

**背景**: Vibecoding（氛围编程）指用自然语言描述任务、让大语言模型自动写出源代码，且常常不经仔细审查就接受结果的 AI 辅助开发方式；该词由 Andrej Karpathy 于 2025 年 2 月提出，后被《柯林斯英语词典》评为 2025 年度词汇。批评者指出，氛围编程产出的软件存在责任不清、可维护性差以及安全漏洞风险更高等问题。OpenCode 则是一款开源、不绑定特定模型厂商的 AI 编程智能体，支持终端、IDE 与桌面端，用户可以阅读源码、自行修改并自托管。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding</a></li>
<li><a href="https://opencode.ai/">OpenCode | The open source AI coding agent</a></li>
<li><a href="https://www.datacamp.com/blog/what-is-opencode">What Is OpenCode? The Open-Source AI Coding Agent Explained | DataCamp</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#OpenCode`, `#developer tools`, `#GitHub`

---

<a id="item-4"></a>
## [Vending Machine Lab：浏览器模拟让 AI 无人工干预经营 14 天](https://vending-machine-lab.pages.dev/) ⭐️ 7.0/10

一位开发者发布了 Vending Machine Lab，这是一个免费的、无需注册的浏览器模拟工具：用户可以选择数字产品、定制数字服务、自动售货机或可复用设备（如自助洗衣店）等生意，设定需求、成本、人员配置和规则，然后在不干预的情况下运行 14 个模拟日，并查看未完成订单、现金、退款以及需要老板处理的请求。作者明确表示，这是把 Andon Labs 的 Vending-Bench 思路泛化为任何人都能上手的交互式试验场，还提供一个可选的复制粘贴流程，让用户自己的 AI 助手基于“已知的虚构两周”来规划决策。 它把“长周期 AI 代理评测”这一话题从研究实验室带到了免费的浏览器小工具中，让开发者和普通读者都能轻松检验“AI 能自主经营生意”这类说法背后的假设。作者自己的结论——目前答案总体上是否定的——本身就是对“自主经营型 AI 代理”炒作的一种有益纠偏。 该网站本身不调用任何 AI 模型：AI 帮助给出的结果是预设的，可选的助手流程也不会在各天之间实时思考，而虚构的客户和故障由模型提供——因此它是一个探索经营假设的工具，而非需求或利润预测。作者在开发中使用了大量 AI 编码辅助、自动化检查、由 AI 扮演不同用户类型/角色的用户测试，以及人类朋友的反馈，并把源码发布在 GitHub 上。

rss · Show HN (self-made tools) · 9月16日 21:05

**背景**: Vending-Bench 由 Andon Labs 在 2025 年 2 月的一篇论文中提出，是一个模拟环境，用来测试基于 LLM 的代理能否在长周期内连贯地经营一门简单生意——运营一台自动售货机——并以最终银行账户余额作为评分标准；Vending-Bench 2 更把时间跨度延长到模拟的一整年。Anthropic 与 Andon Labs 合作的 Project Vend 则把同一问题带入现实：让 Claude Sonnet 3.7 运营 Anthropic 旧金山办公室里的一个小型自动商店。这些工作都凸显出：模型在短时、受限场景中表现良好，但随时间跨度拉长会变得越来越不可预测——而 Vending Machine Lab 正是让用户去戳这个失效模式的工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://andonlabs.com/evals/vending-bench">Vending-Bench: Testing long-term coherence in agents - Andon Labs</a></li>
<li><a href="https://arxiv.org/abs/2502.15840">[2502.15840] Vending-Bench: A Benchmark for Long-Term ... Vending-Bench 2 Leaderboard & Scores — September 2026 Vending-Bench 2: AI Models Put to the Test Running a Business ... Vending-Bench 2 — Benchgen Vending-Bench — Grokipedia</a></li>
<li><a href="https://www.anthropic.com/research/project-vend-1">Project Vend: Can Claude run a small shop? (And why does that matter?) \ Anthropic</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#simulation`, `#Vending-Bench`, `#business automation`, `#browser tool`

---

<a id="item-5"></a>
## [Interakt：面向网站的开源自托管搜索与 AI 对话工具](https://github.com/alphasolutionsrepo/interakt) ⭐️ 7.0/10

一个名为 Interakt 的项目以 "Show HN" 的形式发布在 Hacker News 上，被描述为面向网站的开源、自托管搜索与 AI 对话解决方案，帖子里直接给出了 GitHub 仓库链接（github.com/alphasolutionsrepo/interakt）。该发布帖本身只包含仓库链接，以及被抓取时显示的 2 分、0 条评论等元信息。 它为快速增长的"自托管替代商业站点搜索与 AI 聊天组件"这一类项目又添一员，这对因隐私、合规或成本原因无法把站点内容与用户提问交给第三方 SaaS 的团队尤为重要。如果该项目足够成熟、易于部署，就能降低个人开发者和小公司在自己文档之上加入 AI 问答的门槛，同时避免被供应商锁定。 该发布帖除标题外没有提供任何关于功能、技术栈、许可证、部署要求或安装说明的信息，而且它没有评论、仅得 2 分，因此社区并未对其质量、安全性或成熟度做出验证。感兴趣的人需要直接查看 GitHub 仓库，才能判断该项目实际支持哪些能力。

rss · Show HN (self-made tools) · 9月16日 21:01

**背景**: Hacker News 上的 "Show HN" 是长期存在的发布栏目，开发者借此向社区介绍自己的项目，通常会附上在线演示或源码仓库链接。"自托管"意味着软件运行在你自己的基础设施上——自有服务器、容器或 VPS——而不是作为托管云服务运行，这对处理私有数据的项目来说是常见偏好。"网站的搜索与 AI 对话"通常指一个组件或 API，它先索引网站自身的内容，再让访客以问答方式获取信息，由大语言模型组织回答；这类系统往往采用"先检索相关片段再生成答案"的检索增强思路，不过原帖并未说明 Interakt 的具体实现方式。这里的"开源"意味着代码公开在 GitHub 上，但帖子里并未说明具体采用哪种许可证。

**标签**: `#open-source`, `#self-hosted`, `#ai-chat`, `#website-search`, `#github`

---

<a id="item-6"></a>
## [Qwen 3.8 27B 在单张 RTX 3090 上自主运行 63 小时挑战黎曼猜想](https://www.reddit.com/r/LocalLLaMA/comments/1wi9fau/qwen_38_27b_running_for_63_hours_on_a_rtx_3090_to/) ⭐️ 7.0/10

一位用户让 4bit 量化的 Qwen 3.8 27B（100K 上下文窗口）在单张 RTX 3090 上自主运行了 63 小时，消耗超过 5000 万个 token 尝试求解黎曼猜想。模型最终没有解出问题，但作者称它从未捏造一个答案，并且多次自我纠错；他还把该智能体的内部记忆、代码与策略发布为 Hugging Face 数据集（gr0010/artificium-riemannhypothesis-experiment）。 这是长时程（long-horizon）智能体趋势中一个具体且可复现的案例：一个 27B 级别的开源模型在消费级硬件上维持了长达数天、可自我纠错的研究循环，而不是只做几次工具调用。作者还提出用多张 GPU 把多个智能体组成“蜂群（swarm）”，这暗示了开源权重模型配合编排框架，或许能为未解决的数学或编程问题做出贡献。 该实验在单张 24GB 显存的 RTX 3090 上运行 4bit 量化的 Qwen 3.8 27B，上下文窗口为 100K，历时 63 小时、消耗 5000 万以上 token；其产物（记忆、代码、策略）已在 Hugging Face 公开。需要注意：黎曼猜想本身仍未被解决；“从未捏造答案”和“自我纠错”均为作者的主观观察，并非基准测试结果，该智能体数学产出的质量也尚未被独立验证。

reddit · r/LocalLLaMA · /u/GuiltyBookkeeper4849 · 9月16日 20:50

**背景**: 黎曼猜想由波恩哈德·黎曼于 1859 年提出，涉及黎曼 ζ 函数非平凡零点的位置，是七个“千禧年大奖难题”之一，其 100 万美元奖金至今无人领取。Qwen 3.8 27B 是阿里巴巴 Qwen 系列中一个 270 亿参数的指令微调模型，面向通用文本、视觉与智能体（agentic）任务。所谓“4bit 量化”，是把模型权重从约 16 位压缩到约 4 位存储，从而大幅降低显存占用、但会带来一定精度损失，这正是 27B 模型能塞进单张消费级显卡的原因。“长时程智能体”指的是能在推理、工具调用、观察与修正等大量相互依赖的步骤中长期持续推进的系统，而不是只回答一个孤立提问。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/Qwen/Qwen3.8-27B">Qwen/Qwen3.8-27B · Hugging Face</a></li>
<li><a href="https://huggingface.co/blog/4bit-transformers-bitsandbytes">Making LLMs even more accessible with bitsandbytes, 4-bit ...</a></li>
<li><a href="https://long-horizon-agents.github.io/">Towards Long-Horizon Agents: A Survey</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#ai-agents`, `#long-horizon-agents`, `#experiment`, `#huggingface`

---