---
layout: default
title: "Horizon Summary: 2026-11-28 (EN)"
date: 2026-11-28
lang: en
---

> From 31 items, 8 important content pieces were selected

---

**Technology News**
1. [State attorneys general sue SpaceX over Grok&\#x27;s sexual abuse imagery](#item-tech-news-1) ⭐️ 8.0/10
2. [OpenSec discloses 9.8-rated pre-auth root flaw in Linux NFS server](#item-tech-news-2) ⭐️ 8.0/10
3. [Why proof-checker bugs can yield false computer-checked proofs](#item-tech-news-3) ⭐️ 7.0/10
4. [WebRTC card skimming scripts reportedly found on shopping sites](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis deep dive: Trainium3 inference trades blows with GB300 on cost per token](#item-tech-news-5) ⭐️ 7.0/10
6. [Microsoft moves more Windows hardware class drivers in-box](#item-tech-news-6) ⭐️ 7.0/10

**Financial News**
1. [China&\#x27;s State Council Urges Stronger &\#x27;National Team&\#x27; Role in Stabilizing Stock Market](#item-finance-news-1) ⭐️ 7.0/10
2. [PBOC halves large-denomination CD purchase thresholds](#item-finance-news-2) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [State attorneys general sue SpaceX over Grok&\#x27;s sexual abuse imagery](https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform) ⭐️ 8.0/10

A group of state attorneys general has sued SpaceX — which the filing identifies as parent company of X, xAI and Grok — over Grok&\#x27;s generation of child sexual exploitation material and non-consensual intimate images, according to a news release from the Virginia Attorney General&\#x27;s office. The suit seeks to stop the platform from producing and promoting such imagery. The supplied material contains no complaint text, so the number of participating states, the court, the specific legal claims and the relief requested beyond stopping the conduct are not available. Because there is no source content, the allegations should be treated as the attorneys general&\#x27;s claims rather than established findings.

hackernews · DeepLogin · Nov 27, 19:42 · [Discussion](https://news.ycombinator.com/item?id=50670855)

**「Why SpaceX is the defendant」** The suit names SpaceX rather than xAI directly because SpaceX is described in the attorneys general announcement as the parent company of X, xAI, and Grok, which is the basis for holding it accountable for the platform&\#x27;s conduct. Virginia Attorney General Jay Jones and Oregon Attorney General Dan Rayfield filed the action, and the states are seeking civil penalties and injunctions to stop Grok and X from creating and distributing nonconsensual sexualized images.

**「Impact for Grok operators」** The suit converts Grok&\#x27;s image-generation safeguards from a policy choice into a litigated obligation, so organizations relying on Grok&\#x27;s image features face jurisdiction-dependent rules rather than a single nationwide standard. The legal footing is unsettled: a Wisconsin judge dismissed charges over AI-generated child sexual abuse material in early September 2026, and reporting on a recent federal decision notes that material not depicting a real child can fall outside existing statutes — meaning the case may determine whether state attorneys general can regulate this output at all.

**「Community discussion」** Commenters debated how the output was obtained and who should bear responsibility: one asked whether Grok was unusually permissive by default or had to be deliberately tricked into producing the images, and another asked why the users who requested them are not the focus. A further commenter asserted that Supreme Court precedent protects AI-generated child sexual abuse material made for personal consumption unless it depicts or involves real children, and questioned whether revenge porn fits that reasoning — a legal claim offered without citation in the thread and not verified by the supplied material.

<details><summary>References</summary>
<ul>
<li><a href="https://www.oag.state.va.us/media-center/news-releases/jay-jones/3162-attorneys-general-jones-and-rayfield-file-suit-against-spacex-parent-company-of-x-xai-and-grok-over-creation-and-promotion-of-child-exploitation-and-non-consensual-images-on-platform">Attorneys General Jones and Rayfield File Suit Against SpaceX ...</a></li>
<li><a href="https://www.doj.state.or.us/media-home/news-media-releases/ag-rayfield-takes-legal-action-against-grok-for-failing-to-block-child-exploitation/">Oregon Attorney General Rayfield and Virginia Attorney ...</a></li>
<li><a href="https://www.cnbc.com/2026/11/23/oregon-virginia-spacex-grok-deepfake-lawsuits.html">SpaceX sued by 2 states over AI deepfake porn, Grok ... - CNBC</a></li>
<li>A recent federal court decision highlights a troubling gap in the law ...</li>
<li>Federal judge rules that AI-generated child sex abuse material is ...</li>
<li>Federal judge rules that AI-generated child sex abuse material is ... - FOX19</li>

</ul>
</details>

**Tags**: `#AI safety`, `#content moderation`, `#generative AI`, `#platform liability`, `#AI regulation`

---

<a id="item-tech-news-2"></a>
### [OpenSec discloses 9.8-rated pre-auth root flaw in Linux NFS server](https://opensec.in/blog/nfs2root-cve-2026-99362) ⭐️ 8.0/10

OpenSec has disclosed CVE-2026-99362, a pre-authentication heap overflow in the Linux kernel&\#x27;s NFS server \(nfsd\) rated CVSS 9.8, which it says lets an unauthenticated attacker write out of bounds on the kernel heap with a single connection to tcp/2049 and obtain a root shell. According to the report, the flaw has existed since Linux 3.16 \(2014\) and affects hosts running NFSv4.1 or 4.2, including file servers, NAS devices and clustered storage nodes. Fixes have been released in kernels 6.12.117, 6.18.61, 7.3.2 and 7.4-rc1, and applying them requires upgrading the kernel and rebooting. The CVE was made public on November 20, 2026; the disclosure comes from OpenSec alone and is not independently corroborated in the supplied material.

telegram · zaihuapd · Nov 27, 12:57

**「Background」** NFS server \(nfsd\) is the kernel component that serves NFS exports on TCP port 2049; the vulnerable code is reachable in NFSv4.1 and 4.2 sessions before login, which is why the flaw is classified as pre-authentication. Red Hat&\#x27;s advisory describes the underlying defect as a failure to verify that a response fits within negotiated buffer limits before the server caches it, causing response data to be written past the allocated buffer.

**「Impact」** Administrators of hosts exporting NFSv4.1 or 4.2 must either move to one of the fixed kernels and reboot, or, where immediate upgrade is not possible, restrict access to tcp/2049 at the firewall — the interim workaround the report recommends. Because no authentication is required, any reachable NFS port is exposed, so exposure should be assessed before the next maintenance window.

<details><summary>References</summary>
<ul>
<li><a href="https://access.redhat.com/security/cve/cve-2026-99362">CVE-2026-99362 - Red Hat Customer Portal</a></li>
<li><a href="https://github.com/suominen/CVE-2026-99362/tree/main/">GitHub - suominen/CVE-2026-99362</a></li>

</ul>
</details>

**Tags**: `#Linux kernel`, `#NFS`, `#security vulnerability`, `#CVE`, `#remote exploit`

---

<a id="item-tech-news-3"></a>
### [Why proof-checker bugs can yield false computer-checked proofs](https://cr.yp.to/proofs/falseccp.html) ⭐️ 7.0/10

A technical analysis examines how bugs in proof checkers can let an invalid proof pass as computer-checked, and places that risk alongside known soundness bugs in systems such as Lean and Metamath. It discusses multi-verifier arrangements as a mitigation, while distinguishing acceptance by one checker from actual mathematical truth.

hackernews · \_tk\_ · Nov 27, 15:26 · [Discussion](https://news.ycombinator.com/item?id=50667989)

**「Background」** Computer proof checking verifies a submitted derivation rather than searching for a proof, so the outcome depends on the checker&\#x27;s soundness—its refusal to accept an invalid derivation \[tool-2-3\]. That is the gap the linked page examines: a bug in a checker or trusted kernel can produce a proof that looks machine-checked but is not actually valid.

**「Impact」** For formal-verification practitioners, the practical consequence is that a single checker&\#x27;s acceptance should be treated as one layer of assurance rather than standalone proof of a result; projects can reduce exposure by requiring independent verifiers and informal review of the stated theorem.

**「Community discussion」** Commenters push back on the implied risk: twotwotwo says one bad verification does not easily mislead mathematicians because multiple checkers and informal review stand in the way, and dwheeler notes that Metamath&\#x27;s main databases require five independently created verifiers in five languages. gr\_norm argues the known soundness bugs are rare enough for most software, while andai raises a separate concern that an agent can prove an implementation correct against a mistaken formalization of the requirement.

<details><summary>References</summary>
<ul>
<li>&quot;Case Studies in Proof Checking&quot; by Robert Kam - SJSU ScholarWorks</li>

</ul>
</details>

**Tags**: `#formal verification`, `#proof assistants`, `#soundness bugs`, `#Lean`, `#Metamath`

---

<a id="item-tech-news-4"></a>
### [WebRTC card skimming scripts reportedly found on shopping sites](https://www.infohawk.com/news/2026-11-27-black-friday-webrtc-skimmer) ⭐️ 7.0/10

A report alleges that credit card skimming scripts using WebRTC were found on popular shopping sites, with the technique reportedly aimed at mobile shoppers. The account frames this as a supply-chain and browser-security problem involving third-party scripts, but it does not name affected merchants or scripts, and no independent confirmation is provided.

hackernews · scanr · Nov 27, 15:40 · [Discussion](https://news.ycombinator.com/item?id=50668145)

**「Web skimming, explained」** Web skimming attacks, grouped under the &quot;Magecart&quot; umbrella, work by injecting malicious JavaScript into a checkout page — frequently through a compromised or malicious third-party script the site already loads — so the code can capture card data as shoppers type it. Earlier scans of high-traffic domains have found credit card skimmers and cryptominers planted on many popular sites, which is why defenders treat third-party script tags as a standing supply-chain risk rather than an edge case.

**「Impact」** For e-commerce operators, the reported technique reinforces that third-party scripts on checkout pages sit inside the payment-security boundary, and that monitoring limited to ordinary HTTP request patterns may not catch card-data exfiltration over WebRTC data channels.

**「Community discussion」** Commenters focused less on WebRTC&\#x27;s technical necessity than on monitoring gaps: one argued the approach works because WebRTC traffic is less closely inspected, and that similar theft could use ordinary HTTP requests, while another said ad blocking is a reasonable defense. Others called for sandboxing third-party ads or preventing client-side JavaScript execution entirely, framing embedded third-party code as the root risk.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bleepingcomputer.com/news/security/top-sites-infiltrated-with-credit-card-skimmers-and-crypto-miners/">Top sites infiltrated with credit card skimmers and crypto miners</a></li>
<li><a href="https://www.zdnet.com/article/inter-a-low-bar-kit-for-magecart-website-credit-card-skimmer-attacks/">Inter: a ‘low bar’ kit for Magecart credit card skimmer attacks... - ZDNET</a></li>

</ul>
</details>

**Tags**: `#web security`, `#credit card skimming`, `#WebRTC`, `#supply chain attacks`, `#e-commerce security`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis deep dive: Trainium3 inference trades blows with GB300 on cost per token](https://newsletter.semianalysis.com/p/trainium3-inferencex) ⭐️ 7.0/10

SemiAnalysis published a microarchitecture and inference deep dive on AWS Trainium3, reporting that its InferenceX benchmarks place a Trainium3 server running the vLLM stack with PDS at better performance per dollar of total cost of ownership than every accelerator it tested except Nvidia&\#x27;s Vera Rubin across the throughput-versus-p90-interactivity curve, and &quot;trading blows or even winning&quot; against Nvidia GB300 on cost to generate tokens. The article attributes part of the result to microarchitecture rather than AWS&\#x27;s supply chain: Trainium is designed around tiles as a first-class primitive, and its Descriptor Generation Engines \(DGE\) — the counterpart to Nvidia TMA and AMD MI455X TDM — let the chip reach peak HBM bandwidth utilization at small message sizes, which the authors say is not possible on Nvidia GPUs. The measurements come from SemiAnalysis&\#x27;s UBenchX suite and cover cycle-level SRAM scratchpad \(SBUF to PSUM\) latency and bandwidth, rack-scale bandwidth and latency, attention exponential testing, and how attention head\_dim affects roofline percentage, with AWS Annapurna Labs co-founder Nafea Bshara and Trainium chief architect Ron Diamant helping validate the experiments. The separate AgentX result replays real coding-agent sessions against a Trainium3 server, but the supplied excerpt does not include the underlying throughput, latency, or dollar figures behind the headline claims.

rss · Semianalysis · Nov 27, 15:54

**「Background」** Nvidia’s datacenter GPUs evolved from graphics hardware, with Volta adding Tensor Cores, Hopper adding TMA for HBM-to-SRAM tile movement, and Blackwell adding Tensor Memory for accumulation; AWS instead designed Trainium around ML tiles as a first-class primitive. SemiAnalysis’s InferenceX benchmark compares accelerators along throughput-latency Pareto frontiers at different TCO points, and its UBenchX suite measures microarchitectural behavior such as HBM bandwidth utilization and SRAM scratchpad latency.

**「Impact」** For teams weighing inference cost, the claim is conditional on a specific software path — vLLM on Trainium3 PDS — and on individual configurations along the latency-throughput frontier rather than a single peak number; because AWS engineers helped validate the experiments, the results are best read as vendor-collaborated measurements rather than an independent audit. The open-sourced InferenceX and UBenchX data, which the authors say also covers TPUv7, Nvidia Rubin NVL72, GB300 and AMD parts, gives buyers a way to compare configurations against their own latency targets before committing to a migration.

**Tags**: `#AI hardware`, `#Trainium`, `#AWS`, `#microarchitecture`, `#inference`

---

<a id="item-tech-news-6"></a>
### [Microsoft moves more Windows hardware class drivers in-box](https://www.techspot.com/news/114721-microsoft-wants-replace-most-third-party-device-drivers.html) ⭐️ 7.0/10

Microsoft confirmed at Ignite 2026 that it is developing new class drivers for entire hardware categories and relying more on drivers built into Windows, with the goal of minimizing third-party code in the kernel. Printers are the first priority: the recently introduced Windows Ready Print mode is intended to replace legacy third-party print drivers. Windows product manager Mehmet Kucukgoz said SoundWire and SDCA audio class drivers will soon become built-in Windows components, while I3C bus, USB Ethernet, and MIPI camera class drivers are still in development. Microsoft also introduced a Driver Quality Initiative \(DQI\) to raise driver reliability, quality, and security standards and to encourage third-party developers and OEMs to use in-box drivers where possible.

telegram · zaihuapd · Nov 28, 02:09

**「Why kernel drivers matter」** Windows has long relied on hardware vendors to supply kernel-mode drivers for peripherals, so third-party code from OEMs and component makers runs at the highest privilege level in the OS. A faulty or malicious driver at that level can crash the system or bypass security boundaries, which is why Microsoft has been shifting toward class drivers that cover a whole category of hardware with one Microsoft-maintained component. The printer work builds on the Windows Ready Print mode the item says Microsoft recently introduced to replace legacy third-party print drivers.

**「For driver developers」** Driver developers and OEMs in printing, audio, and related device classes should plan to validate their hardware against Windows&\#x27; in-box class drivers: Microsoft says SoundWire and SDCA audio drivers will soon be built in, and its recently introduced Windows Ready Print mode is intended to replace legacy third-party print drivers. Remaining vendor drivers, including OEM customizations, are expected to follow the new Driver Quality Initiative&\#x27;s reliability and security standards.

**Tags**: `#Windows`, `#device drivers`, `#Microsoft`, `#kernel security`, `#hardware compatibility`

---

## Financial News

<a id="item-finance-news-1"></a>
### [China&\#x27;s State Council Urges Stronger &\#x27;National Team&\#x27; Role in Stabilizing Stock Market](https://www.tmtpost.com/nictation/8220182.html) ⭐️ 7.0/10

A State Council executive meeting chaired by Premier Li Qiang on Nov. 27 called for greater use of the &quot;national team&quot; to stabilize the stock market and for improving Central Huijin&\#x27;s &quot;stabilization fund&quot;-like function, alongside better policies to channel long-term money from insurers, enterprise annuities and the social security fund into equities. The meeting readout gave no new funding size, specific tool design or implementation timetable.

telegram · zaihuapd · Nov 27, 05:35

**「Background」** An expert cited by Eastmoney read the meeting’s wording on Central Huijin’s quasi-“stabilization fund” role—a state-backed mechanism for supporting share prices—as upgrading it from a temporary crisis-response tool to a standing part of national financial governance.

**「Who is affected」** If carried out, the measures would widen the channels through which insurers, corporate annuity plans and the social security fund can buy shares, the long-term funds the meeting named, while pressure on listed companies to raise dividends and buybacks would fall on their existing shareholders.

<details><summary>References</summary>
<ul>
<li><a href="https://finance.eastmoney.com/a/202611273941634358.html">如何理解 国 常会对资本 市 场的最新定调？ 专 家 解读来了 _ 东方财富网</a></li>
<li><a href="https://www.cls.cn/detail/2546318">cls.cn/detail/2546318</a></li>

</ul>
</details>

**Tags**: `#资本市场政策`, `#中央汇金`, `#平准基金`, `#中长期资金入市`, `#国务院常务会议`

---

<a id="item-finance-news-2"></a>
### [PBOC halves large-denomination CD purchase thresholds](https://www.news.cn/fortune/20261127/70789d77822242cc82216f51a416f872/c.html) ⭐️ 7.0/10

The People&\#x27;s Bank of China on Nov. 27 published new rules for large-denomination certificates of deposit that halve the minimum purchase for individual investors to 100,000 yuan and for institutional investors to 5 million yuan, effective March 21, 2027. The same day it issued deposit and loan interest rate rules, also effective that date, requiring financial institutions to set rates independently and barring improper practices such as luring deposits with high interest.

telegram · zaihuapd · Nov 27, 11:36

**「Background」** The 2015 interim rules had set the minimum purchase at 200,000 yuan for individuals and 10 million yuan for institutions; the new measure replaces those rules and takes effect on March 21, 2027.

**「Who is affected」** Households with 100,000–200,000 yuan in savings will for the first time be able to buy large-denomination certificates of deposit, which a Tencent News report says typically pay 0.3–0.9 percentage points more than ordinary fixed deposits of the same term; banks, meanwhile, must set deposit and loan rates on their own and are barred from luring deposits with high interest.

<details><summary>References</summary>
<ul>
<li><a href="https://news.qq.com/rain/a/20260317A05VOS00">同样是 存 10 ...</a></li>

</ul>
</details>

**Tags**: `#央行监管`, `#大额存单`, `#存贷款利率`, `#银行业`, `#个人投资`

---