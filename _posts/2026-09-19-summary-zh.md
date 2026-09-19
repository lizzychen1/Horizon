---
layout: default
title: "Horizon Summary: 2026-09-19 (ZH)"
date: 2026-09-19
lang: zh
---

> 从 56 条内容中筛选出 2 条重要资讯。

---

1. [Von：可替代 JEV 的开源 395M「System One」模型，纯 CPU 即可运行](#item-1) ⭐️ 8.0/10
2. [halogen 0.12.0 修复长上下文衰减：Strix Halo 上 1M 上下文达 38 tok/s](#item-2) ⭐️ 7.0/10

---

<a id="item-1"></a>
## [Von：可替代 JEV 的开源 395M「System One」模型，纯 CPU 即可运行](https://www.reddit.com/r/LocalLLaMA/comments/1wkpxn6/von_opensource_395m_system_one_model/) ⭐️ 8.0/10

开发者（Reddit 用户 wFXx）发布了 Von——一个 395M 参数的开源「System One」模型，定位为 TypeSafe 的 JEV 的即插即用替代品，代码托管在 GitHub（wfzyx/von），权重发布在 HuggingFace（wfzyx/von-1.0）。作者表示该模型完全在 CPU 上运行，占用 1–2 GB 内存，响应时间为 25–300 毫秒，并声称在所有基准测试中都优于 JEV；同时说明有 GPU 会更快，但 GPU 并非必需。 JEV 代表了一类新型的「System One」模型：它不生成文本，而是直接返回结构化的、带类型的决策结果。一个仅 395M 参数的开源复刻版本意味着开发者可以在普通硬件上本地运行这类决策层，无需调用 API，也没有按次计费的成本。如果其声称的基准测试优势得到验证，这将降低把快速结构化决策模型嵌入智能体、游戏和实时软件的门槛，使其不再依赖 TypeSafe 的托管端点。 该模型的核心指标目前均为作者自述，尚未经过独立验证；作者也承认目前几乎没有花时间进行优化（内存占用 1–2 GB，延迟 25–300 毫秒，GPU 可选、可加速）。Von 面向与 JEV 相同的使用场景：JEV 处理带类型的 Noul、Choice 和 Score 问题，并返回带有概率与置信度的校准答案，而不是自由生成的文本。

reddit · r/LocalLLaMA · /u/wFXx · 9月19日 16:00

**背景**: TypeSafe AI 近期提出了「System One」模型这一概念：它是一类新型前沿模型，专为快速、结构化的决策而设计，输出可直接被软件消费，其命名借鉴了「系统一」快速直觉思考与「系统二」缓慢深思熟虑的心理学类比。JEV 是 TypeSafe 的旗舰 System One 模型，也是该类别中的首个模型，通过单一端点（POST /v1/systemone）提供服务，在约 70–500 毫秒内返回带类型的概率化答案，而非撰写文字。Von 则是一次独立的开源尝试，试图以更小、可在本地运行的形态复现这一能力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://typesafe.ai/blog/introducing-system-one-models-and-jev">Introducing System One Models & Jev - TypeSafe AI Blog</a></li>
<li><a href="https://jevapi.org/">Jev API — TypeSafe System One Model API Access, Docs & Code...</a></li>
<li><a href="https://developers.cloudflare.com/ai/models/typesafe/jev/">Jev ( typesafe ) · Cloudflare AI docs · Cloudflare AI docs</a></li>

</ul>
</details>

**标签**: `#open-source-model`, `#llm`, `#local-inference`, `#github-repo`, `#model-release`

---

<a id="item-2"></a>
## [halogen 0.12.0 修复长上下文衰减：Strix Halo 上 1M 上下文达 38 tok/s](https://www.reddit.com/r/LocalLLaMA/comments/1wkyny9/qwen38flashnext_at_1m_context_on_strix_halo_38/) ⭐️ 7.0/10

halogen 的开发者发布了 0.12.0 版本，修复了引擎在上下文加深时出现的性能衰减，并公布了在配备 128 GB 内存的 Ryzen AI Max+ 395 上运行 Qwen3.8-Flash-Next 的前后对比数据。在 1,004,581 token 的上下文下，解码速度从 27.3 tok/s 提升到 38.3 tok/s（使用默认的投机解码草稿模型），冷启动 prefill 时间从 21.2 分钟降至 17.9 分钟，而标准的 32k 十条提示词平均值没有变化。 这表明真正的 100 万 token 上下文推理如今已能在单台消费级统一内存机器上实际运行，而不再依赖数据中心级的 GPU 集群，这对需要在本地处理长文档、长智能体任务或整个代码仓库的用户意义重大。它也说明，即使没有新硬件，仅通过引擎层面对长上下文的处理进行修复就能带来大幅提升，而且作者还公开邀请他人在 0.12.0 上重跑自己的 1M 测试以做独立验证。 1M 配置需要 128 GB 内存的机器，并在 README 的 podman 命令行中额外加上 -e HALOGEN_ROPE_YARN=4 -e HALOGEN_CTX=1048576；262k 和 1M 两行数据分别是单次冷启动的贪婪解码请求、输出 64 个 token，取自响应中的 timings 字段，而非多次运行的平均值。在 1M 上下文下，基于提示词缓存的后续轮次首个 token 约 0.55 秒即可返回，因此上述 prefill 数据仅代表冷启动路径。

reddit · r/LocalLLaMA · /u/peonist-ai · 9月19日 21:49

**背景**: 长上下文模型依赖旋转位置编码（RoPE），它把 token 的位置编码成旋转操作；为了把在短序列上训练的模型扩展到 100 万 token，推理引擎会采用 YaRN 之类的缩放方案，这里通过 HALOGEN_ROPE_YARN=4 这个参数暴露出来。Strix Halo 是 AMD 的 Ryzen AI Max+ 395 平台，其统一内存架构让 CPU 与 GPU 共享一大块内存池（此处为 128 GB），因此很适合在本地承载原本放不进独立显卡显存的大模型。halogen 是一个推理服务程序，把这类模型打包成可直接运行的镜像；prefill 是对整个提示词的首轮计算，decode 是随后的逐 token 生成，而投机解码草稿模型则是一个小模型，用来预先生成候选 token，再由主模型进行校验。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://runaihome.com/blog/ryzen-ai-max-395-strix-halo-local-llm-2026/">AMD Ryzen AI Max+ 395 (Strix Halo) for Local LLMs in 2026 ...</a></li>
<li><a href="https://normxu.github.io/Rethinking-Rotary-Position-Embedding-4/">The Input Context Length Problem Seems to be Solved | まいどぅー</a></li>
<li><a href="https://codersera.com/blog/amd-strix-halo-ryzen-ai-max-local-llm-setup-2026/">Run Local LLMs on AMD Strix Halo (Ryzen AI Max+ 395)</a></li>

</ul>
</details>

**标签**: `#local-llm`, `#llm-inference`, `#long-context`, `#github-repo`, `#quantization-hardware`

---