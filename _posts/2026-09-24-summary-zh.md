---
layout: default
title: "Horizon Summary: 2026-09-24 (ZH)"
date: 2026-09-24
lang: zh
---

> 从 62 条内容中筛选出 8 条重要资讯。

---

1. [AgentRun：把可重复的智能体工作变成可检查工作流的开源 DSL](#item-1) ⭐️ 9.0/10
2. [Simon Willison 推出 Gemini 3.8 TTS 自带密钥试玩页面](#item-2) ⭐️ 8.0/10
3. [谷歌发布 Gemini 3.8 文本转语音，支持 30 秒样本声音克隆](#item-3) ⭐️ 7.0/10
4. [PromptSpend 推出每日更新的 LLM API 价格对比网站](#item-4) ⭐️ 7.0/10
5. [Hugging Face 博客：用 NVIDIA Warp 与 MjWarp 加速机器人仿真](#item-5) ⭐️ 7.0/10
6. [MiMo-V3 将采用以 HySparse2 为核心的新架构](#item-6) ⭐️ 7.0/10
7. [匿名模型 Space Bunny Alpha 在 OpenRouter 免费上线](#item-7) ⭐️ 7.0/10
8. [OpenAI 为 ChatGPT 语音接入插件，并升级到 GPT-6 驱动](#item-8) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [AgentRun：把可重复的智能体工作变成可检查工作流的开源 DSL](https://github.com/Parcha-ai/agentrun) ⭐️ 9.0/10

Grep AI（原 Parcha AI）团队开源了 AgentRun，这是一种 DSL，能把智能体工作中可重复的部分转换成可检查的混合工作流，其中可以混合工具调用、普通代码、由 Jev 驱动的 System One 决策，以及完整的智能体。GitHub 仓库（Parcha-ai/agentrun）提供了示例流程和一个无需任何 API key 即可运行的脚本化演示，该 DSL 还可以作为 Pi 扩展来构建、检查和运行工作流。 许多智能体流水线在本可以确定化的步骤上仍然付出完整 LLM 智能体循环的成本，因此把这类步骤声明式地转成工作流，可以降低开销与延迟，同时让行为可审计。它还让开发者能够单独评估路由和证据筛选逻辑，并在不重建整条流水线的前提下替换某一个智能体，契合当前向“结构化 + 智能体”混合编排演进的趋势。 该 harness 会利用智能体留下的执行轨迹和复盘笔记，判断一项工作中的哪些部分可以转成工作流，而 Jev 专门用于路由、证据筛选这类决策型步骤。Jev 并不是生成文本的 LLM：它是 TypeSafe AI 的专有 System One 模型，返回的是带概率估计和置信度分数的类型化数值，意图是直接由软件消费，而不是供人阅读。

rss · Show HN (self-made tools) · 9月23日 19:42

**背景**: 在智能体工程中，“agent”是一个让 LLM 反复决定下一步调用什么工具或采取什么行动的循环，灵活但昂贵且难以测试；而“workflow”则把步骤顺序硬编码下来。AgentRun 是一门领域特定语言，让开发者能够表达这些固定步骤——例如一个研究流程可以把问题拆成子问题、并行派出智能体调研、对证据进行筛选，再由另一个智能体撰写报告。文中反复提到的 Jev 是旧金山创业公司 TypeSafe AI 的 System One 模型，名字取自卡尼曼所说的快速直觉式思维，其输出是选择、分数或 yes/no 概率而非聊天文本；该仓库所属的 Parcha AI 已经停掉原有的合规产品线，转而专注用于自动化研究密集型知识工作的 Grep AI。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.parcha.ai/">Parcha is now Grep AI</a></li>
<li><a href="https://en.wikipedia.org/wiki/Jev_(AI_model)">Jev (AI model)</a></li>
<li><a href="https://jevmodel.org/">Jev AI Model (TypeSafe) — Typed System One Decisions</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent frameworks`, `#DSL`, `#open source`, `#workflow automation`

---

<a id="item-2"></a>
## [Simon Willison 推出 Gemini 3.8 TTS 自带密钥试玩页面](https://simonwillison.net/2026/Sep/23/gemini-tts-playground/) ⭐️ 8.0/10

谷歌发布了两个新的文本转语音模型 gemini-3.8-flash-tts 和 gemini-3.8-flash-lite-tts，Simon Willison 当天就用 “vibe coding” 方式做出了一个开放的自带密钥（BYOK）网页试玩工具，地址为 tools.simonwillison.net/gemini-tts-playground。该工具支持单语音或多角色对话编排、在约 2,089 个语音的目录中搜索，并能查看原始的请求与响应 JSON。 它让开发者无需安装任何东西就能评估谷歌的新 TTS 模型及其 2,000 多个语音库，从而在投入集成工作前先做判断；而多说话人脚本编排功能则指向更廉价的自动化对话、旁白与本地化流水线。由于该工具依赖底层 Gemini API 的开放 CORS 策略，且用户密钥只保存在页面内存中，它也展示了轻量级纯前端封装如何在模型发布当天就上线、且无需后端。 新模型提供 2,000 多个语音，并支持仅凭 30 秒的音频样本（须为你本人或你拥有使用权的嗓音）创建自定义语音。在 Willison 的演示中，用 gemini-3.8-flash-tts 生成 1 分 18 秒的多说话人音频耗时约 20 秒、花费 2.74 美分；他同时说明 API 密钥不会被写入浏览器存储，而是直接发送给谷歌。

rss · Simon Willison · 9月23日 17:12

**背景**: 文本转语音（TTS）模型把书面文字转换为语音音频，而像谷歌 Gemini 系列这样的近期多模态模型可以通过 HTTP API 直接在浏览器中调用。CORS（跨源资源共享）是一种浏览器机制，通常禁止网页调用其他域名下的 API，除非该 API 显式允许——正因如此，开放的 CORS 策略才使得纯前端试玩工具成为可能。“Vibe coding”（氛围编程）一词由 Andrej Karpathy 于 2025 年 2 月提出，指用自然语言描述目标、让大语言模型生成代码的开发方式，通常不做逐行细致审查。自带密钥（BYOK）则指由用户提供自己的 API 凭据，用量计费和配额都归属用户自己的账户。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Cross-origin_resource_sharing">Cross-origin resource sharing - Wikipedia</a></li>
<li><a href="https://en.wikipedia.org/wiki/Vibe_coding">Vibe coding</a></li>

</ul>
</details>

**标签**: `#text-to-speech`, `#Gemini`, `#AI tools`, `#voice cloning`, `#playground`

---

<a id="item-3"></a>
## [谷歌发布 Gemini 3.8 文本转语音，支持 30 秒样本声音克隆](https://blog.google/innovation-and-ai/models-and-research/gemini-models/gemini-3-8-text-to-speech/) ⭐️ 7.0/10

谷歌发布了 Gemini 3.8 文本转语音模型，只需一段约 30 秒的音频样本（你自己的声音，或你拥有使用授权的声音），就能重建出一致、可复用的音色档案。该版本内置了同意验证机制、SynthID 水印以及 C2PA 内容凭证，意在同时保护开发者和提供声音的音色所有者。 声音克隆在其他厂商那里已经足够普及，以至于谷歌不再犹豫将其正式推出，这意味着该能力从细分创业公司走进了主流开发者平台。做有声书、配音、无障碍工具或游戏对白的开发者现在可以直接基于 Gemini 来实现，但由于谷歌在消费级、专业级和云平台上功能开放程度不一致，实际落地效果会被削弱。 克隆流程要求通过同意验证，并在生成的音频中同时嵌入 SynthID 水印和 C2PA 溯源凭证，这一点很关键，因为检测与溯源正是防止滥用的主要手段。评论者还指出，各平台之间的能力并不对齐：消费级和专业级产品里有的功能，在 Google Cloud 上可能不同甚至完全缺失；也有用户反映，除非愿意写详细脚本，否则对情感表现的精细控制比较有限。

hackernews · swolpers · 9月23日 15:29 · [社区讨论](https://news.ycombinator.com/item?id=49817615)

**背景**: 文本转语音（TTS）系统把书面文字转成语音音频；较新的模型还能从一段很短的参考音频中学习说话人的音色，这种技术通常被称为声音克隆或少样本音色复刻。SynthID 是 Google DeepMind 的水印技术，会在 AI 生成内容中嵌入不易察觉的信号，以便日后识别其为合成内容。C2PA（内容来源与真实性联盟）维护一套开放标准，其签名元数据清单被称作 Content Credentials（内容凭证），可为数字资产的来源和修改历史提供可验证记录。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://deepmind.google/models/synthid/">SynthID - Google DeepMind</a></li>
<li><a href="https://ai.google.dev/responsible/docs/safeguards/synthid">SynthID: Tools for watermarking and detecting LLM-generated Text</a></li>
<li><a href="https://c2pa.org/">C2PA | Verifying Media Content Sources</a></li>

</ul>
</details>

**社区讨论**: Hacker News 的评论者普遍感兴趣，但对谷歌在消费级、专业级和云平台之间缺乏对齐感到不满，指出同一个模型在不同平台上的能力有时并不相同。Simon Willison 认为，声音克隆在其他厂商那里已足够普及，所以谷歌不再犹豫推出该功能；thangalin 则分享了自己本地托管的多人有声书应用 KeenLore，它用 Gemma 4 做文本分析，引用归属准确率达到 97.2%。还有评论者赞赏其庞大的音色库和通过脚本实现的精细控制，认为这很适合指导同人广播剧，并与其他控制力较弱的方案作了对比。

**标签**: `#text-to-speech`, `#gemini`, `#voice-cloning`, `#ai-models`, `#local-ai`

---

<a id="item-4"></a>
## [PromptSpend 推出每日更新的 LLM API 价格对比网站](https://promptspend.com/) ⭐️ 7.0/10

PromptSpend 通过 Show HN 帖子上线，它是一个实时网站，追踪各家 LLM API 的价格，并每天重新核对这些价格，同时为每一个价格标注来源。该网站是一个单一用途的对比工具，面向那些需要获取最新各模型定价、而非依赖过期博客文章或厂商页面的开发者。 LLM API 的定价变动频繁，并且在输入/输出 token、缓存和批处理模式上各不相同，因此开发者在挑选服务商时常常依据的是过时数据。一个每日核对、并标注来源的价格表，可以降低成本对比与模型选型的门槛；不过作为一个小型 Show HN 工具，它目前获得的社区验证还很少。 各家定价页面通常按每百万 token 标价，并将输入与输出成本分开列出，还会有 prompt 缓存、批处理和上下文长度分档等额外系数，因此任何聚合工具都必须处理单位归一化和频繁更新。该工具的差异化之处在于每个价格都标注来源，便于用户核实数字；但该 Show HN 帖子仅有 1 分和 1 条评论，尚无真正的外部准确性或覆盖范围审查。

rss · Show HN (self-made tools) · 9月23日 22:49

**背景**: LLM API 是应用程序用来向大语言模型发送提示并接收生成结果的托管接口，通常按照处理的 token 数量计费，而不是固定订阅。由于 OpenAI、Anthropic、Google 以及众多开源模型托管方各自定价且经常调整，价格对比网站和成本计算器已经成为常见的开发者资源。PromptSpend 正属于这一类工具，它额外加入了每日重新核对的步骤，并为每个价格提供来源链接，以降低展示过时数字的风险。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibm.com/think/insights/llm-apis">LLM APIs: Tips for Bridging the Gap - IBM</a></li>
<li><a href="https://deepchecks.com/glossary/llm-apis/">What are LLM APIs? Applications, Benefits & Integration Tips</a></li>

</ul>
</details>

**标签**: `#LLM APIs`, `#pricing`, `#developer tools`, `#cost optimization`, `#Show HN`

---

<a id="item-5"></a>
## [Hugging Face 博客：用 NVIDIA Warp 与 MjWarp 加速机器人仿真](https://huggingface.co/blog/nvidia/how-to-use-nvidia-warp-and-mjwarp) ⭐️ 7.0/10

NVIDIA 在 Hugging Face 博客上发布了一篇实用教程，讲解如何结合使用 NVIDIA Warp（一个面向 GPU 加速仿真、机器人与机器学习的 Python 框架）与 MjWarp（MuJoCo Warp）来加速机器人仿真与学习工作流。文章给出了具体的库和实现步骤，帮助开发者把基于物理的机器人仿真迁移到 GPU 上运行。 机器人学习（尤其是强化学习）依赖海量的物理仿真步数，因此 GPU 并行化仿真可以大幅缩短训练所需的实际时间和成本。这对在仿真中训练控制策略、再部署到真实硬件上的机器人学与具身智能研究者和开发者尤为重要，而这一流程正日益成为现代机器人与智能体研究的基石。 MjWarp 明确针对吞吐量进行优化，即单位时间内完成的仿真总步数，而标准 MuJoCo 优化的是延迟，也就是单步仿真的耗时；Warp 本身要求 Python 3.10 或更高版本，并在 PyPI 上为 Windows（x86-64）、Linux（x86-64 与 AArch64）以及 macOS（Apple Silicon）提供 wheel 包。值得注意的是，来自 Google DeepMind 的 MJWarp 求解器同时也是 Isaac Lab 中 Newton 物理后端的主要且经过验证的求解器，使这篇教程与更大的生态体系联系在一起。

rss · Hugging Face Blog · 9月23日 18:41

**背景**: MuJoCo 是 "Multi-Joint dynamics with Contact" 的缩写，是一款面向机器人学、生物力学和机器学习的通用物理引擎，最初由华盛顿大学开发，并在 2012 年由 Emanuel Todorov、Tom Erez 和 Yuval Tassa 发表的论文中提出，之后于 2021 年 10 月被 Google DeepMind 收购，并于 2022 年 5 月以 Apache 2.0 许可证开源。NVIDIA Warp 则是另一个独立的 Python 框架，允许开发者编写在 GPU（而非 CPU）上执行的仿真与机器人计算内核。MjWarp（MuJoCo Warp）本质上是在 Warp 中重新实现 MuJoCo 的物理计算，使成千上万个并行仿真环境能够同时运行——这正是规模化训练机器人策略时常用的配置。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/NVIDIA/warp">GitHub - NVIDIA / warp : A Python framework for GPU-accelerated...</a></li>
<li><a href="https://mujoco.readthedocs.io/en/latest/mjwarp/index.html">MuJoCo Warp ( MJWarp ) - MuJoCo Documentation</a></li>
<li><a href="https://en.wikipedia.org/wiki/MuJoCo">MuJoCo</a></li>

</ul>
</details>

**标签**: `#robotics`, `#simulation`, `#NVIDIA Warp`, `#MuJoCo`, `#tutorial`

---

<a id="item-6"></a>
## [MiMo-V3 将采用以 HySparse2 为核心的新架构](https://www.reddit.com/r/LocalLLaMA/comments/1wo7mr6/mimov3_is_getting_a_new_architecture_the_core_of/) ⭐️ 7.0/10

MiMo-V3 将切换到一套新架构，其核心组件 HySparse2 已于今天以 arXiv 论文形式发布（arXiv:2609.26368）。据随附的发布说明，这一新设计相比此前方案能够减少 prefill 计算量、缩小 KV cache，并提升长上下文表现。 架构层面的稀疏化设计直接决定 prefill 速度与 KV cache 显存占用，而这两点正是本地运行长上下文模型以及多轮 agent 工作负载时最主要的现实瓶颈。如果 MiMo-V3 真的按描述搭载 HySparse2，就可能降低长上下文本地推理的硬件门槛，并促使其他开源模型跟进类似的混合稀疏注意力方案。 HySparse2 采用双层 KV 共享机制：外层将 cross-decoder 中 full-attention 层的 KV cache 由 self-decoder 中 full-attention 层的隐藏状态生成，内层则保留 HySparse 核心的 KV Reuse 设计并做了两处改进。它被定位为 HySparse 与 Hybrid SWA 的更高效继任者，面向长程、多轮 agent 类工作负载，但此次发布本身并未附带基准数据或可运行代码。

reddit · r/LocalLLaMA · /u/Recoil42 · 9月23日 14:31

**背景**: Transformer 的注意力机制会让每个 token 与其它所有 token 两两比较，因此上下文越长，计算量和 KV cache（缓存历史 token 的 key/value 状态以避免重复计算）就增长得越快。稀疏注意力通过让每个 token 只关注被选中的部分历史 token 来缓解这一问题，而混合方案则把开销较低的滑动窗口注意力与少量 full-attention 层结合，以兼顾质量。HySparse 就是该模型系列所依托的这一类技术，HySparse2 是其最新迭代版本，据称将成为 MiMo-V3 的架构核心。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2609.26368">HySparse 2 : Hybrid Sparse Attention with Two-Level KV Sharing</a></li>
<li><a href="https://arxiv.org/html/2609.26368">1 HySparse 2 delivers better long-context performance at lower prefill...</a></li>
<li><a href="https://x.com/_LuoFuli/status/2102766365190901957">Fuli Luo on X: "MiMo-V3 is getting a new architecture. The core of it ...</a></li>

</ul>
</details>

**标签**: `#llm-architecture`, `#sparse-attention`, `#MiMo-V3`, `#research-paper`, `#local-llm`

---

<a id="item-7"></a>
## [匿名模型 Space Bunny Alpha 在 OpenRouter 免费上线](https://openrouter.ai/stealth/space-bunny-alpha) ⭐️ 7.0/10

一家未公开身份的第三方供应商于 2026 年 9 月 23 日在 OpenRouter 上发布了预览阶段的模型 Space Bunny Alpha，目前页面显示可免费使用。该模型主打高速推理与代码能力，支持原生多模态输入，并提供 100 万 Token 的上下文窗口。 一个免费、开箱即用且具备 100 万 Token 上下文和原生多模态输入的模型，降低了开发者试验长文档处理与代码工作流的门槛，无需支付 API 费用。在 OpenRouter 这类聚合平台上匿名发布的“隐身模型”常被视作大厂正式发布前的测试，因此其真实供应商身份的揭晓可能比模型本身更有意义。 开发方身份未公开，官方也未公布任何基准测试数据、速率限制、吞吐量保证或稳定性承诺，因此实际效果与可用性仍无法验证。OpenRouter 上的免费预览端点随时可能被限流、调整价格或下线；而且宣传的 100 万 Token 窗口并不代表在该上下文的中段也能保持检索准确率。

telegram · zaihuapd · 9月23日 15:42

**背景**: OpenRouter 是一项 AI 路由服务，通过统一的 API 让开发者访问 Google、OpenAI、Anthropic、Mistral 等众多供应商的数百个模型，并代为处理计费和推理路由。上下文窗口指模型一次能处理的文本总量（以 Token 计），100 万 Token 大致相当于数千个源代码文件，这正是长上下文能力在代码与文档分析场景中备受看重的原因。“原生多模态”指模型在主架构内部就融合了图像、音频等模态，而非通过后期融合把独立编码器嫁接到冻结的语言模型上，通常能带来更好的跨模态表现。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/OpenRouter">OpenRouter</a></li>
<li><a href="https://www.mindstudio.ai/blog/claude-1m-token-context-window-ai-agents">Claude 1M Token Context Window: What It Means for AI Agents and Long-Running Tasks | MindStudio</a></li>
<li><a href="https://arxiv.org/abs/2605.25343">[2605.25343] Toward Native Multimodal Modeling: A Roadmap</a></li>

</ul>
</details>

**标签**: `#LLM`, `#free AI`, `#OpenRouter`, `#multimodal`, `#coding models`

---

<a id="item-8"></a>
## [OpenAI 为 ChatGPT 语音接入插件，并升级到 GPT-6 驱动](https://x.com/OpenAI/status/2102808325742322002) ⭐️ 7.0/10

OpenAI 宣布 ChatGPT 语音现在可以调用邮箱、日历、Slack 等插件，并改用全新的 GPT-6 Astra、Sol 和 Luna 模型驱动，新版本今天在全球范围上线。用户还可以在网页端和移动端的 ChatGPT Work 中用语音创建文档、演示文稿、网站和表格，或在浏览器中处理复杂任务。 这把 ChatGPT 的语音模式从单纯的问答对话，推进为一个能在用户日常工作软件中真正执行操作的智能体式助手。它也抬高了与 Google Gemini 以及各家平台助手在语音助手赛道上的竞争门槛——语音不再只是聊天噱头，而成为触发真实企业工作流的首要入口之一。 GPT-6 家族分为三个层级：GPT-6 Astra 被定位为最智能、对齐程度最高的旗舰模型，而 GPT-6 Sol 与 Luna 采用类似方法训练，把 Astra 在专业工作、事实准确性、编程、计算机操作与对齐方面的进步带到速度更快、成本更低的模型上。微软针对其 Foundry 平台的建议是：高难度任务从 Astra 起步，高并发工作负载则使用 Sol 和 Luna；但 OpenAI 这次的语音公告本身并未给出独立基准测试、延迟数据或语音加插件组合的定价信息。

telegram · zaihuapd · 9月24日 00:02

**背景**: 插件（也常被称为工具调用或函数调用）让语言模型可以把任务的一部分交给外部服务完成，例如读取日历或发送邮件，而不仅仅是生成文本。ChatGPT Work 是 OpenAI 面向工作场景的产品，可连接各类工具、文件和桌面应用，直接产出表格、文档和幻灯片等成品。GPT-6 是 OpenAI 最新的模型世代：Astra 是前沿旗舰模型，Sol 和 Luna 则是更小、更快、更便宜的同类模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/introducing-gpt-6-sol-and-luna/">Introducing GPT-6 Sol and Luna | OpenAI</a></li>
<li><a href="https://openai.com/index/gpt-6-astra/">GPT-6 Astra: A new generation of intelligence | OpenAI</a></li>
<li><a href="https://openai.com/chatgpt-work/">ChatGPT Work for every team - OpenAI</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#ChatGPT`, `#GPT-6`, `#voice-assistant`, `#AI-productivity`

---