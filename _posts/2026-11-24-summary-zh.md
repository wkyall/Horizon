---
layout: default
title: "Horizon Summary: 2026-11-24 (ZH)"
date: 2026-11-24
lang: zh
---

> 从 38 条内容中筛选出 12 条重要资讯。

---

**科技新闻**
1. [Ladybird 独立浏览器引擎发布首个 alpha 版](#item-tech-news-1) ⭐️ 8.0/10
2. [GLM-5.4 发布：首款循环 Transformer 编程模型](#item-tech-news-2) ⭐️ 8.0/10
3. [NariQ 发布 Qwen3.8-27B 低比特量化，宣称接近 BF16](#item-tech-news-3) ⭐️ 7.0/10
4. [Codex2api 疑似被黑：v3.1.11 含无鉴权后门](#item-tech-news-4) ⭐️ 7.0/10
5. [黎曼猜想 AI 证明被指空转，作者承认代码满是垃圾](#item-tech-news-5) ⭐️ 7.0/10
6. [鸿蒙 HarmonyOS 5/6/7 设备突破 1 亿台](#item-tech-news-6) ⭐️ 7.0/10
7. [黄循财：新加坡不会成为规避美国芯片管制的通道](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic 称 Claude 发现 VP≠VNP 并公布 Lean 4 证明](#item-tech-news-8) ⭐️ 7.0/10

**科技博客**
1. [ERNIE 5.5 Flash 的 vLLM Day-0 插件支持](#item-tech-blog-1) ⭐️ 6.0/10

**财经新闻**
1. [Anthropic 上市后 AI 抛售冲击中国科技股，DeepSeek 与月之暗面上市计划承压](#item-finance-news-1) ⭐️ 8.0/10
2. [上海地铁 21 年来首次调整票价，12 月 1 日起实施](#item-finance-news-2) ⭐️ 7.0/10
3. [马斯克承认 SpaceX AI 落后，据报出租算力月入数十亿美元](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Ladybird 独立浏览器引擎发布首个 alpha 版](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

独立浏览器引擎 Ladybird 发布了首个 alpha 版，首次为 macOS 和 Linux 提供无需自行编译的安装包。它自行实现了 HTML 解析、CSS 引擎、布局、JavaScript 和 WebAssembly 等大部分核心组件，只复用 HarfBuzz 文本整形、Skia 2D 图形、ffmpeg 视频和 SQLite 等少数外部库，并按标签页分配独立进程。官方强调这仍是 alpha：部分网站无法使用，浏览器也会崩溃；实测中依赖 service worker 的 Datasette Lite 因 \`navigator.serviceWorker.startMessages\` 尚未实现而报错。项目在 10 月的月度更新中称，借助 AI 编码代理在 web-platform-tests 上新增 75,650 项通过（约 218 万项，超过 Safari、低于 Firefox），并用新的 WebAssembly 引擎在 JetStream 3 上取得 7 倍提升。

hackernews · janvdberg · 11月23日 16:13 · [社区讨论](https://news.ycombinator.com/item?id=50614249)

**「背景」** Ladybird 由更早的 SerenityOS 项目衍生，部分代码直接来自后者；在此之前，外界只能自行编译源码来试用。2026 年 2 月，项目还宣布借助 Claude Code 与 Codex，把 LibJS 的部分代码从 C++ 改写为约 2.5 万行 Rust。此次 alpha 的意义在于把这些自研组件打包成可直接安装的浏览器。

**「影响」** 对普通用户而言，现阶段只适合把它当作测试浏览器：可在 macOS 与 Linux 上安装，并能在浏览器内直接报告坏站、在崩溃后查看并决定是否发送崩溃报告；但 service worker 等能力缺失，意味着依赖后台脚本或离线能力的 Web 应用仍会失败。

**「社区讨论」** 多位评论者表示自己试过的站点几乎都正确渲染，其中 alentred 称 ProxMox 中的 NoVNC 甚至比在 Firefox 里更流畅，freakynit 则提到页面滚动略有卡顿。另有评论者希望 Ladybird 认真处理浏览器指纹问题，主张提供向全体用户返回伪造或随机值的非标准 JS 模式；kvuj 则对项目用 SQLite、Skia 等成熟库替换自研组件感到怀念。

**标签**: `#Ladybird`, `#browser engine`, `#open source`, `#web standards`, `#browser fingerprinting`

---

<a id="item-tech-news-2"></a>
### [GLM-5.4 发布：首款循环 Transformer 编程模型](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai 发布 GLM-5.4，称其为首款采用循环 Transformer 架构的模型，面向编程任务；该架构让一组共享权重的层在一次前向传播中重复运行多次，在不增加参数量的情况下加深网络。目前 GLM-5.4 未提供开放权重，也不能通过常规 API 套餐直接访问；博文作者需订阅 Coding Plan，并用其 API key 通过 https://api.z.ai/api/v1 的 OpenAI 兼容 Responses API 调用。作者用低、高、最高三档推理强度生成“骑自行车鹈鹕”进行对比，认为 5.4 与 5.3 画质相近，风格比 5.1/5.2 更接近 OpenAI 和 Anthropic 模型；这只是初步体验，并非独立基准验证。

hackernews · foohis · 11月23日 10:06 · [社区讨论](https://news.ycombinator.com/item?id=50609685)

**「背景」** GLM-5.4 是 Z.ai 首个采用循环 Transformer 的模型：标准 Transformer 的每一层在一次前向传播中只计算一次，而循环 Transformer 让一组共享权重的层多次迭代，并基于上一轮的隐藏状态继续细化，从而在不增加参数量的情况下加深有效网络。在它发布前三天，Thinking Machines Lab 的 Inkling 2 Mini 也采用了类似设计；据其介绍，该模型会对每个 token 将其中间层运行三次，以提升 agentic coding 等依赖推理质量的任务表现。

**「接入方式与配额变化」** 目前 GLM-5.4 仅对 GLM Coding Plan 订阅用户开放（起价 18 美元/月），普通 Model API 要等安全评估完成后才上线，也未提供开放权重；因此现在要调用该模型的开发者必须改用 Coding Plan 的 API key。好在两套 key 共用同一个 OpenAI 兼容接口（https://api.z.ai/api/v1），现有基于该接口的工具链基本可直接复用，但第三方插件如 llm-zai 尚未适配新模型。Z.ai 文档还说明，周配额套餐中 GLM-5.4 的可用额度提升到 GLM-5.3 的 1.5 倍。

**「社区讨论」** 评论中有人称赞 Zhipu 公开了较多技术细节，并解释循环 Transformer 通过权重共享减少层间 HBM 搬运，从而针对推理内存带宽瓶颈；也有人抱怨部分中国模型的“马拉松式思考”会在简单任务上反复自我检查，拉长完成时间。另有体验者报告，GLM-5.4 目前只能通过 Coding Plan 获取可用 API key，OpenRouter 与常规 Z.ai API 套餐尚不可用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://z.ai/subscribe">GLM Coding Plan — AI Coding Powered by GLM-5.4 &amp; GLM-5.3 ...</a></li>
<li><a href="https://docs.z.ai/guides/llm/glm-5.4">GLM-5.4 - Overview - Z.AI DEVELOPER DOCUMENT</a></li>

</ul>
</details>

**标签**: `#Looped Transformers`, `#LLM architecture`, `#coding models`, `#Zhipu AI`, `#model release`

---

<a id="item-tech-news-3"></a>
### [NariQ 发布 Qwen3.8-27B 低比特量化，宣称接近 BF16](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ 发布 Qwen3.8-27B 的 3 比特及以下量化版本，宣称在智能体长任务、数学、多语言推理和图像理解上保持接近 BF16 的质量，并能装进约 10 GB 的文件；这些基准结果由发布方给出，尚无独立验证。其数据显示 3 比特版在 DeepSWE 得 41.0、Terminal-Bench 2.1 得 63.8，高于所列 BF16 的 39.8 和 62.6，而 2 比特版在两项上分别降至 28.6 和 52.4。运行这些量化目前需要 NariQ 的 llama.cpp 分支；在 RTX PRO 6000 上解码速度与其他量化相当，但 4K 到 64K 上下文的吞吐随长度增加而下降。

hackernews · toebee · 11月23日 13:42 · [社区讨论](https://news.ycombinator.com/item?id=50611402)

**「背景」** 量化是把训练好的权重压缩到更低位宽（如 3-bit 及以下），以便在显存有限的硬件上运行大模型；GGUF 是目前 llama.cpp 生态常用的分发格式，但极低位宽通常会带来明显的能力损失。NariQ 所基于的 Qwen3.8-27B 于 2026 年 8 月中旬在 Hugging Face 以 Apache 2.0 发布，官方仓库标注约 28B 参数，带有视觉编码器和 262k 原生上下文，这解释了此次评测为何同时覆盖数学、多语言与图像理解任务。

**「部署门槛与兼容性」** 对想本地试用的开发者来说，最直接的约束是工具链：官方明确表示运行这些权重目前必须使用其 llama.cpp 分支（nari-llama.cpp），上游 llama.cpp 无法直接加载，现有推理脚本和封装要么自行编译该分支，要么等待上游合并。内存方面，约 10 GB 的单文件低于 Unsloth 文档给出的 27B 模型 4-bit 量化所需 16–19 GB 显存或统一内存这一门槛，但模型卡同时给出 Apple Silicon 上 M3 Pro（18 GB）以 3.0bpw 解码约 3.8 tok/s、远慢于 CUDA 的数据，Mac 用户应按此速度预期规划可用性，而非期待与消费级 GPU 相当的吞吐。

**「社区讨论」** 评论既给出肯定也提出质疑：rao-v 认为这类高算力量化容易过拟合基准，但认可该项目覆盖多种长时程任务并提到留出数据；WithinReason 则根据图表认为大部分提升来自测试框架差异，而非模型本身。另有用户追问量化具体丢失了什么信息、能否在 16 GB Mac 上运行，并报告 M3 Pro 上 3.0 bpw 文件解码约 3.8 tok/s。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.yottalabs.ai/post/qwen-3-8-27b-specs-hardware-requirements-how-to-run-2026">Qwen 3.8 27B: Specs, Hardware Requirements, and How to Run It ...</a></li>
<li><a href="https://huggingface.co/Qwen/Qwen3.8-27B">Qwen/Qwen3.8-27B · Hugging Face</a></li>
<li><a href="https://unsloth.ai/docs/models/qwen3.8">Qwen 3 .8 - How to Run Locally | Unsloth Documentation</a></li>

</ul>
</details>

**标签**: `#model quantization`, `#LLM inference`, `#Qwen`, `#llama.cpp`, `#benchmarking`

---

<a id="item-tech-news-4"></a>
### [Codex2api 疑似被黑：v3.1.11 含无鉴权后门](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

据一份转述自 Telegram 的事件复盘，开源项目 Codex2api 的作者 GitHub 账号疑似被入侵，攻击者绕过 main 分支直接推送 tag，使 Release 构建出带后门的版本；其中 v3.1.11 移除了鉴权，等同于可无密码远程执行命令，另有 workflow 将仓库的 16 个 Actions secrets 外传，波及同一账号下至少 21 个仓库。报告建议已安装或更新到 3.1.10–3.1.12 的用户立即停用并退回 3.1.9，同时轮换 GitHub token、SSH key、数据库及 DeepSeek 等相关密钥。上述说法来自简短的第二手群组转述，尚未经过独立验证，具体受影响的版本范围和仓库数量应以项目方后续说明为准。

telegram · zaihuapd · 11月23日 11:21

**「背景：tag 发布与 Actions secrets」** 在 GitHub 项目中，Release 通常由 GitHub Actions 工作流自动构建，而分支保护规则只作用于 main 等分支，直接推送 tag 仍可触发发布流程，这正是本次事件中攻击者被指采用的绕过路径。与此同时，仓库的 Actions secrets 由工作流在运行时读取，一旦工作流文件本身被改动，这些凭据就可能随构建过程被发送到外部。因此这类事件的处置惯例是先回退到可信版本，再轮换所有可能暴露的凭据。

**「影响与应对」** 回滚到 3.1.9 只能消除后门二进制，无法追回已经外传的凭据：报告称有 workflow 将仓库的 16 个 Actions secrets 送出，并波及同一账号下至少 21 个仓库，因此凡是运行过 3.1.10–3.1.12 的环境都应视为 GitHub token、SSH key 以及数据库和 DeepSeek 等密钥已泄露，必须逐一吊销并重新签发，而不能只做版本回退。同类事件的经验也显示，被窃取的 CI 凭据往往在恶意版本下线后仍可被用于向其他仓库推送窃密 workflow。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.githubforensics.com/en/blog/github-actions-secrets-leak">GitHub Actions secrets leak: investigating exfiltration</a></li>
<li><a href="https://www.endorlabs.com/learn/github-actions-supply-chain-attack-targeting-ci-secrets-at-scale">Hijacked GitHub Accounts Push “wfx” CI Secret Stealer to ...</a></li>

</ul>
</details>

**标签**: `#supply-chain attack`, `#GitHub Actions`, `#secrets exfiltration`, `#remote code execution`, `#open-source security`

---

<a id="item-tech-news-5"></a>
### [黎曼猜想 AI 证明被指空转，作者承认代码满是垃圾](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

一项宣称由 Alpöge 与 Claude 完成、覆盖黎曼猜想及广义版本的 Lean 证明，被研究者指出关键定义被写成恒真、几何条件形同虚设，因而可能只是空转。该工作此前只公开约 1700 万行 Lean 代码和 17.5 万个文件，没有人类可读的证明；Lean 与 Mathlib 社区曾表示对代码证明了这一命题“有充分信心”。23 日，Alpöge 承认“25 万页是玩笑”，称代码“满是垃圾但能编译”，并表示批评完全合理。

telegram · zaihuapd · 11月24日 01:29

**「背景：Lean 证明为何会“空转”」** Lean 是交互式定理证明器，Mathlib 是其数学库；它主要检查代码能否通过类型检查，却不自动判断定义和条件是否忠实表达原命题，因此把关键定义写成恒真、让几何条件形同虚设时，代码仍可能编译并形成“空转”证明。此前 Alpöge 与 Claude 的声明只发布了约 1700 万行 Lean 代码而没有人类可读的论文，核查因此集中在形式化定义是否真正对应黎曼猜想。

**「对形式化验证的影响」** 对使用 Lean、Mathlib 审查 AI 生成证明的研究者而言，这一事件表明“能编译”和代码规模不能替代对定义与命题陈述的人工检查；否则，恒真定义或形同虚设的条件可能让整个证明空转。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://explainx.ai/blog/levent-alpoge-anthropic-riemann-hypothesis-claude-lean-proof-claimed-vs-verified-2026">Riemann Hypothesis Proof Claim: Claimed vs Verified ...</a></li>
<li><a href="https://www.martincid.com/technology-sv/claude-riemann-hypothesis-proof-anthropic-levent-alpoge-lean/">A Riemann hypothesis proof made with Claude compiles, and no ...</a></li>

</ul>
</details>

**标签**: `#AI`, `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI-generated code`

---

<a id="item-tech-news-6"></a>
### [鸿蒙 HarmonyOS 5/6/7 设备突破 1 亿台](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

华为终端有限公司 11 月 24 日宣布，搭载 HarmonyOS 5、6、7 的手机、平板和电脑设备合计已突破 1 亿台。该公司同时称，鸿蒙可获取的应用和服务超过 46 万项，注册开发者超过 1200 万人。开源鸿蒙方面，华为披露已有 1.4 万余名贡献者、120 余个行业发行版，合作伙伴贡献的 160 多项创新能力被 1600 多款应用集成，相关功能一年内使用量提升 90 倍。上述数字均为华为方面公布，公告未披露各版本设备的具体拆分、活跃设备规模或第三方核验数据。

telegram · zaihuapd · 11月24日 01:46

**「背景」** 鸿蒙操作系统于 2019 年首次发布，2024 年 10 月又发布了原生鸿蒙版本。此次公布的 HarmonyOS 5、6、7 设备规模，是在这一版本演进基础上形成的生态数据。

**标签**: `#HarmonyOS`, `#Huawei`, `#operating systems`, `#open source`, `#mobile ecosystem`

---

<a id="item-tech-news-7"></a>
### [黄循财：新加坡不会成为规避美国芯片管制的通道](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

新加坡总理黄循财表示，新加坡不会允许本国被用作企业规避美国芯片出口管制的通道，并证实当局正在调查 Megaspeed 采购英伟达芯片的交易。此前一天，美国商务部将 Megaspeed 及另外 6 家东南亚企业列入贸易黑名单，称这些实体存在向未获授权用户转移先进计算产品的“重大风险”，名单还包括其在马来西亚和泰国的关联实体。路透社报道，阿里巴巴新加坡子公司 Apex Enterprise Solutions 也在名单中；阿里巴巴表示，从未转移受管制的先进计算芯片。

telegram · zaihuapd · 11月24日 05:03

**「背景」** 美国对英伟达等先进计算芯片实施出口管制，美国供应商向受限实体出口此类物项通常需要申请许可。实体清单是执行该管制的核心工具，被列入的企业在采购受控芯片和计算产品时会受到严格审查。

**「影响」** 对在新加坡及东南亚采购或转运先进计算芯片的企业来说，相关交易将面临更严格的出口许可与合规审查；被列名的 Megaspeed 等实体与美国供应商之间的受控物项往来可能受阻。

**标签**: `#semiconductor export controls`, `#AI chips`, `#Nvidia`, `#Singapore`, `#US-China tech`

---

<a id="item-tech-news-8"></a>
### [Anthropic 称 Claude 发现 VP≠VNP 并公布 Lean 4 证明](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 7.0/10

据该 Telegram 来源，Anthropic 于 11 月 24 日公开论文《VP ≠ VNP over every field》及 Lean 4 形式化证明，仓库称结果由内部研究用 Claude 模型发现，论文与代码均由 AI 撰写。论文给出哈密顿圈多项式的超多项式算术电路下界，并据此推出 VP 是 VNP 的真子类；若成立，这将解决 Valiant 1979 年的代数复杂度猜想，但仅针对算术电路，不涉及 P 与 NP。形式化证明经三条标准公理审计及独立内核 nanoda 复核，除预留文件外无 sorry。不过尚无人类数学家通读，Lean 也无法确认形式化陈述与所声称命题一致，附录 Q 列出了出入，仍需独立审阅。

telegram · zaihuapd · 11月24日 06:02

**「背景」** VP 与 VNP 是 Valiant 于 1979 年提出的代数复杂度类：VP 粗略对应可由多项式规模算术电路计算的多项式族，VNP 则对应系数可由 VP 多项式族定义的集合。证明 VP≠VNP 是算术电路模型下的猜想，与 P≠NP 并非同一命题；给出哈密顿圈多项式这类对象的超多项式算术电路下界，是区分两者的典型路线。

**「实际影响」** 对代数复杂度研究者而言，当前可用的只是待审阅的论文与 Lean 4 工件：内核审计和 nanoda 复核只能说明形式证明在其形式陈述下成立且无 sorry，不能证明该陈述就是 VP≠VNP，也不能替代人类数学家核对附录 Q 列出的出入。因此在独立审阅完成前，不应把它当作已确立的复杂度结论引用或用于后续工作。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.alphaxiv.org/abs/2611.vp-vnp-arithmetic-lower-bounds">VP VNP Over Every Field | alphaXiv</a></li>

</ul>
</details>

**标签**: `#complexity theory`, `#Lean 4`, `#AI for mathematics`, `#formal verification`, `#Anthropic`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [ERNIE 5.5 Flash 的 vLLM Day-0 插件支持](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 6.0/10

rss · vLLM Blog · 11月24日 00:00

**「背景」** ERNIE 5.5 Flash Preview 是 280B 总参数、每 token 激活 14B 的稀疏 MoE 模型，支持 1M 上下文和长程 Agent 任务；其新注意力/MoE 结构、超长上下文索引和低精度推理，使发布日即获得高效 vLLM 支持成为挑战。

**「方案」** 百度 ERNIE 团队与 vLLM 合作，以独立 vLLM-ERNIE 插件在 vllm==0.32.0 上实现 Day-0 支持：插件通过 vllm.general\_plugins 入口自动注册模型架构、配置、tokenizer 与解析器，仅在加载 ERNIE 时导入模型代码，因此无需维护 fork、专用镜像或等待 nightly wheel，也不影响同环境中的其他模型。针对 43 层中 37 层 HCA、6 层 MLA-DSA 以及 VHA、Multi-Router Latent MoE、MultiMax 输出头等新结构，作者将跨头混合、路由 GEMM、分段激活等折叠或融合为专用内核，报告单内核较朴素实现快 1.55×–6.53×且数值一致。FlashIndexer 用小路由器按 token 动态选择少量索引头，并用阈值预过滤缩小 top-k 候选，文章称在 1M 上下文带来约 1.4×（40%）索引加速，且不改变下游稀疏注意力接口。默认路由专家为 MXFP4 W4A8、其余权重 FP8、KV cache FP8，并通过与推理数值匹配的 QAT 避免精度落差；三层 MoE 的 DSpark 草稿模型每步最多提议 7 个 token，经多阶段训练和在线蒸馏后，在编码与 Agent 负载上平均接受长度超过 4.0。部署侧还支持注意力 TP、专家并行、PD 分离与 KV cache CPU 卸载，前缀缓存、chunked prefill、CUDA graph 和 OpenAI 兼容服务可直接复用。

**「启示」** 作者的核心结论是：把模型专用代码和内核放进可插拔插件、把通用能力留给 vLLM 核心，可以在发布日支持新模型，同时让融合内核、稀疏索引、量化和投机解码共同压低长上下文推理成本。其更大意义在于为模型厂商提供了一条不 fork vLLM 也能快速交付优化的集成路径。

**标签**: `#vLLM`, `#ERNIE`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [Anthropic 上市后 AI 抛售冲击中国科技股，DeepSeek 与月之暗面上市计划承压](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

据彭博报道，Anthropic 完成 1195 亿美元创纪录 IPO 后，全球 AI 股遭遇抛售，中国科技股自 6 月底以来累计蒸发 1.7 万亿美元，令 DeepSeek、月之暗面和阶跃星辰正在筹备或考虑的股份发行计划蒙上阴影。报道称这些上市安排目前仍属筹备或考虑阶段，尚未确认。

telegram · zaihuapd · 11月23日 09:31

**「背景」** Anthropic 的 1195 亿美元 IPO（首次公开募股）是美国史上规模最大的一笔，但上市首日涨 17% 后次日跌 8.5%，未能提振 AI 股，反而被市场视为全球 AI 股票抛售的导火索；中国科技股自 6 月底以来累计蒸发 1.7 万亿美元。

**「影响」** 这轮抛售直接加大了 DeepSeek、月之暗面和阶跃星辰等筹备上市企业的定价压力：公开市场投资者更谨慎，它们可能被迫接受更低估值或推迟发行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.straitstimes.com/business/chinas-next-ai-deals-clouded-by-sell-off-after-anthropic-ipo">China’s next AI deals clouded by sell-off after Anthropic IPO</a></li>
<li><a href="https://www.cnbc.com/2026/11/19/anthropic-ipo-ai-stocks-selloff.html">Anthropic IPO fails to lift AI stocks - CNBC</a></li>

</ul>
</details>

**标签**: `#AI selloff`, `#China tech stocks`, `#IPO market`, `#Anthropic IPO`, `#market disruption`

---

<a id="item-finance-news-2"></a>
### [上海地铁 21 年来首次调整票价，12 月 1 日起实施](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

上海地铁票价将进行 21 年来首次调整，新起乘价为 3 元、覆盖 0 至 4 公里，12 月 1 日起实施。同步推出 35 次至 90 次四档计次票，售价 190 元至 390 元，11 月 26 日开售；同一支付渠道当月累计满 90 元后享 9 折，旨在减轻对高频出行人群的影响。

telegram · zaihuapd · 11月23日 10:45

**「背景」** 上海轨道交通上一次票价调整是在 21 年前；新方案在起步价之外，按 4、4、4、7、7、10、10 公里加 1 元，50 公里以上每 15 公里加 1 元。

**标签**: `#上海地铁`, `#公共交通票价`, `#民生政策`, `#出行成本`

---

<a id="item-finance-news-3"></a>
### [马斯克承认 SpaceX AI 落后，据报出租算力月入数十亿美元](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 7.0/10

《纽约时报》11 月 23 日援引三名知情人士报道，SpaceX 自今年 5 月起向 Anthropic、Google 等公司出租数据中心算力，月收入达数十亿美元。马斯克据称向员工表示，SpaceX 在 AI 上落后。

telegram · zaihuapd · 11月24日 02:06

**「背景」** 据《纽约时报》报道，SpaceX 自建的数据中心原本也要支撑自家的 AI 研发，但自今年 5 月起，这些算力被出租给 Anthropic 等外部客户，与内部 AI 项目争用同一批资源，这使马斯克自己的 AI 推进更加吃力。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html">Elon Musk Faces an A.I. Dilemma at SpaceX - The New York Times</a></li>
<li><a href="https://www.gate.com/news/detail/SPCX/spacex-rents-computing-power-to-anthropic-and-google-while-grok-ai-lags-25823949">SpaceX Rents Computing Power to Anthropic and Google While ...</a></li>

</ul>
</details>

**标签**: `#SpaceX`, `#AI compute`, `#Anthropic`, `#Google`, `#Elon Musk`

---