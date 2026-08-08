---
layout: default
title: "Horizon Summary: 2026-08-08 (ZH)"
date: 2026-08-08
lang: zh
---

> 从 70 条内容中筛选出 11 条重要资讯。

---

1. [为消费级 Nvidia 显卡启用 PCIe P2P 可大幅提升 vLLM 推理性能](#item-1) ⭐️ 9.0/10
2. [零依赖 C 推理引擎在 Xeon 上以 36 tok/s 运行 BitNet](#item-2) ⭐️ 9.0/10
3. [xAI 发布 Imagine Image 2.0，图像生成排名第二](#item-3) ⭐️ 9.0/10
4. [agent-hop：逆向工程会话格式，可在任意代理中恢复聊天](#item-4) ⭐️ 8.0/10
5. [NVIDIA Parakeet 语音识别模型通过 WebGPU 在浏览器中运行](#item-5) ⭐️ 8.0/10
6. [macOS 版 Clippy：复古回形针助手，支持 AI 计算机操作](#item-6) ⭐️ 8.0/10
7. [用 llama.cpp 在两个集群本地跑起 2.8T 参数 Kimi K3](#item-7) ⭐️ 8.0/10
8. [Claude Code 推出跨会话消息，智能体可互相通信](#item-8) ⭐️ 8.0/10
9. [因人类仅识别出 13.6%危险命令，Claude Code 将默认启用自动模式](#item-9) ⭐️ 8.0/10
10. [七月华语推特硬核神贴榜 TOP 10](#item-10) ⭐️ 8.0/10
11. [Tesla V100 上运行 Qwen3.6 27B：llama.cpp 配置与性能分享](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [为消费级 Nvidia 显卡启用 PCIe P2P 可大幅提升 vLLM 推理性能](https://www.reddit.com/r/LocalLLaMA/comments/1vj7wey/enabling_pcie_p2p_for_consumer_nvidia_cards_will/) ⭐️ 9.0/10

一位 Reddit 用户演示了在四张消费级 Nvidia RTX 5060 Ti 16GB 显卡上为 vLLM 启用 PCIe 点对点（P2P）通信后，预填充吞吐量提升了约 25% 甚至更多，2048 token 预填充测试从约 1,649 t/s 提升到约 2,305 t/s。该方法需要打补丁的 open-gpu-kernel-modules 驱动、Resizable BAR 支持以及特定的 NCCL 环境变量。 这是一个具体且可操作的优化方案，适用于在本地运行多 GPU LLM 推理的开发者，表明尽管 NVIDIA 官方驱动常常禁用 P2P，消费级 GPU 仍能从中受益。它可以在不需要昂贵数据中心硬件的情况下提升服务性能并缩短首 token 延迟。 该测试环境为 4 张 RTX 5060 Ti 16GB 显卡，运行在 PCIe 4.0 x8 模式下，使用张量并行方式在 AMD EPYC 服务器上服务 Qwen3.6-27B-FP8 模型。要启用 P2P，用户需设置 NCCL_P2P_DISABLE=0、VLLM_SKIP_P2P_CHECK=1 和 NCCL_P2P_LEVEL=SYS，同时安装来自 github.com/aikitoria/open-gpu-kernel-modules 的打补丁驱动并在 BIOS 中启用 ReBAR。

reddit · r/LocalLLaMA · /u/BidonPomoev · 8月8日 21:42

**背景**: PCIe 点对点（P2P）允许 GPU 通过 PCIe 总线直接访问彼此的内存，绕过 CPU 和系统内存，这对张量并行中的多 GPU 通信至关重要。vLLM 是一个流行的高吞吐量 LLM 推理库，支持跨多 GPU 的张量并行，但 NVIDIA 官方消费级驱动为了划分产品线通常会禁用 P2P。社区对 open-gpu-kernel-modules 的补丁可以在消费级显卡上重新启用该功能，从而在多 GPU 推理中获得可观的性能提升。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://developer.nvidia.com/gpudirect">GPUDirect | NVIDIA Developer</a></li>
<li><a href="https://docs.vllm.ai/en/v0.8.0/serving/distributed_serving.html">Distributed Inference and Serving — vLLM</a></li>

</ul>
</details>

**标签**: `#PCI-E P2P`, `#multi-GPU`, `#vLLM`, `#LLM inference`, `#performance optimization`

---

<a id="item-2"></a>
## [零依赖 C 推理引擎在 Xeon 上以 36 tok/s 运行 BitNet](https://www.reddit.com/r/LocalLLaMA/comments/1vj1cin/building_a_zerodependency_c_inference_engine_for/) ⭐️ 9.0/10

一位开发者用纯 C99 从零构建了一个零依赖的 BitNet 推理引擎，在 Intel Xeon 上使用 4 线程运行 BitNet b1.58-2B-4T 时达到 36.25 tok/s，并采用了自研的 AVX2/AVX-512 VNNI 内核与 spin-then-yield 线程池。 这展示了量化三元 LLM 可以在普通 CPU 上高效运行，有望在无 GPU 环境下实现本地推理。其中把三元权重每字节打包 4 个、并利用 VNNI 整数累加等具体优化技巧，可直接被从事边缘或纯 CPU 部署的开发者复用。 BitNet 的权重以 {-1, 0, +1} 形式每字节打包 4 个，并通过 vpdpbusds VNNI 指令直接累加到整数寄存器中。该项目是一个独立的 C99 二进制文件，可直接提供与 OpenAI 兼容的 API 端点；作者指出，batch size 为 1 时解码速度受 DRAM 带宽限制，大约已达到理论内存带宽的 95%。

reddit · r/LocalLLaMA · /u/shifu_legend · 8月8日 17:09

**背景**: 1.58 位 LLM（又称三元 LLM）是从一开始就用三元权重原生训练出来的，而不是在训练后从全精度模型量化而来，因此每个权重只有 -1、0 或 +1，Transformer 中的矩阵乘法可以退化为加法、减法和跳过操作。BitNet b1.58-2B-4T 是一个约 20 亿参数、在 4 万亿 token 上训练的模型，以 MIT 许可证发布。AVX-512 VNNI 指令（如 vpdpbusds）能把字节组相乘并累加到 dword 寄存器中，从而让 x86 CPU 上的低精度推理变得很快。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/1.58-bit_large_language_model">1 . 58 - bit large language model - Wikipedia</a></li>
<li><a href="https://apidog.com/blog/microsoft-bitnet-2b/">BitNet b 1 . 58 : How 1 . 58 - Bit LLMs Could Change AI Efficiency</a></li>
<li><a href="https://iq.opengenus.org/avx512-vnni/">AVX512 VNNI : This instruction boosts ML performance by 2X</a></li>

</ul>
</details>

**标签**: `#BitNet`, `#C`, `#inference engine`, `#SIMD`, `#CPU optimization`

---

<a id="item-3"></a>
## [xAI 发布 Imagine Image 2.0，图像生成排名第二](http://grok.com/imagine) ⭐️ 9.0/10

xAI 已将 Imagine Image 2.0 作为 Quality Mode 在 grok.com/imagine 以及 iOS、Android 应用中发布。该版本带来了区域分割、透明背景导出、支持最多五张输入图片的多图参考编辑等高级功能。 此次发布让 xAI 成为图像生成与编辑领域的有力竞争者，其在 Arena 的文本生成图像和图像编辑两个榜单中均位列第二。尤其是多图参考和透明背景等功能，使其直接适用于创意专业人士，而计划中的 API 可能推动更广泛的采用。 该模型支持按比例生成和预置工作流模板，单次编辑可接受最多五张参考图片。它还包含用于局部编辑的区域分割、透明背景导出，以及针对版式和多轮编辑改进的文字渲染能力。

telegram · zaihuapd · 8月8日 05:40

**背景**: Arena 排行榜是一个由社区驱动的平台，用户将不同 AI 模型的输出并排比较，并通过投票进行排名。区域分割将图像划分为不同部分，从而可以仅对局部进行编辑，而透明背景导出则输出带 Alpha 通道的图像，便于后期合成。多图参考编辑利用多张输入图片引导模型生成目标构图，通常用于融合身份、风格或背景元素。xAI 此前专注于 Grok 对话模型，此次图像生成发布扩展了其多模态战略。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arena.ai/leaderboard/text-to-image">Text-to-Image Leaderboard - Best AI Image Generators - arena.ai</a></li>
<li><a href="https://en.wikipedia.org/wiki/Image_segmentation">Image segmentation - Wikipedia</a></li>
<li><a href="https://blog.pixai.art/en/pixai-reference-pro-guide-multi-image-editing-with-natural-language/">PixAI Reference Pro Guide— Multi-Image Editing with Natural ...</a></li>

</ul>
</details>

**标签**: `#AI`, `#image generation`, `#xAI`, `#text-to-image`, `#image editing`

---

<a id="item-4"></a>
## [agent-hop：逆向工程会话格式，可在任意代理中恢复聊天](https://github.com/hetpatel-11/agent-hop) ⭐️ 8.0/10

agent-hop 是一个新的开源工具，可搜索 Codex、Claude Code、Pi、OpenCode 和 Grok 等编码代理的聊天记录，并通过适配器在任何代理中恢复任意会话。该工具以 Show HN 形式发布到 Hacker News，目前获得 2 分和 1 条评论。 它解决了一个现实痛点：编码代理的会话被锁定在专有格式中，导致切换工具时很难保留上下文。通过实现跨代理的会话恢复，agent-hop 有望减少厂商锁定，帮助开发者规范其 AI 辅助工作流。 该项目通过逆向工程每种代理的会话格式并构建适配器来实现恢复。目前它仍处于早期阶段，社区验证有限，在分析时 Hacker News 上仅有一条评论。

rss · Show HN (self-made tools) · 8月8日 19:10

**背景**: Codex、Claude Code、Pi、OpenCode、Grok 等编码代理各自以不同且往往专有的会话格式保存聊天历史。由于每个代理使用自己的存储布局，在一个工具中开始的会话无法直接在另一个工具中恢复。会话管理指南指出，各代理的上下文窗口大小和 token 预算差异很大，这使得跨工具移植成为一个不简单的工程问题。agent-hop 通过逆向工程每种格式并引入适配器在代理之间转换会话，来应对这一挑战。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://agent-sessions.vineethnk.in/session-format">Session Format | agent - sessions</a></li>
<li><a href="https://kissapi.ai/blog/ai-coding-agent-session-management-2026.html">AI Coding Agent Session Management Guide (2026)</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#coding agents`, `#developer tools`, `#workflow`, `#open source`

---

<a id="item-5"></a>
## [NVIDIA Parakeet 语音识别模型通过 WebGPU 在浏览器中运行](https://parakeet.narcotic.sh/) ⭐️ 8.0/10

一个新的 WebGPU 演示在浏览器中完全运行 NVIDIA 的 parakeet-tdt-0.6b-v2 语音识别模型，网址为 parakeet.narcotic.sh。用户无需任何服务器端推理或云端依赖即可试用这个 6 亿参数的 ASR 模型。 该演示表明，一个现代化的 6 亿参数语音识别模型可以在浏览器客户端运行，从而实现私密、低延迟的转写，无需将音频上传到云端。它凸显了设备端 AI 的日益增长趋势，以及 WebGPU 用于机器学习推理的实际可行性。 parakeet-tdt-0.6b-v2 是 NVIDIA 的英语自动语音识别模型，支持标点、大小写和时间戳预测。此处使用的 WebGPU API 通过 Vulkan、Metal 或 Direct3D 12 在浏览器中提供跨平台 GPU 访问；自 2023 年 4 月起 Chrome 和 Edge 支持，Safari 26 和 Firefox 141 最近也加入了支持。

rss · Show HN (self-made tools) · 8月8日 18:58

**背景**: 自动语音识别（ASR）模型传统上因计算需求而在强大的服务器上运行。WebGPU 是一个 W3C 标准，允许 Web 应用访问 GPU 进行高性能计算，包括 AI 和机器学习任务，无需插件。NVIDIA 的 Parakeet 系列由在大规模数据集上训练的 ASR 模型组成，以相对紧凑的规模提供高质量转写，其中 0.6B 变体是一个 6 亿参数的模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/nvidia/parakeet-tdt-0.6b-v2">nvidia/ parakeet - tdt - 0 . 6 b - v 2 · Hugging Face</a></li>
<li><a href="https://build.nvidia.com/nvidia/parakeet-tdt-0_6b-v2/modelcard">parakeet - tdt - 0 . 6 b - v 2 Model by NVIDIA | NVIDIA NIM</a></li>
<li><a href="https://en.wikipedia.org/wiki/WebGPU">WebGPU</a></li>

</ul>
</details>

**标签**: `#speech-recognition`, `#webgpu`, `#ai-tools`, `#browser-ai`, `#parakeet`

---

<a id="item-6"></a>
## [macOS 版 Clippy：复古回形针助手，支持 AI 计算机操作](https://github.com/Ar9av/clippy) ⭐️ 8.0/10

一位开发者发布了 macOS 版 Clippy，这是共享在 Hacker News 上的开源项目，将怀旧的 Clippy 回形针作为浮动助手带回桌面。该项目集成了 AI 驱动的计算机操作能力，使助手可以通过图形界面操作电脑。 该项目展示了如何将复古界面与现代 AI 智能体技术结合，让普通 macOS 用户也能以有趣的方式体验“计算机操作”功能。它也反映了开源 AI 智能体控制操作系统的日益增长趋势，这一领域由 OpenAI 的 Computer-Using Agent 等模型引领。 该项目托管在 github.com/Ar9av/clippy，Hacker News 帖子里没有提供详细的说明文档。这类计算机操作智能体通常依赖视觉语言模型，通过截图并输出界面操作指令（如点击和按键）来完成任务。

rss · Show HN (self-made tools) · 8月8日 17:39

**背景**: 计算机操作智能体（CUA）是一种 AI 系统，它能像人类一样与图形界面交互——通过查看屏幕、决定点击或输入什么，然后执行操作。例如，OpenAI 的 Operator 就使用了结合 GPT-4o 视觉能力与强化学习的 CUA。Clippy 是上世纪 90 年代微软 Office 的助手角色，因其怀旧感和幽默感而被许多用户记住，因此很适合作为 AI 智能体的吉祥物。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/computer-using-agent/">Computer-Using Agent | OpenAI</a></li>
<li><a href="https://grokipedia.com/page/OS_AI_Computer_Use">OS AI Computer Use</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#macOS`, `#computer use`, `#GitHub`, `#assistant`

---

<a id="item-7"></a>
## [用 llama.cpp 在两个集群本地跑起 2.8T 参数 Kimi K3](https://www.reddit.com/r/LocalLLaMA/comments/1vj0hil/my_first_run_of_kimi_k3_locally/) ⭐️ 8.0/10

一位 Reddit 用户分享了自己首次通过 llama.cpp 的 RPC 分布式推理，在两个集群上本地运行 Kimi K3（2.8 万亿参数）的实践经历。目前模型以 IQ1_M 量化级别运行，作者计划后续升级到 Q2_K_XL。 这表明即使参数规模达到 3 万亿级别的开源模型，也能通过激进量化和分布式推理在预算有限的本地硬件上运行，拓宽了本地部署 LLM 的可能性。同时这也展示了一种务实策略：用大模型负责规划，而把具体编码子任务交给更小、更快的模型。 作者指出，两个集群加起来的内存仍无法完整容纳模型，因此主集群仍需部分卸载；如果能把所有 GPU 装进一台机器并去掉 RPC，预计速度可提升 2-3 倍。作者计划将繁重的编码任务交给 DeepSeekV4Flash 和 Qwen3.7-27B 等较小模型。

reddit · r/LocalLLaMA · /u/segmond · 8月8日 16:34

**背景**: Kimi K3 是 Moonshot AI 于 2026 年 7 月发布的旗舰模型，拥有 2.8 万亿参数，基于 Kimi Delta Attention 和 Attention Residuals 构建，支持原生视觉和 100 万 token 上下文窗口，是首个开源权重达到 3T 参数级别的模型。llama.cpp 是一款用 C/C++编写的高性能推理引擎，支持 GGUF 格式模型；量化通过降低权重精度来减小模型体积，其中 IQ1_M 等 i-quant 量化属于极低位宽。为了让超出单机显存的模型能运行，llama.cpp 支持通过 RPC 进行分布式推理，即在多台机器上分别运行 rpc-server 实例。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.kimi.com/blog/kimi-k3">Kimi K3 Tech Blog: Open Frontier Intelligence</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp/discussions/9142">Distributed inference on Hugging Face Spaces · ggml-org llama . cpp ...</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp/blob/master/tools/quantize/README.md">llama.cpp/tools/quantize/README.md at master · ggml-org/llama.cpp</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#llama.cpp`, `#quantization`, `#distributed-inference`, `#kimi-k3`

---

<a id="item-8"></a>
## [Claude Code 推出跨会话消息，智能体可互相通信](https://code.claude.com/docs/en/cross-session-messaging) ⭐️ 8.0/10

Claude Code v2.1.224 起新增跨会话消息功能，不同会话中的智能体可通过 ListAgents 发现彼此，并用 SendMessage 发送纯文本消息。该功能在 macOS 和 Linux 上默认启用，无需额外配置。 该功能消除了在不同会话间手动重复上下文的必要，支持并行工作协调、长任务进度汇报以及跨设备回复。这标志着 AI 智能体工作流向更高互通性迈出了务实的一步。 跨会话消息仅支持纯文本，接收方消息不会绕过权限提示，也无法修改配置或执行命令。该功能要求 v2.1.224 及以上版本，不支持原生 Windows，在 Amazon Bedrock、Google Cloud Agent Platform 等平台不可用；入站消息行为可通过 crossSessionInbound 参数配置为 accept、hold 或 refuse。

telegram · zaihuapd · 8月8日 02:12

**背景**: Claude Code 是 Anthropic 推出的智能体编程工具，运行在命令行中，能够理解代码库、编辑文件并执行命令。此前，每个会话相互隔离，用户需要在不同会话中重复表述上下文。新增的 ListAgents 和 SendMessage 工具扩展了 Claude 的智能体能力，使会话之间可以传递信息，消息的放行或拦截默认根据双方权限模式自动决定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://code.claude.com/docs/en/cross-session-messaging">Message your other Claude Code sessions - Claude Code Docs</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#AI Agent`, `#AI Tools`, `#Workflow`, `#Developer Tools`

---

<a id="item-9"></a>
## [因人类仅识别出 13.6%危险命令，Claude Code 将默认启用自动模式](https://claude.com/blog/auto-mode-default-in-claude-code) ⭐️ 8.0/10

自 8 月 14 日起，Claude Code 将在 Pro、Max 和 Team 计划的新会话中默认启用自动模式，自动拦截危险命令。此前研究显示，自动模式拦截了 89%的危险命令，而人类测试者仅识别出 13.6%。 这一更新大幅降低了 AI 编程代理在用户未监督时执行不可逆或破坏性操作的风险。它也让这一关键安全功能对多数付费用户无需额外操作即可生效，可能为 AI 代理的权限管理树立新的行业标准。 Enterprise、Claude API 及多种云平台用户暂时仍需手动启用自动模式，官方计划在未来一个月内逐步改为默认。分类器检查带来的额外开销自即日起不再向 Pro、Max 和 Team 用户收费。

telegram · zaihuapd · 8月8日 03:02

**背景**: Claude Code 是 Anthropic 推出的 AI 编程代理工具，能够理解代码库、编辑文件并运行命令。自动模式于 2026 年 3 月推出，通过分类器检查每次工具调用，拦截不可逆、破坏性或超出用户环境之外的操作，从而在无需频繁权限提示的情况下支持更长时间的自主工作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/blog/auto-mode">Auto mode for Claude Code | Claude by Anthropic</a></li>
<li><a href="https://claude.com/blog/auto-mode-default-in-claude-code">Auto mode is now the default in Claude Code for Pro, Max, and ...</a></li>
<li><a href="https://code.claude.com/docs/en/auto-mode-config">Configure auto mode - Claude Code Docs</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#AI agents`, `#AI safety`, `#coding tools`

---

<a id="item-10"></a>
## [七月华语推特硬核神贴榜 TOP 10](https://x.com/zjp1997720/status/2086065605346758929) ⭐️ 8.0/10

一份精选榜单整理了七月华语推特上最值得收藏的 10 篇硬核长文，主题集中于 Multi-Agent 协作、数字人、自动化视频和企业知识库等 AI 话题，也涵盖出入金、交易系统等实操内容。榜单采用数据分加链接权重的评分方法。 对中文技术社区和 AI 从业者而言，这份榜单能帮助快速发现实用工具和方法，减少信息噪音，并反映出多智能体、自动化等正在影响 AI 生态的热门趋势。 帖子中的评分公式为“数据分×70% + 链接”，但完整方法因链接截断而无法查看。入选内容兼有 AI 前沿话题和实操性金融/交易经验，说明“硬核”定义较为广泛。

twitter · zjp1997720 · 8月8日 12:22

**背景**: 多智能体系统（MAS）是当前 AI 的重要趋势：它由多个 AI 智能体协同工作以完成复杂任务，使 AI 从独立模型转向协作式、可扩展的解决问题方式。数字人、自动化视频和企业知识库也是中文开发者社区中流行的生成式 AI 应用。FDE 是一个有多种技术含义的缩写，在职业转型帖中的具体所指并不明确。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibm.com/think/topics/multiagent-system">What is a Multi - Agent System? | IBM</a></li>
<li><a href="https://arxiv.org/abs/2501.06322">Multi - Agent Collaboration Mechanisms: A Survey of LLMs</a></li>
<li><a href="https://www.acronymfinder.com/Information-Technology/FDE.html">FDE - Information Technology</a></li>

</ul>
</details>

**标签**: `#AI`, `#curation`, `#multi-agent`, `#automation`, `#knowledge-base`

---

<a id="item-11"></a>
## [Tesla V100 上运行 Qwen3.6 27B：llama.cpp 配置与性能分享](https://www.reddit.com/r/LocalLLaMA/comments/1vixl0f/tesla_v100_qwen36_27b_performance/) ⭐️ 7.0/10

一位 Reddit 用户分享了在 Tesla V100 32GB 上运行 Qwen3.6 27B（Q4_K_M 量化）的详细 llama.cpp 配置，包括 Q8_0 MTP 草稿模型和多模态投影器，并附上了实测性能截图。 这为在 V100 等仍广泛存在且价格低廉的老款数据中心 GPU 上自托管现代 27B 多模态 LLM 提供了一个具体且可复现的方案。它也表明，借助 MTP 推测解码等 llama.cpp 特性，这类模型无需 RTX 4090 或 A100 也能实际可用。 该配置使用 128K 上下文、FlashAttention 和完全 GPU 卸载（n-gpu-layers=999），并将 Q8_0 MTP 模型作为推测解码草稿，同时使用独立的 mmproj 文件处理视觉输入。用户还启用了自定义聊天模板中的 preserve_thinking，并以图片形式发布了性能结果，但文本中没有给出具体的 token/s 数字。

reddit · r/LocalLLaMA · /u/Traditional_Bell8153 · 8月8日 14:34

**背景**: Qwen3.6 27B 是一个大型多模态语言模型，可通过 llama.cpp 以 GGUF 格式本地运行，通常会量化以降低内存占用，其中 Q4_K_M 是常见的 4-bit 量化格式。多 token 预测（MTP）使用一个小型草稿模型一次预测多个 token，再由 llama.cpp 用主模型进行验证，从而加速生成。mmproj 文件（多模态投影器）负责连接视觉编码器与语言模型，使 GGUF 模型能够接受图像输入。Tesla V100 是较老的 Volta 架构数据中心 GPU，拥有 16GB 或 32GB HBM2 显存，因大显存和低二手价格而仍受预算型自托管用户青睐。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/ggml-org/llama.cpp/blob/master/docs/speculative.md">llama.cpp/docs/speculative.md at master · ggml-org/llama.cpp</a></li>
<li><a href="https://arxiv.org/abs/2502.09419">[2502.09419] On multi - token prediction for efficient LLM inference</a></li>
<li><a href="https://github.com/ggml-org/llama.cpp/blob/master/docs/multimodal.md">llama.cpp/docs/ multimodal .md at master · ggml-org/llama.cpp · GitHub</a></li>

</ul>
</details>

**标签**: `#Local LLM`, `#Qwen`, `#V100`, `#llama.cpp`, `#Inference`

---