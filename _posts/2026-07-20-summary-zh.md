---
layout: default
title: "Horizon Summary: 2026-07-20 (ZH)"
date: 2026-07-20
lang: zh
---

> 从 64 条内容中筛选出 14 条重要资讯。

---

1. [Kimi Work：本地 AI 代理，廉价替代 Claude/Codex](#item-1) ⭐️ 9.0/10
2. [Cognikernel：AI 编程助手的本地记忆工具](#item-2) ⭐️ 9.0/10
3. [Unsloth 正式支持 AMD GPU 用于本地大语言模型工作](#item-3) ⭐️ 9.0/10
4. [NInfer 在 RTX 5090 上以 65K 令牌解码实现 Qwen3.6-35B-A3B 每秒 543 令牌](#item-4) ⭐️ 9.0/10
5. [Nativ：在 Mac 上本地运行前沿开放模型](#item-5) ⭐️ 8.0/10
6. [Codex Micro 手机版：AI 编程走向移动端](#item-6) ⭐️ 8.0/10
7. [Memento：开源共享智能体记忆](#item-7) ⭐️ 8.0/10
8. [Provena：用于 AI 代理上下文治理的开源库](#item-8) ⭐️ 8.0/10
9. [NVIDIA 发布 Cosmos 3 Edge 世界模型](#item-9) ⭐️ 8.0/10
10. [超低位宽 Bonsai-27B 模型在 8GB VRAM 上测试终端基准](#item-10) ⭐️ 8.0/10
11. [OpenBMB 发布 MiniCPM5-2B，称霸 4B 以下参数模型](#item-11) ⭐️ 8.0/10
12. [编码代理让逆向工程变得廉价且低维护](#item-12) ⭐️ 7.0/10
13. [Velprium：用 AI 代理快速搭建的时间工作空间应用](#item-13) ⭐️ 7.0/10
14. [1300 万参数 ASR Conformer 模型在 10 美元微控制器上运行](#item-14) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Kimi Work：本地 AI 代理，廉价替代 Claude/Codex](https://www.kimi.com/products/kimi-work) ⭐️ 9.0/10

它为开发者和高级用户提供了一个价格实惠、功能丰富的本地代理，可能使通常昂贵的云服务才能提供的先进 AI 代理能力更加普及。 Kimi Work 完全在本地运行，挂载本地文件夹以直接访问文件，使用 WebBridge 实现自主网页导航，并能执行 Python 脚本和定时任务。它被指出是 Anthropic Codex 的紧密模仿品。

hackernews · ms7892 · 7月20日 17:13 · [社区讨论](https://news.ycombinator.com/item?id=48981703)

**背景**: 本地 AI 代理是指运行在用户自己机器上的软件工具，利用本地计算资源（CPU/GPU）执行代码生成、文件操作和网页自动化等任务，无需将数据发送到云端。Anthropic 的 Claude Codex 是一款流行的代理式编码工具，能理解代码库并运行命令。Kimi Work 旨在以更低成本复制这些功能，但存在数据隐私和抄袭方面的担忧。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://grokipedia.com/page/Gemini_CLI_Codex_CLI_and_Claude_Code">Gemini CLI, Codex CLI, and Claude Code</a></li>

</ul>
</details>

**社区讨论**: 社区反应不一：许多人认为这是对 Claude/Codex 的无耻复制，但赞赏其仅五分之一的价格。一些海外用户提出数据主权担忧，而另一些人则指出复制先行者产品很容易。

**标签**: `#AI Agent`, `#本地工具`, `#任务自动化`, `#价格实惠`, `#复制品`

---

<a id="item-2"></a>
## [Cognikernel：AI 编程助手的本地记忆工具](https://github.com/KanishkNoir/cognikernel) ⭐️ 9.0/10

Cognikernel 是一款新的开源工具，可在 AI 编程会话中自动捕获架构决策和项目上下文，并本地存储，从而消除对 CLAUDE.md 等手动记忆文件的需求。 这解决了开发者使用 AI 编程助手时的一个主要痛点：跨会话的上下文丢失。通过自动保留记忆，它可减少 30% 的 token 使用量和 4 倍的读取工具调用，使编码工作流更高效、更一致。 Cognikernel 是代理无关的，可与 Claude Code 和 Codex 配合使用，数据本地存储，不依赖云端。它自动捕获决策、约束、约定和文件关系，且记忆会随时间改进。

rss · Show HN (self-made tools) · 7月20日 20:20

**背景**: 像 Claude Code 和 Codex 这样的 AI 编程助手通过生成代码来帮助开发者，但它们缺乏跨会话的持久记忆，常常忘记之前做出的架构决策。为此，开发者手动维护像 CLAUDE.md 这样的 markdown 记忆文件，这既繁琐又容易出错。Cognikernel 通过观察编码会话并自动存储相关上下文来解决这个问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://modernorange.io/item/48984355">Show HN: Cognikernel - Local Memory for AI Coding... | Modern Orange</a></li>
<li><a href="https://claude.com/blog/using-claude-md-files">Using CLAUDE.MD files: Customizing Claude Code for your ...</a></li>

</ul>
</details>

**标签**: `#AI coding assistants`, `#local memory`, `#developer tools`, `#GitHub`

---

<a id="item-3"></a>
## [Unsloth 正式支持 AMD GPU 用于本地大语言模型工作](https://www.reddit.com/r/LocalLLaMA/comments/1v1nor4/unsloth_now_supports_amd/) ⭐️ 9.0/10

Unsloth 已正式添加对 AMD GPU 的支持，可在 AMD 硬件上进行本地推理、微调和强化学习，显存使用量最多减少 80%。该支持涵盖 Radeon RX 9000/7000 系列、Instinct MI350/MI300 和 Strix Halo 系统，可通过简单的安装脚本或 pip 获得。 这为之前缺乏优化支持的 AMD GPU 用户提供了高效的大语言模型训练和部署途径。显存消耗大幅降低，使得在消费级 AMD 硬件上微调大型模型成为可能。 优化构建包括 ROCm、Triton、bitsandbytes、PyTorch 和 llama.cpp，全部自动安装。支持的模型包括 Qwen、Gemma、DeepSeek、GLM、Kimi、MiniMax 和 DiffusionGemma，用户可以将模型导出为 GGUF、safetensors 或 LoRA 适配器。

reddit · r/LocalLLaMA · /u/danielhanchen · 7月20日 14:48

**背景**: Unsloth 是一个开源 Python 库，通过自定义内核加速大语言模型的微调和强化学习。AMD GPU 依赖 ROCm 软件栈进行通用计算，bitsandbytes 提供量化以降低内存占用。此次集成将这些技术结合起来，在 AMD 硬件上提供优化性能。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grokipedia.com/page/Unsloth">Unsloth</a></li>
<li><a href="https://en.wikipedia.org/wiki/ROCm">ROCm</a></li>
<li><a href="https://github.com/ROCm/rocm">GitHub - ROCm/ROCm: AMD ROCm™ Software - GitHub Home</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#fine-tuning`, `#AMD`, `#Unsloth`, `#open source`

---

<a id="item-4"></a>
## [NInfer 在 RTX 5090 上以 65K 令牌解码实现 Qwen3.6-35B-A3B 每秒 543 令牌](https://www.reddit.com/r/LocalLLaMA/comments/1v1no8e/543_toks_singlerequest_qwen3635ba3b_on_one_rtx/) ⭐️ 9.0/10

开源 C++/CUDA 推理引擎 NInfer 在单张 RTX 5090 上为 Qwen3.6-35B-A3B 模型生成了完整的 65,536 个令牌，持续速度达到 542.8 tok/s，多令牌预测（MTP）接受率为 73.0%。 这一结果表明，针对特定模型高度优化的推理引擎可以显著超越通用框架，为长推理、代码生成和结构化输出等任务实现实时本地 LLM 部署。 NInfer 使用自定义量化（约 5 bpw）、内核融合和优化的 LM 头草稿路径，支持文本、图像和视频输入，并提供兼容 OpenAI/Anthropic 的 HTTP 端点。该引擎目前仅支持 RTX 5090 和两个 Qwen3.6 检查点，原生上下文长度为 262K。

reddit · r/LocalLLaMA · /u/FormOne2615 · 7月20日 14:48

**背景**: 推理引擎将训练好的 AI 模型转化为可用的预测；NInfer 是从零开始实现的，专门针对特定模型最大化吞吐量。Qwen3.6-35B-A3B 是一个多模态混合思考模型，总参数量为 35B，但通过混合专家（MoE）仅激活 3B 参数，从而实现高效的本地部署。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Neroued/ninfer">GitHub - Neroued/ninfer: High-performance single-GPU ...</a></li>
<li><a href="https://huggingface.co/Qwen/Qwen3.6-35B-A3B">Qwen/ Qwen 3 . 6 - 35 B - A 3 B · Hugging Face</a></li>

</ul>
</details>

**标签**: `#inference engine`, `#local LLM`, `#Qwen`, `#CUDA`, `#optimization`

---

<a id="item-5"></a>
## [Nativ：在 Mac 上本地运行前沿开放模型](https://blaizzy.github.io/nativ/) ⭐️ 8.0/10

Nativ 是一款由 MLX-VLM 的创建者 Prince Canuma 构建的全新 macOS 应用，允许用户在 Apple Silicon Mac 上本地运行前沿开源 AI 模型。 该应用使高级开放模型无需依赖云端即可在 Mac 上轻松使用，利用 MLX 在 Apple 硬件上实现优化性能，并扩展了本地 AI 生态系统。 Nativ 采用 MIT 许可证，基于 MLX-VLM 构建，后者在 Apple 设备上提供比 llama.cpp 更快的推理速度，并能快速更新支持新的多模态模型。

hackernews · aratahikaru5 · 7月20日 18:16 · [社区讨论](https://news.ycombinator.com/item?id=48982681)

**背景**: MLX 是 Apple 推出的开源数组框架，用于在 Apple Silicon 上进行机器学习，提供类似 NumPy 的 API。MLX-VLM 将 MLX 扩展到视觉语言模型，支持推理和微调。Nativ 将其打包成一个易于使用的 macOS 应用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Blaizzy/mlx-vlm">GitHub - Blaizzy/mlx-vlm: MLX-VLM is a package for inference and fine-tuning of Vision Language Models (VLMs) on your Mac using MLX. · GitHub</a></li>
<li><a href="https://mlx-framework.org/">MLX</a></li>
<li><a href="https://github.com/ml-explore/mlx">GitHub - ml-explore/mlx: MLX: An array framework for Apple ...</a></li>

</ul>
</details>

**社区讨论**: 社区对该应用来自 MLX-VLM 维护者表示积极，但一些用户质疑“前沿”标签，因为真正的前沿模型需要庞大的硬件。还有用户指出 LM Studio 等现有工具已提供类似功能，并且存在关于 MLX 与 llama.cpp 性能的争论，部分用户报告 llama.cpp 更稳定。

**标签**: `#macOS`, `#local AI`, `#MLX`, `#open models`, `#tool`

---

<a id="item-6"></a>
## [Codex Micro 手机版：AI 编程走向移动端](https://github.com/maxxspotter/codex-micro-app) ⭐️ 8.0/10

开发者发布了名为 'codex-micro-app' 的 GitHub 仓库，首次将 OpenAI 的 AI 编程助手 Codex Micro 带到移动设备上。这是对原本设计为硬件可编程键盘的工具的第三方改编。 该项目将 AI 辅助编程功能普及到智能手机，惠及没有桌面环境或偏好移动端工作流的开发者。同时，它展示了社区将硬件专属 AI 工具改造为软件的创新能力。 该仓库似乎是一个 React Native 或基于 Web 的应用，通过 OpenAI Codex API 进行交互，但具体实现细节未完全公开。注意 'Codex Micro' 最初由 OpenAI 和 Work Louder 宣布为实体硬件设备，因此此手机版是非官方改编。

rss · Show HN (self-made tools) · 7月20日 20:53

**背景**: Codex Micro 是 OpenAI 与硬件公司 Work Louder 合作推出的 AI 编程助手，设计为紧凑型可编程键盘以加速编码任务。该硬件于 2025 年 4 月预告但尚未发布。此 GitHub 项目提供纯软件替代方案，将 Codex API 用于移动设备，可能填补官方移动支持到来前的空白。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbctv18.com/technology/codex-micro-openai-first-hardware-reveal-accessory-ai-powered-coding-assistant-19935348.htm">What is Codex Micro? Here is all you need to know about OpenAI's first ever hardware - CNBC TV18</a></li>
<li><a href="https://www.timesofai.com/news/openai-codex-micro-features-use-case-details/">OpenAI Codex Micro Explained: Features, Uses and More</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#GitHub`, `#mobile development`, `#coding assistant`

---

<a id="item-7"></a>
## [Memento：开源共享智能体记忆](https://rcarmo.github.io/projects/memento/) ⭐️ 8.0/10

Memento 是一个开源项目，提供共享智能体记忆，允许多个 AI 智能体协同池化和检索上下文。 共享智能体记忆对于构建能够维持长期上下文和协调的多智能体系统至关重要，而 Memento 提供了一个实用的本地优先实现。 Memento 被描述为本地优先的 MCP 中间件，具有时间图记忆、主动强制和目标对齐功能，并作为 PyPI 包 (memento-mcp) 提供。

rss · Show HN (self-made tools) · 7月20日 20:50

**背景**: 智能体记忆使 AI 智能体能够跨交互存储和回忆信息，类似于人类记忆。共享智能体记忆将这一概念扩展到多个智能体，允许它们访问共同的上下文，这对于协作任务和长时间运行的智能体工作流至关重要。像 A-MEM 和 Databricks 的 agent memory 等项目也探索了类似的想法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://pypi.org/project/memento-mcp/1.2.0/">memento -mcp · PyPI</a></li>
<li><a href="https://arxiv.org/abs/2502.12110">[2502.12110] A-MEM: Agentic Memory for LLM Agents - arXiv.org [2607.09493] Shared Selective Persistent Memory for Agentic ... Why shared memory is agentic AI’s biggest consumer moment Agent memory - Databricks on AWS Building Multi-Agent Systems with Shared Memory Guide</a></li>
<li><a href="https://github.com/agiresearch/A-mem">GitHub - agiresearch/A-mem: A-MEM: Agentic Memory for LLM ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#memory`, `#open source`, `#agent frameworks`

---

<a id="item-8"></a>
## [Provena：用于 AI 代理上下文治理的开源库](https://github.com/rajfirke/provena) ⭐️ 8.0/10

Provena 是一个新的开源库，用于治理 AI 代理的上下文输入层，填补了检索结果、工具输出等进入上下文窗口的数据此前不受治理的空白。 这填补了 AI 代理治理的关键空白，因为现有工具关注行为、输出或通信，却忽略了可能引入偏见或不安全数据的输入上下文，从而实现更安全、更可靠的代理部署。 该库在 GitHub 上开源，现有 7 位贡献者、11 个“良好的第一个问题”标签和 17 个“寻求帮助”的问题，便于社区贡献。它专门治理流入上下文窗口的数据，包括检索结果、工具输出和代理消息。

rss · Show HN (self-made tools) · 7月20日 20:31

**背景**: AI 代理通常使用上下文窗口处理来自不同来源的数据，但现有的治理工具如 Microsoft AGT、Guardrails AI 和 NVIDIA NeMo 只治理代理的行为、输出或通信协议。它们都没有治理输入上下文数据本身，而这些数据可能包含不可信或未经验证的信息，影响代理的行为。Provena 专门解决这一层，确保只有安全且经过审查的数据进入代理的推理过程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/microsoft/agent-governance-toolkit">GitHub - microsoft/agent-governance-toolkit: AI Agent ...</a></li>
<li><a href="https://guardrailsai.com/">Guardrails AI</a></li>
<li><a href="https://developer.nvidia.com/topics/ai/nemotron">Nemotron AI Models | NVIDIA Developer</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#open-source`, `#context governance`, `#agent framework`, `#LLM`

---

<a id="item-9"></a>
## [NVIDIA 发布 Cosmos 3 Edge 世界模型](https://huggingface.co/blog/nvidia/cosmos3edge) ⭐️ 8.0/10

NVIDIA 发布了 Cosmos 3 Edge，这是一个为边缘设备优化的开放世界基础模型，通过共享多模态注意力将自回归和扩散 transformer 塔结合在一起。 这为边缘设备带来了强大的世界模型能力，使得在设备上直接实现实时、物理基础的视觉分析和机器人动作成为可能，对机器人和自主系统意义重大。 该模型的混合 transformer 架构使其能够理解和生成文本、图像、视频、环境声音和动作，并且与 NVIDIA 新发布的 Jetson T2000 和 T3000 模块兼容。

rss · Hugging Face Blog · 7月20日 15:58

**背景**: 世界基础模型是模拟物理世界以预测和规划动作的 AI 模型。边缘设备是本地硬件，计算资源有限，常用于机器人领域。NVIDIA 的 Jetson 系列为这类应用提供嵌入式 AI 主板。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://unrollnow.com/status/2079236204743053592">Thread By @NVIDIAAI - Introducing Cosmos 3 Edge : our open...</a></li>
<li><a href="https://blogs.nvidia.com/blog/siggraph-news-2026/">At SIGGRAPH, NVIDIA Advances Graphics and... | NVIDIA Blog</a></li>
<li><a href="https://spoonai.me/posts/2026-07-19-nvidia-cosmos3-edge-robot-world-model-jul2026-en">Nvidia put a world model inside the robot itself — Cosmos 3 Edge ...</a></li>

</ul>
</details>

**标签**: `#AI`, `#edge computing`, `#NVIDIA`, `#model release`

---

<a id="item-10"></a>
## [超低位宽 Bonsai-27B 模型在 8GB VRAM 上测试终端基准](https://www.reddit.com/r/LocalLLaMA/comments/1v1ya97/i_ran_ternarybonsai27b_2bit_and_bonsai27b_1bit_on/) ⭐️ 8.0/10

一位用户在 8GB RTX 5070 笔记本 GPU 上对 Ternary-Bonsai-27B（2-bit）和 Bonsai-27B（1-bit）进行了 Terminal-Bench 2.0 基准测试，发现 2-bit 变体准确率为 7.9%，低于 Qwen3.5-9B 的 9.2%，但解析错误为零。1-bit 模型无法生成有效结果，并且由于无法终止而不适合智能体任务。 该基准测试为消费级 GPU 上本地部署 LLM 的超低位宽量化权衡提供了实用见解，表明三元 2-bit 可将大模型装入 8GB VRAM，但性能可能不如标准量化下较小的密集模型，从而质疑了在智能体工作负载下的效率提升。 测试使用了 little-coder 框架和 harbor 适配器，运行 Terminal-Bench 2.0 全部 89 个任务，单次尝试（k=1），40 轮上限，温度 0.2。2-bit 模型需要 PrismML 的自定义 llama.cpp 分支；原版 llama.cpp 无法加载其内核。1-bit 模型在第一个任务中生成了超过 14,000 个 token 的完成结果，没有停止标记，耗尽了 32k 上下文。

reddit · r/LocalLLaMA · /u/Creative-Regular6799 · 7月20日 21:15

**背景**: Bonsai 27B 是基于 Qwen3.6 27B 的多模态模型，其权重被端到端量化到 1-bit 或三元（2-bit），从而可以在 VRAM 有限的设备（如笔记本电脑和手机）上运行。Terminal-Bench 2.0 是一个包含 89 个命令行界面任务的基准测试，旨在测试 LLM 在真实工作流程中的智能体能力。PrismML 提供了自定义的 llama.cpp 分支以支持加载这些超低位宽模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.prismml.com/models/bonsai-27b">Bonsai 27B - Bonsai - docs.prismml.com</a></li>
<li><a href="https://www.tbench.ai/">Terminal-Bench</a></li>
<li><a href="https://github.com/PrismML-Eng/llama.cpp">GitHub - PrismML-Eng/llama.cpp: LLM inference in C/C++ · GitHub</a></li>

</ul>
</details>

**标签**: `#LLM benchmark`, `#quantization`, `#local models`, `#VRAM efficiency`, `#terminal bench`

---

<a id="item-11"></a>
## [OpenBMB 发布 MiniCPM5-2B，称霸 4B 以下参数模型](https://www.reddit.com/r/LocalLLaMA/comments/1v1m264/openbmb_released_minicpm52b_not_yet_available_at/) ⭐️ 8.0/10

OpenBMB 发布了 MiniCPM5-2B，这是一个 20 亿参数的语言模型，声称在 Artificial Analysis Intelligence Index 上领先所有 40 亿参数以下的模型。 这款紧凑型模型能够支持强大的设备端 AI 应用，尤其适用于智能手机和边缘设备，同时挑战了微软 Phi-3 等其他高效模型。其强劲性能与广泛的芯片支持使其对本地部署极具意义。 MiniCPM5-2B 支持原生 512K 上下文长度、可选的思考模式，以及在九种芯片平台上的即日适配，包括移动和边缘硬件。但截至发布时，该模型尚未在 Hugging Face 上架。

reddit · r/LocalLLaMA · /u/Illustrious-Swim9663 · 7月20日 13:47

**背景**: MiniCPM 是 OpenBMB（一个开源 AI 实验室）开发的一系列小而强大的语言模型。4B 参数以下细分市场竞争激烈，包括微软 Phi-3 和谷歌 Gemma 2 等模型。Artificial Analysis Intelligence Index 对模型能力进行基准测试，此前 MiniCPM5-1B 在 1B 模型中领先。MiniCPM5-2B 旨在将这一领先优势扩展到 2B 规模。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.remio.ai/post/minicpm5-2b-release-claims-the-sub-4b-lead-and-nine-chip-support">MiniCPM 5 - 2 B Release Claims the Sub-4B Lead and Nine-Chip Support</a></li>
<li><a href="https://artificialanalysis.ai/articles/minicpm5-1b-the-leading-1b-open-weights-model">MiniCPM 5 -1B: The leading 1B open weights model</a></li>

</ul>
</details>

**标签**: `#MiniCPM`, `#local LLM`, `#openbmb`, `#model release`

---

<a id="item-12"></a>
## [编码代理让逆向工程变得廉价且低维护](https://simonwillison.net/2026/Jul/20/cheap-reverse-engineering/#atom-everything) ⭐️ 7.0/10

Simon Willison 报告称，编码代理（AI 辅助编程工具）极大地降低了逆向工程家庭设备以实现自动化的成本和维护负担，改变了此类项目的投资回报率计算方式。 这一转变使家庭自动化对更多人变得可行，并鼓励逆向工程的尝试，因为未来维护的心理障碍降低了。它也凸显了 AI 代理降低软件开发任务成本的更广泛趋势。 关键见解是，在编码代理出现之前，逆向工程未文档化、不稳定的 API 存在未来中断的高风险；而有了代理，初始编码和后续维护都足够廉价，值得一赌。

rss · Simon Willison · 7月20日 19:24

**背景**: 逆向工程涉及分析设备的软件或硬件以了解其内部工作原理，通常用于创建自定义自动化。编码代理，如 Cursor 或 Zencoder，是辅助编写代码的 AI 工具，显著降低了开发成本。两者的结合使爱好者无需深厚专业知识即可快速为智能家居设备制作自动化原型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/AI-assisted_reverse_engineering">AI-assisted reverse engineering - Wikipedia</a></li>
<li><a href="https://www.apriorit.com/dev-blog/reverse-engineering-with-ai">Automating Software Reverse Engineering with AI - Apriorit</a></li>
<li><a href="https://cursor.com/">Cursor: AI coding agent</a></li>

</ul>
</details>

**标签**: `#reverse-engineering`, `#coding agents`, `#home automation`, `#AI agents`, `#cost reduction`

---

<a id="item-13"></a>
## [Velprium：用 AI 代理快速搭建的时间工作空间应用](https://www.velprium.com/) ⭐️ 7.0/10

独立开发者 Minjae 发布了 Velprium，这是一款将日历和笔记整合的时间工作空间应用，支持事件属性和第三个“视角”维度，并使用编码代理在两周内完成构建。 这表明 AI 辅助开发可以极大加速复杂生产力工具的建设，降低独立开发者创建创新性一体化工作与生活管理解决方案的门槛。 Velprium 引入了三个维度：时间（x 轴）、事件属性（y 轴）和通过页面与区域实现的视角（z 轴）；它还包含用于日历数据文本转 SQL 分析的 AI 查询功能，以及保留历史延期记录的“推迟”特性。

rss · Show HN (self-made tools) · 7月20日 21:30

**背景**: 编码代理是一种 AI 系统，能够根据自然语言描述自主执行编写、编辑和重构代码等任务。传统日历只使用时间和描述，而 Velprium 通过可自定义属性和多种视图扩展了这一点，旨在解决个人数据分散在 Notion 和 Obsidian 等工具中的问题。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grokipedia.com/page/Coding_agent">Coding agent</a></li>
<li><a href="https://agentic.ai/best/coding-agents">20 Best AI Coding Agents in 2026 — Agentic.ai</a></li>

</ul>
</details>

**标签**: `#productivity tool`, `#calendar app`, `#AI-assisted development`, `#solo developer`, `#workspace`

---

<a id="item-14"></a>
## [1300 万参数 ASR Conformer 模型在 10 美元微控制器上运行](https://www.reddit.com/r/LocalLLaMA/comments/1v1pume/running_a_13m_asr_conformer_on_a_microcontroller/) ⭐️ 7.0/10

一个 1310 万参数的自动语音识别 Conformer 模型，通过量化和蒸馏优化，成功部署在成本不到 10 美元的 ESP32-S3 微控制器上。 这一成就表明，复杂的 ASR 模型可以在廉价、节能的边缘设备上运行，使得语音接口对业余项目和经济型物联网应用变得触手可及。 蒸馏和量化后的模型仅占用 14 MB 闪存，并使用 256 KB SRAM 和 4 MB PSRAM 来转录 8 秒音频，尽管推理速度仍然较慢（最初需 10 分钟，现已改善）。

reddit · r/LocalLLaMA · /u/wunschpunsch3D · 7月20日 16:09

**背景**: Conformer 架构结合了卷积和自注意力机制，实现了最先进的语音识别。量化通过降低数值精度来减少内存和计算量，知识蒸馏则将知识从大型教师模型转移到小型学生模型，从而实现在资源受限硬件上的部署。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://sh-tsang.medium.com/brief-review-conformer-convolution-augmented-transformer-for-speech-recognition-88dbf40240db">Brief Review — Conformer: Convolution-augmented Transformer for Speech Recognition | by Sik-Ho Tsang | Medium</a></li>
<li><a href="https://developer.nvidia.com/blog/model-quantization-concepts-methods-and-why-it-matters/">Model Quantization: Concepts, Methods, and Why It Matters</a></li>
<li><a href="https://en.wikipedia.org/wiki/Knowledge_distillation">Knowledge distillation - Wikipedia</a></li>

</ul>
</details>

**标签**: `#Edge AI`, `#ASR`, `#Quantization`, `#Microcontroller`, `#Conformer`

---