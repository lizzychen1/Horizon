---
layout: default
title: "Horizon Summary: 2026-08-04 (ZH)"
date: 2026-08-04
lang: zh
---

> 从 78 条内容中筛选出 15 条重要资讯。

---

1. [面向自我改进编程代理的 Harness 工程](#item-1) ⭐️ 9.0/10
2. [MiniMax-H3 多模态视频模型现已通过 MLX 在 Apple Silicon 上运行](#item-2) ⭐️ 9.0/10
3. [完整版 Kimi K3 模型在 16 台 DGX Spark 集群上跑出 20+tps](#item-3) ⭐️ 9.0/10
4. [Ling-3.0-flash 开放权重模型上线 Hugging Face，采用 MIT 许可](#item-4) ⭐️ 9.0/10
5. [Mistral 发布 Shieldstral：3B 开放权重多模态审核模型](#item-5) ⭐️ 8.0/10
6. [DeepSeek V4 Flash 在单块 AMD MI300X 上实现 150+ tokens/秒](#item-6) ⭐️ 8.0/10
7. [开源手语翻译系统支持智能眼镜](#item-7) ⭐️ 8.0/10
8. [开发者给视频编辑器添加 MCP 服务器，让 Claude 能剪辑视频](#item-8) ⭐️ 8.0/10
9. [Watchfire：面向 AI 编程代理的开源控制室](#item-9) ⭐️ 8.0/10
10. [Hyperlane IDE：融合代理工作树与原生调试工具](#item-10) ⭐️ 8.0/10
11. [LFM2.5-2.6B：Liquid AI 面向本地代理的紧凑模型](#item-11) ⭐️ 8.0/10
12. [llama.cpp 新 PR 在 GPU 上缓存热门 MoE 专家，8GB 显存速度提升最高 2 倍](#item-12) ⭐️ 8.0/10
13. [开发者开源 Web Clipper，并用它批量保存 Dan Koe 2026 年全部文章作为压力测试](#item-13) ⭐️ 8.0/10
14. [让 Codex 管理 Thread；新编排技能使用 Sol 和 Luna](#item-14) ⭐️ 8.0/10
15. [Pleasantries：为 AI 编码 CLI 拦截寒暄式提示的预钩子脚本](#item-15) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [面向自我改进编程代理的 Harness 工程](https://lilianweng.github.io/posts/2026-07-04-harness/) ⭐️ 9.0/10

Lilian Weng 于 2026 年 7 月发表的文章提出了 Harness 工程这一概念，将其作为构建自我改进编程代理的方法，并详细说明了如何利用适应度函数和基于轨迹的优化来改进代理的外围结构。社区讨论还分享了在大规模实施这些手段时的实用技巧。 在大模型权重难以继续大幅提升的背景下，Harness 工程为提升代理的性能、质量和成本效率提供了新的手段。对于所有构建 LLM 代理的团队来说，这都很重要，因为实际部署中的可靠性往往取决于 Harness（外围结构）而非仅取决于模型本身。 文章将适应度函数视为强制执行架构属性的护栏，并建议利用执行轨迹来发现和修复实际问题，例如将 20k token、15 次工具调用的上下文压缩为 800 token 和 1 次调用。文章还建议让代理自行编写工具、测试和验证集，以扩展自身的 Harness。

hackernews · tosh · 8月4日 06:17 · [社区讨论](https://news.ycombinator.com/item?id=49164896)

**背景**: Harness 工程是围绕 LLM 代理设计外围支撑结构的学科，包括上下文传递、工具接口、规划产物、记忆、沙箱和可观测性。适应度函数是自动化检查机制，类似于架构的单元测试，用于将代理行为约束在期望的边界内。基于轨迹的优化则通过分析代理的真实执行记录来定位低效和错误。与模型权重训练不同，调整 Harness 没有梯度下降可循，但可以更高效地利用样本，因为人类和代理可以直接推理因果层面的失败原因。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://martinfowler.com/articles/harness-engineering.html">Harness engineering for coding agent users</a></li>
<li><a href="https://www.infoq.com/articles/fitness-functions-architecture/">Fitness Functions for Your Architecture - InfoQ</a></li>
<li><a href="https://www.langchain.com/blog/the-anatomy-of-an-agent-harness">The Anatomy of an Agent Harness</a></li>

</ul>
</details>

**社区讨论**: 评论区整体热情高涨：bisonbear 呼吁为大型代码库建立通用的适应度函数；zby 认为提示词和代码的训练将成为下一个范式。scosman 分享说，当代理阅读生产轨迹、自行编写工具并使用 evals 和验证/测试集时，基于轨迹的自动研究“出奇地强大”。storus 则提出疑问：Harness 何时能自己生成 RLHF/DPO 训练集并对模型进行 LoRA 微调？Kinrany 的“追寻 Torment Nexus”玩笑则为讨论增添了一点幽默。

**标签**: `#AI agents`, `#LLM`, `#prompt engineering`, `#agent harness`, `#meta-optimization`

---

<a id="item-2"></a>
## [MiniMax-H3 多模态视频模型现已通过 MLX 在 Apple Silicon 上运行](https://simonwillison.net/2026/Aug/4/minimax-h3-mlx/#atom-everything) ⭐️ 9.0/10

Simon Willison 使用 PipeNetwork 的 MLX 移植版，在 M5 Max MacBook Pro 上成功运行了 MiniMax-H3。这个新型全模态生成模型可以接受文本、图像、音频和视频输入，并生成最长 15 秒、含音频的视频片段。 这意味着 AI 开发者可以在 Apple Silicon 设备上本地运行前沿的视频生成模型，无需依赖云端 API。它让 Mac 成为多模态生成工作流的实用平台，并可能推动本地视频生成工具的普及。 运行过程需要下载约 115 GB 的模型文件，在 M5 Max MacBook Pro 上生成一段 15 秒视频耗时接近 45 分钟。由于没有按提示词指南指定音频内容，Willison 测试中生成的音频听起来像奇怪的语音噪声；MiniMax 提供了提示词指南来获得更好的结果。

rss · Simon Willison · 8月4日 19:10

**背景**: MLX 是 Apple 推出的面向 Apple Silicon 的机器学习数组框架，其 API 类似 NumPy，专为统一内存架构优化。MiniMax-H3 是 MiniMax 发布的开源通用全模态生成模型，可理解文本、图像、视频和音频，并一次性生成最高 2K 分辨率、15 秒时长且带原生立体声的视频。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://opensource.apple.com/projects/mlx/">Apple Open Source</a></li>
<li><a href="https://www.minimax.io/blog/minimax-h3">MiniMax H 3 : An Open Model Breaking the Boundaries Between Tasks...</a></li>
<li><a href="https://comfyui-wiki.com/en/models/minimax">MiniMax H3: Open Omni - Modal Video Model With... | ComfyUI Wiki</a></li>

</ul>
</details>

**标签**: `#MLX`, `#MiniMax-H3`, `#multimodal`, `#Apple Silicon`, `#video generation`

---

<a id="item-3"></a>
## [完整版 Kimi K3 模型在 16 台 DGX Spark 集群上跑出 20+tps](https://www.reddit.com/r/LocalLLaMA/comments/1vfl525/kimi_k3_full_model_running_on_16x_gb10_cluster_at/) ⭐️ 9.0/10

Reddit 用户 /u/ciprianveg 分享了完整版 Kimi K3 模型在 16 节点 DGX Spark（GB10）集群上的首次成功运行结果。在 llama-benchy 的连贯语料上，集群平均速度达到每秒 20+ tokens，峰值解码 38 tps，预填充 750 tps。 这一结果意义重大，因为它证明了一个 2.8 万亿参数量的旗舰模型可以在少量桌面级 AI 超级计算机组成的集群上以可用速度自托管运行。它为本地大模型爱好者和小型团队提供了在不依赖云 GPU 实例的情况下运行前沿级开源权重模型的具体路径。 该配置使用了 16 台搭载 Nvidia GB10 Grace Blackwell 超级芯片的 DGX Spark 节点；用户计划在调优完成后发布 vLLM 镜像和操作说明。原帖没有说明量化细节，因此具体的内存占用和精度还有待披露。

reddit · r/LocalLLaMA · /u/ciprianveg · 8月4日 19:56

**背景**: Kimi K3 是 Moonshot AI 的旗舰大语言模型，拥有 2.8 万亿参数、100 万 token 上下文窗口，并采用名为 Kimi Delta Attention（KDA）的混合线性注意力机制。Nvidia DGX Spark 是一款围绕 GB10 Grace Blackwell 超级芯片构建的桌面工作站，配备 128GB 一致性统一内存，FP4 精度下 AI 算力最高可达 1 petaFLOP。本新闻中的用户使用 llama-benchy 对集群进行基准测试，该工具可针对任何 OpenAI 兼容端点测量类似 llama-bench 的解码与预填充统计数据。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Kimi_(AI)">Kimi ( AI ) - Wikipedia</a></li>
<li><a href="https://www.nvidia.com/en-us/products/workstations/dgx-spark/">Personal AI Supercomputer Powered by Blackwell | NVIDIA DGX Spark</a></li>
<li><a href="https://platform.kimi.ai/docs/guide/kimi-k3-quickstart">Kimi K3 - Kimi API Platform</a></li>

</ul>
</details>

**标签**: `#Kimi K3`, `#vLLM`, `#DGX Spark`, `#local LLM`, `#cluster inference`

---

<a id="item-4"></a>
## [Ling-3.0-flash 开放权重模型上线 Hugging Face，采用 MIT 许可](https://www.reddit.com/r/LocalLLaMA/comments/1vfdeek/inclusionailing30flash_weights_are_up_on_hugging/) ⭐️ 9.0/10

inclusionAI 已在 Hugging Face 上发布 Ling-3.0-flash 权重，无需申请即可下载，提供 BF16（约 255GB，24 个分片）和官方 FP8（约 128GB）两个版本。该模型总参数量为 127.5B，但每 token 仅激活 5.1B 参数，采用 512 个专家、每 token 激活 8 个专家的精细 MoE 架构。 宽松的 MIT 许可和官方 FP8 量化使得它无需额外转换即可直接用于本地和多 GPU 部署，省去法律或量化成本。其 512 专家的超细 MoE 粒度在开源 MoE 模型中较为罕见，为社区提供了新的效率与质量权衡。 该模型采用 BailingMoeV3 架构，model_type 为“bailing_hybrid”，并使用自定义代码，与 Ling-2.6-flash 同属一个系列。思考模式（thinking）是聊天模板中的按请求开关，默认开启，因此没有单独推理版本的 SKU。

reddit · r/LocalLLaMA · /u/derspenti · 8月4日 15:21

**背景**: MoE（混合专家）模型会将每个 token 路由到少数大型“专家”参数上，从而在保持大模型总参数量的同时降低推理开销。FP8 量化将权重以 8 位浮点数存储，与 BF16 相比可将内存占用大致减半，且在许多情况下质量损失很小。像 Ling-3.0-flash 这样的开放权重模型允许开发者自行托管或微调，而 MIT 等宽松许可则移除了商业使用的限制。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://agihunt.info/en/e/19fcd5e1d55d6d0b5b5a2e6a166">inclusionAI Open-Sources 127B MoE Model… · AGI Hunt</a></li>
<li><a href="https://thesiftai.com/inclusionais-ling-3-0-flash-weights-released-on-hugging-face/">InclusionAI’s Ling-3.0 Flash Weights Released on Hugging Face</a></li>

</ul>
</details>

**社区讨论**: 讨论中最受关注的是实际兼容性问题：发帖者询问 llama.cpp 是否已支持“bailing_hybrid”，还是目前仅支持 vllm 和 sglang，因为这将决定他们当晚能否在本地运行。还有人提到，此前某位参与者对 Q8_0 大小约 135GB 的粗略猜测与官方 FP8 的大小接近。

**标签**: `#AI model`, `#Open weights`, `#Hugging Face`, `#FP8`, `#MoE`

---

<a id="item-5"></a>
## [Mistral 发布 Shieldstral：3B 开放权重多模态审核模型](https://mistral.ai/news/shieldstral/) ⭐️ 8.0/10

Mistral 发布了 Shieldstral，一个 3B 参数、开放权重的多模态安全分类器，用于内容审核。该模型的表现优于体型大至其 7 倍的分类器，并已在 Hugging Face 上提供。 Shieldstral 为开发者提供了一个可调、可本地运行的审核替代方案，不同于大科技平台的封闭 API。其小尺寸和开放权重使其在不需要将数据发送到外部服务的情况下，也能实际用于工作流中的内容安全集成。 该模型在 Hugging Face 上以 mistralai/Shieldstral-1.0-3B 提供，并可通过 vLLM 提供服务。它支持设备端部署，并可根据组织的审核政策进行适配。

hackernews · riadsila · 8月4日 16:36 · [社区讨论](https://news.ycombinator.com/item?id=49171268)

**背景**: 多模态学习是一种深度学习方式，它整合并处理多种类型的数据，例如文本、音频、图像或视频。开放权重模型公开其训练好的参数，允许开发者自由下载、微调和部署。这一发布顺应了小型化、专用化模型的趋势，这类模型相比大型封闭模型提供了更强的控制力和隐私保护。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://mistral.ai/news/shieldstral/">Introducing Shieldstral . | Mistral AI</a></li>
<li><a href="https://huggingface.co/mistralai/Shieldstral-1.0-3B">mistralai/ Shieldstral -1.0-3B · Hugging Face</a></li>
<li><a href="https://en.wikipedia.org/wiki/Multimodal_learning">Multimodal learning - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论者询问 Shieldstral 是否支持任意的自定义规则集，还是仅支持固定的审核风格，以及它与 OpenAI 的 omni-moderation API 相比如何。还有人称赞 Mistral 专注于更小、更精细调整模型的策略，并分享了 Hugging Face 链接。

**标签**: `#AI model`, `#content moderation`, `#Mistral`, `#open-weights`, `#multimodal`

---

<a id="item-6"></a>
## [DeepSeek V4 Flash 在单块 AMD MI300X 上实现 150+ tokens/秒](https://github.com/ryanzhou/deepseek-v4-flash-mi300x) ⭐️ 8.0/10

ryanzhou 的 GitHub 仓库演示了在单块 AMD MI300X 加速卡上运行 DeepSeek V4 Flash（284B 参数 MoE 模型）。该方案在 256K 上下文下实现了每秒超过 150 tokens 的速度，并在 README 中讨论了相关取舍。 这一成果的意义在于，它为在单块 AMD GPU 上自托管大型混合专家（MoE）模型提供了具体且可操作的方案，随着 DeepSeek 模型被广泛采用，这一点愈发重要。它也展示了量化与高效推理技术如何克服单 GPU 的显存限制。 模型上下文窗口从原始的 100 万 tokens 缩减到 256K tokens；MI300X 是 OAM 模块，通常以 8 卡整板形式出售而非单卡。该方法保留了模型完整的推理权重，并依赖原生 MXFP4 量化将其装入 192GB HBM3 显存。

hackernews · zhoutong · 8月4日 10:00 · [社区讨论](https://news.ycombinator.com/item?id=49166386)

**背景**: DeepSeek V4 Flash 是一个混合专家（MoE）语言模型，总参数 284B，但每个 token 只激活 13B 参数，并支持 100 万 token 的上下文。AMD Instinct MI300X 是数据中心级 GPU，配备 192GB HBM3 显存、750W TDP，基于 CDNA 3 架构，通常以 8 卡整板形式部署。量化通过将权重表示为 4-bit（MXFP4）等更低精度格式来减小模型显存占用，这正是大型模型能装入单张 GPU 的关键手段。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash">deepseek-ai/DeepSeek-V4-Flash · Hugging Face</a></li>
<li><a href="https://www.techpowerup.com/gpu-specs/radeon-instinct-mi300x.c4179">AMD Radeon Instinct MI300X Specs | TechPowerUp GPU Database</a></li>
<li><a href="https://www.digitalocean.com/community/tutorials/model-quantization-large-language-models">Understanding Model Quantization in Large Language ... | DigitalOcean</a></li>

</ul>
</details>

**社区讨论**: 评论区提出了实际注意点：有人指出 MI300X 无法单卡购买（只有约 25 万欧元的 8 卡整板），也有人提出 144GB 的 MI350P PCIe 卡在 MXFP4 量化下或许也能运行。还有评论者赞赏这项工作，并引用了相关的 2xMI300X 实验，指出主要取舍是上下文从 100 万降到 256K，而速度和完整权重精度均得到保留。

**标签**: `#deepseek`, `#ai-inference`, `#github`, `#amd`, `#quantization`

---

<a id="item-7"></a>
## [开源手语翻译系统支持智能眼镜](https://github.com/aadisang/hand-wave) ⭐️ 8.0/10

这个开源项目首次将 Meta 智能眼镜与手语指拼翻译软件集成，使用训练于 Google FSboard 数据集的 CNN+GRU 模型，并采用 CTC 束搜索和 KenLM 语言模型进行解码。 该项目针对手语翻译这一长期被忽视的问题，利用可穿戴设备实现实时翻译，具有实用性和新颖性。作为完全开源的 FOSS 项目，它能为开发者提供可复现的基座，推动辅助 AI 和可穿戴视觉技术的发展。 系统支持网页和 iOS 平台，也可不使用智能眼镜。由于低端设备上性能受限，模型托管在 Modal 上运行；目前仅支持指拼（fingerspelling）识别。

rss · Show HN (self-made tools) · 8月4日 21:58

**背景**: FSboard 是谷歌发布的大规模美国手语指拼数据集，包含 320 万字符和 266 小时视频。CTC（联结主义时间分类）是一种无需逐帧对齐即可训练序列模型的损失函数，KenLM 则是常用的统计语言模型工具，两者结合可改善手语识别的准确性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/pdf/2407.15806">FSboard : Over 3 million characters of ASL</a></li>
<li><a href="https://openaccess.thecvf.com/content/CVPR2025/supplemental/Georg_FSboard_Over_3_CVPR_2025_supplemental.pdf">FSboard</a></li>

</ul>
</details>

**标签**: `#sign-language`, `#wearable`, `#computer-vision`, `#open-source`, `#AI-app`

---

<a id="item-8"></a>
## [开发者给视频编辑器添加 MCP 服务器，让 Claude 能剪辑视频](https://www.shorz.ai/) ⭐️ 8.0/10

一名开发者在 Hacker News 上展示了一个 MCP 服务器项目，它把 Claude 连接到视频编辑器，让 AI 可以完成视频剪辑任务。项目托管在 shorz.ai。 这是利用 MCP 将 AI 助手变成实用视频剪辑工具的具体案例，可能让视频剪辑变得更加易用。它反映了 AI 代理通过标准协议控制专业桌面软件的流行趋势。 该帖子除了 shorz.ai 链接外，没有提供代码、文档或使用说明，Hacker News 讨论区也暂无评论。这个项目看起来更像早期或个人工具，而不是完整的开源发布。

rss · Show HN (self-made tools) · 8月4日 21:52

**背景**: 模型上下文协议（MCP）是 Anthropic 于 2024 年 11 月推出的开放标准，用于将 Claude 等 AI 应用连接到外部工具、数据源和工作流。MCP 服务器就像 AI 的“USB-C 接口”，让模型可以调用外部函数，由此催生了不断壮大的视频编辑 MCP 服务器生态，例如 reap.video 支持剪辑、字幕和配音等功能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://modelcontextprotocol.io/docs/2026-07-28/getting-started/intro">What is the Model Context Protocol (MCP)?</a></li>
<li><a href="https://reap.video/mcp">Video Editing MCP Server: Clip, Caption & Dub from Any AI Agent | reap</a></li>

</ul>
</details>

**标签**: `#MCP`, `#Claude`, `#video editing`, `#AI agent`, `#tool`

---

<a id="item-9"></a>
## [Watchfire：面向 AI 编程代理的开源控制室](https://github.com/watchfire-io/watchfire) ⭐️ 8.0/10

Watchfire 是一款新的开源工具，让开发者无需反复批准权限即可安全地运行多个 AI 编程代理。它支持基于规范的任务，并且可以作为 MCP 服务器公开。 这很重要，因为它解决了使用 AI 编程代理时的一个常见痛点：管理权限和多个代理的负担。其安全特性和 MCP 支持使其更容易集成到现有开发者工作流中，可能加速 AI 辅助编程的采用。 该工具最初是为了绕过权限提示而开发的，后来演变成一个注重安全的控制室。最新增加的功能是暴露为 MCP 服务器，允许其他 MCP 主机连接 Watchfire。由于刚发布，目前还没有社区反馈。

rss · Show HN (self-made tools) · 8月4日 20:57

**背景**: 模型上下文协议（MCP）是一种开放协议，标准化了 AI 应用程序如何连接到外部数据和工具。MCP 服务器提供资源和工具，供 MCP 主机（如 AI 代理）使用。基于规范的开发方法通常涉及创建定义所需行为的规范，然后从该规范生成供代理执行的任务。Watchfire 充当控制室，为开发者提供一个集中管理多个 AI 代理的地方。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://modelcontextprotocol.io/docs/2026-07-28/learn/server-concepts">Understanding MCP servers - Model Context Protocol</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#open-source`, `#coding tools`, `#MCP`, `#dev workflow`

---

<a id="item-10"></a>
## [Hyperlane IDE：融合代理工作树与原生调试工具](https://hyperlaneide.com/) ⭐️ 8.0/10

Hyperlane 是一款基于 VS Code 源代码（Code OSS）构建的独立 IDE，将基于工作树（worktree）的代理开发与原生调试、性能分析和测试工具融为一体。它可免费下载，无需注册账号，并支持 Claude Code、Codex 和 opencode 等多种代理工具。 这直接解决了使用 AI 编码代理的团队面临的一个主要痛点：无需离开编辑器即可审查和调试并行的代理工作树。通过将代理编排器与完整 IDE 工具连接起来，Hyperlane 可以让代理生成的代码在商业场景中更安全、更容易集成。 Hyperlane 支持 macOS（Apple Silicon）、Windows 和 Linux（x64/arm64，提供 .deb 和 .rpm 包），并包含每个工作树独立的标签页、编辑器、窗口和终端，以及跨工作树缓存以避免重复复制仓库。它还内置了强大的 git 客户端、三方冲突编辑器、按工作树查看 blame 和 diff、针对 GitHub/GitLab/Codeberg/自托管 Forgejo 的 PR 支持，以及用于实时视觉编辑的设计模式；不过目前它是闭源的，仓库仅用于发布和问题跟踪。

rss · Show HN (self-made tools) · 8月4日 20:31

**背景**: 像 Codex CLI 这样的代理编排器通常使用 git 工作树（worktree）让多个 AI 代理并行运行，但它们缺少完整的 IDE 功能来调试和审查代码。Git 工作树允许开发者同时检出同一个仓库的多个分支，在并行代理驱动开发中越来越流行。VS Code 本身是专有软件，但其开源基础 Code OSS 采用 MIT 许可证，是许多第三方编辑器的基石。Hyperlane 基于 Code OSS 构建，将这两种工作流合并到一个工具中。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/sonim1/using-git-worktree-for-parallel-ai-agent-development-44nb">Using git worktree for parallel AI agent development - DEV Community</a></li>
<li><a href="https://thamizhelango.medium.com/why-git-worktrees-are-the-secret-weapon-for-parallel-development-in-coding-agents-a969bc20d04e">Why Git Worktrees Are the Secret Weapon for Parallel Development ...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Visual_Studio_Code">Visual Studio Code - Wikipedia</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#IDE`, `#developer tools`, `#workflow`, `#agent development`

---

<a id="item-11"></a>
## [LFM2.5-2.6B：Liquid AI 面向本地代理的紧凑模型](https://huggingface.co/blog/LiquidAI/lfm2-5-2-6b) ⭐️ 8.0/10

Liquid AI 发布了 LFM2.5-2.6B，这是一个 2.69B 参数、支持 128K 上下文和原生工具调用的模型，并针对多步骤代理工作流进行了后训练。官方 Q4_K_M GGUF（约 1.67 GB）已可直接在 llama.cpp 上运行，在厂商测试中手机可达 30 tok/s，Apple M5 Max 可达 220 tok/s。 LFM2.5-2.6B 让常驻本地的 AI 代理在手机和消费级 CPU 上变得切实可行，减少了对云端调用的依赖。它在同尺寸下表现出有竞争力的工具使用基准分数，意味着小型模型可以作为廉价的执行代理完成信息提取、搜索和重复性工具调用，而更大的模型负责规划。 后训练包含四个阶段，在真实运行环境（OpenClaw、Hermes Agent）中进行 Agentic RL，而不仅仅是离线蒸馏。在厂商基准中，它在 ToolSandbox（77.83 vs 76.44）和 IFBench（59.17 vs 56.47）上超过 Qwen3.5-9B，但在 BFCLv4（56.88 vs 60.13）和 LiveCodeBench（59.41 vs 69.86）上落后；Liquid 的模型卡不建议将其用于智能体编码。

rss · Hugging Face Blog · 8月4日 13:58

**背景**: LFM2.5-2.6B 是 Liquid AI 推出的一款 2.6B 参数稠密模型，专为端侧代理工作负载设计，支持 128K 上下文窗口和原生工具调用。GGUF 是在 llama.cpp 上运行的量化模型的标准格式，Q4_K_M 是一种广泛使用的 4-bit 量化，在质量与内存占用之间取得平衡。像这样的小型本地模型旨在低成本处理重复性工具编排和提取任务，而更大的模型则负责规划和复杂推理。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.liquid.ai/lfm/models/lfm25-2.6b">LFM2.5-2.6B - Liquid Docs</a></li>
<li><a href="https://aiweekly.co/alerts/liquid-ai-ships-lfm25-26b-a-phone-ready-agent-model">Liquid AI Ships LFM2.5-2.6B, a Phone-Ready Agent Model | AI Weekly</a></li>
<li><a href="https://willitrunai.com/blog/quantization-guide-gguf-explained">GGUF Quantization Guide (2026): Q4_K_M Saves 72% VRAM — Q4 vs Q5 vs Q8 | Will It Run AI Blog</a></li>

</ul>
</details>

**社区讨论**: Reddit 用户 BTA_Labs 强调了该模型在工具使用上的优势和编码方面的局限，指出厂商基准需要独立验证，而且在手机上 128K 上下文会受到 KV cache 和较长代理历史的限制。他们呼吁在 Android、旧笔记本电脑和迷你 PC 上进行实测，尤其是连续 10 次以上的工具调用。总体情绪是谨慎乐观：小型模型最适合作为廉价的执行代理，而不是唯一的智能助手。

**标签**: `#AI agents`, `#local LLM`, `#model release`, `#Hugging Face`

---

<a id="item-12"></a>
## [llama.cpp 新 PR 在 GPU 上缓存热门 MoE 专家，8GB 显存速度提升最高 2 倍](https://www.reddit.com/r/LocalLLaMA/comments/1vfhns3/a_llamacpp_pr_caches_hot_moe_experts_on_the_gpu/) ⭐️ 8.0/10

llama.cpp 的新拉取请求（#26563）引入了一套专家热度图机制：把混合专家（MoE）模型中频繁被选中的专家缓存在显存里，而不常用的专家继续留在 CPU 上运行。作者报告称，在 8GB 显存下运行 Qwen3.6-35B-A3B 时，token 生成速度最高提升 2.07 倍（Q2_M：33.25→56.0 tok/s；Q5_K_P：17.34→35.93 tok/s）。 这项优化有望让更大的 MoE 模型在显存有限的消费级 GPU 上变得更为实用，降低对输出质量影响很大的极端低比特量化的依赖。它也为在无需专用硬件的前提下提升本地大模型推理效率指出了一个有前景的方向。 该加速并非普遍适用：Qwen3.5-122B-A10B 和 Laguna-S-2.1 在启用缓存后反而变慢，说明收益取决于专家复用模式。当前限制包括：仅支持 CUDA、仅在单 token 解码阶段生效、输出会因缓存了哪些专家而略有变化，并且这仍是一个未合并的开放 PR。

reddit · r/LocalLLaMA · /u/BTA_Labs · 8月4日 17:52

**背景**: 混合专家（MoE）是一种模型架构，每个 token 只激活一小部分专家模块，从而在计算成本不成比例增长的情况下扩大模型规模。llama.cpp 是广泛用于本地运行大模型的 C/C++ 推理引擎，当显存不足时通常会把部分层或专家卸载到 CPU 内存；Q2_M、Q5_K_P 等量化格式通过降低每个权重的比特数来减小模型体积和内存占用，但会牺牲一定质量。搜索结果中引用的 VRAM 专家缓存 gist 和 CPU offload 指南等社区工作，已经对类似的 MoE 专家缓存/卸载思路进行过探索，而 --expert-hot-s 这类 auto-fit 功能也是这一持续努力的一部分。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gist.github.com/dekoza/e6b4a69989b3d5bd0f904ce204f1646c">llama . cpp MoE VRAM expert cache (PR #24524 rebased to...)</a></li>
<li><a href="https://huggingface.co/blog/Doctor-Shotgun/llamacpp-moe-offload-guide">Performant local mixture-of- experts CPU inference with GPU...</a></li>

</ul>
</details>

**社区讨论**: 讨论中指出，负面结果可能比加速本身更有意思，说明这并非一个普遍适用的“让 MoE 更快”的开关。作者和原帖用户还希望社区成员在 RTX 3060、4060 等显卡上测试该分支，并对比编码、日常对话和长上下文等负载下的专家缓存命中率与 tok/s。

**标签**: `#llama.cpp`, `#MoE`, `#LLM inference`, `#VRAM optimization`, `#open source`

---

<a id="item-13"></a>
## [开发者开源 Web Clipper，并用它批量保存 Dan Koe 2026 年全部文章作为压力测试](https://x.com/zjp1997720/status/2084617997738754270) ⭐️ 8.0/10

开发者 @zjp1997720 将其自制的 Web Clipper 开源，并利用它把 Dan Koe 在 2026 年发布的全部文章剪藏到 Obsidian 库中，以此作为一次真实压力测试，要求“一篇不漏”。 这件事的意义在于，它展示了一个实用的开源方案，用于 AI 驱动的内容捕获——不再只是简单添加书签，而是通过 AI Skill 实现自动化批量剪藏。对于 Obsidian 和自动化爱好者来说，它示范了一种结合 AI Skill、网页抓取与本地知识管理的真实工作流。 开发者明确指出，这个项目的起点并非只是再做一款网页保存工具，而是将其构建为一个可复用的“Skill”，用 AI 智能体执行剪藏任务。压力测试目标是 Dan Koe 2026 年的全部文章，工具成功将它们全部剪入 Obsidian，没有遗漏。该项目现已开源，但推文中的仓库链接被截断。

twitter · zjp1997720 · 8月4日 12:30

**背景**: Obsidian Web Clipper 是一款免费、开源的浏览器扩展，可以让用户把网页内容直接保存到本地 Obsidian 库中，支持模板和高亮功能。AI Skill 在 Anthropic Claude 等智能体的语境下，是一种可复用的指令包，用于教会智能体处理某一类具体任务，让它能根据上下文做决策而非执行固定自动化流程。Dan Koe 是一位知名作家和内容创作者，其大量发文适合作为大规模剪藏测试的对象。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://obsidian.md/clipper">Obsidian Web Clipper</a></li>
<li><a href="https://obsidian.md/help/web-clipper">Introduction to Obsidian Web Clipper - Obsidian Help</a></li>
<li><a href="https://github.com/ComposioHQ/awesome-claude-skills">GitHub - ComposioHQ/awesome-claude- skills : A curated list of...</a></li>

</ul>
</details>

**标签**: `#web-clipper`, `#obsidian`, `#open-source`, `#AI-skill`

---

<a id="item-14"></a>
## [让 Codex 管理 Thread；新编排技能使用 Sol 和 Luna](https://x.com/zjp1997720/status/2084584278810394875) ⭐️ 8.0/10

作者分享了让 Codex 自己管理 Thread 这一默会但很有价值的做法，因为 Codex 比人更擅长创建、管理和归档 Thread。此外，他还设计了一个 Orchestrator 技能：主线程中使用 Sol 进行任务编排，并并行调用 Luna Max 或 X。 这很重要，因为它展示了一种成本高效的多智能体编排模式：用 Sol 这样强大的模型做规划，把执行任务委托给 Luna 这样更便宜的模型。AI 开发者可以借鉴这种做法，在不使 token 费用暴涨的情况下扩展智能体工作流。 这个 Orchestrator 技能在主线程中使用 Sol 进行编排，并并行调用 Luna Max 或 X 处理子任务。推文附有图片/链接（t.co/xRJkbAjXl9）提供更多细节，并提到 Luna 目前非常便宜。

twitter · zjp1997720 · 8月4日 10:16

**背景**: Codex 是 OpenAI 的 AI 编程代理，能够通过函数调用自主创建和管理 Thread（对话/任务）。OpenAI 的 GPT-5.6 系列包含 Sol（旗舰，最适合编排）、Terra（均衡）和 Luna（便宜、高效），于 2026 年 7 月 9 日发布。编排模式让一个强大的模型负责规划并把任务委托给更便宜的子代理，从而在保持质量的同时降低成本。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.mindstudio.ai/blog/gpt-5-6-sol-orchestrator-cheaper-sub-agent-models">How to Use GPT-5.6 Sol as an Orchestrator with Cheaper Sub-Agent Models | MindStudio</a></li>
<li><a href="https://kie.ai/blog/gpt-5-6-sol-terra-luna-deep-dive">GPT-5.6 Deep Dive: Sol, Terra, Luna Release</a></li>
<li><a href="https://explainx.ai/blog/openai-codex-computer-use-windows-mobile-control-2026">OpenAI Brings Full Computer Control to Codex on Windows | explainx. ai</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Codex`, `#orchestration`, `#LLM`, `#workflow`

---

<a id="item-15"></a>
## [Pleasantries：为 AI 编码 CLI 拦截寒暄式提示的预钩子脚本](https://github.com/QAInsights/pleasantries) ⭐️ 7.0/10

QAInsights 发布了 Pleasantries，这是一组用于 AI 编码 CLI 的预钩子脚本，能够过滤掉诸如“hi”“thank you”之类的纯寒暄提示，强制用户提交真正的编程任务。 该工具解决了 AI 辅助开发中一个常见的低效问题：随意的问候会浪费 token 并增加延迟。通过自动过滤这类提示，它简化了交互，并推动用户与 AI 编码助手进行更高效、更面向任务的沟通。 该项目托管在 GitHub 的 QAInsights 组织下，主要面向用于 AI 编码的命令行界面。预钩子脚本会在提示发送到 AI 模型之前进行拦截，并拒绝仅包含寒暄语句的消息。

rss · Show HN (self-made tools) · 8月4日 21:59

**背景**: 预钩子脚本是在主命令或操作之前运行的小程序，常用于验证或修改输入。AI 编码 CLI 是基于终端的工具，让开发者可以与大型语言模型交互以完成代码生成、解释等任务。在许多此类工具中，用户输入对话式提示，而“hi”“ok”之类的寒暄会触发不必要的 API 调用并造成延迟。

**标签**: `#AI coding`, `#CLI`, `#developer tools`, `#GitHub`, `#productivity`

---