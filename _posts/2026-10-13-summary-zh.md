---
layout: default
title: "Horizon Summary: 2026-10-13 (ZH)"
date: 2026-10-13
lang: zh
---

> 从 67 条内容中筛选出 10 条重要资讯。

---

1. [Boole-1.7B：247MB 的 1-bit Qwen3-1.7B，性能超越 Bonsai-1.7B](#item-1) ⭐️ 8.0/10
2. [Launch HN：Agent37 推出超低价 AI 智能体沙箱](#item-2) ⭐️ 7.0/10
3. [Simon Willison 发布 web-edit 0.1a0：可由智能体启动、手机可用的文件编辑器](#item-3) ⭐️ 7.0/10
4. [SolidCraft：用 Rust 编写的开源参数化 CAD 库，支持 MCP](#item-4) ⭐️ 7.0/10
5. [Show HN：Personal Agent Proxy 为个人 AI 智能体集中管理授权](#item-5) ⭐️ 7.0/10
6. [Chkit 为 ClickHouse 带来类型安全的 schema、迁移与回填工具](#item-6) ⭐️ 7.0/10
7. [Lucid：用本地大模型把口述想法变成图表的开源工具](#item-7) ⭐️ 7.0/10
8. [Vibecheck：用 LLM 检查你是否理解 AI 写的代码的 GitHub 合并关卡](#item-8) ⭐️ 7.0/10
9. [MiniCPM-V 4.7 35B-A3B：该系列首个 MoE 视觉语言模型](#item-9) ⭐️ 7.0/10
10. [OpenCode「Cheepseek 行动」第三阶段：DeepSeek V4.1 Flash 额度提至 80 美元](#item-10) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Boole-1.7B：247MB 的 1-bit Qwen3-1.7B，性能超越 Bonsai-1.7B](https://www.reddit.com/r/LocalLLaMA/comments/1x452zj/boole17b_a_1bit_qwen317b_model_that_outperforms/) ⭐️ 8.0/10

Precision Numerics 发布了其首个模型 Boole-1.7B，这是 Qwen3-1.7B 的 1-bit 量化版本，打包后的权重仅 247 MB，比 BF16 小 13.9 倍，同时在 10 项任务的评测中保留了 BF16 模型平均得分的 85.9%。权重已上传至 Hugging Face（precision-numerics/Boole-1.7B），并提供 vLLM、llama.cpp 的示例代码以及浏览器内的本地聊天演示；官方称其性能超过 1-bit 的 Bonsai-1.7B，并接近 1.58-bit 的 Bonsai-1.7B。 这标志着可用语言模型进一步被压缩到 300 MB 以下的区间，从而能够在浏览器标签页、手机或可穿戴设备上运行，无需 GPU 或云端连接。如果 1-bit 模型能保住约 86% 的全精度质量，那么本地与边缘部署对于低延迟、常驻类任务就不再只是研究玩具，而是真正可行。 在 1-bit 量化中，每个权重被压缩为单个符号位，并按权重分组共享一个 FP16 scale 因子，因此昂贵的乘法运算可以被简化为加法；代价是精度损失，这里损失了约 14% 的 BF16 平均得分。Precision Numerics 指出浏览器演示仅面向英语、非 thinking 模式的低延迟任务，因此推理密集型或多语言场景明确不在该部署路径的适用范围之内。

reddit · r/LocalLLaMA · /u/d77chong · 10月12日 15:35

**背景**: 量化通过降低模型权重的数值精度来压缩体积；1-bit 量化是其中的极端情形，每个权重只保留符号（+1 或 −1），理论上可把内存降到 16-bit 模型的约 1/16。与之相近的是由 BitNet 带火的 1.58-bit（三值）方案，允许 −1、0、+1 三种取值，因此模型稍大但更准确。PrismML 的 Bonsai-1.7B 是已有的 1-bit 模型系列，面向智能眼镜和常驻后台任务，而 Boole-1.7B 通过量化阿里的 Qwen3-1.7B 与其直接竞争；要让这类模型顺畅运行，仍需 llama.cpp、MLX 等框架支持专门的低位宽 kernel。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://docs.prismml.com/models/bonsai-1-7b">Bonsai 1.7B - Bonsai - docs.prismml.com</a></li>
<li><a href="https://huggingface.co/prism-ml/Bonsai-1.7B-gguf">prism-ml/Bonsai-1.7B-gguf · Hugging Face prism-ml/Bonsai-1.7B-unpacked · Hugging Face bonsai-ollama/models/bonsai-1.7b at main · eSlider/bonsai ... Run an AI Model Locally in Your Browser — No GPU, No Cloud How to Run a 1.7B Parameter LLM in Your Browser With WebGPU PrismML — Concentrating intelligence</a></li>
<li><a href="https://en.wikipedia.org/wiki/1.58-bit_large_language_model">1.58-bit large language model - Wikipedia</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#quantization`, `#qwen3`, `#model-release`, `#llama.cpp`

---

<a id="item-2"></a>
## [Launch HN：Agent37 推出超低价 AI 智能体沙箱](https://news.ycombinator.com/item?id=50059096) ⭐️ 7.0/10

由前亚马逊工程师 Vishnu 创立、入选 YC F26 的 Agent37 在 Hacker News 上正式发布，提供用于运行 AI 智能体的沙箱服务，成本不到大多数沙箱厂商的 10%，客户平均每个沙箱每月花费 0.37 美元。该公司还宣布目前已能负担免费套餐，因为免费沙箱的基础设施成本平均为每用户每月约 0.05 至 0.10 美元。 对于任何需要长期运行或常驻 AI 智能体的人来说，沙箱算力是一项持续性开销，因此免费套餐和不到一美元的月费能让个人开发者和中小团队真正跑得起智能体。同时这也让本已拥挤的智能体沙箱赛道竞争更加激烈，资金雄厚的平台可能通过大幅让利来把用户锁定到利润更高的服务上。 Agent37 降低成本的主要手段包括：采用基于 gVisor 的隔离方案，在不同沙箱间共享主机内存而无需为每个实例预留整台虚拟机的内存；绕开超大规模云厂商，转而从 Hetzner、OVH 等更便宜的供应商租用主机；以及按内存而非 CPU 来选配服务器。代价是 gVisor 沙箱无法运行 Docker-in-Docker 或 Android 模拟器，因此针对这类工作负载另行提供完整虚拟机沙箱，价格更高但仍然较低。

hackernews · vishnukool · 10月12日 16:46

**背景**: 智能体“运行框架”（agent harness，也称 scaffolding）是包裹在大语言模型外的软件层，为模型提供工具调用、记忆、状态持久化和执行环境，从而把一个无状态的模型变成能够完成多步骤任务的智能体，Claude Code 和 OpenClaw 都是常见例子。由于这类框架需要执行任意代码、shell 命令和浏览器操作，通常要跑在沙箱里，也就是与宿主机隔离的环境中，以免智能体的行为影响主机。gVisor 是开源的“应用内核”，通过拦截系统调用来隔离容器，其隔离强度高于普通容器但弱于硬件虚拟机。发布帖还提到，Agent37 最初是 2026 年初众多“OpenClaw 套壳”公司之一。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://gvisor.dev/docs/">What is gVisor ? - gVisor</a></li>
<li><a href="https://en.wikipedia.org/wiki/Agent_harness">Agent harness</a></li>
<li><a href="https://en.wikipedia.org/wiki/OpenClaw">OpenClaw - Wikipedia</a></li>

</ul>
</details>

**社区讨论**: 评论整体偏正面，但对商业模式看法不一：有用户表示自己在原型中实际使用过 Agent37，效果出色、成本很有吸引力，只是冷启动稍显烦人；另有人将其价格与 boat.dev 作比较，认为更便宜但存储更少，并吐槽 Daytona 的额度在未达到 tier 3 之前几乎没用。也有更悲观的评论认为这是与资金雄厚对手的“内卷式价格战”，对方可以亏本卖沙箱来推广更粘性、更高利润的服务；还有重视安全的评论者指出 gVisor 的安全性弱于虚拟机，因此 Agent37 与基于虚拟机的沙箱做价格对比并非同类比较。

**标签**: `#ai-agents`, `#sandboxes`, `#developer-tools`, `#infrastructure`, `#agent-frameworks`

---

<a id="item-3"></a>
## [Simon Willison 发布 web-edit 0.1a0：可由智能体启动、手机可用的文件编辑器](https://simonwillison.net/2026/Oct/12/web-edit/) ⭐️ 7.0/10

Simon Willison 发布了 web-edit 0.1a0，这是一个小型的 Python Web 应用，提供浏览器界面来浏览和编辑某个文件夹中的文件。它由 Codex（配合 GPT-6 Astra Extra High）构建，设计上通过 Tailscale 运行，因此编码智能体可以把它启动起来，Willison 随后就能直接从手机上编辑文件——例如凭据文件。该版本已在 GitHub 上以 0.1a0 标签发布。 它针对的是智能体辅助开发中的一个具体痛点：编辑密钥或配置文件时，不必把这些内容送进大模型的上下文里。它展示的模式——让智能体启动一个小型本地 Web 工具，开发者再通过私有网状网络从手机访问——很可能会随着越来越多的编码工作经由智能体远程完成而流行起来。 编辑功能由 CodeMirror 6 驱动；Willison 表示曾考虑 Monaco，但它在移动端的体验仍不够好。界面支持按名称/大小/修改时间浏览文件夹、下载和删除文件、新建与上传文件（需指定目标文件夹并为每个文件设置文件名），以及将小于 2 MB 的图片内联显示。它目前是早期 alpha 版本（0.1a0），功能较为单一。

rss · Simon Willison · 10月12日 15:54

**背景**: Tailscale 是一种软件定义的网状 VPN，可在你自己的设备之间建立零配置的私有网络，这正是为什么在笔记本上启动的服务可以安全地从手机访问，而无需暴露到公网。Codex Remote 是配套功能，让你能在 ChatGPT 手机应用中启动、指导、批准和审阅运行在已连接 Mac 或 Windows 机器上的 Codex 任务。web-edit 正处在这一工作流的中间：由智能体启动它，而人类用它来操作那些不应让智能体看到的文件。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Tailscale">Tailscale</a></li>
<li><a href="https://learn.chatgpt.com/docs/remote">Codex Remote | ChatGPT Learn</a></li>

</ul>
</details>

**标签**: `#github`, `#ai-tools`, `#coding-agents`, `#python`, `#workflow-tips`

---

<a id="item-4"></a>
## [SolidCraft：用 Rust 编写的开源参数化 CAD 库，支持 MCP](https://github.com/bherbruck/solidcraft) ⭐️ 7.0/10

一位开发者发布了 SolidCraft——一个用 Rust 编写的开源参数化 CAD 库，托管在 GitHub 的 bherbruck/solidcraft 仓库中。它最突出的特点是内置对模型上下文协议（MCP）的支持，因此支持 MCP 的 AI 智能体可以把它当作工具直接调用。 MCP 已成为连接大模型智能体与外部工具的事实标准，因此一个通过 MCP 暴露自身能力的 CAD 内核，能把原本小众的工程领域变成 AI 智能体可以编程驱动的对象。这也反映了更广泛的趋势：领域专用库从一开始就提供面向智能体的接口，而不是事后才补上。 该项目是一个 Rust crate，因而具备这门语言在内存安全和性能上的特性，其目标场景是参数化建模——几何体由可调整的约束、尺寸和关系定义，而非固定形状。由于该 Hacker News 帖子仅获得 9 分且零评论，目前尚无社区对其功能完整度、成熟度以及 MCP 接口的具体实现方式进行验证。

rss · Show HN (self-made tools) · 10月13日 00:11

**背景**: 参数化 CAD 是一类设计软件，其模型由可调整的参数和约束驱动，改变一个尺寸就会自动更新整个模型，知名的开源例子是 SolveSpace。模型上下文协议（MCP）是 Anthropic 于 2024 年 11 月提出的开放标准，用于规范大语言模型等 AI 系统如何读取文件、执行函数并与外部工具共享数据，此后已被 OpenAI 和 Google DeepMind 等主要厂商采纳。MCP 服务器本质上让 AI 智能体可以把某个应用当作可调用的工具来使用。SolidCraft 把这两者结合起来：一个智能体可以通过 MCP 调用的 CAD 引擎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Model_Context_Protocol">Model Context Protocol</a></li>
<li><a href="https://en.wikipedia.org/wiki/SolveSpace">SolveSpace - Wikipedia</a></li>
<li><a href="https://modelcontextprotocol.io/">What is the Model Context Protocol (MCP)? - Model Context Protocol</a></li>

</ul>
</details>

**标签**: `#MCP`, `#open-source`, `#Rust`, `#AI-agents`, `#dev-tools`

---

<a id="item-5"></a>
## [Show HN：Personal Agent Proxy 为个人 AI 智能体集中管理授权](https://github.com/personalagentproxy/proxy) ⭐️ 7.0/10

一位开发者与朋友 Konsti 一起发布了一个名为 Personal Agent Proxy 的开源、可自托管访问层，它把所有第三方连接（邮箱、日历、工具）统一保存在一处，供多个个人 AI 智能体共享使用。该项目仅用几天时间开发完成，并以 Show HN 的形式发布到 Hacker News，当时只有 2 分和 0 条评论。 Muse、Instinct、Grokbot、Poke 等个人 AI 智能体都会要求用户重复授权同一个邮箱、日历和工具账号，而每个提供商最终都在重复开发同样的集成。一个可审计的共享授权层可以减少这种重复劳动，让用户对各智能体的行为拥有细粒度控制权，并能轻松切换不同的智能体应用而无需重新连接所有服务。 该代理把授权与智能体应用分离，可记录智能体的操作、支持细粒度权限，并特别注重自托管体验；作者表示他的 Instinct 现在在笔记本上拥有与 Claude Code 和 Codex 相同的工具。不过它仍是一个仅有数天历史的早期业余项目，尚缺乏社区验证和成熟文档。

rss · Show HN (self-made tools) · 10月12日 23:30

**背景**: 个人 AI 智能体是常驻运行、代表用户行事的助手，因此需要访问 Gmail、Google 日历等服务。这类访问通常通过 OAuth 授权，即第三方应用获取令牌以代表用户操作账号的标准协议。把凭据集中保存在一个组件中、只给智能体授予狭窄且可撤销权限的做法，与 IETF 的《Credential Broker for Agents》草案等新兴方案思路一致。这里的“自托管”指在自己的电脑或服务器上运行该代理，而不必信任厂商的云端。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/personalagentproxy/proxy">GitHub - personalagentproxy/proxy: Personal Agent Proxy is an ...</a></li>
<li><a href="https://github.com/personalagentproxy">Personal Agent Proxy - GitHub</a></li>
<li><a href="https://www.ietf.org/archive/id/draft-hartman-credential-broker-4-agents-00.html?trk=article-ssr-frontend-pulse_little-text-block">Credential Broker for Agents (CB4A)</a></li>

</ul>
</details>

**标签**: `#ai-agents`, `#open-source`, `#github`, `#self-hosting`, `#auth-permissions`

---

<a id="item-6"></a>
## [Chkit 为 ClickHouse 带来类型安全的 schema、迁移与回填工具](https://github.com/obsessiondb/chkit) ⭐️ 7.0/10

ObsessionDB 联合创始人 Marc 开源了 Chkit，这是一个基于 TypeScript 的工具，允许开发者用代码定义 ClickHouse 的 schema、据此生成包含 DDL 的迁移、在 CI 中检测 schema 漂移，并针对不兼容的 schema 变更自动生成回填（backfill）方案。它通过 `npm create chkit@latest` 安装，还能反向拉取已有的 ClickHouse 实例结构，让团队无需从零开始即可接入。 ClickHouse 在分析型负载中被广泛使用，但它的迁移与 schema 演进能力历来远弱于关系型/OLTP 数据库，管理成百上千张表和物化视图的团队往往只能靠临时脚本应付。Chkit 把 Drizzle 风格的「用 TypeScript 定义 schema」工作流引入 OLAP 场景，有望让分析管道的演进更安全、更易审查，也可能推动其他工具厂商为列式数据库提供类似的类型安全工作流。 其工作流是：用 TypeScript 定义带类型的表、物化视图和列类型；生成包含 DDL 的迁移，把实例推进到目标状态；由 CI 检查 schema 漂移；将迁移应用到生产；随后在写入数据时使用生成的类型，确保数据符合预期结构。作者指出，最棘手的部分是在 schema 变更不向后兼容时，生成通过中间表完成数据回填的正确执行序列，而这在大表规模下确实是个难题。

rss · Show HN (self-made tools) · 10月12日 21:55

**背景**: ClickHouse 是一个面向在线分析处理（OLAP）的开源列式 SQL 数据库管理系统，专为在超大规模数据集上执行实时分析查询而设计。Drizzle ORM 是一个轻量级 TypeScript ORM，以「直接在 TypeScript 中定义 schema」并生成可预测、完全类型安全的 SQL 而闻名，与 Prisma 这类 schema 优先的方案形成对比。回填（backfill）是指把缺失或需要修正的历史数据补写进某个数据集或系统的过程；当 schema 变更导致数 TB 级表中的既有行失效时，回填就会变成一项重要的工程任务。Chkit 把这两套思路结合起来：把来自 Drizzle 世界的「TypeScript 定义 schema」用在 ClickHouse 的分析表和物化视图上。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://clickhouse.com/docs/get-started/about/intro">What is ClickHouse? - ClickHouse Documentation</a></li>
<li><a href="https://orm.drizzle.team/docs/overview">Drizzle ORM - Why Drizzle?</a></li>
<li><a href="https://stackoverflow.com/questions/70871818/what-is-backfilling-in-data">database - What is backfilling in data ? - Stack Overflow</a></li>

</ul>
</details>

**标签**: `#ClickHouse`, `#database-migrations`, `#TypeScript`, `#open-source`, `#developer-tools`

---

<a id="item-7"></a>
## [Lucid：用本地大模型把口述想法变成图表的开源工具](https://github.com/triggeredcode/lucid) ⭐️ 7.0/10

一位开发者在 Show HN 上发布了 Lucid，这是一款开源的辅助功能与生产力工具，能把粗糙的口述输入转换成结构化的笔记、图表和表格，并且生成后还可以继续编辑。它通过 LM Studio 调用本地 AI 模型运行，发布时同时提供了演示视频、GitHub 仓库和项目官网。 这是本地大模型用于辅助功能工具的一个具体案例：即使有人暂时或永久无法有效打字，也能通过语音产出结构化的设计产物。由于模型在本地而非云端运行，口述内容留在用户自己的电脑上，这对涉及专有系统设计的工作尤为重要。 语音输入尚未内建——作者目前仍需借助单独的听写应用，因此语音转文字这一步仍是手工变通方案。此外它是一个个人独立副业项目，没有公开的基准测试，所以其输出质量以及与成熟图表/笔记工具相比的成熟度尚未得到验证。

rss · Show HN (self-made tools) · 10月12日 21:39

**背景**: LM Studio 是一款在个人电脑上本地运行大语言模型的桌面软件，它以 llama.cpp 作为推理引擎来加载 GGUF 格式的模型，并提供一个带 OpenAI 兼容 API 的本地服务，供其他应用调用。以这种方式运行模型无需把提示词发送给云端服务商，但模型能力受限于用户自身的硬件以及所选择下载的开源权重模型。Show HN 是 Hacker News 上开发者发布自己项目以获取反馈的板块。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/LM_Studio">LM Studio</a></li>
<li><a href="https://lmstudio.ai/download">Download LM Studio - Mac, Linux, Windows</a></li>
<li><a href="https://you.com/resources/run-llm-locally">You.com | How to Run an LLM Locally : A Practical Walkthrough</a></li>

</ul>
</details>

**标签**: `#ai-tools`, `#github-repo`, `#local-llm`, `#productivity`, `#system-design`

---

<a id="item-8"></a>
## [Vibecheck：用 LLM 检查你是否理解 AI 写的代码的 GitHub 合并关卡](https://github.com/bhurghundii/vibecheck.dev) ⭐️ 7.0/10

一位开发者发布了 Vibecheck，这是一个自托管的 GitHub 合并关卡（merge gate），通过 LLM 向 PR 作者提问，在发现疑似把 AI 生成代码原样提交、作者并不理解的情况下阻止合并。它采用自带密钥（BYOK，Anthropic）模式，代码仓库公开在 GitHub 上，并附有两个演示 PR，分别展示被拦截和顺利通过的情况。 随着 AI 编程助手让生成大量 pull request 变得轻而易举，评审者越来越多地面对团队中无人真正理解的代码；在合并前强制要求作者理解自己代码的工具，正好切中一个真实且日益严重的工作流问题。如果这类关卡被广泛采用，可能会改变团队对待 AI 辅助贡献的作者身份、责任归属和评审负担的方式。 Vibecheck 需要自行部署，并要求使用者提供自己的 Anthropic API 密钥，因此部署成本与推理费用都由采用方承担；该项目仍处于早期阶段，其 Hacker News 帖子仅有 1 分且没有评论，尚未获得社区验证。

rss · Show HN (self-made tools) · 10月12日 21:13

**背景**: 合并关卡（merge gate）是挂在代码仓库上的一种自动检查，在 pull request 创建时触发，可以阻止 PR 合并直到某个条件被满足——这与 CI 测试、代码检查（lint）或必需审批所用的机制相同。BYOK（bring your own key，自带密钥）意味着该工具并不转售模型访问权限，而是由用户接入自己在 Anthropic 等服务商处的账号，凭证和账单仍由自己掌控。在本例中，这道关卡并非单元测试，而是由 LLM 对作者进行提问式审查，目的是区分真正的理解与对模型输出的盲目复制粘贴。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/BYOK">BYOK</a></li>
<li><a href="https://github.com/ShunsukeHayashi/mergegate">GitHub - ShunsukeHayashi/mergegate: MergeGate: deterministic ...</a></li>

</ul>
</details>

**标签**: `#AI code review`, `#developer tools`, `#GitHub`, `#LLM workflows`, `#open source`

---

<a id="item-9"></a>
## [MiniCPM-V 4.7 35B-A3B：该系列首个 MoE 视觉语言模型](https://www.reddit.com/r/LocalLLaMA/comments/1x47taj/openbmbminicpmv4735ba3b/) ⭐️ 7.0/10

openbmb 发布了 MiniCPM-V 4.7 35B-A3B，这是 MiniCPM-V 视觉语言系列中首个混合专家（MoE）模型，并已在 Hugging Face 上发布了 GGUF 量化权重。官方宣称该模型是首个能在端侧流畅运行的开源 MoE 视觉语言模型，在 iPhone 17 Pro Max 上解码速度达到 13+ tokens/s。 它推进了多模态大模型的性能-效率帕累托前沿：MoE 架构每个 token 只激活 350 亿参数中的一小部分，使大规模视觉语言能力在手机和本地设备上成为可能。同时它首日即支持 vLLM、SGLang、llama.cpp 和 Ollama，降低了开发者无需云端 GPU 即可构建和微调多模态应用的门槛。 端侧流畅运行依赖三项技术：Lookahead Expert Scheduling（LES，前瞻专家调度），通过协调专家权重的加载来避免权重存于 SSD 时造成的生成停顿；细粒度逐层量化；以及集成 DSpark 投机采样。视觉编码器采用 LLaVA-UHD v4 的 ViT 内部早期压缩技术，并支持 4x/16x 混合视觉 token 压缩；模型提供 GGUF、BNB、AWQ、GPTQ 及 FP8 量化版本，并支持 SWIFT、LLaMA-Factory 以及 Self-Replay 微调。

reddit · r/LocalLLaMA · /u/Skyline34rGt · 10月12日 17:16

**背景**: MoE（混合专家）模型把前馈层拆分成许多“专家”子网络，每个 token 只路由到其中少数几个，因此总参数 350 亿的模型每 token 可能只用到约 30 亿参数——这正是“35B-A3B”命名的由来，其中 A3B 表示 30 亿激活参数。GGUF 是 llama.cpp 项目于 2023 年 8 月推出的二进制文件格式，将张量和元数据打包进单个文件，现已成为本地推理量化模型分发的事实标准。投机采样则通过先用小模型廉价地草拟若干 token，再用完整模型一次性验证，从而加速生成。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/GGUF">GGUF</a></li>
<li><a href="https://x.com/OpenBMB/status/2109694597345796544">OpenBMB on X: "⚡ Lookahead Expert Scheduling: Making On ...</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#vision-language-model`, `#moe`, `#gguf`, `#on-device-inference`

---

<a id="item-10"></a>
## [OpenCode「Cheepseek 行动」第三阶段：DeepSeek V4.1 Flash 额度提至 80 美元](https://t.me/zaihuapd/44361) ⭐️ 7.0/10

OpenCode 宣布「Cheepseek 行动」已进入第三阶段，将通过 OpenCode 提供的 DeepSeek V4.1 Flash 使用额度提升到价值 80 美元。公告本身并未说明截止日期、完整的适用条件，也没有给出直接领取该额度的链接。 免费或大幅补贴的模型额度是开发者零成本试用新型编程智能体的主要途径，因此额度提高到 80 美元能显著降低在智能体工作流中试用 DeepSeek V4.1 Flash 的门槛。这也说明 OpenCode 愿意不断加码基于 DeepSeek 的促销，以在与竞品智能体和 IDE 争夺用户时保持竞争力。 此次调整是建立在第二阶段的基礎上：第二阶段曾针对每月 10 美元的 OpenCode Go 订阅用户，将 DeepSeek V4.1 Flash 的月度额度从 15 美元的基线永久提升到 60 美元，因此新的 80 美元是目前公布过的最高档。该帖并未说明这 80 美元额度适用于所有 OpenCode 用户还是仅限付费订阅用户，也没有说明已有额度是否会自动升级。

telegram · zaihuapd · 10月12日 13:17

**背景**: OpenCode 是一款开源 AI 编程智能体，以 Go 语言编写的 CLI 应用形式发布，提供终端交互界面（TUI），可对接多种 AI 模型来辅助完成编程任务；其项目主页称已获得超过 20.8 万个 GitHub star，月活开发者超过 1600 万。DeepSeek V4.1 Flash 是中国 AI 公司 DeepSeek 推出的模型，通过其 API 以 deepseek-flash 这一模型名提供服务，原生支持多模态，取代了已下线的 V4-Flash 和 V4-Flash-Vision-Exp。所谓「Cheepseek」是 OpenCode 的促销活动名称（取自 cheap 与 DeepSeek 的谐音组合），把折扣或免费的 DeepSeek 模型用量打包进智能体；而「使用额度」指的是以美元计价的 API 可用金额，用户在自行付费前可先消耗这部分额度。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://freeaiapi.org/articles/opencode-longcat-cheepseek-guide">OpenCode Dual Breakthrough: LongCat 2.5 Free... — Free AI API</a></li>
<li><a href="https://www.deepseek.com/en/news/deepseek-v4-1-flash/">DeepSeek | Introducing DeepSeek-V4.1-Flash: smarter, faster ...</a></li>
<li><a href="https://opencode.ai/">OpenCode | The open source AI coding agent</a></li>

</ul>
</details>

**标签**: `#AI福利`, `#free-credits`, `#DeepSeek`, `#OpenCode`, `#coding-agent`

---