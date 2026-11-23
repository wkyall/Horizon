---
layout: default
title: "Horizon Summary: 2026-11-23 (ZH)"
date: 2026-11-23
lang: zh
---

> 从 37 条内容中筛选出 11 条重要资讯。

---

**科技新闻**
1. [XNU Linux：在 Linux 上运行完整 OS X GUI 的实验项目](#item-tech-news-1) ⭐️ 7.0/10
2. [OpenAI 探讨困惑度与模型智能关系](#item-tech-news-2) ⭐️ 7.0/10
3. [O&\#x27;Reilly 文章追问硅谷变迁与机制设计](#item-tech-news-3) ⭐️ 7.0/10
4. [谷歌用模拟互联网测试 Chrome AI 代理](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows Server 2028 将默认移除 WoW64](#item-tech-news-5) ⭐️ 7.0/10

**科技博客**
1. [NVMe 取代 DRAM 的 KV 池](#item-tech-blog-1) ⭐️ 8.0/10
2. [不确定时，如何有章法地试错](#item-tech-blog-2) ⭐️ 5.0/10
3. [OpenAI 模型困惑度曲线解读](#item-tech-blog-3) ⭐️ 5.0/10

**财经新闻**
1. [美股科技股大跌，亚洲多地调整融资与卖空规则](#item-finance-news-1) ⭐️ 9.0/10
2. [厄尔尼诺海温创纪录，世界粮食计划署警告粮食援助承压](#item-finance-news-2) ⭐️ 7.0/10
3. [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](#item-finance-news-3) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [XNU Linux：在 Linux 上运行完整 OS X GUI 的实验项目](https://github.com/AFK-surf/xnulinux) ⭐️ 7.0/10

一个名为 XNU Linux 的 GitHub 项目以“在 Linux 上运行完整 OS X GUI 用户空间”为标题，面向希望在不启动 macOS 的情况下使用其图形用户空间的 Linux 用户。现有材料没有给出发布版本、安装步骤或兼容性细节，项目被描述为实验性。评论者指出它仍需要 Apple 硬件，因而并非普通 PC 上的现成方案。

hackernews · mmastrac · 11月23日 03:49 · [社区讨论](https://news.ycombinator.com/item?id=50607261)

**「背景：XNU 作为 Linux 模块」** XNU 是苹果以开源形式发布的 macOS 内核。据项目说明，xnulinux 从苹果公开源码构建 XNU，并将其作为可加载模块 xnu.ko 放入未修改的 arm64 Linux 内核中运行；这样 XNU 直接管理 CPU 和 MMU，使 macOS 进程与 Linux 进程在同一批 CPU 上原生并行，而不经过 hypervisor。

**「影响」** 对没有 Apple 硬件的普通 PC 用户，评论指出该项目仍依赖 Apple 硬件，因此它目前不能作为运行 macOS GUI 用户空间的可行替代；开发者若要评估，应准备 Apple 设备并把代码视为实验性。

**「社区讨论」** 有评论者认为，与其依赖 Apple 硬件，不如改进 GNUstep，并称其 Cocoa 后端可在 macOS 与 Linux/BSD 间复用；另有人以 Stela 从 GitHub 消失为例，担心此类兼容项目的可持续性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://hotrepo.ai/AFK-surf/xnulinux">AFK-surf/xnulinux: Run macOS userspace on arm64 Linux via XNU ...</a></li>
<li><a href="https://snslive.uk/article/2945906">XNU Linux: Full OS X GUI Userspace on Linux — Sovereign News ...</a></li>

</ul>
</details>

**标签**: `#macOS userspace`, `#Linux`, `#XNU`, `#OS compatibility`, `#reverse engineering`

---

<a id="item-tech-news-2"></a>
### [OpenAI 探讨困惑度与模型智能关系](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI 网站的一篇文章讨论困惑度（perplexity）与语言模型智能之间的关系，相关技术讨论延伸到交叉熵、压缩和评测基准。有评论者指出文章没有给出困惑度的定义，并补充说它衡量模型预测下一 token 时的意外程度：最好为 1，最差为词表大小。文章的核心论点及讨论围绕一个更简单的基础模型指标是否能反映能力趋势展开。

hackernews · acossta · 11月22日 17:06 · [社区讨论](https://news.ycombinator.com/item?id=50601525)

**「背景」** 困惑度是语言建模中常用的评估指标，与交叉熵损失直接相关，用来衡量模型对留出文本中下一个 token 的预测不确定性；数值越低，通常表示模型对文本的预测越准确。OpenAI 首席科学家 Jakub Pachocki 在文中主张把这一指标用于跨开发者比较和共同安全标准。

**「社区讨论」** 讨论中最受关注的是交叉熵损失与能力趋势之间出乎意料的清晰相关性：有人原以为强化学习会让这一指标不再重要，并认为相比日益复杂的评测，困惑度是更简单的基准；也有人从“预测即压缩”的角度认为这种对应关系并不意外。另有评论者转述微软 Mustafa Suleyman 的推文，称 MAI-2 Base 在 OpenAI 的评测集上 log-perplexity 为 0.819，与 GPT-5.6 Sol 基础模型相近，这属于厂商说法，尚未独立验证。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>

</ul>
</details>

**标签**: `#perplexity`, `#language-model-evaluation`, `#cross-entropy`, `#AI-scaling`

---

<a id="item-tech-news-3"></a>
### [O&\#x27;Reilly 文章追问硅谷变迁与机制设计](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

奥莱利（O&\#x27;Reilly）刊发的一篇评论文章追问硅谷为何偏离原有轨迹，主张重新设计市场机制，把目标从股东价值转向“人类繁荣”，而不是继续把现有市场规则当作自然现象。文章把机制设计称为“反向博弈论”，要求先追问“我们应当玩什么游戏”，而不是只研究当前游戏的规则。该文在 Hacker News 引发大量讨论，但其核心主张属于观点与分析，并非已经落地实施的政策、产品或可独立验证的结果。

hackernews · greenyouse · 11月22日 19:20 · [社区讨论](https://news.ycombinator.com/item?id=50602947)

**「背景」** 机制设计（mechanism design）在经济学中常被称为&quot;逆向博弈论&quot;：博弈论是在既定规则下推演结果，机制设计则从想要的结果反推应该制定什么规则。O&\#x27;Reilly 这篇文章正是用这一框架发问，并被 Hacker News 讨论帖引述为&quot;如果我们想玩的游戏是人类繁荣，就需要设计能把我们引向该结果的机制&quot;；其批评对象是长期以来把股东价值（shareholder value）当作默认优化目标的硅谷公司治理与市场规则。

**「社区讨论」** 评论区总体认同文章对机制设计的追问，但对硅谷变化的直接原因看法不一：有评论者强调零利率（ZIRP）时代让公司过度扩张，如今利率回升后又借 AI 削减核心能力；也有人把问题归咎于华尔街与“VC 网红”文化。另有评论者认为，市场并非自然现象，而是被人建造并设定了目标的机器，因此需要重新编程其目标。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50602947">What Happened to Silicon Valley ? | Hacker News</a></li>

</ul>
</details>

**标签**: `#Silicon Valley`, `#mechanism design`, `#tech industry`, `#shareholder capitalism`, `#AI`

---

<a id="item-tech-news-4"></a>
### [谷歌用模拟互联网测试 Chrome AI 代理](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

蓝点网报道称，谷歌为 Chrome 的 AI 代理搭建了一个名为 Mirror Dimension 的模拟互联网，并在隔离环境中测试它打开网站、搜索浏览、登录、加购和完成任务等操作。该环境包含数千个模拟网站，每名工程师单独隔离测试，每天运行超过 1000 个测试案例，重点是防御恶意网页的提示词注入等攻击。目前这些信息来自二手报道，尚无谷歌的一手确认，报道也未说明该测试环境是否公开或已用于正式版本。

telegram · zaihuapd · 11月23日 01:30

**「背景」** 浏览器 AI 代理需要依据网页内容自主点击、输入并完成任务，因此测试环境既要接近真实上网场景，又不能让测试直接暴露真实账号和网站。谷歌安全博客称，Mirror Dimension 是 Chrome 团队搭建的合成网络，用数千个模拟站点复现日常上网路径，并在隔离环境中评估自动浏览功能；Wired 报道称该环境完全由 Chrome 团队控制，还会加入隐藏的提示词注入攻击来检验防御。

**「影响」** 对希望让 Chrome AI 代理执行登录、加购等操作的用户而言，报道所强调的提示词注入防御是判断这类操作能否安全交付的关键；但报道没有披露测试通过率、实际防护效果或上线时间，因此无法据此判断代理的真实安全性。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents : Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://www.wired.com/story/google-built-a-giant-mirror-dimension-internet-to-test-its-chrome-ai-agents/">Google Built a Giant ‘ Mirror Dimension ’ Internet to Test Its Chrome ...</a></li>

</ul>
</details>

**标签**: `#Chrome AI agent`, `#prompt injection`, `#AI agent testing`, `#browser security`, `#Google`

---

<a id="item-tech-news-5"></a>
### [Windows Server 2028 将默认移除 WoW64](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

微软在 Ignite 2026 上表示，计划于 2027 年秋季与 Windows 11 27H2 一同发布的 Windows Server 2028 将默认不再包含 WoW64，因此开箱无法运行 32 位应用。需要兼容旧软件的管理员可通过按需功能（FoD）装回 WoW64，在 Server Core 上通常使用 PowerShell 或 DISM 添加。微软称此举旨在减少攻击面并阻止 32 位恶意软件；Windows 11 目前仍保留 WoW64，且微软未公布移除计划。

telegram · zaihuapd · 11月23日 03:03

**「背景」** WoW64 是 64 位 Windows 中的兼容层，负责在 64 位系统上加载并运行 32 位应用；此前它随系统默认提供，服务器管理员通常无需额外配置。Windows Server 2028 将该组件改为按需功能（FoD），意味着默认安装后 32 位程序无法启动，需由管理员显式添加。

**「升级前需清点 32 位依赖」** 对仍运行 32 位管理代理、备份软件或旧安装程序的企业来说，升级到 Windows Server 2028 前需要清点这些依赖，并在部署流程中预留通过 PowerShell 或 DISM 添加 WoW64 按需功能的步骤，否则相关程序在开箱状态下无法启动。自动化部署脚本、系统镜像和标准化服务器模板也要相应调整，把这一兼容层作为显式安装项处理。

**标签**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

## 科技博客

<a id="item-tech-blog-1"></a>
### [NVMe 取代 DRAM 的 KV 池](https://vllm.ai/blog/2026-11-23-skip-the-dram-tier) ⭐️ 8.0/10

rss · vLLM Blog · 11月23日 00:00

**「背景」** 作者指出，智能体服务多是重发长前缀的多轮会话：AgentX 回放的中位每轮输入为 142K token，96%以上是已见过的前缀；GPU 显存和主机 DRAM 很快被填满，1.8TB DRAM 池标价约 7.6 万美元却只能保留 23–47 分钟 KV。

**「方案」** 在 AMD MI355X 和 MoRI UMBP 上，作者把 vLLM 的 1.8TB KV 池直接放到本地 NVMe，仅用约 80GB DRAM 缓冲写入和暂存读取。回放 AgentX 的 Kimi-K3 负载时，同容量 NVMe 池在 48、70、96 并发会话下吞吐与 DRAM 相差不超过 1%，并在另一对机器复现；作者认为关键是同容量池保持相近命中率，且异步加载被预填充等待掩盖。成本从“每 TB 持有”转为“每 TB 写入”：按标价，支撑每天 83TB 写入的硬盘约 5.9 万美元可留一天 KV，7.6 万美元 DRAM 池只留 31 分钟；低于约 24 分钟时 DRAM 更便宜。调优上，256MiB 小段文件替代 4GiB 让 70 会话吞吐提高 15.6%、TTFT p90 从 63.0 降到 21.3 秒；把 GPU 命中“touch”回池、加密检查点（命中率 91.4%→95.6%，吞吐+33%）也有效。作者也提醒写入会磨损 SSD：96 会话下测试盘约每天 11 次盘写、额定寿命约 5.5 个月，需分布式铺开；部分保留收益由串联模型估算。

**「启示」** 作者的核心结论是：在智能体 KV 缓存场景，NVMe 池的容量与保留时间可以比 DRAM 层更重要，只要命中率和异步加载管理得当，跳过 DRAM 层在性能上几乎不损失，而成本模型从持有容量转向写入寿命。这使 KV 池的规模应由会话保留时间与 SSD 写入预算决定，而不是默认复制 DRAM 层；但该结论仍受特定 AMD/MoRI/vLLM 设置与写入磨损约束。

**标签**: `#KV cache`, `#LLM inference`, `#NVMe`, `#vLLM`, `#benchmarking`

---

<a id="item-tech-blog-2"></a>
### [不确定时，如何有章法地试错](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** 面对缺乏明确指引、不知道什么会有帮助的局面，等待彻底看清再行动往往并不可取；作者提出，更有效的是主动“乱试”，但必须承认这会带来声誉风险。

**「方案」** 作者把“乱试”定义为三条相互支撑的原则：大量尝试不同方案、密切观察反馈、对没有正反馈的方案果断放弃。多试既是为了直接接触现实，也是因为多数初始想法并不可靠，同时持有多个方案还能避免过度投入。产品上，他在 GitHub Models（现已停运）做过许多未奏效的功能，但“用 GitHub Actions token 运行 AI 推理”意外留存，并成为 Continuous AI 的种子；工程上，与其先啃透庞大系统，不如做若干探索性改动，看效果再决定是否深入；组织问题上，可尝试自动化、接手任务或提出长期方案，但这类情境尤其要敏感于反馈，否则帮助对象的不满会转向自己。作者也提醒，从内部看这很像反复失败，但管理者可能只看到主动实验，因此要识别这种心理不适并继续推进。

**「启示」** 作者的结论不是盲目忙碌，而是在信息不足时以低承诺、快反馈的方式换取理解，并随时砍掉失败方案；只要守住反馈纪律，这种看似狼狈的试错往往比先求全懂更有效。

**标签**: `#engineering management`, `#decision-making under uncertainty`, `#experimentation`, `#career advice`

---

<a id="item-tech-blog-3"></a>
### [OpenAI 模型困惑度曲线解读](https://seangoedecke.com/notes-on-openais-perplexity-reveal/) ⭐️ 5.0/10

rss · Sean Goedecke · 11月23日 00:00

**「背景」** OpenAI 公布了覆盖已发布模型的困惑度随时间变化图，作者据此讨论这是否能让外界看清前沿实验室的训练指标。困惑度衡量模型对特定留出文本的预测能力，主要用于预训练阶段。

**「方案」** 作者指出，这张图虽提供了罕见可见性，但读数高度依赖数据集，不能直接与其他实验室的数据横向比较，也不反映后训练中的强化学习和思维链能力。图中只有少数模型共享同一基座，作者据此认为 o1 与 o3 同源，而 GPT-4.5 处出现停滞；GPT-5.2 之后损失下降明显加速，这与“实验室已放弃预训练、转向强化学习”的流行说法相矛盾。关于对齐透明度，作者认为帮助有限：若要监测异常下降或设定阈值，OpenAI 还需公布未发布预训练模型的困惑度及具体评测集。至于主观能力感受，作者称 o3 和 GPT-5.3-Codex 才是明显跃升，GPT-5.5 并未带来同等体感，这可能源于强化学习对思维链和迎合行为的塑造，而困惑度不会体现这些变化。

**「启示」** 作者的核心结论是：困惑度图能透露预训练进展并反驳“只剩强化学习”的叙事，但它只是受数据集限制的预训练指标，既不足以衡量模型实际能力，也不足以单独支撑安全透明度。

**标签**: `#perplexity`, `#LLM training metrics`, `#model evaluation`, `#AI safety transparency`, `#OpenAI`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [美股科技股大跌，亚洲多地调整融资与卖空规则](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

美国 AI 科技股周五遭大规模抛售，纳斯达克指数单日下跌 5.28%，费城半导体指数重挫近 11%；中国内地将融资保证金最低比例下调至 80%，韩国和中国台湾地区也调整了回购与卖空规则。

telegram · zaihuapd · 11月22日 13:24

**「背景」** 在亚洲各方出手前，美国股市周五出现科技股集中抛售，彭博报道称，中国、台湾和韩国随后推出稳市措施，以遏制跌势。韩国股市稳定基金是用于填补国内股市流动性缺口的政策工具，此次是重启部署准备。

**「影响」** 这些规则变化将直接改变中国内地融资交易者、韩国回购方以及中国台湾地区卖空与融券投资者的资金成本和可操作空间。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-22/china-lowers-margin-requirement-to-80-to-boost-stock-liquidity">Asia’s Stock Rescue Efforts Gather Pace After Wall Street... - Bloomberg</a></li>
<li><a href="https://finance.biggo.com/news/41704fd7-7d88-4cb6-8773-17f6b6f5c964">South Korea Restarts Stock Market Stabilization Fund Preparations...</a></li>

</ul>
</details>

**标签**: `#US tech selloff`, `#Asian markets`, `#market stabilization`, `#short-selling restrictions`, `#margin rules`

---

<a id="item-finance-news-2"></a>
### [厄尔尼诺海温创纪录，世界粮食计划署警告粮食援助承压](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

据伯克利地球气候学家 Zeke Hausfather，截至 10 月，衡量厄尔尼诺强度的中热带太平洋升温已达 3.5℃，超过此前约 2.75℃的纪录，并预计在初冬升至约 4℃的峰值。世界粮食计划署 8 月警告，本轮厄尔尼诺可能在 2027 年底前把额外 4900 万人推入急性粮食不安全、使总数达 2.74 亿，而全球援助资金 2025 年较 2022 年峰值下降 30%。

telegram · zaihuapd · 11月22日 14:09

**「背景」** 厄尔尼诺是指赤道太平洋中部和东部海温异常升高、进而改变全球降雨格局的气候现象；本轮升温幅度已超过 2015–2016 年那次约 2.75℃ 的纪录，而世界粮食计划署指出，当年那轮厄尔尼诺曾影响 6000 万至 1 亿人的粮食安全。

**「影响」** 若预测成真，依赖粮食援助的低收入国家家庭将面临双重压力：气候冲击推高需求，而援助资金较 2022 年峰值减少 30%迫使机构缩小覆盖，更多家庭可能得不到足够的紧急粮食支持。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.un.org/en/story/2026/08/1168079">Strengthening El Niño to push 49 million more people into ...</a></li>
<li><a href="https://www.theclimatebrink.com/p/the-strongest-el-nino-ever">The Strongest El Niño Ever - by Zeke Hausfather</a></li>
<li><a href="https://www.theguardian.com/global-development/2026/sep/10/global-humanitarian-aid-crisis-64m-fewer-people-received-help-report">Tens of millions of people fail to get humanitarian aid as ...</a></li>

</ul>
</details>

**标签**: `#El Niño`, `#food security`, `#humanitarian aid`, `#climate risk`, `#global economy`

---

<a id="item-finance-news-3"></a>
### [蚂蚁集团领投 Simplexity Robotics 1 亿美元 pre-A 轮，投后估值 16 亿美元](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

彭博报道，中国具身智能公司 Simplexity Robotics 完成 1 亿美元 pre-A 轮融资，由蚂蚁集团领投，投后估值 16 亿美元。

telegram · zaihuapd · 11月23日 02:02

**「背景」** 这家公司 2025 年 7 月成立于杭州；据盖世汽车报道，其在今年 3 月称成立半年内完成五轮融资、累计 20 亿元人民币，投后估值已超过 10 亿美元。

**「影响」** 据彭博报道，这笔资金将用于与宇树、优必选等更成熟的厂商争夺市场，反映出资本正加码中国人形机器人行业。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.gasgoo.com/robot/news/70449505-%E7%90%86%E6%83%B3%E5%89%8D%E9%AB%98%E7%AE%A1%E5%81%9A%E6%9C%BA%E5%99%A8%E4%BA%BA-%E5%8D%8A%E5%B9%B4%E8%9E%8D%E4%BA%8620%E4%BA%BF-%E6%80%8E%E4%B9%88%E5%81%9A%E5%88%B0%E7%9A%84/">理想前高管做机器人，半年 融 了20 亿 ，怎么做到的？ | 盖世汽车</a></li>

</ul>
</details>

**标签**: `#humanoid robotics`, `#venture funding`, `#Ant Group`, `#China tech`, `#startup valuation`

---