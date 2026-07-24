---
layout: default
title: "Horizon Summary: 2026-07-24 (ZH)"
date: 2026-07-24
lang: zh
---

> 从 65 条内容中筛选出 15 条重要资讯。

---

1. [Anthropic 发布 Claude Opus 5，无数据保留要求](#item-1) ⭐️ 9.0/10
2. [Fractal：树结构中每个节点使用一个 Git worktree 的编码代理](#item-2) ⭐️ 9.0/10
3. [开源 OCR 服务成本低至每千页 1 美元](#item-3) ⭐️ 9.0/10
4. [VinvAI 将运行时追踪与代码绑定，防止奖励破解](#item-4) ⭐️ 9.0/10
5. [CachyLLama：持久化 KV 缓存加速本地 LLM 会话](#item-5) ⭐️ 9.0/10
6. [新技能自动关闭低使用率的 Codex 技能以节省 Token](#item-6) ⭐️ 9.0/10
7. [开源技能让 Codex 向 GPT-5.6 Sol Pro 求助](#item-7) ⭐️ 9.0/10
8. [Lotor：带自我批评面板的 AI 智能体网关](#item-8) ⭐️ 8.0/10
9. [LoongForge：百度的高性能具身 AI 训练系统](#item-9) ⭐️ 8.0/10
10. [Hugging Face 发布 The Stack v3——最大开源代码数据集](#item-10) ⭐️ 8.0/10
11. [引入期望接受率(EAR)的统计无损大模型量化方法](#item-11) ⭐️ 8.0/10
12. [Laguna S 2.1 对步行或开车 69 米去洗车过度思考](#item-12) ⭐️ 8.0/10
13. [Claude 语音模式扩展至 Opus 与 Sonnet 模型](#item-13) ⭐️ 8.0/10
14. [卸载未使用的 Codex 插件以减少上下文](#item-14) ⭐️ 8.0/10
15. [Agent 架构权衡：上下文 vs 并行](#item-15) ⭐️ 8.0/10

---

<a id="item-1"></a>
## [Anthropic 发布 Claude Opus 5，无数据保留要求](https://www.anthropic.com/news/claude-opus-5) ⭐️ 9.0/10

Anthropic 发布了 Claude Opus 5，该模型以 Claude Fable 5 一半的价格提供接近前沿的性能，并且不要求保留用户数据。 此次发布为组织提供了一个强大且避开 Fable 的 30 天数据保留政策的模型，有助于在隐私敏感和企业环境中更广泛采用。同时也加剧了 AI 模型提供商之间的竞争，凸显了模型路由的趋势。 Claude Opus 5 现已可用，其智能接近 Claude Fable 5 的前沿水平，价格仅为后者的一半。社区测试显示，在图像转 HTML 任务上它优于 Fable，但写作风格保留了典型的“Claude 特色”。

hackernews · alvis · 7月24日 16:57 · [社区讨论](https://news.ycombinator.com/item?id=49038433)

**背景**: Claude 是 Anthropic 开发的一系列大型语言模型，采用“宪法 AI”进行伦理对齐训练。每一代通常包括三个尺寸：Haiku、Sonnet 和 Opus。2026 年，Anthropic 还发布了 Claude Fable（更强大的 Mythos 的公开版本，带有更严格的安全措施）。Opus 5 在成本与能力之间架起桥梁，提供了无数据保留的 Fable 替代方案。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.anthropic.com/news/claude-opus-5">Introducing Claude Opus 5 \ Anthropic</a></li>
<li><a href="https://en.wikipedia.org/wiki/Claude_Opus">Claude Opus</a></li>
<li><a href="https://benchlm.ai/compare/claude-opus-5-vs-gpt-5-6-sol">Claude Opus 5 vs GPT-5.6 Sol: Benchmarks, Pricing... | BenchLM.ai</a></li>

</ul>
</details>

**社区讨论**: 社区成员强调 Opus 5 没有数据保留要求是其相对于 Fable 的关键优势。一位用户报告其在图像转 HTML 任务上的准确率优于 Fable 和 Gemini 3.1 Pro。其他人注意到模型路由的趋势，因为出现了大量模型变体和定价层级，还有人观察到 Opus 5 保留了之前 Claude 版本的写作风格特征。

**标签**: `#Claude`, `#Opus5`, `#LLM`, `#AI model`, `#image-to-html`

---

<a id="item-2"></a>
## [Fractal：树结构中每个节点使用一个 Git worktree 的编码代理](https://github.com/plasma-ai/fractal) ⭐️ 9.0/10

Fractal 是一个开源的 GitHub 项目，它将编码代理组织成树形结构，每个节点拥有独立的 Git worktree。 这种方法允许多个编码代理并行处理不同分支，避免冲突，有望提升 AI 辅助代码生成与协作的效率。 树形结构支持节点间的层级关系，每个节点的 worktree 为其代理提供独立但相互关联的工作目录。

rss · Show HN (self-made tools) · 7月24日 21:59

**背景**: Git worktree 是 Git 的一个功能，允许为单个仓库附加多个工作目录，从而在不同分支上同时工作。编码代理是能够自主编写或修改代码的 AI 驱动工具。Fractal 将两者结合，为基于代理的开发创建了一个新颖的框架。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://git-scm.com/docs/git-worktree">Git - git - worktree Documentation</a></li>

</ul>
</details>

**标签**: `#coding agents`, `#git`, `#GitHub`, `#tool`, `#AI`

---

<a id="item-3"></a>
## [开源 OCR 服务成本低至每千页 1 美元](https://www.openparser.dev/cheapest-ocr) ⭐️ 9.0/10

一位开发者基于开源权重模型 PaddleOCR-VL 部署了生产级 OCR 服务，成本约为每千页 1 美元，并通过 OpenParser.dev 公开了接口端点。 这大幅降低了高质量文档解析的成本，使小型开发者和大规模数据处理都能负担，同时价格低于 Mistral OCR 和 Azure Read 等竞品。 该服务使用 PaddleOCR-VL-0.9B，一个紧凑的视觉语言模型，支持 109 种语言和复杂元素识别。开发者指出，合理的 GPU 利用率是实现低成本的关键。

rss · Show HN (self-made tools) · 7月24日 20:41

**背景**: PaddleOCR-VL 是一个专为文档解析设计的开源权重视觉语言模型，集成了 NaViT 风格的动态分辨率视觉编码器与语言模型。开源权重模型允许任何人下载和使用，从而实现经济高效的部署。开发者自建服务是因为现有提供商要么质量低要么价格高。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/PaddlePaddle/PaddleOCR-VL">PaddlePaddle/PaddleOCR-VL · Hugging Face</a></li>
<li><a href="https://arxiv.org/abs/2510.14528">[2510.14528] PaddleOCR-VL: Boosting Multilingual Document Parsing via a 0.9B Ultra-Compact Vision-Language Model</a></li>

</ul>
</details>

**社区讨论**: Hacker News 帖子获得了 4 个积分和 1 条评论，但提供的资料中没有评论内容。

**标签**: `#OCR`, `#document parsing`, `#AI tool`, `#open-weight model`, `#cost-efficient`

---

<a id="item-4"></a>
## [VinvAI 将运行时追踪与代码绑定，防止奖励破解](https://github.com/VinvAI/VinvAI) ⭐️ 9.0/10

VinvAI 是一款新的开源工具，它将运行时执行轨迹与特定代码段关联起来，帮助开发者检测并防止 AI 代理中的奖励破解（reward hacking）。它通过将高奖励与产生这些奖励的确切代码路径关联，提供了一种在训练过程中审计代理行为的具体方法。 奖励破解是强化学习中的一个关键问题，指代理利用奖励函数的漏洞获得高分，而并非真正学习。VinvAI 通过将运行时追踪与代码直接关联来应对这一问题，帮助开发者识别并修复非预期行为，从而构建更可靠、更安全的 AI 系统。 该工具似乎使用 Go 实现，并利用 runtime/trace 包捕获执行信息。通过将追踪数据映射回源代码位置，开发者可以查看哪些代码段导致了异常高奖励，从而实现针对性调试。

rss · Show HN (self-made tools) · 7月24日 19:38

**背景**: 奖励破解（reward hacking）指 AI 代理利用奖励函数中的缺陷或模糊性来获得高奖励，而并未完成预期任务，这一现象与古德哈特定律（Goodhart's law）相关。运行时追踪（runtime trace）记录程序的执行流程，包括函数调用和 goroutine 活动，有助于诊断性能问题和理解程序行为。VinvAI 结合这两个概念，为 AI 代理训练提供了一种新的调试工具。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Reward_hacking">Reward hacking - Wikipedia</a></li>
<li><a href="https://lilianweng.github.io/posts/2024-11-28-reward-hacking/">Reward Hacking in Reinforcement Learning | Lil'Log</a></li>
<li><a href="https://pkg.go.dev/runtime/trace">trace package - runtime/trace - Go Packages</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#reward hacking`, `#debugging`, `#runtime trace`, `#GitHub`

---

<a id="item-5"></a>
## [CachyLLama：持久化 KV 缓存加速本地 LLM 会话](https://www.reddit.com/r/LocalLLaMA/comments/1v5k08a/cachyllamas_llamacpp_fork_with_persistent_kv/) ⭐️ 9.0/10

CachyLLama 是 llama.cpp 的一个分支，引入了基于 SSD 的持久化 KV 缓存，消除了长时间本地代理会话中的重复提示处理，将 15,700 token 提示的冷启动评估时间从超过 140 秒降低到不到 1 秒。 这一创新直接解决了慢速硬件上本地 LLM 代理用户的主要痛点，通过避免对系统提示和工具定义等共享上下文的冗余重新计算，使得长时间的代理编码会话响应速度大幅提升。 CachyLLama 使用多层级 KV 缓存管理，包括可跨服务器重启持久化的 SSD 检查点，并针对 Qwen 3.5/3.6、Gemma 4 和 GLM-4.7 等混合架构（其循环状态恢复更复杂）进行了特殊处理。

reddit · r/LocalLLaMA · /u/UsualResult · 7月24日 18:39

**背景**: 在大语言模型推理中，KV 缓存存储注意力机制中的键值对，以避免每个新 token 都重新计算。对于长时间代理会话，重复处理相同前缀（系统提示、对话历史）会浪费时间。持久化 SSD-backed KV 缓存将已处理状态保存到磁盘，允许后续请求快速恢复，这一技术也在 LMCache 等项目以及 Tutti 等学术论文中得到探索。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2605.03375">Tutti: Making SSD-Backed KV Cache Practical for Long-Context LLM Serving</a></li>
<li><a href="https://github.com/lmcache/lmcache">GitHub - LMCache/LMCache: LMCache: Supercharge Your LLM with the Fastest KV Cache Layer · GitHub</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#KV cache`, `#local LLM`, `#agent framework`, `#tool`

---

<a id="item-6"></a>
## [新技能自动关闭低使用率的 Codex 技能以节省 Token](https://x.com/zjp1997720/status/2080700007376986548) ⭐️ 9.0/10

一位开发者创建了一个技能，用于分析 Codex 中所有技能的使用频次，并一键自动关闭低频技能，从而减少 Token 消耗。 该工具直接解决了 AI agent 开发者的 Token 成本优化问题，使维护 Codex 平台上的高效技能集更加容易，并可能降低运营费用。 该技能可能利用频率分析来识别未充分利用的技能并自动禁用，但具体实现细节和潜在风险（例如意外禁用所需技能）尚未公开。

twitter · zjp1997720 · 7月24日 17:01

**背景**: Codex 是 OpenAI 开发的 AI 编程 agent，可执行软件工程任务。Token 优化对于 AI agent 至关重要，因为 Token 用量直接影响成本和性能；减少不必要的技能调用可以节省 Token 并提高效率。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Codex_(AI_agent)">OpenAI Codex ( AI agent ) - Wikipedia</a></li>
<li><a href="https://skills.pawgrammer.com/skills/skill-performance-profiler">Skill Performance Profiler | Claude Skills Market</a></li>
<li><a href="https://sombrainc.com/blog/token-optimization">Token Optimization for Agentic AI</a></li>

</ul>
</details>

**标签**: `#AI agent`, `#token optimization`, `#codex`, `#tool`, `#productivity`

---

<a id="item-7"></a>
## [开源技能让 Codex 向 GPT-5.6 Sol Pro 求助](https://x.com/zjp1997720/status/2080633539167469845) ⭐️ 9.0/10

一位开发者开源了一个技能，让 OpenAI 的 Codex 编码代理能向 GPT-5.6 Sol Pro 请求复杂任务的帮助。该技能使用 Codex Chrome 插件收集上下文和文件，然后在发送前提示用户确认已选中 GPT-5.6 Sol Pro。 这种集成弥合了 Codex 以代码为中心的能力与 GPT-5.6 Sol Pro 更强推理能力之间的差距，使开发者更容易处理架构设计和商业决策。它也展示了将 AI 代理串联起来的实用模式，可能激发更多协作式 AI 工作流。 该技能默认调用 Codex Chrome 插件，收集真实文件和上下文，并要求用户在发送前验证已选中 GPT-5.6 Sol Pro。它专为架构设计、商业决策和其他技能相关的复杂任务而设计。

twitter · zjp1997720 · 7月24日 12:37

**背景**: OpenAI Codex 是一套通过自然语言命令自动化软件工程任务的 AI 代理套件。GPT-5.6 Sol Pro 是 GPT-5.6 中能力最强的变体，针对困难问题进行了优化，拥有 1.1M token 的大上下文窗口。Codex Chrome 插件使 Codex 能够通过 Chrome 浏览器与网页内容交互。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grokipedia.com/page/OpenAI_Codex">OpenAI Codex</a></li>
<li><a href="https://help.openai.com/en/articles/20001354">GPT - 5 . 6 in ChatGPT | OpenAI Help Center</a></li>
<li><a href="https://developers.openai.com/codex/app/chrome-extension">Codex Chrome extension – Codex app</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#Codex`, `#GPT`, `#skill`, `#open-source`

---

<a id="item-8"></a>
## [Lotor：带自我批评面板的 AI 智能体网关](https://github.com/githubscum/lotor) ⭐️ 8.0/10

Lotor 是一个新的开源 AI 智能体网关，包含一个展示自身弱点和缺陷的面板，托管在 GitHub 上 (github.com/githubscum/lotor)。 该工具将透明度和自我意识引入 AI 智能体管理，使开发者能够直接看到并解决网关的局限性，从而可能提高自动化智能体工作流的信任度和可靠性。 该仓库在 Hacker News 上只有 1 分和 1 条评论，表明处于早期开发阶段；提供的资料中尚未记录自我批评面板的具体实现细节。

rss · Show HN (self-made tools) · 7月24日 20:56

**背景**: AI 智能体是代表用户自主执行任务的程序。AI 智能体的"网关"通常控制访问、路由或执行智能体请求。自我批评或反思循环（AI 评估自身输出）已被证明可将推理任务的准确性提高多达 20%，但将这种方法应用于网关本身是一种新颖的做法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.ibm.com/think/topics/ai-agents">What Are AI Agents ? | IBM</a></li>
<li><a href="https://www.mindstudio.ai/blog/what-is-self-qa-loop-ai-agents">What Is the Self-QA Loop? How AI Agents Critique Their Own Output Before You See It | MindStudio</a></li>
<li><a href="https://www.taskade.com/blog/self-improving-ai-agents-reflection">Self-Improving AI Agents: The Reflection Loop (2026)</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#GitHub`, `#tool`, `#gate`, `#self-critique`

---

<a id="item-9"></a>
## [LoongForge：百度的高性能具身 AI 训练系统](https://github.com/baidu-baige/LoongForge/tree/master/loongforge/embodied) ⭐️ 8.0/10

百度开源了 LoongForge，这是一个模块化、可扩展的训练框架，专门用于具身 AI 模型的高性能训练，已托管在 GitHub 上。 具身 AI 是一个快速发展的领域，它将数字 AI 与物理机器人连接起来，而 LoongForge 提供了优化的训练系统，可能加速机器人技术和自主系统的研发。 LoongForge 使用声明式 YAML 配置从不同模态组件组合多模态模型，支持预训练、微调和 RLHF 阶段。

rss · Show HN (self-made tools) · 7月24日 19:45

**背景**: 具身 AI 指的是通过传感器和执行器与物理世界交互的 AI 系统，例如机器人。训练这类模型需要大规模处理多种数据模态（视觉、语言、动作），这要求高性能基础设施。LoongForge 旨在通过提供模块化和高效的训练流程来满足这些需求。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/baidu-baige/LoongForge">GitHub - baidu-baige/ LoongForge : A modular, scalable, and highly...</a></li>
<li><a href="https://www.nvidia.com/en-us/glossary/embodied-ai/">What is Embodied AI ? | NVIDIA Glossary</a></li>
<li><a href="https://baidu-baige.github.io/LoongForge/?ref=producthunt">LoongForge — Fast Training for LLM, VLM, DiT & Embodied AI</a></li>

</ul>
</details>

**标签**: `#embodied AI`, `#training system`, `#GitHub repo`, `#machine learning`, `#high-performance`

---

<a id="item-10"></a>
## [Hugging Face 发布 The Stack v3——最大开源代码数据集](https://www.reddit.com/r/LocalLLaMA/comments/1v59aek/hugging_face_releases_the_stack_v3_largest_open/) ⭐️ 8.0/10

Hugging Face 发布了 The Stack v3，这是最大的开源代码数据集，容量达 114 TB，提供两个版本：一个经过处理、去重的训练集，以及一个用于自定义过滤的原始完整语料库。 该数据集使开发者能够在代码上训练和微调大型语言模型，质量显著提升，因为近去重和 PII 审核减少了噪声和隐私风险。 处理版本'stack-v3-train'包括近去重、质量过滤和 PII 审核，内容内联；而原始版本'stack-v3-full'保留所有重复项并附带聚类 ID，供自定义处理。

reddit · r/LocalLLaMA · /u/Nunki08 · 7月24日 11:57

**背景**: 大型代码数据集通常包含近重复内容和个人身份信息（PII），如电子邮件或 API 密钥，这可能降低模型性能并带来隐私风险。使用局部敏感哈希的近去重技术通过移除冗余样本来提升模型质量，而 PII 审核则保护敏感数据。Hugging Face Storage Buckets 提供类似 S3 的对象存储，无出站费用，使得 114 TB 的原始语料库可供自定义使用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/blog/dedup">Large-scale Near-deduplication Behind BigCode</a></li>
<li><a href="https://huggingface.co/docs/hub/storage-buckets">Storage Buckets · Hugging Face</a></li>

</ul>
</details>

**标签**: `#dataset`, `#code`, `#HuggingFace`, `#LLM`, `#open-source`

---

<a id="item-11"></a>
## [引入期望接受率(EAR)的统计无损大模型量化方法](https://www.reddit.com/r/LocalLLaMA/comments/1v5j35f/paper_statisticallylossless_quantization_of_large/) ⭐️ 8.0/10

该论文提出了大语言模型的统计无损量化方法，定义了三种无损概念，并提出了一种新的保真度指标——期望接受率(EAR)，用于衡量量化模型与原始模型之间下一个词分布的匹配程度。 这项研究填补了有损量化与无损量化之间的空白，提供了一个可直接指导部署决策的实用保真度指标，使得在最小化性能损失的前提下实现高效的大语言模型推理成为可能。 通过提出的 SLQ 方法，作者实现了每参数低于 4 比特的任务无损压缩，以及每参数 5-6 比特的分布无损压缩，在 GPU 和 CPU 上相较 FP16 获得了 1.7-3.6 倍的推理加速。

reddit · r/LocalLLaMA · /u/pmttyji · 7月24日 18:06

**背景**: 量化通过降低模型权重的精度到更低位宽，实现更快速、更节省内存的部署。传统方法如 GPTQ 和 AWQ 是有损的，而完全无损的技术无法加速推理。本文提出的统计无损量化在保持输出分布的同时实现了加速。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2605.02404">Statistically-Lossless Quantization of Large Language Models</a></li>

</ul>
</details>

**标签**: `#quantization`, `#LLM`, `#deployment`, `#efficiency`, `#paper`

---

<a id="item-12"></a>
## [Laguna S 2.1 对步行或开车 69 米去洗车过度思考](https://www.reddit.com/r/LocalLLaMA/comments/1v5l75x/asking_laguna_s_21_i_want_to_wash_my_car_the_car/) ⭐️ 8.0/10

一位 Reddit 用户向 Laguna S 2.1 提问：步行还是开车 69 米去洗车？模型生成了冗长且过度思考的推理链，幽默地忽略了显而易见的答案。 这个例子突显了大型推理模型常见的问题——对简单查询过度思考——这可能导致低效甚至滑稽的输出，并强调了更好校准推理深度的必要性。 所使用的模型是 Laguna S 2.1，一个总参数量 118B、激活参数 8B 的混合专家模型，用户将其量化为 UD-Q5_K_XL（Unsloth Dynamic 5-bit 量化）。

reddit · r/LocalLLaMA · /u/_TheWolfOfWalmart_ · 7月24日 19:21

**背景**: Laguna S 2.1 是由 Poolside 开发的最先进的编码代理模型，针对扩展推理和代理任务进行了优化。像 UD-Q5_K_XL 这样的量化技术可以在保持性能的同时减小模型体积。LLM 中的过度思考是指推理模型倾向于为简单提示生成不必要的长思维链，这通常是由于训练激励要求展示推理过程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://ollama.com/library/laguna-s-2.1">laguna - s - 2 . 1</a></li>
<li><a href="https://huggingface.co/poolside/Laguna-S-2.1/tree/main">poolside/ Laguna - S - 2 . 1 at main</a></li>
<li><a href="https://news.ycombinator.com/item?id=48638281">Can somebody help me understand the Quantization ... | Hacker News</a></li>

</ul>
</details>

**标签**: `#AI model testing`, `#local LLM`, `#reasoning`, `#Laguna 2.1`, `#edge case`

---

<a id="item-13"></a>
## [Claude 语音模式扩展至 Opus 与 Sonnet 模型](https://www.theverge.com/ai-artificial-intelligence/970065/anthropic-voice-mode-claude-opus-sonnet-haiku-ai) ⭐️ 8.0/10

Anthropic 将 Claude 的语音模式从 Haiku 模型扩展至更强大的 Opus 和 Sonnet 模型，并新增了 Gmail、Slack、Canva 等第三方应用集成。用户现在可以在对话中自由切换文字与语音模式以及不同模型。 此次升级使 Claude 的语音模式达到与其文本智能相当的水平，支持更复杂的业务场景。扩展的语言支持与第三方集成也拓宽了它的全球可访问性和实用性。 此前语音模式仅限 Claude Haiku（最快但能力最弱的模型）。Anthropic 还新增了法语、德语、西班牙语、印地语、印尼语、意大利语、日语、韩语和葡萄牙语支持，这些语言已脱离测试版。

telegram · zaihuapd · 7月24日 07:03

**背景**: Claude 是 Anthropic 的大型语言模型系列，包括 Haiku（快速）、Sonnet（均衡）、Opus（强大）和 Fable（最新）等层级。语音模式于 2025 年首次在 Haiku 上推出，但难以胜任深度对话。扩展到更强模型旨在弥补这一局限，同时集成生产力应用以执行实际任务。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.theverge.com/ai-artificial-intelligence/970065/anthropic-voice-mode-claude-opus-sonnet-haiku-ai">Claude ’s voice mode is now available for Opus and Sonnet | The Verge</a></li>
<li><a href="https://9to5mac.com/2026/07/23/anthropic-upgrades-claude-voice-mode-with-more-powerful-models/">Anthropic upgrades Claude voice mode with more... - 9to5Mac</a></li>
<li><a href="https://claude.com/resources/tutorials/choosing-the-right-claude-model">Choosing the right Claude model : Haiku , Sonnet , Opus , or Fable</a></li>

</ul>
</details>

**标签**: `#Claude`, `#语音模式`, `#AI工具`, `#模型更新`

---

<a id="item-14"></a>
## [卸载未使用的 Codex 插件以减少上下文](https://x.com/zjp1997720/status/2080677076290740298) ⭐️ 8.0/10

一位用户发现 Codex 默认加载了 54 个技能，包括许多未使用的，建议卸载不必要的插件以缩短上下文长度并减少模型混淆。 未使用的插件浪费上下文窗口并可能误导 AI 模型，降低编码任务的性能。这种简单的清理可以显著提高 Codex 对开发者的效率和准确性。 用户发现 Codex 加载了 54 个技能，仅 data-analytics 就贡献了 15 个未使用的，他们自己又添加了 19 个。移除这些可以减少模型干扰并缩短上下文。

twitter · zjp1997720 · 7月24日 15:30

**背景**: Codex 有一个插件系统，允许用户安装技能和扩展以增强其能力。技能使用渐进式披露，但所有加载的技能都会向上下文贡献元数据，可能增加 token 使用量并分散模型注意力。卸载未使用的插件是一种实用的优化。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.codex-marketplace.com/">Codex Plugin Marketplace</a></li>
<li><a href="https://github.com/storywithoutend/plugins-research-wiki/blob/main/codex-plugins.md">plugins -research-wiki/ codex - plugins .md at main...</a></li>
<li><a href="https://developers.openai.com/codex/skills/?ref=robert-glaser.de">Give Codex new capabilities and expertise</a></li>

</ul>
</details>

**标签**: `#codex`, `#plugins`, `#ai-assistant`, `#productivity`, `#tips`

---

<a id="item-15"></a>
## [Agent 架构权衡：上下文 vs 并行](https://x.com/zjp1997720/status/2080660613530038730) ⭐️ 8.0/10

一位开发者报告，主从 Agent 架构在执行任务时会丢失上下文，而在同一会话中直接切换 Agent 则成功率和效率更高。但主从 Agent 的优势在于可以并行执行任务，这是同一会话切换无法做到的。 这一见解帮助开发者在构建 AI Agent 系统时做出更明智的架构决策，在上下文保留与并行执行能力之间取得平衡。它直接影响复杂工作流的多 Agent 系统设计。 该观察来自 AI Agent 的实践经验，比较了主从架构和同一会话切换两种方式。主从架构的并行执行以丢失上下文为代价，而同一会话切换保留上下文但无法并行运行任务。

twitter · zjp1997720 · 7月24日 14:25

**背景**: 在 Agent 架构中，主从（或控制器-代理）模型通常将任务分配给多个 Agent 进行并行处理，但每个 Agent 独立运行，可能会丢失共享上下文。同一会话切换将 Agent 保持在同一会话中，保留状态但限制了并行能力。这种权衡对于设计高效的多 Agent 系统至关重要。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://dev.to/ashiqursuperfly/jenkins-controller-agent-master-slave-setup-in-10-minutes-using-docker-2a78">Jenkins controller- agent ( master - slave ) setup in 10... - DEV Community</a></li>
<li><a href="https://community.latenode.com/t/how-to-keep-browser-session-alive-between-multiple-autonomous-ai-agents/48705">How to keep browser session alive between multiple autonomous ai ...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#agent architecture`, `#parallel execution`, `#context`, `#session management`

---