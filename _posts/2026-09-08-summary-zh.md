---
layout: default
title: "Horizon Summary: 2026-09-08 (ZH)"
date: 2026-09-08
lang: zh
---

> 从 54 条内容中筛选出 11 条重要资讯。

---

1. [Keyclasp 让 AI 代理使用密钥而不在提示中暴露令牌](#item-1) ⭐️ 9.0/10
2. [MiniCPM5-2B 发布：成 4B 以下开放权重模型中得分最高](#item-2) ⭐️ 9.0/10
3. [九步教程：用 llama.cpp、MCP 与 FreeCAD 制作可 3D 打印的零件](#item-3) ⭐️ 9.0/10
4. [视频压缩器：用 Claude Code 与 FFmpeg WebAssembly 构建的实用工具](#item-4) ⭐️ 8.0/10
5. [任务感知量化达到 BF16 推理 99%性能，体积仅 15%](#item-5) ⭐️ 8.0/10
6. [独立开发者发布 Jenny 应用：本地运行大模型并支持工具调用](#item-6) ⭐️ 8.0/10
7. [ExLlamaV3 被低估：量化质量与速度优于 llama.cpp](#item-7) ⭐️ 8.0/10
8. [从墨卡托到 Equal Earth：AI 构建的地图动画](#item-8) ⭐️ 7.0/10
9. [Animaxxing：用 AI 智能体自动为网站添加动画](#item-9) ⭐️ 7.0/10
10. [WorldFixture：提供一家模拟公司供软件进行真实集成测试的开源工具](#item-10) ⭐️ 7.0/10
11. [DeepSeek-V4-Flash-Vision-Exp：凭借截图两天构建游戏世界](#item-11) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Keyclasp 让 AI 代理使用密钥而不在提示中暴露令牌](https://github.com/AndreaCatalucci/keyclasp) ⭐️ 9.0/10

Keyclasp 是一个新发布的开源工具，可将凭据存入本地加密保险库，并让 AI 代理通过密钥名称启动命令，只把真实令牌作为环境变量注入子进程。它还带有输出守卫，一旦在标准输出或错误流中检测到被注入的值就会将其脱敏。 它填补了本地编码代理工作流中的一个实际安全漏洞——密钥常常会泄露到提示词或命令输出里。Keyclasp 加入了一个日益壮大的工具生态，这类工具的目标是让凭据完全不进入大模型上下文，在 AI 代理拥有敏感系统访问权限的当下尤为重要。 该工具运行时不经 shell 启动命令，并拦截常见的环境变量导出命令；输出守卫只对长度至少 8 个字符的完整注入值进行脱敏，较短值、编码形式和片段不在保护范围内。它是 keyblind.dev 的一个分支，采用 MIT 许可，可用 npm install -g keyclasp@beta 安装。

rss · Show HN (self-made tools) · 9月7日 21:43

**背景**: 本地 AI 编码代理往往需要 API 密钥或令牌来执行命令，但把密钥放进提示词可能导致密钥出现在对话记录或输出中。Keyclasp 以及 agentsecrets、secretsh 等类似工具都采用基于保险库的方案：代理只能看到密钥名称，真实值在进程启动时才注入。这与业界日益关注降低 AI 代理部署中密钥泄露和提示注入风险的总体方向一致。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/AndreaCatalucci/keyclasp">GitHub - AndreaCatalucci/ keyclasp : Runtime secrets for coding agents...</a></li>
<li><a href="https://github.com/the-17/agentsecrets">GitHub - The-17/agentsecrets: Zero-knowledge credentials infrastructure built for AI agents to operate, not just consume. · GitHub</a></li>
<li><a href="https://unit42.paloaltonetworks.com/ai-agent-prompt-injection/">Fooling AI Agents: Web-Based Indirect Prompt Injection Observed in the Wild</a></li>

</ul>
</details>

**标签**: `#AI代理`, `#凭据安全`, `#开发者工具`, `#GitHub项目`

---

<a id="item-2"></a>
## [MiniCPM5-2B 发布：成 4B 以下开放权重模型中得分最高](https://www.reddit.com/r/LocalLLaMA/comments/1w9skjz/minicpm52b_release_day/) ⭐️ 9.0/10

OpenBMB 发布了 MiniCPM5-2B，一个拥有 25.2 亿参数（2.52B）的稠密开放权重语言模型。它在 Artificial Analysis Intelligence Index v4.2 上获得 15 分，是 4B 参数及以下开放权重模型中得分最高的。 此次发布增强了能在本地设备上运行的小型开放权重模型的生态，为开发者提供了在端侧处理智能体与工具调用任务的高性能选择。这也表明 MiniCPM 系列正在小型模型赛道上积极竞争。 该模型是一个稠密 Transformer，总参数量为 2,516,756,480，其中约 19.8 亿为非嵌入参数，在 34 项基准测试中平均得分 53.9。它的优势主要体现在工具调用、编码智能体以及 NoLiMa 风格的长上下文检索上，而在 MMLU-Pro、GPQA-Diamond 和 MATH-500 等知识密集型测试上落后于更大模型。

reddit · r/LocalLLaMA · /u/Equivalent-Grass-527 · 9月7日 13:43

**背景**: 开放权重模型会公开发布训练好的参数，使任何人可以下载、推理，并且通常允许微调。Artificial Analysis Intelligence Index v4.2 是多个生产环境基准分数的加权平均值，按 0 到 100 缩放，涵盖 Terminal-Bench v2.1、SciCode、Humanity's Last Exam 等测试。MiniCPM5-2B 是继 OpenBMB 于 5 月 19 日开源 MiniCPM5-1B 之后发布的第二款 MiniCPM5 系列模型，专为端侧部署设计。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.orcarouter.ai/blog/minicpm5-2b-vs-gemma-4-12b">MiniCPM 5 - 2 B vs Gemma 4 12B: which local model wins?</a></li>
<li><a href="https://www.marktechpost.com/2026/09/07/openbmb-releases-minicpm5-2b-a-2-52b-dense-model-averaging-53-9-across-34-benchmarks-and-built-to-run-on-device/">OpenBMB Releases MiniCPM 5 - 2 B : A 2.52B Dense Model Averaging...</a></li>
<li><a href="https://artificialanalysis.ai/evaluations/artificial-analysis-intelligence-index">Artificial Analysis Intelligence Index v 4 . 2 | Artificial Analysis</a></li>

</ul>
</details>

**标签**: `#model release`, `#open weights`, `#MiniCPM`, `#Hugging Face`, `#LocalLLaMA`

---

<a id="item-3"></a>
## [九步教程：用 llama.cpp、MCP 与 FreeCAD 制作可 3D 打印的零件](https://www.reddit.com/r/LocalLLaMA/comments/1w9r73k/9_easy_steps_for_llamacpp_a_local_model_freecad/) ⭐️ 9.0/10

一位 Reddit 用户分享了一个九步教程，教大家通过 freecad-mcp 仓库，将 llama.cpp 的 llama-server（或 pi 编程代理）与 FreeCAD 结合使用。该流程让具备视觉能力的本地 GGUF 模型能读取 FreeCAD 截图，生成可 3D 打印或铣削的机械实体对象。 它展示了全本地的智能体式 CAD 建模思路：在不上传云端的情况下，由本地模型直接控制设计工具。随着开发者越来越多地探索用支持 MCP 的智能体进行实体产品设计、离线制造和隐私敏感工作流，这类方案尤其具有参考价值。 安装时需克隆 neka-nat/freecad-mcp 仓库，并将插件复制到 FreeCAD 的 Mod 目录；MCP 配置写在 pi 的 ~/.pi/agent/mcp.json 中，或写入 llama-server 的 freecad_mcp.json 中。教程还建议加载独立的 mmproj GGUF 文件，让模型能查看 FreeCAD 截图，并在 llama-server 的 Web UI 中将 Agentic turns 设为 99。

reddit · r/LocalLLaMA · /u/DevelopmentBorn3978 · 9月7日 12:45

**背景**: 模型上下文协议（MCP）是 Anthropic 于 2024 年 11 月推出的开放标准，旨在统一 AI 系统连接数据源和工具的方式。llama.cpp 是一个广受欢迎的 C/C++ 本地大语言模型推理引擎，GGUF 正是为该引擎设计的模型格式。pi 是一个极简的开源终端编程代理框架，MCP 等额外能力通过扩展按需加载。FreeCAD 是一款开源参数化 CAD 应用，freecad-mcp 将其操作封装成 MCP 工具，从而让本地模型生成和修改实体模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol - Wikipedia</a></li>
<li><a href="https://huggingface.co/docs/hub/gguf">GGUF · Hugging Face</a></li>
<li><a href="https://pi.dev/">Pi Coding Agent</a></li>

</ul>
</details>

**标签**: `#llama.cpp`, `#FreeCAD`, `#MCP`, `#coding agent`, `#3D printing`

---

<a id="item-4"></a>
## [视频压缩器：用 Claude Code 与 FFmpeg WebAssembly 构建的实用工具](https://simonwillison.net/2026/Sep/7/video-compressor/) ⭐️ 8.0/10

Simon Willison 发布了一个基于浏览器的视频压缩器；他用 Claude Code for web 让 Claude Fable 5.1 基于 FFmpeg 的 WebAssembly 版本帮他生成这个工具。该工具在约 11.8 秒内把手机录制的 Equal Earth 演示视频压缩成 5 个版本，最小输出为 145 KB，相当于原视频的 48%。 这件事之所以重要，是因为它展示了一个从简单的自然语言请求生成的、真正可用的浏览器工具，而不是演示片段，说明 AI 编程代理能如何加速实际开发工作。Willison 同时分享了成品压缩器和对应的 Claude Code 会话，这为其他开发者提供了一个具体、可复现的 AI 辅助工具构建流程示例。 该工具通过 ffmpeg.wasm 完全在浏览器中运行，提供从 Largest 到 Smallest 的 5 个预设，输出分辨率可达 854×370 或 640×276，CRF 值从 22 到 28，音频比特率从 64 到 128 kbps。此外还可设置编码速度、H.264 配置、30 fps 限制、去除元数据、去掉音频以及只编码前 10 秒；每个生成结果都会显示实际使用的 ffmpeg 命令。

rss · Simon Willison · 9月7日 18:29

**背景**: Claude Code 是 Anthropic 推出的代理式编程工具；开发者用自然语言描述需求，代理会制定计划、编写代码并运行命令来完成任务。ffmpeg.wasm 通过 Emscripten 把 FFmpeg 这个强大的多媒体框架编译成 WebAssembly，让视频转码可以在浏览器中以接近原生的速度运行。CRF（Constant Rate Factor，恒定速率因子）是一种以一致的感知质量为目标、允许码率浮动的编码模式，因此这个工具把它作为主要质量设置。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://claude.com/product/claude-code">Claude Code by Anthropic | AI Coding Agent, Terminal, IDE</a></li>
<li><a href="https://ffmpegwasm.netlify.app/docs/overview/">Overview | ffmpeg .wasm</a></li>
<li><a href="https://slhck.info/video/2017/02/24/crf-guide.html">CRF Guide (Constant Rate Factor in x264, x265 and libvpx)</a></li>

</ul>
</details>

**标签**: `#Claude Code`, `#FFmpeg`, `#WebAssembly`, `#AI-assisted development`, `#video compression`

---

<a id="item-5"></a>
## [任务感知量化达到 BF16 推理 99%性能，体积仅 15%](https://www.reddit.com/r/LocalLLaMA/comments/1wa5dp9/my_qwen3827b_taskaware_quant_reaches_99_of_bf16/) ⭐️ 8.0/10

Reddit 用户 u/devildip（ByteOtter）发布了 TAK（Task Aware Knapsack，任务感知背包）量化流程。其量化版 Qwen3.8-27B 在推理基准上得分 82.81%，达到 BF16 得分（83.59%）的约 99%，同时超过同字节数的 Unsloth IQ2_S 量化版（77.34%），而模型体积约为原始的 15%。 这表明任务感知的精度分配能在模型体积大幅缩小时保留接近全精度的推理能力，对在有限硬件上本地运行 LLM 很有价值。同时，这也为通用低比特量化提供了一种实用的、以基准测试为导向的替代思路。 TAK 将基于任务特定语料构建的 imatrix 与字节预算约束下的张量级精度分配相结合，借鉴了与 TASA 和 TAQ 类似的思想。它纯属训练后量化，不涉及剪枝、微调或模型融合，且所有结果都在保留数据集（held-out dataset）上进行了评估。

reddit · r/LocalLLaMA · /u/devildip · 9月7日 21:42

**背景**: 训练后量化（PTQ）将 LLM 权重压缩为低比特格式，以降低显存和计算开销。标准 PTQ 通常使用统一精度，而 TAQ、TASA 等任务感知方法会利用目标任务上的校准数据，在固定比特预算内为任务关键层分配更高精度。TAK 将这一思路转化为背包式的字节预算分配，使模型能针对推理等特定任务领域进行适配。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2511.06516v3">You Had One Job: Per-Task Quantization Using LLMs’ Hidden Representations</a></li>
<li><a href="https://arxiv.org/html/2607.00908">Beyond Activation Alignment: The Alignment-Diversity Tradeoff in Task-Aware LLM Quantization</a></li>
<li><a href="https://medium.com/data-science/gguf-quantization-with-imatrix-and-k-quantization-to-run-llms-on-your-cpu-02356b531926">GGUF Quantization with Imatrix and K- Quantization to Run LLMs on...</a></li>

</ul>
</details>

**标签**: `#quantization`, `#LLM`, `#Qwen`, `#efficiency`, `#local-LLM`

---

<a id="item-6"></a>
## [独立开发者发布 Jenny 应用：本地运行大模型并支持工具调用](https://www.reddit.com/r/LocalLLaMA/comments/1w9wvkb/after_over_a_year_of_my_nights_and_weekends_the/) ⭐️ 8.0/10

开发者正式发布 Jenny——一款免费、MIT 许可的 Electron 桌面应用，用于在本地运行大语言模型，支持工具调用、回滚和 IDE。经过 1.5 年独立开发的夜间与周末工作，该应用现已支持 llama.cpp、vLLM 以及任何兼容 OpenAI 的本地端点，并可通过受管 llama-server 运行 GGUF 模型。 这意义重大，因为它提供了一个免费、自托管的替代方案，替代由风投补贴的云端 LLM API，减少对日后可能“变质”的 VC 支持服务的依赖。通过在本地小模型上启用工具调用，Jenny 也降低了注重隐私的 AI 开发者尝试智能体工作流的门槛。 Jenny 内置安全功能，例如执行破坏性 Shell 命令需要用户批准，并对文件编辑设置检查点，从而在小模型出错时保护用户。Windows 版本稳定，已在 RTX 5070 Ti 与 ornith1.5:9b 模型上测试；macOS 尚未测试，Linux 因引擎提供商原因暂不支持。

reddit · r/LocalLLaMA · /u/TangySword · 9月7日 16:27

**背景**: 在 AI 工程中，“harness”（控制框架）指围绕模型的辅助基础设施，作为运行时控制系统来管理长时间运行的任务和交互，从而把模型变成智能体。工具调用（tool calling）让 LLM 从单纯生成文本转变为能够执行实际操作，例如调用 API 或获取数据。Jenny 是众多本地 LLM 桌面控制框架之一（LM Studio、Unsloth Desktop 和 Open WebUI 是其他例子），让用户能完全在自己的硬件上私密运行开放权重模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://tenx.studio/blog/llm-tool-calling">Your LLM Can Book Flights Now — Here's How Tool Calling Works</a></li>
<li><a href="https://dev.to/nirvana_andy/what-does-harness-mean-to-ai-agents-p7o">What does “ Harness ” mean to AI Agents? - DEV Community</a></li>
<li><a href="https://www.linkedin.com/pulse/what-ai-harness-why-you-should-care-lot-ronni-holmvig-strøm-m20ce">What is an AI harness ? And why you should care (a lot).</a></li>

</ul>
</details>

**标签**: `#local LLM`, `#open source`, `#tool calling`, `#desktop app`, `#AI harness`

---

<a id="item-7"></a>
## [ExLlamaV3 被低估：量化质量与速度优于 llama.cpp](https://www.reddit.com/r/LocalLLaMA/comments/1wa36d1/exllamav3_is_underrated/) ⭐️ 8.0/10

一位 Reddit 用户在 r/LocalLLaMA 上发帖称赞 ExLlamaV3，称它是针对 NVIDIA GPU 的被低估的本地 LLM 推理引擎，并声称其 EXL3 量化质量更高、KLD 指标更低，且速度比 llama.cpp 更快。该用户还提到最近的更新加入了 CPU MoE offload 支持，并且他们一直将 tabbyAPI ExL3 后端搭配 Qwen 模型作为日常使用。 这篇帖子为 NVIDIA GPU 用户提供了一个可替代 llama.cpp 的方案，可能会引导本地 LLM 爱好者转向 ExLlamaV3，以获得更好的单位比特质量和速度。它也反映出社区对默认 llama.cpp 之外的专用推理引擎越来越感兴趣。 用户的个人测试属于主观体验，并非正式基准测试；其日常使用的模型包括通过 tabbyAPI ExL3 后端运行的 Qwen 3.8 27B SC 6bpw H6 和 Qwen 3.8 Flash Next 4bpw。ExLlamaV3 是一个面向现代消费级 GPU 的优化量化与推理库，但仅支持 NVIDIA，而近期新增的 CPU MoE offload 支持可能是其人气上升的原因。

reddit · r/LocalLLaMA · /u/Embarrassed_Soup_279 · 9月7日 20:16

**背景**: ExLlamaV3（托管于 turboderp-org）是一个针对消费级 GPU 上的量化 LLM 推理进行优化的库。KLD（Kullback-Leibler 散度）是一种保真度指标，用来衡量量化模型与原始模型输出概率分布之间的差异，因此较低的 KLD 通常表示量化模型更接近未量化模型。tabbyAPI 是 ExLlamaV3 的官方 API 服务器，提供兼容 OpenAI 的本地部署接口。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/turboderp-org/exllamav3">GitHub - turboderp-org/exllamav3: An optimized quantization and inference library for running LLMs locally on modern consumer-class GPUs · GitHub</a></li>
<li><a href="https://github.com/theroyallab/tabbyAPI">GitHub - theroyallab/ tabbyAPI : The official API server for Exllama.</a></li>
<li><a href="https://huggingface.co/blog/rishiraj/kld-guided-quantization">Why Maybe We're Measuring LLM Compression Wrong</a></li>

</ul>
</details>

**标签**: `#ExLlamaV3`, `#local LLM`, `#inference`, `#NVIDIA`, `#llama.cpp`

---

<a id="item-8"></a>
## [从墨卡托到 Equal Earth：AI 构建的地图动画](https://simonwillison.net/2026/Sep/7/equal-earth/) ⭐️ 7.0/10

Simon Willison 在 ChatGPT Work 中使用 GPT-6 Astra（medium），让 AI 用 D3 构建了一个在墨卡托投影与 Equal Earth 投影之间切换的动画可视化。他已将该交互工具发布在 tools.simonwillison.net/equal-earth，并公开了完整的 ChatGPT 对话作为提示词工程示例。 这是“vibe coding”在地理空间可视化中的一个具体而及时的示例，恰逢联合国大会投票鼓励采用 Equal Earth 等等面积投影之后不久。它展示了 GPT-6 Astra 等模型如何将一个随意的提问变成精致的交互式 D3 演示，从而降低探索地图投影概念的门槛。 该工具包含一段动画演示，整个可视化是通过 ChatGPT Work 使用 D3 生成的，而不是手工编写代码。公开的对话是一个有用的提示词工程示例，展示了如何让 AI 生成自定义地图投影过渡效果；不过作者没有发布独立的 GitHub 仓库或可复用代码包。

rss · Simon Willison · 9月7日 16:24

**背景**: 墨卡托投影能保持局部的角度和形状，但会严重扭曲高纬度地区陆地的相对面积。Equal Earth 投影由 Bojan Šavrič、Tom Patterson 和 Bernhard Jenny 于 2018 年提出，是一种等面积的伪圆柱投影，能保持面积真实，使各大洲的相对大小更准确。2026 年 9 月，联合国大会就一项鼓励使用 Equal Earth 等等面积投影的决议进行了表决。D3.js 是常用于构建网页交互式可视化的 JavaScript 库；“vibe coding”指用自然语言描述需求、让 AI 模型生成代码的做法。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Equal_Earth_map_projection">Equal Earth map projection</a></li>
<li><a href="https://en.wikipedia.org/wiki/D3.js">D3.js</a></li>
<li><a href="https://equal-earth.com/equal-earth-projection.html">Equal Earth Wall Map - Projection</a></li>

</ul>
</details>

**标签**: `#vibe coding`, `#ChatGPT`, `#data visualization`, `#geospatial`, `#D3`

---

<a id="item-9"></a>
## [Animaxxing：用 AI 智能体自动为网站添加动画](https://animaxxing.com/) ⭐️ 7.0/10

Animaxxing 是一款使用 AI 智能体为网站添加动画效果的工具，它以 Show HN 的形式被发布到 Hacker News，并可在 animaxxing.com 直接试用。截至目前，该提交只获得了 4 个积分和 2 条评论，互动量还比较有限。 这件事值得关注，因为它反映了 agentic AI 工具正从代码生成延伸到前端美化与设计领域。缺乏动画专业经验的开发者，可以借助这类工具，用更少的手动操作让网站变得更有吸引力。 从 Hacker News 的列表来看，该项目得到的社区验证还很少：只有 4 个积分和 2 条评论。提交内容里没有附带 GitHub 仓库或详细技术文档，因此其底层架构和所用 AI 模型尚不明确。

rss · Show HN (self-made tools) · 9月7日 22:14

**背景**: 动画是一种通过连续播放静态画面来制造运动幻觉的视觉技法，现代电脑动画通常依赖 CGI。在网页语境下，动画通常指用 CSS 或 JavaScript 实现的动态效果，让页面更生动、更具交互感。Animaxxing 自称使用 AI 智能体来自动为网站添加这类效果，而不需要开发者手动编写动画。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Animation">Animation</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#web animation`, `#AI tool`, `#developer tool`, `#Show HN`

---

<a id="item-10"></a>
## [WorldFixture：提供一家模拟公司供软件进行真实集成测试的开源工具](https://worldfixture.com/) ⭐️ 7.0/10

WorldFixture 是一款新展示的开源工具，可模拟 Stripe、Gmail、Slack、GitHub 等第三方服务，并统一由一个连贯的假公司数据集支撑。它从 droplive.io 中独立出来，并以 Show HN 项目的形式发布。 集成测试和端到端测试往往因为第三方沙箱缺乏互相关联的一致数据而显得不够真实。WorldFixture 通过跨多个服务提供一致的假公司数据并支持事件流式推送，帮助开发者构建更有说服力的测试和演示。 所有模拟服务的数据都围绕同一家虚构公司组织，因此 API 返回内容具有连贯的故事性，并且可以随时间流式产生事件，让应用显得“活”起来。当默认假公司不满足需求时，开发者还可以创建自己的数据集或“worlds”。

rss · Show HN (self-made tools) · 9月7日 21:42

**背景**: WorldFixture 起源于 droplive.io——一个在限时 microVM（轻量级虚拟机）中让用户体验托管开源软件的服务。microVM 是一种注重快速启动和缩小攻击面的轻量级虚拟机，Firecracker 便是典型例子。作者发现没有数据的演示效果很差，于是加入了更真实的数据和模拟服务，最终把这部分功能独立成了一个项目。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/firecracker-microvm/firecracker">GitHub - firecracker- microvm /firecracker: Secure and fast microVMs...</a></li>
<li><a href="https://www.koyeb.com/blog/what-is-a-microvm">What is a microVM ? - Koyeb</a></li>

</ul>
</details>

**标签**: `#open-source`, `#developer-tools`, `#testing`, `#mocking`, `#workflow`

---

<a id="item-11"></a>
## [DeepSeek-V4-Flash-Vision-Exp：凭借截图两天构建游戏世界](https://www.reddit.com/r/LocalLLaMA/comments/1wa06k3/deepseekv4flashvisionexp_is_amazing_at_creating/) ⭐️ 7.0/10

一位开发者展示了自己利用 DeepSeek-V4-Flash-Vision-Exp 的新视觉能力，通过截图迭代生成和修正游戏纹理、修复视觉故障、用脚本驱动动画并测试 UI 与玩法，大约两天就完成了一个完整的游戏世界。 这一实操展示表明，具备视觉能力的大语言模型可以将 AI 辅助游戏开发中的资产生成与测试迭代从数周压缩到数天，也凸显了多模态开源模型在端到端创作工作流中日益重要的价值。 开发者在本地运行 DeepSeek-V4-Flash-Vision-Exp，并在等待时改用 API，同时公开分享了完整游戏但没有直接提供代码仓库链接。由于发现游戏在笔记本上运行缓慢，作者后来加入了一些性能优化。

reddit · r/LocalLLaMA · /u/sloptimizer · 9月7日 18:27

**背景**: DeepSeek-V4-Flash-Vision-Exp 是 DeepSeek 推出的首个多模态实验模型，在以文本为重的 V4-Flash 基础上增加了视觉能力，同时保持相近的文本性能。它面向多模态 Agent 任务设计，因此能够理解截图并据此采取行动，从而支持“查看并修正”的资产生成、基于截图的动画序列脚本以及自动游戏测试等工作流。Reddit 帖子还提及阿里巴巴基于 Qwen4 架构的开放权重预览模型 Qwen3.8-Flash-Next，该模型此前一次性生成了一个 Cat-Hunt 游戏演示，促使作者进行此次对比尝试。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/deepseek-ai/DeepSeek-V4-Flash-Vision-Exp">deepseek-ai/DeepSeek-V4-Flash-Vision-Exp · Hugging Face</a></li>
<li><a href="https://api-docs.deepseek.com/news/news260821/">DeepSeek-V4-Flash-Vision-Exp Release: Multimodal API Now Live | DeepSeek API Docs</a></li>
<li><a href="https://codepick.dev/en/guides/deepseek-v4-flash-vision-guide/">DeepSeek V4 Flash Vision: Hands-On Guide to DeepSeek's First Vision Model | CodePick</a></li>

</ul>
</details>

**标签**: `#DeepSeek`, `#vision model`, `#game dev`, `#AI workflow`, `#LLM`

---