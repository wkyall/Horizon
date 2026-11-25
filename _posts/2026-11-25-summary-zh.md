---
layout: default
title: "Horizon Summary: 2026-11-25 (ZH)"
date: 2026-11-25
lang: zh
---

> 从 27 条内容中筛选出 6 条重要资讯。

---

**科技新闻**
1. [Simon Willison 复盘 LLM 编程代理的三次拐点](#item-tech-news-1) ⭐️ 8.0/10
2. [vCenter 曝 9.8 分免鉴权漏洞，Broadcom 发布补丁](#item-tech-news-2) ⭐️ 8.0/10
3. [OpenAI 仓库预印本声称矩阵乘法指数为 9/4](#item-tech-news-3) ⭐️ 7.0/10
4. [Check Point 管理服务器遭活跃入侵](#item-tech-news-4) ⭐️ 7.0/10
5. [Ternary Bonsai 2.5 27B 本地实测：22 tok/s、128k 上下文](#item-tech-news-5) ⭐️ 7.0/10

**财经新闻**
1. [小米 2026 年三季度经调整净利同比降 56.8%](#item-finance-news-1) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [Simon Willison 复盘 LLM 编程代理的三次拐点](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 8.0/10

Simon Willison 在 11 月 24 日的文章中，以 Claude Opus 4.5 发布一周年为参照，回顾过去十二个月 LLM 编程代理的三次能力拐点。他认为第一次是 2025 年 11 月的 Opus 4.5 与 GPT-5.1 系列（含 GPT-5.1-Codex-Max），它们让 Claude Code 与 Codex 的输出“默认通常正确”，从需要频繁纠错变为可日常依赖；第二次是 2026 年 6–7 月的“Fable 类”模型，只需给出目标和工具就能自行拆解问题，其中 Claude Fable 5 曾因美国出口管制被下架，7 月 1 日才恢复；第三次是 2026 年 9–10 月，Opus 5.5（9 月 22 日发布）等前沿模型在 3D 建模与游戏开发上明显进步，他称 Opus 5.5 用 12 小时试玩和调参把一款即时战略游戏从乏味改得有趣。文章明确这些是个人使用判断与案例，而非独立基准测试结果。

rss · Simon Willison · 11月24日 23:02

**「背景」** 这篇文章以 Claude Opus 4.5 发布一周年为回顾节点。该模型于 2025 年 11 月 24 日发布；当时 Claude Code 才问世约九个月，它是在 2025 年 2 月 24 日随 Claude 3.7 Sonnet 一同推出的。作者因此把 Claude Opus 4.5 视为编程智能体可靠性跨过实用门槛的起点。

**「影响」** 对使用编程代理的开发者，最直接的后果是“默认输出即可用”的期望被抬高：Willison 称 Opus 4.5 之后多数日常编码问题无需纠正即可通过，但他也说明这是个人体验，团队仍应在自有代码库上验证。另一个实际约束是可用性风险——Fable 5 曾因出口管制短暂下架，依赖单一模型的开发流程需要准备替代方案。

**标签**: `#LLM coding agents`, `#AI engineering`, `#Claude Opus`, `#model capabilities`, `#industry analysis`

---

<a id="item-tech-news-2"></a>
### [vCenter 曝 9.8 分免鉴权漏洞，Broadcom 发布补丁](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom 为 VMware 产品线发布覆盖 23 个漏洞的补丁，其中 vCenter 目录服务（vmdir）的鉴权绕过漏洞 CVE-2026-123903 被评为 9.8 分。该漏洞无需认证，只要能访问 vCenter，就能绕过认证直接进入系统，受影响管理员应优先安装更新。报道称该漏洞在补丁发布前几天已被作为零日利用。

telegram · zaihuapd · 11月24日 14:50

**「背景」** vmdir 是 vCenter 内置的目录服务，负责处理身份与目录相关请求；鉴权绕过出现在这一层，意味着未认证访问者可直接接触 vCenter 的管理面。9.8 分属于严重级评分，此次漏洞的处置重点因此落在暴露在互联网或不可信网络中的 vCenter 端点。

**「影响」** 对能够访问 vCenter 的管理员来说，该漏洞的后果是：一次失败的 LDAP SASL bind 会把所声明身份的访问令牌挂到连接上，随后明文 LDAP 操作就以该身份执行，攻击者无需任何凭据。应优先把 vCenter 升级到包含 CVE-2026-123903 修复的补丁，并鉴于该漏洞在补丁发布前已遭零日利用，检查暴露面和相关 LDAP 活动，而不只是更换账号口令。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/dinosn/CVE-2026-123903">dinosn/ CVE - 2026 - 123903 : CVE - 2026 - 123903 : VMware vCenter vmdir ...</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/vmware-patches-vcenter-zero-day-exploited-in-attacks-since-september/">VMware patches vCenter zero - day exploited in attacks since...</a></li>

</ul>
</details>

**标签**: `#VMware vCenter`, `#security vulnerability`, `#authentication bypass`, `#zero-day`, `#CVE-2026-123903`

---

<a id="item-tech-news-3"></a>
### [OpenAI 仓库预印本声称矩阵乘法指数为 9/4](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

一篇发布在 OpenAI GitHub 仓库的预印本声称，矩阵乘法的复杂度精确为 Θ\(n^2.25\)，即指数为 9/4。该主张针对算法研究者关心的核心指数问题，但所给材料只有标题和 PDF 链接，尚无技术细节或独立复核。在同行评审和复现之前，它应被视为未确认的预印本结论，而不是已确立的定理。

hackernews · E-Reverance · 11月25日 01:19 · [社区讨论](https://news.ycombinator.com/item?id=50637220)

**「背景」** 矩阵乘法指数 ω 指矩阵乘法所需的最小渐近指数；其精确值长期未知，尽管理论界用数十年时间不断缩小可能范围，却始终未能将其固定为单一数值。OpenAI 于 2026 年 11 月 24 日在公开的 openai/math 仓库发布预印本，声称 ω 在每个域上都恰好等于 9/4（即 2.25）；这仍是待验证的预印本主张，而非已确认的定理。

**「影响」** 在结果被独立验证前，算法库维护者和开发者不应把 9/4 当作已确立的复杂度界来调整实现；现有材料也没有提供可直接部署的算法证据。

**「社区讨论」** 评论区对结果的范围存在分歧：zone411 称该预印本给出每个域上的精确指数 9/4，反驳了指数等于 2 的猜想；orlp 指出标题应写成 Θ\(n^2.25\)，brandonb 则称该工作只证明 Ω\(n^2.25\) 的下界，2.25 的上界此前已知，并提到已有但远不实用的 O\(n^2.25\) 算法。上述均为评论者说法，未获来源或独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://cryptobriefing.com/openai-matrix-multiplication-exponent-9-4/">OpenAI preprint claims the matrix multiplication exponent is ...</a></li>
<li><a href="https://letsdatascience.com/news/openai-preprint-claims-matrix-multiplication-exponent-is-exa-7997d3b1">OpenAI preprint claims matrix multiplication exponent is ...</a></li>

</ul>
</details>

**标签**: `#matrix multiplication`, `#algorithms`, `#AI for mathematics`, `#OpenAI`, `#preprint verification`

---

<a id="item-tech-news-4"></a>
### [Check Point 管理服务器遭活跃入侵](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

GreyNoise 报告称，一场针对 Check Point 安全管理服务器的活跃入侵活动正在进行，攻击者据称通过重建 V8 PRNG 状态恢复会话 Cookie 签名密钥。已提供的评论引述报告细节称，攻击者反复请求 HFS 的 loginSrp1 登录端点，收集 JavaScript Math.random\(\) 的输出，重建 Node.js V8 PRNG 内部状态，进而伪造签名的管理员会话 Cookie。报告对初始访问路径的说明仍不完整；评论还提出，多个 Check Point 客户受影响可能指向 CVE-2026-16232，但这些管理服务器是否暴露于互联网尚未确认。

hackernews · louiereederson · 11月24日 16:32 · [社区讨论](https://news.ycombinator.com/item?id=50630594)

**「背景：CVE-2026-16232 与暴露面」** 这轮活动针对的 Check Point 安全管理服务器此前已存在一个关键漏洞：Check Point 披露的 CVE-2026-16232 属于认证绕过，远程攻击者可取得应用登录令牌，并通过 SmartConsole 获得完整管理员权限。Check Point 于 2026 年 7 月发布补丁、9 月更新修复；其公告指出，成功利用要求管理服务器 IP 可从互联网访问，且未限制 Trusted Clients。

**「影响与处置」** 运行 Check Point 安全管理服务器，且其管理 IP 直接暴露在互联网上、又未限制受信任客户端的组织，面临 CVE-2026-16232 认证绕过风险；Check Point 说明，成功利用需要满足上述暴露条件。相关管理员应限制管理接口的互联网可达性并配置受信任客户端，同时在安全网关上更新到最新 IPS，以启用针对该漏洞利用尝试的防护。

**「社区讨论」** 评论中最实质的质疑是初始访问路径仍不清楚：omh 指出，多家 Check Point 客户同时受影响暗示 CVE-2026-16232 可能是入口，但报告未说明这些管理服务器是否都暴露在互联网上。另有评论者主张应修复 Math.random 本身，而不是只归咎于使用它的应用。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://support.checkpoint.com/results/sk/sk185169">sk185169 - CVE-2026-16232 - Authentication bypass with ...</a></li>
<li><a href="https://www.cybersecuritydive.com/news/ai-enabled-campaign-targets-check-point-security-management-servers/875622/">AI-enabled campaign targets Check Point Security Management ...</a></li>
<li><a href="https://support.checkpoint.com/results/sk/sk185169">sk185169 - CVE-2026-16232 - Authentication bypass with ...</a></li>
<li><a href="https://blog.checkpoint.com/security/security-advisory-action-required-active-exploitation-of-check-point-smartconsole-authentication-bypass-cve-2026-16232">Security Advisory - Action Required - July 2026 Security ...</a></li>
<li><a href="https://advisories.checkpoint.com/defense/advisories/public/2026/cpai-2026-9895.html">CPAI-2026-9895 - Check Point Software</a></li>

</ul>
</details>

**标签**: `#cybersecurity`, `#Check Point`, `#PRNG`, `#session-cookie forgery`, `#threat intelligence`

---

<a id="item-tech-news-5"></a>
### [Ternary Bonsai 2.5 27B 本地实测：22 tok/s、128k 上下文](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

社区讨论中的 Ternary Bonsai 2.5 27B 是 Bonsai2 之后的 27B 本地模型版本，以 Q2 GGUF 形式运行；一位用户在 Mac Mini M5 Pro（24GB 内存、512GB SSD）上报告生成速度约 22.3 tok/s、首 token 2.12 秒，并能轻松将 128k 上下文放入内存。该用户认为它可能适合 agentic coding，但表示还需实际尝试简单代理任务。另一位评论者称其在 SWE-bench Verified 上与 Opus 4.6 得分相当，却没有给出可核验数据，并质疑这有多少来自针对基准的优化、基准本身变化，或小模型约六个月后接近前沿表现的趋势。由于所给材料没有厂商公告或独立基准，这些速度、长上下文和基准结论都应视为社区报告而非已确认能力。

hackernews · b0m · 11月24日 20:08 · [社区讨论](https://news.ycombinator.com/item?id=50633922)

**「背景：三值量化与 Bonsai 上一代」** 三值（ternary）量化把权重限制在 -1、0、+1 三档，平均每个参数约 2 bit，因此 27B 规模的模型可以压到 5.9 GB 左右在本地运行——官方模型文档标注三值权重占用为 5.93 GB，并称其面向 agent 场景提供 262K token 上下文。据 Hugging Face 模型页，本代之前同系列的上一个版本是 2026 年 9 月的 Bonsai 2，官方给出的解码速度提升正是以该版本的 llama.cpp 构建在同一批文件上作对比基准；而 2.5 在体积基本不变的前提下，主打更强的 agentic coding、多轮工具调用与多步任务执行能力。

**「本地部署与性能权衡」** 对本地编码代理用户，实际门槛降到约 5.93 GB 的 GGUF 文件：模型卡称其可通过 llama.cpp、MLX 运行，也可用 vLLM 部署；社区在 24 GB 内存的 Mac Mini 上报告 128k 上下文可轻松驻留、生成约 22–25 tok/s，因此适合批量或长上下文代理任务，但需先确认运行时支持该 ternary/Q2 量化格式。性能仍有上限：模型卡给出 SWE-bench Verified 75.6、Terminal-Bench 2.1 60.1，低于同源全精度 Qwen3.8 27B 的 80.6；一位用户的私有长程测试中，2.5 版通过数仍为 5/8，只是步骤少 17%、耗时少 29%。

**「社区讨论」** 有评论者希望看到与同尺寸模型的直接对比，例如 Qwen3.8 的 Q1/Q2 量化或 1B–10B 级别的 SOTA 模型，并质疑 SWE-bench Verified 的代表性。另一位用户用自己的长程本地任务基准报告，Bonsai2.5 与 Bonsai2 同为 5/8 通过，但步数少 17%、耗时少 29%（76 分钟对 107 分钟），认为完成时间有改善。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2.5 27B: Powering ...</a></li>
<li><a href="https://docs.prismml.com/models/bonsai-2-5-27b">Ternary Bonsai 2.5 27B - Bonsai - docs.prismml.com</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism-ml/Ternary-Bonsai-2.5-27B-GGUF · Hugging Face</a></li>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2 . 5 27 B : Powering Agentic...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism-ml/ Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>
<li><a href="https://tproger.ru/news/prism-ml-vypustila-ternary-bonsai-2-5-27b-model-v-5-9-gb-dlya-a">Ternary Bonsai 2 . 5 27 B : тернарная модель для агентного кодинга</a></li>

</ul>
</details>

**标签**: `#local LLMs`, `#model quantization`, `#ternary models`, `#agentic coding`, `#SWE-bench`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [小米 2026 年三季度经调整净利同比降 56.8%](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

小米集团发布 2026 年第三季度财报，经调整净利润为 48.84 亿元，同比下降 56.8%，略高于市场预期的 47.46 亿元；营收为 1072.4 亿元，同比下降 5.2%。当季汽车交付量为 100,975 辆。

telegram · zaihuapd · 11月24日 10:09

**「背景」** 公司把盈利承压归因于存储芯片等元器件涨价和研发投入增加；更早的 2025 年第四季度，小米经调整净利润已出现三年来首次季度下滑。

<details><summary>参考链接</summary>
<ul>
<li>China&#x27;s Xiaomi posts first quarterly profit decline in three years | Reuters</li>

</ul>
</details>

**标签**: `#Xiaomi`, `#quarterly earnings`, `#adjusted net profit`, `#EV deliveries`, `#smartphone shipments`

---