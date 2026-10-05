---
layout: default
title: "Horizon Summary: 2026-10-05 (ZH)"
date: 2026-10-05
lang: zh
---

> 从 48 条内容中筛选出 9 条重要资讯。

---

1. [Strata 让 125B 的 Qwen 3.8 Flash Next 在单张 RTX 4090 上跑到 124 T/s](#item-1) ⭐️ 8.0/10
2. [Show HN：SCM 为 macOS 上每一张照片和每一帧视频带来 AI 语义搜索](#item-2) ⭐️ 8.0/10
3. [Show HN：Shlexball 用本地 1.5B 模型在 Mac 上按描述找文件](#item-3) ⭐️ 8.0/10
4. [Show HN：EditUI 让浏览器内也能实现 Cursor/Claude Design 式界面编辑](#item-4) ⭐️ 7.0/10
5. [Show HN：开源 AI 驱动 PDF 脱敏工具 Redactpdf.ai](#item-5) ⭐️ 7.0/10
6. [爱好者分享本地后训练 Yandex AliceAI-80B-A3B 的第 4 次进展](#item-6) ⭐️ 7.0/10
7. [全本地跑酷 Demo：GLM 5.3 Flash 经 vLLM TP2 跑在双 DGX Spark 上](#item-7) ⭐️ 7.0/10
8. [开发者仅用 865 亿 token 从零训练出 3.87B MoE 模型](#item-8) ⭐️ 7.0/10
9. [Google 发布 VeriHarness：面向长程任务的自我验证框架](#item-9) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Strata 让 125B 的 Qwen 3.8 Flash Next 在单张 RTX 4090 上跑到 124 T/s](https://github.com/Niko1221/Strata) ⭐️ 8.0/10

Hacker News 上出现了一个名为 Strata 的项目（github.com/Niko1221/Strata），它让 125B 参数的 Qwen 3.8 Flash Next 模型能够在消费级显卡上运行；有评论者报告称，在单张 Nvidia RTX 4090 搭配 128GB DDR5 内存和 Ryzen 7950X3D 的机器上达到了 124 tokens/秒。另有用户 AntiRush 表示，在 RTX 6000 Pro 上运行该模型的 Q4 量化版本，解码速度约 255 tokens/秒、预填充约 1,251 tokens/秒，并可支持 4 路并发流。 在单张消费级显卡上以每秒 100+ token 的速度运行 125B 级别的多模态 MoE 模型，让个人开发者和中小团队无需服务器级硬件或云端租用就能本地跑大模型。这也凸显了当前亚 4-bit 量化浪潮的核心矛盾：显存占用大幅下降，但模型精度（尤其是视觉任务上的精度）会出现可测量的损失。 最具体的负面证据来自评论者 Jackson__：他做了一个 50 张图片的视觉基准测试，要求模型输出目标物体的精确坐标，Strata 的中位误差为 154.8 像素（平均 168.8），而在 llama.cpp 上使用完全相同的 GGUF 权重和视觉适配器，中位误差仅为 46.5 像素（平均 81.4）。此外，报告中 124 T/s 的速度来自一套特定配置（RTX 4090、128GB DDR5、Ryzen 7950X3D），因此不同机器之间的吞吐量数字并不能直接横向比较。

hackernews · snehesht · 10月4日 12:51 · [社区讨论](https://news.ycombinator.com/item?id=49953495)

**背景**: Qwen 3.8 Flash Next 是 Qwen 推出的开放权重多模态混合专家（MoE）模型，基于全新的 Qwen 4 架构，总参数 125B，另加 51B 的 N-gram 嵌入，但每个 token 仅激活约 6B 参数；MoE 设计使得即便模型总量巨大，单 token 的计算量仍保持较低。量化则把模型权重压缩到更少比特（4-bit，亚 4-bit 时更低）以便塞进有限的显存，代价是精度有所损失。Strata 更应被理解为一个专门针对该 Qwen 模型调优的运行时，而非像 llama.cpp 那样的通用推理引擎。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/qwenlm/qwen3.8-flash-next">GitHub - QwenLM/ Qwen 3 . 8 - Flash - Next : Qwen 3 . 8 - Flash - Next is the...</a></li>
<li><a href="https://huggingface.co/Qwen/Qwen3.8-Flash-Next">Qwen / Qwen 3 . 8 - Flash - Next · Hugging Face</a></li>
<li><a href="https://unsloth.ai/docs/models/qwen3.8-next">Qwen 3 . 8 - Flash - Next : How to Run Locally | Unsloth Documentation</a></li>

</ul>
</details>

**社区讨论**: 社区整体态度是既感兴趣又存疑。snehesht 与 AntiRush 等支持者表示效果出乎意料地好、吞吐量可观；而 a11r 对低于 4-bit 的量化持怀疑态度，jacquesm 则警告各大 LLM 论坛正被 Strata 链接刷屏，蜜月期过后是否还站得住脚有待观察。最有力的反证来自 Jackson__ 的硬核基准测试：在相同权重下，Strata 的视觉坐标定位精度大约比 llama.cpp 差三倍。

**标签**: `#local-llm-inference`, `#quantization`, `#github-repo`, `#consumer-hardware`, `#qwen`

---

<a id="item-2"></a>
## [Show HN：SCM 为 macOS 上每一张照片和每一帧视频带来 AI 语义搜索](https://github.com/allenv0/SCM) ⭐️ 8.0/10

一位开发者在 Hacker News 的 Show HN 板块发布了 SCM，这是一个开源 macOS 应用，能够对整个照片库以及本地视频的每一帧进行 AI 驱动的语义搜索——后者是相对少见的能力。该项目通过 GitHub 仓库 github.com/allenv0/SCM 发布，在此次精选资讯中获得 8.0/10 的评分。 它把 Google Photos 等云服务普及的那种自然语言、基于内容的媒体搜索能力搬到了本地硬件上，用户可以直接用语义查询自己的文件（例如“有棕榈树的房子”），而无需把任何内容上传到服务器。对于拥有大量个人媒体资料的 macOS 用户而言，这是一个可直接上手、且能保护隐私的订阅制相册服务替代方案。 由于逐帧建立索引的成本很高，视频抽帧率是决定总耗时的主要因素——一位评论者称，对 1.2 万个视频按每秒 1 帧采样耗时数天，而只采样关键帧则能在 M1 机器上压缩到一个通宵完成。对于图片中的文字识别，评论者强烈建议使用 Apple 的端上 Vision 框架而非 Tesseract，因为它在速度和准确率上都更优。

hackernews · allenleee · 10月4日 09:24 · [社区讨论](https://news.ycombinator.com/item?id=49952111)

**背景**: 语义（或称“近似”）媒体搜索通常依赖 CLIP 这类多模态嵌入模型，它把图像和文本查询映射到同一个向量空间中，因此像“厨房”这样的查询可以匹配到从未被打上该标签的照片。OCR（光学字符识别）则是另一层能力，用于从照片（例如路牌或截图）中提取可读文字，使其也能被索引和检索。视频会让问题更复杂：模型只能看到被抽取出来的孤立帧，而采样的密度直接决定了索引耗时与可检索内容覆盖度之间的取舍。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://boardsnap.ai/blog/on-device-ocr-is-already-good-enough/">On-Device OCR Is Already Good Enough — BoardSnap Field Notes</a></li>
<li><a href="https://en.wikipedia.org/wiki/Tesseract_OCR">Tesseract OCR</a></li>
<li><a href="https://bockdev.com/posts/native-video-understanding-beyond-stitched-photo-analysis.html">Native Video Understanding: Beyond "Stitched Photo..." | Bockdev</a></li>

</ul>
</details>

**社区讨论**: 评论整体建设性较强：有人强烈建议把 OCR 换成 Apple 的 Vision 框架，并指出 Claude、DeepSeek、Qwen、Codex 等多个大模型也推荐它而非 Tesseract。另一些人提出了相关问题——大模型是否会削弱小项目的版权保护、Immich 作为跨平台替代方案的推荐，以及基于 CLIP 的亲身经验说明 M1 上抽帧策略“才是决定性因素”。还有用户询问它在面对约 2000 张素材照片、检索“有棕榈树的房子”或“沙漠西南部风景”时的实际效果如何。

**标签**: `#AI search`, `#computer vision`, `#macOS`, `#GitHub project`, `#local AI`

---

<a id="item-3"></a>
## [Show HN：Shlexball 用本地 1.5B 模型在 Mac 上按描述找文件](https://shlexball.com/) ⭐️ 8.0/10

Shlexball 在 Show HN 上发布：它是一个本地运行的 1.5B 参数语言模型，能把对文件的自然语言描述转换成 bash 命令，从而在 Apple Silicon Mac 上定位该文件，并支持检索 PDF 和 Word 文档内部的文本。作者同时发布了自建的 FindBench 基准测试，包含 312 条模型在训练中从未见过的自然语言请求，并声称其表现超过了 Gemini 3.8 Flash 等云端模型和 310 亿参数的 Gemma 模型。 它表明在狭窄的特定任务上，一个极小、专用于单一任务的本地模型可以胜过体量大得多的云端模型，这对不愿为琐碎任务消耗付费编程助手额度的用户很有意义。它也契合了隐私优先的端侧推理趋势：API 密钥、私人文档等敏感文件无需离开本地电脑。 该模型专为 Apple Silicon 设计，内存占用很小，既能搜索文件名，也能搜索 PDF 和 Word 文件内部的文本，并提供 30 次免费搜索。主要需要注意的是，“优于 Gemini 和 Gemma”的说法完全基于作者自建的 FindBench 基准测试，而且该工具是单一用途的文件搜索器，并非通用助手。

rss · Show HN (self-made tools) · 10月4日 23:05

**背景**: 在 macOS 上，按内容查找文件通常要用 Spotlight 或 find、mdfind 之类的命令行工具，前提是你已经知道确切的文件名、路径或元数据。15 亿参数的模型足够小，可以完全在笔记本上运行，而 Apple Silicon 的统一内存架构让端侧推理无需独立显卡也能实用。FindBench 会用包含正确文件以及刻意设置相似干扰项的测试文件夹，考察模型是否选对了搜索方式和查询条件；因此 312 条请求的规模只能视为参考性结果，而非定论。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://shlexball.com/">Shlexball: Find files on your Mac by describing them</a></li>
<li><a href="https://insiderllm.com/guides/best-local-llms-mac-2026/">Best Local LLMs for Mac in 2026 — M1 through M5 Tested | InsiderLLM</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#ai-tools`, `#macos`, `#small-models`, `#show-hn`

---

<a id="item-4"></a>
## [Show HN：EditUI 让浏览器内也能实现 Cursor/Claude Design 式界面编辑](https://www.editui.app/) ⭐️ 7.0/10

EditUI 在 Hacker News 上以 Show HN 形式发布，是一款无需安装、直接在浏览器中运行的 UI 编辑工具，提供类似 Cursor 与 Claude Design 的可视化编辑体验。该帖直接附上了可访问的线上站点 editui.app，任何人都能立刻试用。 它处在两股快速演进的浪潮交汇处：一类是 Cursor 这样的 AI 编程代理，另一类是 Claude Design 这样由提示词生成界面的设计工具，而 EditUI 把这种能力搬进了无需安装的浏览器工作流，降低了设计师和开发者迭代界面的门槛。如果这条路走得通，未来可视化地调整界面并让 AI 生成对应代码，可能就在同一个浏览器标签页里完成。 该帖提供的技术信息非常有限：没有代码仓库，没有说明底层使用了哪些 AI 模型或框架，没有价格信息，也没有解释生成的界面如何导出回代码库。同时它的初始热度极低（Hacker News 上仅 1 分、1 条评论），因此这款工具尚未经过验证，其能力最好通过直接试用网站来判断。

rss · Show HN (self-made tools) · 10月4日 23:33

**背景**: Cursor 是 Anysphere 推出的 AI 代码编辑器，开发者可以用自然语言指令来编写和修改代码，既支持精准的局部编辑，也支持更自主的代理式改动。Claude Design 则是 Anthropic 的设计能力，可以把一句提示词变成界面、原型和幻灯片，并支持在 Claude 对话中进行画布内编辑。因此“Cursor/Claude Design 式”这一说法，指的是由 AI 交互式辅助完成界面工作的工具，而 EditUI 的卖点就是把这类编辑从桌面应用搬到浏览器里。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Cursor_(code_editor)">Cursor (code editor)</a></li>
<li><a href="https://claude.com/product/design">Claude Design | Turn Ideas into Design | Claude by Anthropic</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#UI editing`, `#dev tools`, `#browser-based`, `#Show HN`

---

<a id="item-5"></a>
## [Show HN：开源 AI 驱动 PDF 脱敏工具 Redactpdf.ai](https://redactpdf.ai/) ⭐️ 7.0/10

一位开发者在 Hacker News 的 Show HN 栏目发布了 Redactpdf.ai，这是一个基于 AI 的开源 PDF 脱敏工具，并提供了可直接访问的线上站点 redactpdf.ai，任何人都能立刻试用。该帖子目前很新、关注度极低（仅 3 分、1 条评论），因此这个项目尚未经过更广泛社区的实际检验。 手动 PDF 脱敏既繁琐又容易出错，现实中曾多次因为黑色遮盖框并未真正写入文件而导致信息泄露，因此一款能自动识别敏感内容的开源 AI 工具确实切中了法律、医疗和人力资源等场景的合规需求。同时，由于它是开源且可自行部署的，也为那些必须把机密文件上传到第三方服务器的纯云端脱敏服务提供了替代方案。 该帖没有说明所使用的底层模型、识别准确率、支持语言、文件大小限制或开源许可证，因此潜在用户需要直接查看仓库和站点后再决定是否依赖它。对任何脱敏工具而言一个关键技术要点是：删除文字必须真正移除或栅格化内容，而不只是画一个矩形遮盖，因为被覆盖的文字往往仍可从 PDF 的底层内容流中提取出来。

rss · Show HN (self-made tools) · 10月4日 23:18

**背景**: PDF 脱敏是指在文件共享之前永久删除或不可逆地遮盖其中的敏感信息，例如姓名、账号、病历和个人身份标识。过去这项工作靠手工完成：用户在编辑器里用黑框盖住文字，但在若干广为人知的事件中，原文依然可以被还原，因为那层黑框只是视觉图层。基于 AI 的脱敏工具试图把识别环节自动化，扫描文档中的个人身份信息（PII）或其他受监管数据并标记出来供人工复核，这一点也与 GDPR 和 HIPAA 的合规流程密切相关。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://grokipedia.com/page/PDF_Redaction">PDF Redaction</a></li>
<li><a href="https://redactionpdf.com/">PDF Redaction Tool for Secure Document Sharing | RedactionPDF</a></li>

</ul>
</details>

**标签**: `#AI tools`, `#open source`, `#PDF redaction`, `#document automation`, `#Show HN`

---

<a id="item-6"></a>
## [爱好者分享本地后训练 Yandex AliceAI-80B-A3B 的第 4 次进展](https://www.reddit.com/r/LocalLLaMA/comments/1wxlytt/update_4_post_training_yandexaliceai80ba3b/) ⭐️ 7.0/10

一位爱好者开发者（u/jjusko20）发布了为 Yandex 的 AliceAI-80B-A3B-Base 构建 instruct/agentic 微调版本的第 4 次进展：第一轮 SFT 确实让模型学会了思维链推理和对话式回复，但由于指令数据不足而严重欠拟合，因此 checkpoint #1 被评价为“基本没用”且不予发布。此后他通过接入多个 base URL、在 3 个实例上各跑 4 个并行 worker，把本地合成数据生成速度从约 80 tokens/秒提升到约 240 tokens/秒，并正在生成第二个约 500 万 token、覆盖面更广的通用指令数据集，以取代原先偏代码方向的配比。 这说明仅用消费级/准专业级硬件（3 块 32GB 的 V100）和本地生成的数据，就能对 80B 的混合专家模型做后训练，而这一流程正被越来越多的爱好者和小型实验室用来改造开放权重基座模型。作者坦率地公开了第一轮失败，并将其归因于数据覆盖广度不足而非硬件限制，这对其他尝试同类蒸馏微调的人是有价值的现实参照。 最初的约 500 万 token SFT 数据集过窄且偏代码方向，导致含糊的提问或与训练数据精确匹配度较低的提示会生成乱码；解决方案是再补充约 500 万 token 覆盖更广的通用指令数据，并在 checkpoint 1.0 alpha 之上以更低学习率继续训练。训练数据由作者自研的 off-policy 蒸馏引擎 sftmill 生成，他已将其作为开源分支发布在 github.com/jackjusko/sftmill；目前尚未发布任何可用的 checkpoint 或权重仓库。

reddit · r/LocalLLaMA · /u/jjusko20 · 10月4日 17:55

**背景**: Yandex 的 AliceAI-Foundation-80B-A3B-Base 是一个开放权重（Apache 2.0）的语言模型，完全从零训练，而非基于 Qwen 或 Llama 的权重初始化；名称中的“A3B”表示它是 800 亿参数的混合专家（MoE）架构，但每个 token 只激活约 30 亿参数，因此相对总规模而言推理成本较低。SFT（监督微调）是把原始基座模型变成可用 instruct/对话模型的阶段，方式是拿提示—回复配对数据训练；而“思维链”指模型在给出答案前先生成中间推理步骤。作者正把这一推理行为从更大的教师模型（Qwen 3.8 27B）蒸馏成合成训练数据，属于 off-policy 蒸馏路线，然后用这些数据在本地微调 Yandex 基座模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/yandex/AliceAI-Foundation-80B-A3B-Base">yandex / AliceAI -Foundation- 80 B - A 3 B -Base · Hugging Face</a></li>
<li><a href="https://dev.to/klukyanov/yandex-open-sourced-an-80b-model-trained-from-scratch-whats-inside-and-where-it-wins-3c3g">Yandex open-sourced an 80 B model trained from... - DEV Community</a></li>
<li><a href="https://ai-manual.ru/article/entuziast-doobuchil-yandex-aliceai-80b-a3b-na-sinteticheskih-dannyih-i-gotovit-gguf-kvantyi-dlya-lokalnogo-zapuska/">Энтузиаст дообучил Yandex AliceAI-80B-A3B на... | AiManual</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#fine-tuning`, `#SFT`, `#mixture-of-experts`, `#chain-of-thought`

---

<a id="item-7"></a>
## [全本地跑酷 Demo：GLM 5.3 Flash 经 vLLM TP2 跑在双 DGX Spark 上](https://www.reddit.com/r/LocalLLaMA/comments/1wxp21n/fully_local_little_parkour_sim/) ⭐️ 7.0/10

一位开发者公开了完全本地的搭建方案：在双 NVIDIA DGX Spark 上通过 vLLM 张量并行（TP2）运行 GLM 5.3 Flash，并把配置配方发布在公开的 GitHub 仓库中。同时他还展示了一个用 Claude Code 作为脚手架、以 260k 上下文在周末做出来的跑酷模拟 demo，实测预填充约 1500 tokens/s、100k 上下文下解码约 40 tokens/s。 它为自托管推理和 agent 开发者提供了可复现的具体配方与真实吞吐数据，表明双机桌面级 AI 设备如今已能完全离线达到"够用"的交互速度。这会把实际的 agent 开发从云端 API 推向家庭实验室硬件，不过硬件成本限制了能照做的人群。 公开的数据大致是预填充 1500 tokens/s、100k 上下文下解码 40 tokens/s，agent 脚手架使用的是 260k 上下文窗口。主要限制在硬件：该配方需要两台 DGX Spark，而 NVIDIA 官方最多只支持两台设备直连，因此这是一个小众且高成本的配置，多数读者难以复现。

reddit · r/LocalLLaMA · /u/-dysangel- · 10月4日 20:00

**背景**: GLM（General Language Model）是中国公司 Z.ai 推出的一系列开放权重的大语言模型，多数权重以 MIT 或 Apache 2.0 许可发布，既可本地运行也可云端运行；GLM-5.3-Flash 是围绕能力与效率重新设计的版本，支持最高 100 万 token 的上下文窗口。vLLM 是广泛使用的开源推理服务框架，张量并行（TP）会把同一个模型切分到多块 GPU 上协同推理，这里的 TP2 就是把模型拆分到两台 DGX Spark 上。NVIDIA DGX Spark 则是基于 Blackwell 的紧凑型"个人 AI 超级计算机"，面向本地 AI 工作负载。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://huggingface.co/zai-org/GLM-5.3-Flash">zai-org/ GLM - 5 . 3 - Flash · Hugging Face</a></li>
<li><a href="https://www.nvidia.com/en-us/products/workstations/dgx-spark/">Personal AI Supercomputer Powered by Blackwell | NVIDIA DGX Spark</a></li>
<li><a href="https://grokipedia.com/page/NVIDIA_DGX_Spark">NVIDIA DGX Spark</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#vllm`, `#glm`, `#self-hosted-inference`, `#agent-scaffolding`

---

<a id="item-8"></a>
## [开发者仅用 865 亿 token 从零训练出 3.87B MoE 模型](https://www.reddit.com/r/LocalLLaMA/comments/1wxiy8y/i_trained_a_387b_moe_145b_active_from_scratch_on/) ⭐️ 7.0/10

一位开发者发布了 Apex-2：一个仅解码器架构的混合专家（MoE）模型，总参数 3.87B、每 token 激活 1.45B，完全不依赖外部基础权重、从零开始用 865 亿预训练 token 加约 25 亿 SFT token 训练而成。模型权重已发布在 Hugging Face 上，可通过 Qwen3MoeForCausalLM 映射在 transformers 或 vLLM 中加载，作者同时公布了基准测试结果与训练经验。 它提供了一个具体且可复现的数据点：从零训练的 MoE 模型在单卡到双卡预算下也能在代码任务上追平使用远多 token 的基线——Apex-2 仅用约 0.087 万亿预训练 token，其 HumanEval+ 成绩就与用了 18 万亿 token 的 Qwen2.5-1.5B 相当。作者报告的负面结果（DPO 让回答变长并损害了代码、数学和 IFEval 表现）对计划在小模型上做后训练的人同样有参考价值。 该模型采用 32 层、d_model 2048、GQA（16 个查询头 / 4 个 KV 头）、16 个专家且 top-4 路由、4096 token 上下文以及 Qwen3 分词器（15.1 万词表）；预训练先在一块 GH200 上运行，随后借助 DiLoCo 扩展到两块。作者公布的分数（SFT、贪心解码、聊天模板）包括 HumanEval 43.9、HumanEval+ 41.5、MBPP 56.3、GSM8K 零样本 CoT 32.4、MATH-500 21.0、IFEval 44.7 和 5-shot MMLU 28.6；同时作者坦承模型以英文为主、知识薄弱且经常产生幻觉，在 LiveCodeBench 中等/困难题目上接近零分，并且仅支持 4k 上下文。

reddit · r/LocalLLaMA · /u/Prestigious-Taste-63 · 10月4日 15:50

**背景**: 混合专家（MoE）用多个并行的“专家”子网络替代稠密前馈层，并通过路由器把每个 token 只送给其中少数几个专家，因此总参数量可以很大而单 token 计算量保持较小——这正是本模型中 3.87B 总参数与 1.45B 激活参数的由来。分组查询注意力（GQA）让多个查询头共享同一个 key/value 头，从而降低 KV 缓存占用；DiLoCo 是一种分布式训练算法，允许连接较弱的设备各自独立训练、只在外部循环中低频同步，从而大幅降低通信开销。DPO（直接偏好优化）是一种后训练对齐方法，直接用“优选/劣选”答案对来微调模型，而无需单独训练奖励模型。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/abs/2311.08105">DiLoCo : Distributed Low-Communication Training of Language Models</a></li>
<li><a href="https://cyrilzakka.github.io/llm-playbook/nested/gqa.html">Grouped - Query Attention ( GQA ) - The Large Language Model...</a></li>
<li><a href="https://hackernoon.com/direct-preference-optimization-your-language-model-is-secretly-a-reward-model">Direct Preference Optimization : Your Language Model... | HackerNoon</a></li>

</ul>
</details>

**标签**: `#LLM training`, `#MoE`, `#open-source models`, `#benchmarks`, `#LocalLLaMA`

---

<a id="item-9"></a>
## [Google 发布 VeriHarness：面向长程任务的自我验证框架](https://arxiv.org/abs/2610.00972v1) ⭐️ 7.0/10

Google 研究团队发布 VeriHarness，这是一个无需训练、可即插即用的智能体验证框架，用生成候选结果的同一模型来执行验证：对分歧主张核查环境证据，对共识主张主动挑战，并据此选择、修订或重建最终结果。项目在 5 个长程任务基准、2 个模型上取得最高选择分；经证据驱动修订后，相较单次生成平均提升 Gemini 3.5 Flash 6.2 分、Claude Opus 4.8 6.4 分，并公开了约 2.6 万条 rollouts。 长程任务（即多步骤、错误会不断累积的工作流）目前的瓶颈往往不在于模型的原始生成能力，而在于无法可靠判断多个候选结果中哪一个才是正确的。一个无需训练、把生成模型本身变成验证器的框架，让智能体开发者无需微调、也无需额外引入评判模型就能提升准确率，有望成为 LLM 工作流中的标准组件层。 VeriHarness 明确强调无需训练、可跨基准与模型即插即用，并把验证视为不断演进的验证技能，而非固定的检查清单；其验证是“证据绑定”的，即对有争议的主张必须对照环境证据核查，而不能仅凭模型自我断言。所报告的提升来自证据驱动的修订环节，而非单纯生成；团队还随基准结果公开了约 2.6 万条 rollouts，便于外部复现并进一步分析其选择与修订行为。

telegram · zaihuapd · 10月4日 13:32

**背景**: 长程任务指需要多步骤完成的工作，例如跨多个网站检索、编辑文档、串联调用工具链，其中早期的一个错误会一路传播并毁掉最终结果，因此比许多基准所测试的单步短任务难得多。常见做法是采样大量候选 rollout 再从中挑选，例如用 self-consistency（多数投票）来决定答案，但这类方法只比较表面答案，无法检验推理是否真的与环境相符。VeriHarness 正处于这一位置：它是一套 harness（围绕现有模型搭建的脚手架层），负责提供验证流程，再由模型自己去执行这套流程。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://arxiv.org/html/2610.00972">VeriHarness : Scaling Agentic Verification for Long-Horizon Tasks</a></li>
<li><a href="https://github.com/SKZL-AI/veriharness">GitHub - SKZL-AI/ veriharness : An evidence-bound...</a></li>

</ul>
</details>

**标签**: `#AI agents`, `#LLM verification`, `#long-horizon tasks`, `#framework`, `#research`

---