---
layout: default
title: "Horizon Summary: 2026-09-18 (ZH)"
date: 2026-09-18
lang: zh
---

> 从 58 条内容中筛选出 8 条重要资讯。

---

1. [Prism ML 发布三元权重 Bonsai 2 27B，体积缩小约 9 倍](#item-1) ⭐️ 8.0/10
2. [Show HN：Vim 风格终端 LLM 客户端将上下文压缩至 2-8 万 token](#item-2) ⭐️ 8.0/10
3. [Cactus Needle 3：可切片的 8-29MB 端侧函数调用基础模型](#item-3) ⭐️ 8.0/10
4. [IFM 发布 K2-Horizon-7B：扩散增强 LLM 达 5200 tokens/秒](#item-4) ⭐️ 8.0/10
5. [Respawn：为 AI 智能体打造的 Rust 本地优先撤销工具](#item-5) ⭐️ 7.0/10
6. [Unmute：用一份声明式定义编写语音智能体，可编译到任意技术栈](#item-6) ⭐️ 7.0/10
7. [Swift Qwen 3.8 27B 下载量破 10 万，登顶 HuggingFace 微调榜](#item-7) ⭐️ 7.0/10
8. [作者开源了一年前的「Jev」式非自回归强化学习架构](#item-8) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Prism ML 发布三元权重 Bonsai 2 27B，体积缩小约 9 倍](https://prismml.com/news/bonsai-2-27b) ⭐️ 8.0/10

Prism ML 发布了 Ternary Bonsai 2 27B，这是一个 270 亿参数的语言模型，其权重被限制在三元集合 {-1, 0, +1} 中，并配合 FP16 分组缩放，有效位宽约为 1.76 比特/权重，体积比全精度模型缩小约 9 倍，同时宣称质量接近无损。GGUF 权重已在 Hugging Face 的 prism-ml/Ternary-Bonsai-2-27B-gguf 仓库发布，运行它们需要 Prism 自己的 llama.cpp 分支（发布标签 prism-b10685），而非上游 llama.cpp。 如果“接近无损”的说法成立，那么低于 2 比特的三元权重将让 27B 级别的模型可以轻松装进消费级笔记本，甚至完全在浏览器中运行，这对本地大模型部署而言是重要的一步。这也意味着极低位宽量化正从研究实验走向普通用户可直接下载使用的成品，对关注本地推理的开发者影响尤其明显。 这些 GGUF 文件无法在原生 llama.cpp 上直接使用：simonw 指出必须安装 Prism 的分支，目前提供的是 macOS 运行时构建（prism-b10685）；而且发布材料中并未与标准 2 比特量化做直接对比测试。早期实测数据并不惊艳——在 NVIDIA DGX Spark 上生成速度约为 34.38 tokens/秒，且尚无 drafter 模型，因此无法完整测试投机解码（speculative decoding）。

hackernews · JonSchneider · 9月17日 21:13 · [社区讨论](https://news.ycombinator.com/item?id=49746618)

**背景**: 量化通过压缩神经网络权重来减少内存占用并加快推理速度，通常把权重存成 2 到 8 比特的整数格式；而三元量化更进一步，只允许 {-1, 0, +1} 三个取值，再配上一个分组缩放系数。GGUF 是 llama.cpp 使用的二进制模型文件格式，llama.cpp 是一个开源推理库，已成为 Ollama、LM Studio 等几乎所有本地大模型工具背后的“事实标准”引擎。由于三元权重需要专门的计算内核，新的量化方案往往必须先给推理引擎打补丁才能加载运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Llama.cpp">Llama.cpp</a></li>
<li><a href="https://huggingface.co/docs/hub/gguf">GGUF · Hugging Face</a></li>
<li><a href="https://www.emergentmind.com/topics/ternary-quantization-scheme">Ternary Quantization in Neural Networks</a></li>

</ul>
</details>

**社区讨论**: Hacker News 上的评论整体务实且带谨慎怀疑：simonw 贴出了 Prism macOS 运行时的具体 curl 与运行命令；adrian17 质疑官方博客为何不将该模型与常见的 Q2 量化（约 2.6 bpw，已处在可用性边缘）做对比；danbrooks 则询问它与 Unsloth 对同一基础模型的量化版本相比如何。flutetornado 报告在 DGX Spark 上生成速度约 34.38 tokens/秒，并认为性能瓶颈在于机器的内存带宽而非模型大小；Aurornis 给出了浏览器 WebML 演示链接，但提醒该模型在较长任务中会明显崩坏。

**标签**: `#local-llm`, `#quantization`, `#model-release`, `#llama.cpp`, `#gguf`

---

<a id="item-2"></a>
## [Show HN：Vim 风格终端 LLM 客户端将上下文压缩至 2-8 万 token](https://easiest.ai/) ⭐️ 8.0/10

一位开发者发布了 easiest.ai，这是一款受 Vim 启发的终端（TUI）LLM 客户端，声称可将单个任务的上下文用量从许多智能体工作流常见的 35 万 token 以上压缩到 2 万至 8 万 token，早期独立测试者反馈可节省 90% 以上的 API 成本。该工具通过混合式客户端压缩（上下文压缩）、工具压缩、更小的上下文窗口、避免污染基础提示词的系统提示（system nudges），以及带 LLM 引导上下文交接的按需子智能体来实现这一目标。 上下文和 API 费用失控是开发者运行 LLM 编程智能体时最实际的瓶颈之一，因此一个能把上下文缩减约一个数量级的客户端，可能让智能体工作流的成本大幅下降、更可持续。如果这一效率主张站得住脚，它反映出一种更大趋势：把上下文管理与压缩当作 LLM 工具的一等功能，而非事后补救。 该工具是一个无需外部依赖的单一自包含包，提供 Vim 风格快捷键（支持有限的鼠标操作）、自定义 Markdown/LaTeX/Mermaid 渲染、线程池、不降级体验的 PowerShell 支持，甚至还有 VGA/VESA 模式，可在 GPU 驱动故障时运行。需要注意：这是一个早期个人项目，没有公开仓库或基准测试来独立验证其节省 token 的主张，而且它明确是「有主见」的终端优先工具，网页版聊天和桌面应用只是「即将推出」。

rss · Show HN (self-made tools) · 9月17日 20:26

**背景**: 上下文压缩（context compaction）是一种基于删除的技术，从 LLM 的上下文窗口中移除低信息量的 token，这与摘要式改写（summarization，把 token 重写成摘要）和编码式压缩（compression，把 token 编码为更密集的格式）不同；这一区分正是此类工具声称能在不改变语义的前提下降低成本的关键。子智能体（subagents）是作为工具被调用的独立 LLM 循环，一种常见的设计原则是：它们存在的首要目的是通过用各自聚焦的上下文处理子任务，来保护主智能体的上下文窗口。由于每一次工具调用、文件读取和对话轮次都会被重新发送给模型，长时间的智能体会话很容易膨胀到数十万 token，这正是该项目要解决的痛点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.morphllm.com/context-compaction">Context Compaction: Delete Noise, Keep Signal | Technical Guide</a></li>
<li><a href="https://www.huuhka.net/primary-vs-subagents-in-llm-harnesses/">Primary vs Subagents in LLM harnesses</a></li>
<li><a href="https://docs.ag2.ai/docs/user-guide/subagents/">Subagents - AG2</a></li>

</ul>
</details>

**标签**: `#LLM tooling`, `#token efficiency`, `#TUI/terminal`, `#AI agents`, `#GitHub/Show HN`

---

<a id="item-3"></a>
## [Cactus Needle 3：可切片的 8-29MB 端侧函数调用基础模型](https://www.reddit.com/r/LocalLLaMA/comments/1wj4qj4/cactus_needle_3_a_sliceable_829mb_automation/) ⭐️ 8.0/10

Cactus Compute 发布了 Needle 3，这是一个专为工具/函数调用打造的、可切片的端侧基础模型，以 8-29MB 的二进制文件形式在 Hugging Face、GitHub、PyPI（包名 cactus-needle）以及浏览器沙盒中发布，覆盖 29M 至 121M 参数的深度阶梯。其中完整的 20 层 121M 版本以 2-bit 二进制形式在 Mobile Actions 基准（961 条手机指令，按精确调用匹配）上取得 86.0 分，而 LFM2.5 1.2B 为 82.4 分，DeepSeek V4 Flash 通过其云端 API 为 88.4 分。 让一个只有几十兆的端侧模型具备可靠的函数调用能力，可以省去通常迫使 agent 与自动化流程依赖云端 API 的网络往返，这对手机、可穿戴设备、智能家居和微控制器等受延迟、隐私与连接性限制的场景尤为重要。这意味着 DeepSeek V4 Flash 在 Mobile Actions 上引以为傲的能力（88.4 分）几乎被一个体积小约三个数量级的模型追平，使本地 agent 工具链从“听起来不错”变成真正可用。 Needle 3 有意不具备聊天能力：每一轮都是函数调用，若没有任何已声明的工具能处理该请求，它会返回空列表而不是猜测；无证据支撑的可选参数会被省略，无证据的必填参数会阻止调用发出，调用内容在由 schema 编译出的字节级语法约束下生成，因此 JSON 始终可解析。架构上它是一种 Simple Attention Network，用 Monarch Hadamard MLP 取代了稠密前馈层（每层 25.6K 参数，而非 4.7M），并且 121M 参数中有 70.8M 存放在由 gather 读取的哈希 n-gram 表 engram 中，使其以约 50M 模型的算力运行，每 token 仅需 100 MFLOPs，而同规模 transformer 需要 296 MFLOPs。取舍在短板处很明显：在 BFCL v4 上它得 50.2 分，而 DeepSeek V4 Flash 为 77.2 分；较小的层级在通用任务上衰减很快（29M/4 层版本在 Mobile Actions 上仅得 11.7 分）。

reddit · r/LocalLLaMA · /u/Henrie_the_dreamer · 9月17日 20:05

**背景**: 函数调用（又称工具调用）是指把一组已声明的函数或输出 schema 与用户请求一起交给语言模型，模型返回一个每个参数都已填好的结构化调用；它是大多数 agent、自动化与检索流程的基础。前沿的函数调用模型通常托管在云端且体积庞大——例如 DeepSeek V4 Flash 是一个 284B 参数的混合专家模型，每 token 激活 13B 参数——因此在手机、可穿戴设备或微控制器上使用它一般需要一次网络往返。Needle 3 正是针对这一缺口，完全放弃通用聊天能力，把全部参数预算投入到三件事上：工具调用、结构化抽取和文本嵌入。这里的“可切片”指训练出的网络是嵌套的：从 2 层到完整 20 层堆栈的每一级都是一个单独训练的模型，其模块是完整模型的子集，因此一个基座可以导出多个不同体积的二进制文件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cactuscompute.com/needle">Needle 3 - 8-29 MB foundation model for tiny devices | Cactus</a></li>
<li><a href="https://github.com/cactus-compute/needle">GitHub - cactus-compute/needle: 14MB foundation model for tiny devices; phones, wearables, smart home, and robots. · GitHub</a></li>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash">deepseek-ai/DeepSeek-V4-Flash · Hugging Face</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#function-calling`, `#ai-agents`, `#on-device`, `#open-source-models`

---

<a id="item-4"></a>
## [IFM 发布 K2-Horizon-7B：扩散增强 LLM 达 5200 tokens/秒](https://www.reddit.com/r/LocalLLaMA/comments/1wj2hsm/ifmk2horizon7buno_hugging_face_5200tps_with_no/) ⭐️ 8.0/10

IFM（基础模型研究院）在 Hugging Face 上发布了 K2-Horizon-7B-Uno，这是一个在原有自回归（causal）权重之外额外挂载即插即用扩散适配器的模型。该发布配有 arXiv 论文 2609.04010，声称可在最高 5200 tokens/秒的速度下实现无损生成。 如果“无损”这一说法经得起验证，那么用户就能在本地以远高于传统逐 token 解码的吞吐量运行 7B 级模型，这可能会改变目前依赖投机解码（speculative decoding）或量化技巧的推理流程。这也表明扩散式并行解码正从研究论文走向可直接下载、可实际运行的模型发布。 关键注意事项在于，“无损”的质量声明与 5200 tokens/秒的数值都只是 IFM 单方面给出的说法，尚未被独立复现，而这类工作的吞吐量通常高度依赖 GPU 型号、批大小和序列长度。由于扩散组件被描述为即插即用，它被定位为挂载在自回归权重上的附加适配器，而不是从零训练的全新模型架构。

reddit · r/LocalLLaMA · /u/Zulfiqaar · 9月17日 18:43

**背景**: 标准大语言模型是自回归的：一次只生成一个 token，每个新 token 都必须等前一个完成，因此解码过程受显存带宽限制，难以并行化。扩散语言模型则通过迭代去噪并行生成多个 token，但这通常会改变模型的输出分布，可能造成质量下降。“扩散增强 LLM”这一思路试图在保持精确自回归分布定义的同时获得并行采样的速度，这正是“无损”一词的含义；而“即插即用适配器”的概念来自图像扩散加速方案（如 SpeedUpNet、X-Adapter），即用一个小的附加模块加速被冻结的基座模型。IFM（基础模型研究院）是一家开放式 AI 研究实验室，还发布过 K2-Horizon 系列的其他模型，例如面向长上下文的 3.7B 版本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2609.04010">Unlocking Lossless Speedups in LLMs via Discrete Diffusion</a></li>
<li><a href="https://huggingface.co/IFM">IFM (Institute of Foundation Models)</a></li>
<li><a href="https://recipes.vllm.ai/IFM/K2-Horizon-3.7B">IFM /K2-Horizon-3.7B | vLLM Recipes</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#diffusion-llm`, `#model-release`, `#inference-speed`, `#huggingface`

---

<a id="item-5"></a>
## [Respawn：为 AI 智能体打造的 Rust 本地优先撤销工具](https://github.com/savageAZfck/respawn) ⭐️ 7.0/10

一条 Show HN 帖子介绍了名为 "Respawn" 的开源项目（仓库地址 github.com/savageAZfck/respawn），它用 Rust 编写，自称是 AI 智能体的"撤销按钮"，以本地优先（local-first）的方式实现回滚，完全不依赖云端服务。该帖本身几乎没有技术细节，只有仓库链接、2 个积分和 0 条评论，因此其具体 API、支持的智能体框架和成熟度都无法从现有内容中核实。 AI 智能体越来越多地执行带有真实副作用的操作——写文件、调用 API、改动基础设施——而不可逆的错误正是阻碍它们更自主运行的主要障碍之一。一个轻量、本地优先的回滚层能让开发者获得安全网，同时把智能体状态保留在本机，而不必交给第三方服务托管。 在本地优先模式中，数据的权威副本保存在用户设备上，服务器只承担同步或备份角色，这也正是"离线、无云端"的撤销层能够成立的前提。关键限制在于：回滚只对可逆操作有效，像已发出的邮件、已完成的 API 调用或已经生效的基础设施变更这类外部副作用，无法靠本地快照撤销。

rss · Show HN (self-made tools) · 9月17日 22:36

**背景**: 本地优先（local-first）软件这一概念由研究机构 Ink & Switch 在 2019 年的一篇宣言中提出，指的是本地设备持有数据权威副本、服务器只负责同步与备份而非作为主要数据源的设计理念。Respawn 所针对的问题在智能体领域被称为检查点（checkpointing）：定期保存智能体完整的执行状态，以便在失败或出错后恢复并继续，IBM Research 在 2025 年提出的面向云工程智能体的"撤销并重试"机制也属于这一方向。近期已有多个项目切入同一细分领域，例如 agent-undo，它提供单个 Rust 二进制文件，快照编程智能体写入的每个文件，并允许用户用一条命令撤销整个会话。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.powersync.com/resources/local-first-software">Understand the local - first software architecture pattern and how...</a></li>
<li><a href="https://research.ibm.com/blog/undo-agent-for-cloud">An ’undo-and-retry’ mechanism for agents - IBM Research</a></li>
<li><a href="https://agent-undo.com/">agent-undo — git for humans, au for agents</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent tooling`, `#Rust`, `#open source`, `#local-first`

---

<a id="item-6"></a>
## [Unmute：用一份声明式定义编写语音智能体，可编译到任意技术栈](https://github.com/slng-ai/unmute) ⭐️ 7.0/10

开源项目 Unmute 由 slng-ai 发布，是一个命令行编译器：开发者用一小包 YAML 和 Markdown 描述语音智能体，再把它编译成可运行在生产环境中的代码，目标运行时包括 Pipecat、LiveKit 和 SLNG。该项目以 Show HN 形式发布到 Hacker News，目前在 GitHub 上的最新版本为 v0.5.2。 语音智能体通常是与某一家厂商的实时音频栈深度绑定的代码，而 Unmute 承诺用一份可移植的定义来降低锁定风险，让团队不必重写智能体逻辑就能更换或混用运行时。如果这一思路可行，它就指向一种声明式、配置驱动的智能体开发模式，类似 AI 工具生态其他领域已经出现的做法。 定义被拆分为 YAML 与 Markdown 两部分：YAML 声明智能体的身份、所用模型、可调用的工具、通话过程中持久化的状态以及任务如何拆分为步骤，编译器则输出归开发者所有的代码。作为一个 v0.5.x 版本的项目，它仍处于早期阶段，而且这次 Show HN 提交只获得 1 分、0 条评论，因此目前还没有独立证据说明生成的代码在生产环境中的表现如何。

rss · Show HN (self-made tools) · 9月17日 22:36

**背景**: 语音智能体是“语音输入、语音输出”的实时对话式 AI，与听写转写或简单的电话菜单机器人不同。构建这类系统通常需要选定一个实时音频与编排框架——Pipecat、LiveKit 和 SLNG 都属于此类技术栈——并编写与该框架绑定的命令式代码。由微软 Copilot 扩展能力带火的“声明式智能体”则改为用 YAML 或 JSON 描述智能体，使配置更易于审阅、修改和共享。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/slng-ai/unmute">GitHub - slng-ai/unmute: Voice agents in YAML, compiled into production code you own. · GitHub</a></li>
<li><a href="https://unmute.ai/">Unmute - Unmute</a></li>
<li><a href="https://github.com/slng-ai/unmute/releases/tag/v0.5.2">Release v0.5.2 · slng-ai/unmute</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#voice agents`, `#open source`, `#GitHub`, `#developer tools`

---

<a id="item-7"></a>
## [Swift Qwen 3.8 27B 下载量破 10 万，登顶 HuggingFace 微调榜](https://www.reddit.com/r/LocalLLaMA/comments/1wj3s31/thank_you_swift_qwen_38_27b_now_has_100k/) ⭐️ 7.0/10

小型开源实验室 UkisAI 宣布，其首个开源模型 Swift Qwen 3.8 27B 下载量已突破 10 万次，目前在 HuggingFace Trending 上位列微调模型第一、总榜第九。同一篇帖子里，团队感谢社区贡献的各种量化版本与二次微调，并预告两个即将发布的版本：修复训练 bug 并加入更多强化学习的 Swift 1.5 Qwen3.8 27B，以及将在一周内推出的 Swift Qwen3.8 Flash Next。 这一结果表明，小型实验室也能凭借一个可本地下载的模型冲上 HuggingFace 榜单前列，进一步印证了前沿能力向开放权重迁移的趋势。更实际的意义在于，这套可复用的方法在几乎不损失准确率的前提下将 token 用量降低 58.3%、推理速度提升 1.95 倍，能直接降低本地部署推理模型或构建智能体流水线的成本与延迟。 其核心技术并非训练模型输出更短的推理过程，而是让模型"思考得更高效"——模型卡将 Swift 描述为一个专注于 token 高效思考、抑制病态过度思考模式的推理模型。目前 ukisai 官方与第三方量化者 bartowski 都提供了 GGUF 量化版本；作者还表示，下一轮基准测试将按用户要求加入更多编程与长程任务评测。

reddit · r/LocalLLaMA · /u/Secure_Recording_472 · 9月17日 19:30

**背景**: Qwen 3.8 27B 是阿里巴巴以 Apache 2.0 协议发布的一款 270 亿参数开放权重稠密模型，规模小到可以单张 24GB 显卡运行。Swift 是该基座模型的微调版本，并同时提供 GGUF 量化文件——这是 llama.cpp 等本地推理工具用来在消费级硬件上运行模型的格式。所谓"病态过度思考"，指推理模型倾向于生成冗长、重复的思维链，既增加 token 消耗与延迟，又无法提升甚至可能损害准确率；LLMThinkBench、OptimalThinkingBench 等近期基准正是为衡量这一现象而设计。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/ukisai/Swift-Qwen3.8-27b">ukisai/ Swift - Qwen 3 . 8 - 27 b · Hugging Face</a></li>
<li><a href="https://ollama.com/smtek/Swift-Qwen3.8-27B">smtek/ Swift - Qwen 3 . 8 - 27 B</a></li>
<li><a href="https://arxiv.org/html/2507.04023">Do LLMs Overthink Basic Math Reasoning? Benchmarking the...</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#open-source-model`, `#finetune`, `#llm-efficiency`, `#huggingface`

---

<a id="item-8"></a>
## [作者开源了一年前的「Jev」式非自回归强化学习架构](https://www.reddit.com/r/LocalLLaMA/comments/1wijo3e/i_literally_built_the_jev_architecture_one_year/) ⭐️ 7.0/10

一位 Reddit 用户（DeepMostInnovations 的 u/Nandakishor_ml）发布了一整套开源产物，称自己在 2025 年 3 月就构建了该架构：arXiv 论文 2503.23303、2025 年 9 月的第二篇论文 2510.01237、Hugging Face 模型与训练数据集，以及 PyPI 包。其核心主张是：某前沿实验室后来提出了非常相似的「非自回归 + JSON Schema 概率预测」架构（即「Jev」），并把它宣传为突破，却没有公开技术论文、模型权重和数据集。 这件事反映开源研究中的一种反复出现的矛盾：当资源雄厚的前沿实验室把类似想法包装成突破却不公开产物时，个人或小团队的工作很容易被淹没。对于研究非自回归（替代逐 token 解码）方案的开发者而言，这是一个具体且有据可查的案例——它附带真实的权重、数据和代码，而不只是一个说法。 作者的模型使用 PPO 在序列嵌入上训练，输出逐轮（turn-by-turn）的转化轨迹，即 0.0 到 1.0 之间的概率；而据其描述，Jev 使用通过 RLCD 训练的并行采样来输出置信度分布和 schema 选择。作者自己也承认，这一比较属于架构层面以及垂直场景（销售对话）层面的相似，而非直接的基准对比；此外原帖据称被 Reddit 的过滤器删除后重新发布。

reddit · r/LocalLLaMA · /u/Nandakishor_ml · 9月17日 04:18

**背景**: 非自回归模型会并行生成输出元素，而不是严格从左到右逐个生成，因此推理速度更快，但历史上其生成质量通常不如 GPT 系列这类自回归模型。PPO（Proximal Policy Optimization，近端策略优化）是 OpenAI 提出的、被广泛使用的强化学习算法，它在优化策略以获取奖励的同时限制每次更新对策略的改变幅度。将两者结合起来，该架构可以直接预测结构化输出（例如 JSON Schema 字段和概率），而不是逐 token 地生成它们。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2102.08220">[2102.08220] Non-Autoregressive Text Generation with Pre ... Non-Autoregressive Language Models for Fast and Flexible Text ... Non-Autoregressive Text Generation with Pre-trained Language ... Difference Between Autoregressive And Non ... - GeeksforGeeks GitHub - LitterBrother-Xiao/Overview-of-Non-autoregressive ... Non-Autoregressive Text Generation with Pre-trained Language ... ELMER: A Non-Autoregressive Pre-trained Language Model for ...</a></li>
<li><a href="https://openai.com/index/openai-baselines-ppo/">Proximal Policy Optimization | OpenAI</a></li>
<li><a href="https://pengzhangzhi.github.io/NonAR-LM/">Non-Autoregressive Language Models for Fast and Flexible Text ...</a></li>

</ul>
</details>

**标签**: `#open-source`, `#LLM architecture`, `#reinforcement-learning`, `#arxiv`, `#huggingface`

---