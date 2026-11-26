---
layout: default
title: "Horizon Summary: 2026-11-26 (ZH)"
date: 2026-11-26
lang: zh
---

> 从 35 条内容中筛选出 10 条重要资讯。

---

**科技新闻**
1. [GRH 的 Lean 验证推出大幅精简版本](#item-tech-news-1) ⭐️ 8.0/10
2. [1Password 确认部分客户账户信息被窃](#item-tech-news-2) ⭐️ 8.0/10
3. [Minecraft Java 版曝高危 RCE，1.20.5 起受影响](#item-tech-news-3) ⭐️ 8.0/10
4. [Google Research 发布整数分解与离散对数相关论文合集](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis 发布 GDPx，首日最高分仅 12%](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI 押注网络安全，推出 GPT-6 Cyber](#item-tech-news-6) ⭐️ 7.0/10
7. [腾讯开源 Hy4 flash GGUF 量化权重，最小版可跑在 64GB Mac mini](#item-tech-news-7) ⭐️ 7.0/10
8. [三星与 SK 海力士据报将采用长江存储 Xtacking 技术](#item-tech-news-8) ⭐️ 7.0/10

**财经新闻**
1. [法庭文件：美商务部被指施压英特尔交出 10%股份](#item-finance-news-1) ⭐️ 9.0/10
2. [美国拟对 14 个贸易伙伴加征国别关税，对华再加征 20%](#item-finance-news-2) ⭐️ 8.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [GRH 的 Lean 验证推出大幅精简版本](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

GRH 相关 Lean 验证出现了一个大幅精简、可读性更强的版本，社区讨论称规模从约 1700 万行降至约 7.6 万行，缩减约 99.56%。该版本将“已知数学”和“新数学”清楚分开，并配有较完整的人类可读文档，便于读者理解原有形式化证明。现有材料没有提供独立代码审查结果或新的数学结论，因此这应视为对既有验证在可读性和体积上的改进，而不是新的数学突破。

hackernews · nb-t · 11月25日 21:48 · [社区讨论](https://news.ycombinator.com/item?id=50648050)

**「背景」** 此前，Alpöge/Claude 的广义黎曼假设（GRH）证明已以 Lean 形式发布，规模为 175,187 个文件、约 1700 万行；据维基百科条目，Lean FRO 与 Mathlib Initiative 于 2026 年 11 月 21 日宣布完成验证并对其正确性有充分信心。此次更短版本是在同一形式化证明上的压缩与可读性重写，目的是让机器可检验的证明更易审阅，而非提出新的数学论证。

**「影响」** 对形式化验证和 AI 辅助数学的读者而言，直接变化是可以在更小的代码库中定位 GRH 证明的关键结构，并借助“已知/新数学”分区与文档区分既有引理和新论证；但在独立审查或数学论文出现前，不宜把这次精简当作对证明正确性的额外保证。

**「社区讨论」** 有评论者赞赏可读性提升，spootydooty 指出文档和“已知/新数学”分区有助于消化证明；gre 则追问，这是否反驳了 Tao 此前关于“巨大证明缺乏洞见”的担忧，还是说明更聪明的 LLM 已能压缩并解释证明。AIShill101 表示仍希望有数学家真正理解核心论证，并写成数学论文、在会议上讲解。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Alp%C3%B6ge&#x27;s_proof_of_the_Riemann_hypothesis">Alpöge&#x27;s proof of the Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge/Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**标签**: `#Lean`, `#formal verification`, `#GRH`, `#AI-assisted mathematics`, `#Anthropic`

---

<a id="item-tech-news-2"></a>
### [1Password 确认部分客户账户信息被窃](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password 确认发生安全事件：攻击者入侵一名员工的企业 GitHub 账户，借此访问源代码并向后台服务推送恶意代码，导致部分客户账户信息被下载。公司称泄露数据包括姓名、邮箱地址、账户标识以及账户创建和最近登录时间，受影响用户数量尚未披露。公司于 11 月 19 日开始调查，已停用涉事账户、轮换或撤销可能暴露的内部凭证，并加强邀请和恢复邮件的验证码；其表示客户保险库及内容未受影响，用户无需更改账户，但应警惕钓鱼。

hackernews · lxhrstn · 11月25日 17:18 · [社区讨论](https://news.ycombinator.com/item?id=50644817)

**「背景」** 1Password 是托管式密码管理器，客户账户信息由其后台服务处理。此次披露的关键风险在于代码供应链：员工企业 GitHub 账户被入侵后，攻击者可访问源代码并向后台服务推送恶意代码，使代码部署链路成为接触账户数据的入口。

**「影响与应对」** 对客户而言，实际动作是保持警惕而非重置账户：1Password 表示客户保险库内容未被访问，用户无需更改账户，但泄露的姓名、邮箱和账户元数据可被用于针对性钓鱼。对软件团队而言，此次事件表明员工 GitHub 账户被攻陷后恶意代码可被推送到后台服务，应核查生产仓库的分支保护、代码审查和部署审批是否确实能阻止未授权推送。

**「评论讨论」** 评论者 tptacek 认为，员工终端被攻陷后攻击者向 GitHub 推送代码并被部署，是 SaaS 公司长期存在的标准入侵路径；ctidd 则批评公告未说明是否缺少分支保护规则，也未解释恶意推送为何能被允许。qixxiq 报告收到一封包含部分个人细节、并非来自 1Password 官方域名的高质量钓鱼邮件，并推测其利用了此次泄露数据，但明确表示这是个人判断。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>

</ul>
</details>

**标签**: `#security incident`, `#1Password`, `#supply chain security`, `#SaaS security`, `#phishing`

---

<a id="item-tech-news-3"></a>
### [Minecraft Java 版曝高危 RCE，1.20.5 起受影响](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

11 月 22 日公开的 minecraft2shell 显示，Minecraft Java 版可通过服务器资源包中的特制 TrueType 字体触发 FreeType 2.14.3 及更早版本的原生越界写，并在 26.3 Windows 客户端执行任意代码。受影响版本为 Java 版 1.20.5 至 1.21.10 以及 26.1 至 26.4 快照，1.20.4 及更早版本和基岩版不受影响。Mojang 目前仍使用 lwjgl-freetype 3.4.3，尚无官方补丁；社区于 11 月 24 日发布 m2sfix 1.0.0，通过 Java agent 或 mod 关闭字体 hinting 作为临时缓解。

telegram · zaihuapd · 11月25日 12:46

**「背景」** Minecraft Java 版通过 LWJGL 的 FreeType 绑定加载资源包中的 TrueType 字体；当 FreeType 启用 hinting 时，它会运行字体自带的字节码。社区修复 m2sfix 让字体在不启用 hinting 的情况下加载，使这段字体字节码不再执行，从而阻止资源包触发本地代码执行。

**「影响与建议」** 在官方修复发布前，用户和服务器管理员应避免添加任何资源包，将多人游戏服务器的资源包权限设为“禁用”，或安装 m2sfix 1.0.0 临时修复；这些措施针对的是资源包字体触发的攻击路径。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cyberkendra.com/2026/11/minecraft2shell-minecraft-java-rce-resource-pack.html">Minecraft2Shell RCE in Minecraft Java Still Unpatched</a></li>
<li><a href="https://github.com/sunrisemc-tw/minecraft2shell-fix">GitHub - sunrisemc-tw/minecraft2shell-fix: Client-side ...</a></li>

</ul>
</details>

**标签**: `#Minecraft`, `#RCE vulnerability`, `#FreeType`, `#security advisory`, `#community patch`

---

<a id="item-tech-news-4"></a>
### [Google Research 发布整数分解与离散对数相关论文合集](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research 在其公开的 google-research GitHub 仓库中新增了一个名为 cogentic\_research\_papers 的论文合集，主题涉及整数分解、离散对数及相关方向。现有材料只提供了仓库条目，没有论文摘要、具体算法结果或独立验证，因此这些论文是否构成密码学意义上的实质进展尚无法判定。整数分解与离散对数正是 RSA、Diffie-Hellman 等公钥密码体制所依赖的困难问题，这也是该合集在技术社区引发关注的原因。

hackernews · rgwohlbold · 11月25日 13:33 · [社区讨论](https://news.ycombinator.com/item?id=50642086)

**「背景」** 这批论文最受关注的主张是：对任意整数 N 都能求出完整素因子分解，并且最坏情况下的期望时间为 L\_N\[1/3, 105\]。L 记号是数论里描述分解算法亚指数复杂度的常用写法；在指数 1/3 下，第二个参数越小，表示算法越快，所以这项主张的分量取决于它相对既有启发式界究竟改善了多少。据 MLQ.ai 和 R&amp;D World 的报道，这批结果来自基于 Gemini 4 的 Cogentic 智能体；一个提交里共有六篇论文，覆盖整数分解、离散对数、博弈论、复杂度理论和图论，但文中提到的 Lean 形式化证明尚未完成。因此，目前公开的仍是论文层面的主张，还不是经过机器验证的定理。

**「对密码实践的直接影响尚不成立」** 该仓库目前只提供论文本身，没有附带摘要、算法复杂度或实测运行数据，因此尚不能据此判断 RSA 所依赖的整数分解，或 Diffie-Hellman、DSA 等方案所依赖的离散对数问题已被削弱，也没有理由现在调整密钥长度或启动算法迁移。讨论中有评论者指出，整数分解与离散对数是两个不同的问题，即使前者出现实用算法，也不能自动推出后者同样可解，且密码学界早已因分解问题的长期不确定性而发展了 RSA 之外的替代方案。

**「社区讨论」** Hacker News 上有评论援引一则外部帖文中的传言，称这批论文只是“更大成果的一角”，但该说法未获证实；另有评论把当下情况类比为 AlphaGo 用搜索加学习攻克围棋的庞大搜索空间，认为 AI 正在同样方式进入 Navier-Stokes、黎曼猜想等问题，并反思“砸钱解决数学难题”是否可行。也有评论指出，尽管此类消息频繁出现，AI 相关市场却在下跌，暗示投资者对纯数学进展并不买账。

<details><summary>参考链接</summary>
<ul>
<li>Google&#x27;s Cogentic agent posts six math papers, led by a claimed proven L[1/3] bound for factoring integers | MLQ.ai</li>
<li>Google&#x27;s Gemini 4 agent claims six math proofs in a day, including one on factoring 30 years in the making - R&amp;D World</li>
<li>Google Cogentic: 6 Math Papers, Factoring Unverified - shattered.io</li>
<li><a href="https://news.ycombinator.com/item?id=50642086">Google releases Cogentic papers on integer factorization , discrete ...</a></li>

</ul>
</details>

**标签**: `#integer factorization`, `#discrete logarithms`, `#cryptography`, `#AI for mathematics`, `#Google Research`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis 发布 GDPx，首日最高分仅 12%](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis 推出 GDPx 基准，用于评估前沿模型在芯片设计、网络安全、生物、金融、法律、量化交易、递归自我改进、硬件设计、材料科学、对齐和软件工程 11 个领域的表现；它表示与 14 家专业数据伙伴共同制作了 206 项任务，并刻意排除政府、房地产等按 GDP 占比或 O\*NET 分类选样的领域。GDPx 于 11 月 1 日上线时，发布日得分最高的 Opus 5.5 仅得 12%，远低于常见基准首日头名超过 50% 的水平，SemiAnalysis 以此说明该基准仍能区分未来模型，而不像 Terminal Bench 4.0 那样趋于饱和。文章还称，自上线以来 Anthropic 和 OpenAI 发布了新的前沿模型，Google 凭 Gemini 4 系列强势回归，阿里巴巴和 Moonshot 也有值得注意的发布；但所给节选未包含完整排行榜结果。

rss · Semianalysis · 11月26日 00:05

**「背景」** 现有智能体基准通常只覆盖编程、法律等单一领域；少数试图覆盖多个领域的基准，例如 GDPVal 和 Agent&\#x27;s Last Exam，则按行业占 GDP 的比重或 O\*NET 职业分类来挑选测试领域。SemiAnalysis 于 11 月 1 日发布 GDPx，主张前沿模型的经济影响在各行业间分布极不均匀，因此改为聚焦芯片设计、网络安全、生物、金融、法律和量化交易等它认为最具经济价值的领域。

**「实际影响」** 对追踪前沿模型的团队而言，GDPx 的超低初始分数意味着短期内榜单变化可能更多反映新模型在少数高价值领域的增量，而不是被饱和基准压缩后的微小差距；使用该榜单时需注意，Fable 5.2 和 GPT-6.2 Astra 因安全分类器在网络安全、生物和对齐领域的得分被压低，SemiAnalysis 另给出了排除这三个领域并对法律、金融改用部分评分的调整版榜单。

**标签**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#GDPx`, `#SemiAnalysis`

---

<a id="item-tech-news-6"></a>
### [OpenAI 押注网络安全，推出 GPT-6 Cyber](https://www.theinformation.com/newsletters/ai-agenda/openais-roadmap-making-cyber-bigger-coding-remains-blurry) ⭐️ 7.0/10

OpenAI 正将网络安全定位为下一个增长引擎。公司 CFO 表示，外界对网络安全市场规模超过 3000 亿美元的估算“仍被低估”；总裁格雷格·布罗克曼则称，网络安全未来会成为比编程更大的业务板块。OpenAI 已推出面向安全研究的 GPT-6 Cyber，并扩大 Daybreak 受信访问计划；截至今年 9 月，该计划覆盖数千名经核验的防御者以及约 2000 个获批组织和工作空间，用于漏洞发现、代码库分析和二进制逆向。报道同时指出，OpenAI 与 Anthropic、Google 的竞争及规模化商业化路径仍不清晰。

telegram · zaihuapd · 11月25日 04:51

**「背景」** 受信访问计划通常指模型厂商不向所有人开放全部能力，而是让经过身份验证的安全团队在受控条件下使用，以降低相关技术被滥用于攻击的风险。Daybreak 就是 OpenAI 面向网络安全防御者的这类计划；来源称其覆盖范围已从个人验证扩展到获批组织和工作空间。把网络安全与编程并列，涉及的是 OpenAI 现有商业化参照：编程已是其面向开发者的重要业务，而网络安全能否更大仍取决于企业采用与付费规模。

**「影响」** 对安全团队来说，GPT-6 Cyber 能否实际使用，取决于是否通过 Daybreak 审批：获批组织可通过 Daybreak 的 Defense Factory 连接代码库，使用红队测试以及 Codex Security CLI/SDK 等入口；尚未获批的团队则不能假设自己能直接获得同等访问。由于多数专用网络安全模型都被置于审批计划之后，企业在评估该产品时，需要把资格审核、授权测试范围和终端集成一并纳入部署安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/daybreak/">Daybreak | OpenAI for cybersecurity | OpenAI</a></li>
<li><a href="https://benchlm.ai/cybersecurity">Best AI Models for Cybersecurity , by Task (November...) | BenchLM.ai</a></li>

</ul>
</details>

**标签**: `#OpenAI`, `#cybersecurity`, `#AI security`, `#product strategy`

---

<a id="item-tech-news-7"></a>
### [腾讯开源 Hy4 flash GGUF 量化权重，最小版可跑在 64GB Mac mini](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

腾讯混元通过模型压缩加速工具箱 AngelSlim 开源了 224B 参数模型 Hy4 flash 的 GGUF 量化权重，原权重约 410.27GiB。其中最小的 IQ2-AH 版本为 125.73GiB，约为原版的 30%，发布方称借助 Strata offload 框架可在 64 GB Mac mini 上运行。随发布给出的数据称，48 GB 显存设备在 10K 上下文下每秒生成 89 个 token，M5 Max 128 GB 上 Q3\_K 版本在 32K 上下文下每秒生成 47 个 token。发布方还称在 DeepSWE v1.1 等评测中，Q3\_K 与原模型的得分差距不超过 0.4 分；上述体积、吞吐与质量数据均来自发布方说明，尚未经独立验证。

telegram · zaihuapd · 11月25日 09:29

**「背景」** AngelSlim 是腾讯的大模型压缩工具包，其 GitHub 说明已支持 Hunyuan、Qwen2.5/Qwen3、DeepSeek-R1-Distill-Qwen 等模型的 INT8/FP8/INT4 量化。Hy4 flash 的 Hugging Face 模型页也把 AngelSlim 列为配套量化工具，因此这次发布的 GGUF 权重是该工具链针对 Hy4 flash 的量化产物。

**「64GB Mac mini 部署仍受存储与卸载带宽制约」** 即使最小的 IQ2-AH 版本为 125.73GiB，仍远超 64GB 统一内存，Mac mini 上的运行要靠 Strata offload 从外部存储换入权重，因此可用磁盘空间和卸载速度才是实际瓶颈，而非内存容量。原文给出的 89 token/s（48GB 显存设备、10K 上下文）与 47 token/s（M5 Max 128GB、Q3\_K、32K 上下文）都不是 64GB Mac mini 的实测数据，打算在本地部署的用户需自行验证该配置下的实际吞吐。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://github.com/Tencent/AngelSlim">GitHub - Tencent / AngelSlim : Model compression toolkit engineered...</a></li>
<li><a href="https://huggingface.co/tencent/Hy4-flash">tencent / Hy 4 - flash · Hugging Face</a></li>
<li><a href="https://huggingface.co/strata-engine/Hy4-Flash-Strata">strata-engine/Hy4-Flash-Strata · Hugging Face</a></li>
<li><a href="https://original.ifeng.com/c/8yLCKwSsFD6">腾讯混元Hy4 flash开源GGUF量化权重 224B模型可跑在64GB Mac mini上</a></li>

</ul>
</details>

**标签**: `#LLM quantization`, `#local inference`, `#GGUF`, `#Tencent Hunyuan`, `#model compression`

---

<a id="item-tech-news-8"></a>
### [三星与 SK 海力士据报将采用长江存储 Xtacking 技术](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

据媒体报道，三星电子和 SK 海力士已通过交叉许可协议，同意在 3D NAND 闪存中采用长江存储 Xtacking 堆叠技术的部分内容；三星、SK 海力士和长江存储三方均拒绝置评，协议细节与适用范围未获确认。Xtacking 将存储单元和控制电路（CMOS）分别制作在两片晶圆上，再通过键合工艺合为一体，使两部分可以独立生产和优化。Omdia 高级分析师称，厂商因此可自行生产存储阵列，把逻辑电路交由晶圆代工厂生产，从而采用更先进制程；这一说法解释的是键合技术的潜在优势，并非对上述协议的独立确认。

telegram · zaihuapd · 11月25日 14:33

**「背景」** Xtacking 是长江存储约四年前率先用于 3D NAND 的混合键合技术：存储阵列与 CMOS 逻辑电路分别在不同晶圆上制造，再键合为一体，两部分可各自独立优化。据 TechPowerUp 报道，三星和 SK 海力士在推进数百层堆叠 NAND 时遭遇单晶圆工艺的限制，而 Xtacking 已经过量产验证，这让两家公司更容易转向该方案。另有行业人士称，三星此次授权包含交叉许可安排，时点在长江存储 2024 年于美国起诉美光 NAND 专利侵权之后。

**「对 NAND 制造分工的影响」** 如果许可最终实施，三星和 SK 海力士就能在 3D NAND 中把存储阵列与外围 CMOS 分开制造。按照来源中 Omdia 分析师的说法，逻辑电路可以交给晶圆代工厂，使用更先进的制程，这会为 NAND 工艺路线和代工协作提供新选项。TrendForce 援引日经的报道称，三星已在推进商用采用，但三家公司都拒绝置评，实际采用范围仍不确定。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Yangtze_Memory_Technologies">Yangtze Memory Technologies - Wikipedia</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC &#x27;s Xtacking ... | TechPowerUp</a></li>
<li><a href="https://www.trendforce.com/news/2025/02/24/news-samsung-rumored-to-adopt-hybrid-bonding-patent-from-chinas-ymtc-for-400-layer-nand/">[News] Samsung Rumored to Adopt Hybrid Bonding Patent from...</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC &#x27;s Xtacking ... | TechPowerUp</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing ...</a></li>

</ul>
</details>

**标签**: `#3D NAND`, `#Xtacking`, `#semiconductor manufacturing`, `#Samsung`, `#SK Hynix`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [法庭文件：美商务部被指施压英特尔交出 10%股份](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

据《连线》（WIRED）报道，法庭文件显示，2025 年 8 月美国商务部律师在与英特尔首席财务官的通话中称，不要“误以为这是一场谈判”，并提醒若董事会拒绝，将带来“无法预测的后果”。数日后英特尔董事会交出美方所要求的股份，特朗普随后宣布美国政府“完全拥有并控制英特尔 10%的股份”、且未为此付钱，这批股份现值约 110 亿美元——上述内容来自法庭文件中的指控，并非已经核实的事实。

telegram · zaihuapd · 11月25日 13:25

**「背景」** 美国政府直接持有私营企业股份并非惯常做法；据《纽约时报》报道，特朗普政府已在英特尔等公司推进以十亿美元计的政府持股交易。

**「潜在影响」** 据路透社报道，投资者担心此举会开启政府干预产业政策的先例：其他接受《芯片法案》补贴的芯片企业也可能被要求以政府入股的方式换取补贴，从而改变其股权结构和治理安排。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.nytimes.com/2025/11/25/us/politics/trump-intel-steel-minerals-china.html">Trump Administration Is Taking Billions in Stakes in Firms Like Intel ...</a></li>
<li>Investors worry Trump&#x27;s Intel deal kicks off era of US industrial policy | Reuters</li>

</ul>
</details>

**标签**: `#Intel`, `#US industrial policy`, `#semiconductor industry`, `#government equity stake`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [美国拟对 14 个贸易伙伴加征国别关税，对华再加征 20%](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

美国政府拟依据 1974 年《贸易法》第 301 条，对中国、欧盟、日本、印度等 14 个贸易伙伴加征按国别设定、不设统一税率的新关税，理由是这些经济体制造业存在靠补贴生产并压低价格的结构性产能过剩。按该计划，中国将在 2018 年已加征的 25%关税之上再加征 20%；若中国未遵守 2025 年 10 月在韩国釜山达成的贸易休战协议，对华新关税可能升至 40%。

telegram · zaihuapd · 11月25日 13:59

**「背景」** 此次拟议关税依据 1974 年《贸易法》第 301 条，针对调查所指的、受补贴支撑的制造业产能过剩。它源于为期八个月的调查，并旨在替代美国最高法院今年早些时候裁定无效的关税。

**「谁受影响」** 若拟议关税实施，从中国、欧盟、日本、印度等 14 个贸易伙伴进口受覆盖商品的美国进口商需按国别税率缴税，进口成本将上升；其中中国商品在 2018 年已加征的 25%之上再加 20%，若中国未遵守贸易休战协议，税率可能升至 40%。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U . S . unveils new Section 301 tariffs targeting China , EU and others</a></li>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on China ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U.S. unveils new Section 301 tariffs targeting China, EU and ...</a></li>
<li><a href="https://www.theguardian.com/us-news/2026/nov/25/trump-new-china-tariffs-europe">Trump proposing new tariffs on 14 partners including China ...</a></li>
<li><a href="https://thenextweb.com/news/new-tariffs-14-trading-partners-china-eu-section-301-excess-capacity">US proposes new tariffs on 14 trading partners, including ...</a></li>

</ul>
</details>

**标签**: `#贸易政策`, `#关税`, `#中美贸易`, `#301条款`, `#全球贸易`

---