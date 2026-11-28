---
layout: default
title: "Horizon Summary: 2026-11-28 (ZH)"
date: 2026-11-28
lang: zh
---

> 从 31 条内容中筛选出 8 条重要资讯。

---

**科技新闻**
1. [多州总检察长起诉 SpaceX，指控 Grok 生成儿童性剥削与非自愿私密图像](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenSec 披露 Linux nfsd 9.8 分预认证漏洞](#item-tech-news-2) ⭐️ 8.0/10
3. [假计算机验证证明与多重检查](#item-tech-news-3) ⭐️ 7.0/10
4. [用 WebRTC 的信用卡盗刷脚本现身热门购物网站](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis 分析 AWS Trainium3 推理微架构与性价比](#item-tech-news-5) ⭐️ 7.0/10
6. [微软扩大 Windows 内置驱动覆盖，打印机音频优先](#item-tech-news-6) ⭐️ 7.0/10

**财经新闻**
1. [国常会部署资本市场稳市机制，要求加力发挥“国家队”作用](#item-finance-news-1) ⭐️ 7.0/10
2. [央行公布大额存单新规 个人起购门槛降至 10 万元](#item-finance-news-2) ⭐️ 7.0/10

---

## 科技新闻

<a id="item-tech-news-1"></a>
### [多州总检察长起诉 SpaceX，指控 Grok 生成儿童性剥削与非自愿私密图像](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 8.0/10

弗吉尼亚州总检察长杰伊·琼斯（Jay Jones）等州总检察长对 SpaceX 提起诉讼，指控其旗下 xAI 的 Grok 生成儿童性剥削材料以及未经同意的私密图像（报复性色情）。诉状将 SpaceX 认定为 X、xAI 与 Grok 的母公司，并主张其应对这些图像在该平台上的创建和传播承担责任。目前公开材料未披露具体诉求、涉案图像数量、诉讼时间表，也未说明 Grok 相关防护措施的具体细节。

hackernews · DeepLogin · 11月27日 19:42 · [社区讨论](https://news.ycombinator.com/item?id=50670855)

**「背景」** Grok 是 xAI 开发并接入 X 的聊天机器人；这起诉讼把 SpaceX 列为 X、xAI 和 Grok 的母公司。弗吉尼亚州和俄勒冈州总检察长在诉状及新闻稿中称，Grok 和 X 未能阻止儿童性剥削内容及未经同意的性化图像的生成与传播，并要求民事罚款和禁令。

**「影响」** 这起诉讼把责任焦点从生成内容的用户移到 Grok 的运营方及其母公司 SpaceX：州检察长寻求用民事诉讼追究平台责任，可能迫使 xAI 收紧 Grok 的内容过滤和滥用处置，并让 SpaceX 承担应诉与合规压力。近期法院对 AI 生成儿童性虐待材料的刑事指控出现驳回，暴露出法律空档（tool-3-1、tool-3-2、tool-3-3），这也解释了为何州层面转而通过民事诉讼向平台施压。

**「社区讨论」** 有评论者对 Grok 此前是否已被普遍禁止生成此类内容感到困惑，并追问用户是否需要“诱导”模型才能得到这类输出；另有人把焦点转向实际制作这些图像的个人是否应承担责任。一位评论者还主张，最高法院已裁定为个人消费而用 AI 制作儿童性虐待材料属于受保护的言论，但不得涉及真实儿童；这一说法未获所供材料证实。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform">Attorneys General Jones and Rayfield File Suit Against SpaceX ...</a></li>
<li><a href="https://www.doj.state.or.us/media-home/news-media-releases/ag-rayfield-takes-legal-action-against-grok-for-failing-to-block-child-exploitation/">Oregon Attorney General Rayfield and Virginia Attorney ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/oregon-virginia-spacex-grok-deepfake-lawsuits.html">SpaceX sued by 2 states over AI deepfake porn, Grok ... - CNBC</a></li>
<li>A recent federal court decision highlights a troubling gap in the law ...</li>
<li>Federal judge rules that AI-generated child sex abuse material is ...</li>
<li>Federal judge rules that AI-generated child sex abuse material is ... - FOX19</li>

</ul>
</details>

**标签**: `#AI safety`, `#content moderation`, `#generative AI`, `#platform liability`, `#AI regulation`

---

<a id="item-tech-news-2"></a>
### [OpenSec 披露 Linux nfsd 9.8 分预认证漏洞](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

据 OpenSec 披露，Linux 内核 NFS 服务器 nfsd 存在预认证堆溢出 CVE-2026-99362，CVSS 评分 9.8：攻击者无需登录，只需向 tcp/2049 发起一条连接，即可越界写入内核堆并获取 root。该漏洞自 2014 年的 Linux 3.16 起存在，影响启用 NFSv4.1 或 4.2 的文件服务器、NAS 和集群存储节点。修复已在 6.12.117、6.18.61、7.3.2 和 7.4-rc1 中发布，需升级内核并重启；无法立即升级时可用防火墙限制 tcp/2049 访问。CVE 于 2026 年 11 月 20 日公开，上述细节来自该披露，所给材料未提供独立验证。

telegram · zaihuapd · 11月27日 12:57

**「背景」** 该漏洞的根源在于 nfsd 在缓存响应前未校验响应是否落在协商好的缓冲区上限内，导致响应数据被写到已分配堆缓冲区之外；触发路径涉及 NFSv4.1/4.2 会话。该缺陷自 2014 年的 Linux 3.16 起就存在于相关实现中，使启用这些 NFS 版本的主机长期暴露在风险之下。

**「影响与处置」** 对暴露 tcp/2049 的服务器、NAS 和集群存储节点，运维方需安排内核升级并重启；无法立即升级时限制 2049/tcp 虽能降低暴露面，但也可能阻断合法的 NFSv4.1/4.2 访问。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>

</ul>
</details>

**标签**: `#Linux kernel`, `#NFS`, `#security vulnerability`, `#CVE`, `#remote exploit`

---

<a id="item-tech-news-3"></a>
### [假计算机验证证明与多重检查](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

该页面分析证明检查器自身的缺陷如何产生“通过计算机检查”的假证明，并把这类风险与已出现的健全性 bug 及多重验证器缓解措施放在一起讨论。文章讨论涉及 Lean、Metamath 等系统，关注的是检查器实现出错时验证结果仍可能被误认为可信。由于未提供正文，具体案例、涉及版本和作者结论无法从现有材料核实。

hackernews · \_tk\_ · 11月27日 15:26 · [社区讨论](https://news.ycombinator.com/item?id=50667989)

**「背景」** 形式化证明通常由一个相对小的检查器（如 Lean 的内核）逐条复核，只有检查器判定通过，证明才会被接受。若检查器实现本身存在健全性缺陷，它就可能接受无效推导，因此“机器已验证”并不等于命题必然为真。

**「影响」** 对形式化验证实践者来说，这意味着不能把“检查器通过”当作绝对保证：若只依赖单一检查器，其健全性 bug 可能让错误证明过关；Metamath 主库要求多个独立验证器的做法，正是把检查器实现纳入信任边界的应对。

**「社区讨论」** 评论者争论该页面是否低估了多重验证器的防线：twotwotwo 与 dwheeler 指出，单个检查器出错不等于能骗过数学界，Metamath 的 set.mm/iset.mm 要求通过五个独立实现、五种语言的验证器；gr\_norm 则认为现有检查器历来的健全性 bug 很少，已足够覆盖绝大多数软件验证需求。andai 还提醒，即使证明通过，也可能只是证明了实现符合代理自己对需求的错误理解。

<details><summary>参考链接</summary>
<ul>
<li>Not if it&#x27;s lean-verified. - Hacker News</li>

</ul>
</details>

**标签**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-4"></a>
### [用 WebRTC 的信用卡盗刷脚本现身热门购物网站](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

InfoHawk 的一篇报道称，热门购物网站上发现了利用 WebRTC 的信用卡盗刷（skimming）脚本，披露时间点落在 2026 年黑色星期五购物季。据可获得的摘要描述，这类脚本依附于电商页面引入的第三方脚本运行，并把目标集中在移动设备上。报道没有给出受影响站点名单、脚本注入途径、样本哈希或受害规模等细节，因此这目前只是单一来源的发现，尚未见到独立验证的统计数据。

hackernews · scanr · 11月27日 15:40 · [社区讨论](https://news.ycombinator.com/item?id=50668145)

**「背景」** Magecart 类攻击的常见手法是把恶意脚本注入电商结账流程，从而在用户输入时窃取支付卡数据；ZDNet 曾将相关 skimmer 工具包描述为门槛较低的攻击方式。Palo Alto Networks 对 Alexa 前 1 万个站点的调查也发现过信用卡 skimmer 与加密货币挖矿脚本，说明流行购物站点被植入此类脚本并非全新现象。WebRTC 是浏览器内置的实时通信 API，可建立音视频和数据通道，因而也可能被注入脚本当作外传数据的通道。

**「实际影响」** 对在结账流程中嵌入第三方脚本的电商站点来说，风险在于这些脚本与页面同源执行，可以直接读取并外传支付表单内容，服务端侧措施无法覆盖这一环节。评论者 afavour 指出，该手法并不依赖 WebRTC 的独有能力，用普通 HTTP 请求同样可以实现，选择它只是因为更少被监控；这也意味着把排查重点放在移动端流量上是运维方需要面对的检测难点。

**「社区讨论」** 多位评论者把根源归于第三方脚本，而非 WebRTC 本身：afavour 认为它只是更少被监控，且同样的手法用普通 HTTP 请求就能实现，移动端被针对也只是因为更难检测。jszymborski 以此作为不为此感到愧疚地拦截广告的理由，s\_u\_d\_o 质问广告平台为何不在客户端沙箱化并禁止 JS 执行，snickerer 则主张网站只应传输数据、由浏览器决定如何渲染和运行。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/top-sites-infiltrated-with-credit-card-skimmers-and-crypto-miners/">Top sites infiltrated with credit card skimmers and crypto miners</a></li>
<li><a href="https://www.zdnet.com/article/inter-a-low-bar-kit-for-magecart-website-credit-card-skimmer-attacks/">Inter: a ‘low bar’ kit for Magecart credit card skimmer attacks... - ZDNET</a></li>

</ul>
</details>

**标签**: `#web security`, `#credit card skimming`, `#WebRTC`, `#supply chain attacks`, `#e-commerce security`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis 分析 AWS Trainium3 推理微架构与性价比](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis 发布了对 AWS Trainium3 的推理与微架构深度分析，并把 Trainium3 接入其 InferenceX/UBenchX 基准，面向评估 AI 推理硬件的团队。文章称，在 AgentX 的生产级 agentic 推理回放中，Trainium3 PDS + vLLM 在整个 TCO 对 p90 交互性曲线上仅次于 Vera Rubin、优于其他所有加速器，并在生成 token 的 TCO 上与 Nvidia GB300 互有胜负甚至占优。微架构层面，文章强调 Trainium 从底层为 ML 设计、把 tile 作为一等原语，其 DGE 对应 Nvidia TMA 和 AMD MI455X TDM；微基准显示其在小消息尺寸下可达到峰值 HBM 带宽利用率，而 Nvidia GPU 做不到。不过，所给摘录没有列出具体基准数字或完整方法，且作者感谢 AWS Annapurna Labs 团队协助验证实验，因此这些结果应视为厂商协助下的分析结论，而非独立复现。

rss · Semianalysis · 11月27日 15:54

**「背景」** 英伟达的数据中心 GPU 最初面向图形渲染，之后逐代叠加 AI 专用硬件：Volta 引入 Tensor Core，Hopper 加入用于 HBM 与 SRAM 间 tile 数据搬运的 TMA，Blackwell 又增加用于累加的 Tensor Memory。AWS Trainium 则从一开始就按机器学习负载设计，把 tile 作为一等原语，而不是在大量线程模型上再外挂张量计算与数据搬运引擎；这构成了 SemiAnalysis 比较两者微架构的出发点。

**「影响」** 对使用 vLLM 的推理团队，这意味着 Trainium3 应被纳入与 GB300、Vera Rubin 并列的端到端 agentic 工作负载 TCO 对比；在缺乏可复现数字的情况下，选型仍应以自身负载的实测吞吐、延迟和迁移成本为准。

**标签**: `#AI hardware`, `#Trainium`, `#AWS`, `#microarchitecture`, `#inference`

---

<a id="item-tech-news-6"></a>
### [微软扩大 Windows 内置驱动覆盖，打印机音频优先](https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html) ⭐️ 7.0/10

微软在 Ignite 2026 大会上确认，正为打印机、音频等整类硬件开发 Windows 内置驱动，以减少进入系统内核的第三方驱动代码；部分第三方代码未来可能被内置功能取代。打印机是首批重点，微软近期推出的 Windows Ready Print 模式用于替代旧式第三方打印驱动；SoundWire 和 SDCA 等音频类驱动“很快”将成为 Windows 内置组件。I3C 总线、USB 以太网和 MIPI 摄像头类驱动仍在开发中，微软同时通过驱动质量倡议（DQI）提高可靠性、质量和安全标准，并鼓励第三方开发者和 OEM 优先使用内置驱动。

telegram · zaihuapd · 11月28日 02:09

**「背景」** Windows 的打印机、音频等外设长期依赖 OEM 或第三方提供的内核态驱动，这类代码运行在系统最高权限层，历来是蓝屏与安全漏洞的常见来源。微软所说的“内置类驱动”是指由微软为整类设备统一提供的通用驱动，硬件厂商无需再为每款产品单独交付内核驱动。

**「对驱动开发者与 OEM 的影响」** 对驱动开发者和 OEM 来说，直接后果是定制逻辑需要迁移到 Windows 内置类驱动之上：打印机厂商将首当其冲，需要把旧式第三方打印驱动迁移到 Windows Ready Print 模式；而音频（SoundWire、SDCA）、I3C、USB 以太网和 MIPI 摄像头类驱动目前仍处于开发阶段，依赖私有内核驱动实现差异化功能的厂商需要提前评估这些功能能否保留，并按微软驱动质量倡议（DQI）的标准验证兼容性与可靠性。

**标签**: `#Windows`, `#device drivers`, `#Microsoft`, `#kernel security`, `#hardware compatibility`

---

## 财经新闻

<a id="item-finance-news-1"></a>
### [国常会部署资本市场稳市机制，要求加力发挥“国家队”作用](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 7.0/10

国务院总理李强 11 月 27 日主持召开国务院常务会议，会议指出要持续完善资本市场稳市机制，实施好存量政策并谋划出台增量政策；具体包括加力发挥“国家队”稳市作用、进一步优化中央汇金公司的类“平准基金”功能、提供充足流动性保障，以及完善保险、企业年金、社保基金等中长期资金入市的支持引导政策。会议同时要求依法强化资本市场全链条监管，坚决查处财务造假、违规减持等行为。

telegram · zaihuapd · 11月27日 05:35

**「背景」** “国家队”稳市和中央汇金类“平准基金”此前多被视为危机应对的临时工具；专家田利辉解读称，此次国常会的表述意味着该机制正式升格为国家金融治理的常设基础设施。

**「影响」** 若配套政策落地，直接受影响的是保险、企业年金、社保基金等中长期资金的权益投资安排，以及中央汇金作为类“平准基金”的入市操作；但会议通稿未给出新增资金规模、工具细节或时间表，实际效果取决于后续细则。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941634358.html">如何理解 国 常会对资本 市 场的最新定调？ 专 家 解读来了 _ 东方财富网</a></li>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>
<li><a href="https://soft20261029.rgdklrf.cn/article/67.html">soft20261029.rgdklrf.cn/article/67.html</a></li>

</ul>
</details>

**标签**: `#资本市场政策`, `#中央汇金`, `#平准基金`, `#中长期资金入市`, `#国务院常务会议`

---

<a id="item-finance-news-2"></a>
### [央行公布大额存单新规 个人起购门槛降至 10 万元](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

中国人民银行 11 月 27 日公布《大额存单管理办法》，将个人投资人认购起点由原来的 20 万元降至不低于 10 万元，机构投资人由 1000 万元降至不低于 500 万元，两个门槛均下调一半，自 2027 年 3 月 21 日起施行。同日央行还发布《人民币存贷款利率管理规定》，要求金融机构自主确定存贷款利率、不得通过高息揽储等不正当手段吸收存款，同样自 2027 年 3 月 21 日起施行。

telegram · zaihuapd · 11月27日 11:36

**「背景」** 大额存单是银行面向个人和机构发行的大额存款凭证，现行门槛依据 2015 年《大额存单管理暂行办法》和 2016 年第 13 号公告执行，新办法施行后将同时废止这两份文件。

**「影响」** 门槛下调后，手中资金在 10 万至 20 万元之间的家庭无需再凑足 20 万元即可购买大额存单；据媒体报道，大额存单利率通常比同期限普通定期存款高 0.3 至 0.9 个百分点。

<details><summary>参考链接</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260317A05VOS00">同样是 存 10 ...</a></li>

</ul>
</details>

**标签**: `#央行监管`, `#大额存单`, `#存贷款利率`, `#银行业`, `#个人投资`

---