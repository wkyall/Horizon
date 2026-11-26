---
layout: default
title: "Horizon Summary: 2026-11-26 (EN)"
date: 2026-11-26
lang: en
---

> From 35 items, 10 important content pieces were selected

---

**Technology News**
1. [GRH Lean verification reportedly cut from 17M to 76k lines](#item-tech-news-1) ⭐️ 8.0/10
2. [1Password confirms incident after attacker pushed code to backend](#item-tech-news-2) ⭐️ 8.0/10
3. [Minecraft Java Edition RCE exploit abuses resource-pack fonts; no official patch](#item-tech-news-3) ⭐️ 8.0/10
4. [Google Research posts Cogentic papers on factoring and discrete logarithms](#item-tech-news-4) ⭐️ 7.0/10
5. [SemiAnalysis launches GDPx benchmark, reports 12% top score for Opus 5.5](#item-tech-news-5) ⭐️ 7.0/10
6. [OpenAI Pushes Into Cybersecurity, Says It Could Eclipse Coding](#item-tech-news-6) ⭐️ 7.0/10
7. [Tencent open-sources Hy4 flash GGUF weights down to 125.73GiB](#item-tech-news-7) ⭐️ 7.0/10
8. [Samsung, SK Hynix reportedly to adopt YMTC Xtacking for 3D NAND](#item-tech-news-8) ⭐️ 7.0/10

**Financial News**
1. [Report: Commerce Department pressed Intel to hand over 10% equity stake](#item-finance-news-1) ⭐️ 9.0/10
2. [US Plans New Tariffs on China, EU and 12 Other Trading Partners](#item-finance-news-2) ⭐️ 8.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [GRH Lean verification reportedly cut from 17M to 76k lines](https://github.com/lsernau/grh-lean) ⭐️ 8.0/10

The GitHub repository lsernau/grh-lean publishes a much shorter, more readable Lean version of GRH-related verification work associated with Anthropic, according to the Hacker News item. Commenters describe the reduction as roughly 17 million lines to about 76,000 lines and say the rewrite includes human-readable documentation and a clear separation between known mathematics and new mathematics. The item frames this as a size and readability improvement over an existing verification, not as a new mathematical proof of GRH or an independent check of the result.

hackernews · nb-t · Nov 25, 21:48 · [Discussion](https://news.ycombinator.com/item?id=50648050)

**「Earlier 17-million-line Lean proof」** The new Lean development reworks an earlier formalization of the Generalized Riemann Hypothesis attributed to Alpöge and Claude, which was released as roughly 17 million lines across 175,187 files; on 21 November 2026 the Lean FRO and Mathlib Initiative announced that they had verified that original proof. Anthropic researcher Luke Sernau&\#x27;s alternative version was published on 25 November 2026, and published line counts for it differ: the item and commenters describe about 76,000 lines, while a Wikipedia summary cites 300,000. Lean is a proof assistant, so these files are machine-checkable proof code rather than a conventional mathematical paper.

**「Impact」** For readers trying to audit the formalization, the documented known/new split gives a concrete starting point for inspecting which parts rely on established mathematics and which are new, rather than working through a 17-million-line artifact. The supplied comments do not show that this shorter version has itself been independently verified.

**「Community discussion」** The thread debates whether a shorter, better-documented Lean proof addresses the concern, attributed in the comments to Tao, that huge proofs can provide little insight; one commenter asks whether proof-golfing LLMs have already moved past that problem. Another says they still want mathematicians to understand the core argument and present it as a conventional paper or conference talk.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Alp%C3%B6ge&#x27;s_proof_of_the_Riemann_hypothesis">Alpöge&#x27;s proof of the Riemann hypothesis - Wikipedia</a></li>
<li><a href="https://www.math.uwaterloo.ca/~mrubinst/alpoge_claude_grh/">Alpöge/Claude proof of the Generalized Riemann Hypothesis</a></li>

</ul>
</details>

**Tags**: `#Lean`, `#formal verification`, `#GRH`, `#AI-assisted mathematics`, `#Anthropic`

---

<a id="item-tech-news-2"></a>
### [1Password confirms incident after attacker pushed code to backend](https://1password.com/blog/update-on-nov-2026-security-incident) ⭐️ 8.0/10

1Password confirmed a security incident in which an attacker accessed internal systems and stole some customer account information, including names, email addresses, account identifiers, and account creation and most recent login times; the company said customer vaults and their contents were not affected. 1Password began investigating on November 19 after detecting compromise of an employee&\#x27;s corporate GitHub account, which the attacker used to access source code and push malicious code to backend services, leading to the download of information. 1Password did not disclose how many users were affected; it disabled the involved account, rotated or revoked potentially exposed internal credentials, and strengthened verification codes for invitation and recovery emails. It said users do not need to change their accounts but should be alert to phishing.

hackernews · lxhrstn · Nov 25, 17:18 · [Discussion](https://news.ycombinator.com/item?id=50644817)

**「Background」** 1Password is a hosted credential manager in which customer vaults are distinct from the account records and backend services that support the product. The incident reflects a common SaaS supply-chain risk: if an attacker takes over an employee’s code-hosting account and can push code that production services deploy, the attacker can reach provider systems without directly breaking vault protection.

**「Phishing risk」** Affected customers face a targeted phishing risk because names, email addresses, and account metadata were exposed, even though 1Password says vault contents were not accessed. 1Password says users do not need to change their accounts, but they should verify unexpected vault-sharing, login, or recovery messages through the official app or site rather than trusting the message.

**「Community discussion」** Commenters treated a compromised employee endpoint that can push code into production as the central SaaS supply-chain risk, with one arguing that the probability approaches one as headcount grows and another criticizing the disclosure for not saying whether branch protections blocked or could have blocked the backend push. A user also reported receiving a high-quality phishing email that referenced the incident and included some personal details, sent from a non-1Password domain and using a fake vault-sharing notification.

<details><summary>References</summary>
<ul>
<li><a href="https://1password.com/blog/update-on-nov-2026-security-incident">Update on a security incident involving... | 1 Password</a></li>
<li><a href="https://www.macrumors.com/2026/11/25/1password-security-breach/">1 Password Security Breach: What Was Accessed and... - MacRumors</a></li>

</ul>
</details>

**Tags**: `#security incident`, `#1Password`, `#supply chain security`, `#SaaS security`, `#phishing`

---

<a id="item-tech-news-3"></a>
### [Minecraft Java Edition RCE exploit abuses resource-pack fonts; no official patch](https://github.com/bikini/minecraft2shell) ⭐️ 8.0/10

A proof-of-concept published on November 22 as minecraft2shell shows that a crafted TrueType font delivered in a server resource pack can trigger a native out-of-bounds write in FreeType 2.14.3 and earlier and execute arbitrary code on Minecraft Java Edition 26.3 Windows clients. Affected versions run from 1.20.5 through 1.21.10 and snapshots 26.1 to 26.4; 1.20.4 and earlier and Bedrock Edition are unaffected. Mojang still ships lwjgl-freetype 3.4.3 and has no official patch, while a community fix, m2sfix 1.0.0 released November 24, disables font hinting through a Java agent or mod.

telegram · zaihuapd · Nov 25, 12:46

**「Background」** Minecraft: Java Edition resource packs can carry custom fonts, and the client loads them through FreeType by way of LWJGL. That makes the font parser reachable from a server-supplied pack, and the reported flaw is a native out-of-bounds write in FreeType&\#x27;s handling of TrueType fonts. The community m2sfix works by disabling font hinting so the font&\#x27;s bytecode is not executed, rather than by replacing Mojang&\#x27;s bundled lwjgl-freetype.

**「Impact」** Because the malicious font arrives through a server resource pack, the delivery path can be closed by declining or blocking resource packs: players are advised to add none until a fix lands, and server operators can set the multiplayer resource-pack permission to &quot;disabled&quot; or install the m2sfix agent or mod.

<details><summary>References</summary>
<ul>
<li><a href="https://wurst.wiki/minecraft2shell">Minecraft2Shell Vulnerability - wurst.wiki</a></li>
<li><a href="https://github.com/sunrisemc-tw/minecraft2shell-fix">GitHub - sunrisemc-tw/minecraft2shell-fix: Client-side ...</a></li>

</ul>
</details>

**Tags**: `#Minecraft`, `#RCE vulnerability`, `#FreeType`, `#security advisory`, `#community patch`

---

<a id="item-tech-news-4"></a>
### [Google Research posts Cogentic papers on factoring and discrete logarithms](https://github.com/google-research/google-research/tree/master/cogentic_research_papers) ⭐️ 7.0/10

Google Research has released a repository of Cogentic papers covering integer factorization, discrete logarithms, and related topics, making them available to cryptography and algorithms researchers. The supplied item provides no abstracts, results, or independent verification, so it does not establish a cryptographic breakthrough or a practical capability. The practical significance of the work therefore remains unestablished.

hackernews · rgwohlbold · Nov 25, 13:33 · [Discussion](https://news.ycombinator.com/item?id=50642086)

**「Why the L-notation bound matters」** Factoring and discrete-logarithm algorithms are usually compared using L-notation, which expresses subexponential running time; the best general-purpose classical methods for these problems sit in that regime, which is why a claimed improvement draws scrutiny from cryptographers. Coverage of the release describes the lead paper as claiming an algorithm that completely factors any integer N in worst-case expected time L\_N\[1/3, 105\], produced with a Gemini 4-based Cogentic agent, while also reporting that the accompanying Lean proofs were still pending at the time of writing.

**「No actionable change for deployed cryptography yet」** Because the release as described supplies no abstracts, complexity bounds, or measured runtimes, cryptography operators have no evidence-based reason to change key sizes or migrate systems on account of it. The Hacker News discussion notes that factoring&\#x27;s fragility has long motivated alternatives to RSA, and that even a practical classical factoring algorithm would not by itself say much about discrete-log-based systems, so the useful next step is to read the papers for their stated complexity and parameters before treating any deployed scheme as affected.

**「Community discussion」** Commenters treated the release as a possible signal of broader progress in AI-assisted mathematics: one pointed to a rumored larger result, while another compared recent math discoveries to AlphaGo&\#x27;s search over Go move trees. These are community opinions and speculation, not confirmed technical findings, and other commenters debated computer-science career prospects and whether money can reliably solve hard math problems.

<details><summary>References</summary>
<ul>
<li>Google&#x27;s Cogentic agent posts six math papers, led by a claimed proven L[1/3] bound for factoring integers | MLQ.ai</li>
<li>Google&#x27;s Gemini 4 agent claims six math proofs in a day, including one on factoring 30 years in the making - R&amp;D World</li>
<li><a href="https://news.ycombinator.com/item?id=50642086">Google releases Cogentic papers on integer factorization , discrete ...</a></li>

</ul>
</details>

**Tags**: `#integer factorization`, `#discrete logarithms`, `#cryptography`, `#AI for mathematics`, `#Google Research`

---

<a id="item-tech-news-5"></a>
### [SemiAnalysis launches GDPx benchmark, reports 12% top score for Opus 5.5](https://newsletter.semianalysis.com/p/evaluating-recent-model-releases) ⭐️ 7.0/10

SemiAnalysis is evaluating recent frontier model releases on GDPx, a benchmark it launched on November 1 covering 11 domains it considers most economically valuable for frontier intelligence: chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering. The benchmark contains 206 tasks built with 14 specialized data partners and deliberately excludes sectors such as government and real estate, which the authors say are over-weighted by benchmark selection based on GDP share or the O\*NET taxonomy \(as in GDPVal and Agent&\#x27;s Last Exam\). SemiAnalysis reports that Opus 5.5, the highest-scoring model on release day, reached just 12% — headroom the firm argues lets GDPx discriminate between future releases where benchmarks such as Terminal Bench 4.0 are saturated. The post adds that safety classifiers on models including Fable 5.2 and GPT-6.2 Astra suppressed overall scores, and presents a second leaderboard excluding the cyber, biology, and alignment domains and switching legal and finance from binary to partial grading; the rankings themselves are published only as images and are not reproduced here.

rss · Semianalysis · Nov 26, 00:05

**「What GDPx measures」** SemiAnalysis launched GDPx on November 1 as an agentic benchmark covering domains it considers most valuable for frontier intelligence, including chip design, cybersecurity, biology, finance, legal, quant trading, recursive self-improvement, hardware design, materials science, alignment, and software engineering. The benchmark was built with 14 specialized data partners and 206 tasks, and it deliberately excludes sectors such as government and real estate rather than selecting domains by GDP share or the O\*NET taxonomy.

**「Impact for benchmark users」** For anyone using GDPx to compare models, the headline leaderboard is not a like-for-like ranking: models with active safety classifiers lose points on cyber, biology, and alignment tasks, and the binary grading used in legal and finance yields little partial credit on very hard tasks, so SemiAnalysis&\#x27;s adjusted view — those three domains dropped and partial grading applied — is the more comparable basis for judging closely matched releases.

**Tags**: `#AI benchmarks`, `#frontier models`, `#model evaluation`, `#GDPx`, `#SemiAnalysis`

---

<a id="item-tech-news-6"></a>
### [OpenAI Pushes Into Cybersecurity, Says It Could Eclipse Coding](https://www.theinformation.com/newsletters/ai-agenda/openais-roadmap-making-cyber-bigger-coding-remains-blurry) ⭐️ 7.0/10

OpenAI is positioning cybersecurity as its next growth engine, with its CFO claiming that the commonly cited estimate of a market worth more than $300 billion is still far too low and President Greg Brockman saying security will become a larger business for OpenAI than coding, according to The Information. The company has launched GPT-6 Cyber for security research and expanded its Daybreak trusted-access program, which as of September covered thousands of verified defenders and about 2,000 approved organizations and workspaces for vulnerability discovery, codebase analysis, and binary reverse engineering. The report says competition with Anthropic and Google, and the path to scaled commercialization, remain unclear, and it offers limited technical detail on the new model&\#x27;s capabilities.

telegram · zaihuapd · Nov 25, 04:51

**「Gated cyber access」** OpenAI&\#x27;s Daybreak is a gated cybersecurity access program rather than a general-availability product: the source says it reached thousands of verified defenders and about 2,000 approved organizations and workspaces by September, for tasks such as vulnerability discovery, codebase analysis, and binary reverse engineering. That verified-access structure is the prerequisite for understanding OpenAI&\#x27;s cyber push, because it pairs a specialized model, GPT-6 Cyber, with controlled distribution.

**「Gated access」** Because cyber-specialized models are distributed through approval programs rather than open API tiers, security teams that want GPT-6 Cyber must be verified into Daybreak instead of simply signing up; per OpenAI, the program&\#x27;s tooling includes the Daybreak plugin, a Red Team mode for authorized testing, and a Codex Security CLI and SDK for terminal and custom workflows.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/daybreak/">Daybreak | OpenAI for cybersecurity | OpenAI</a></li>
<li><a href="https://benchlm.ai/cybersecurity">Best AI Models for Cybersecurity , by Task (November...) | BenchLM.ai</a></li>

</ul>
</details>

**Tags**: `#OpenAI`, `#cybersecurity`, `#AI security`, `#product strategy`

---

<a id="item-tech-news-7"></a>
### [Tencent open-sources Hy4 flash GGUF weights down to 125.73GiB](https://mp.weixin.qq.com/s/o0xxShVQX6g2UllrrEv1WQ) ⭐️ 7.0/10

Tencent Hunyuan has released GGUF quantized weights for its 224B-parameter Hy4 flash model through its AngelSlim compression toolkit. The original weights are about 410.27GiB; the smallest IQ2-AH build is 125.73GiB, roughly 30% of the original, and Tencent says it can run on a 64GB Mac mini using the Strata offload framework. Tencent reports 89 tokens/s at 10K context on a 48GB-VRAM device, and 47 tokens/s at 32K context for the Q3\_K build on a 128GB M5 Max. It also reports that Q3\_K scores within 0.4 points of the original model on evaluations including DeepSWE v1.1; these are vendor-provided results, not independent measurements.

telegram · zaihuapd · Nov 25, 09:29

**「Background」** Hy4 flash is Tencent Hunyuan&\#x27;s 224B-parameter model, and this release publishes GGUF quantized versions of its weights rather than a new base checkpoint. Tencent&\#x27;s AngelSlim toolkit, which its repository describes as supporting INT8/FP8/INT4 quantization for Hunyuan and other model families, is the compression route used for those files. Because even the smallest IQ2-AH variant is 125.73GiB, running it on a 64 GB Mac mini relies on Strata offload to avoid holding the full weight set in memory at once.

**「Mac mini 路径下的预期表现」** 由于最小的 IQ2-AH 权重仍有 125.73GiB，64 GB Mac mini 只能通过 Strata 的 offload 将大部分模型驻留在存储中，因此实际吞吐量取决于内存与磁盘之间的传输带宽，不能直接参照宣传中的速度数字。唯一公布的吞吐量基准针对的是具有 48 GB 显存的设备（10K 上下文下为 89 token/s），而 M5 Max 128 GB 上 32K 上下文下为 47 token/s，所以统一内存用户应预期模型能够运行，而不是速度相当。

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/Tencent/AngelSlim">GitHub - Tencent / AngelSlim : Model compression toolkit engineered...</a></li>
<li><a href="https://huggingface.co/tencent/Hy4-flash">tencent / Hy 4 - flash · Hugging Face</a></li>
<li><a href="https://huggingface.co/strata-engine/Hy4-Flash-Strata">strata-engine/Hy4-Flash-Strata · Hugging Face</a></li>
<li><a href="https://original.ifeng.com/c/8yLCKwSsFD6">腾讯混元Hy4 flash开源GGUF量化权重 224B模型可跑在64GB Mac mini上</a></li>

</ul>
</details>

**Tags**: `#LLM quantization`, `#local inference`, `#GGUF`, `#Tencent Hunyuan`, `#model compression`

---

<a id="item-tech-news-8"></a>
### [Samsung, SK Hynix reportedly to adopt YMTC Xtacking for 3D NAND](https://tech.ifeng.com/c/8yLRPKxQy4L) ⭐️ 7.0/10

Samsung Electronics and SK Hynix have reportedly agreed, through cross-licensing, to use parts of Yangtze Memory Technologies&\#x27; Xtacking technology in 3D NAND flash. All three companies declined to comment, so the scope and terms of any agreement remain unconfirmed. Xtacking fabricates the memory array and CMOS control circuitry on separate wafers and bonds them, allowing each part to be produced and optimized independently; an Omdia senior analyst said this lets NAND makers build the memory array themselves and delegate logic to foundries, giving access to more advanced process nodes.

telegram · zaihuapd · Nov 25, 14:33

**「Background」** Xtacking is YMTC&\#x27;s hybrid-bonding process for 3D NAND; TrendForce reported in February 2025 that YMTC was the first to apply the technology to 3D NAND around four years earlier. TechPowerUp notes that Samsung and SK hynix are already building NAND with hundreds of layers and encountering limits of single-wafer manufacturing, making a production-tested bonding process attractive. YMTC has also pressed its NAND patents in court, suing Micron in the U.S. in 2024 for alleged infringement.

**「What the licensing changes」** Under the reported cross-licensing deals, Samsung and SK Hynix would gain access to Xtacking&\#x27;s separate array/CMOS wafer-bonding approach, which lets a NAND maker fabricate the memory array in-house while sourcing the logic die from a foundry on a more advanced process. TrendForce, citing Nikkei, reports that Samsung is already moving toward commercial adoption; if that holds, NAND process roadmaps and foundry-sourcing decisions beyond YMTC&\#x27;s own products would be affected. Because all three companies declined to comment, the scope of the licensed technology remains unconfirmed.

<details><summary>References</summary>
<ul>
<li><a href="https://en.wikipedia.org/wiki/Yangtze_Memory_Technologies">Yangtze Memory Technologies - Wikipedia</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC &#x27;s Xtacking ... | TechPowerUp</a></li>
<li><a href="https://www.trendforce.com/news/2025/02/24/news-samsung-rumored-to-adopt-hybrid-bonding-patent-from-chinas-ymtc-for-400-layer-nand/">[News] Samsung Rumored to Adopt Hybrid Bonding Patent from...</a></li>
<li><a href="https://en.wikipedia.org/wiki/Yangtze_Memory_Technologies">Yangtze Memory Technologies - Wikipedia</a></li>
<li><a href="https://www.techpowerup.com/355199/samsung-and-sk-hynix-to-license-ymtcs-xtacking-technology">Samsung and SK hynix to License YMTC &#x27;s Xtacking ... | TechPowerUp</a></li>
<li><a href="https://www.trendforce.com/news/2026/11/25/news-sk-hynix-reportedly-joins-samsung-in-licensing-ymtcs-xtacking-technology-as-nand-race-heats-up/">[News] SK hynix Reportedly Joins Samsung in Licensing ...</a></li>

</ul>
</details>

**Tags**: `#3D NAND`, `#Xtacking`, `#semiconductor manufacturing`, `#Samsung`, `#SK Hynix`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Report: Commerce Department pressed Intel to hand over 10% equity stake](https://www.wired.com/story/inside-trumps-demands-to-another-chips-ceo/) ⭐️ 9.0/10

Court filings reported by WIRED show that in an August 2025 phone call, a US Commerce Department lawyer told Intel&\#x27;s chief financial officer not to &quot;mistake this for a negotiation,&quot; warning that the board could refuse the government&\#x27;s demand for a 10% equity stake but would face unpredictable consequences. Intel&\#x27;s board ceded the shares days later, and President Trump then announced the US government &quot;fully owns and controls&quot; 10% of Intel without having paid for it — a holding now worth about $11 billion, according to the report.

telegram · zaihuapd · Nov 25, 13:25

**「Background」** According to the New York Times, the Trump administration has been spending billions of dollars on deals for ownership stakes in private companies, including Intel, making the reported pressure from the Commerce Department part of a broader pattern of government equity purchases.

**「Impact」** The government&\#x27;s equity stake gives it a shareholder role in Intel, and Reuters reported that investors worry the deal marks the start of a broader US industrial policy affecting chipmakers.

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2025/11/25/us/politics/trump-intel-steel-minerals-china.html">Trump Administration Is Taking Billions in Stakes in Firms Like Intel ...</a></li>
<li>Investors worry Trump&#x27;s Intel deal kicks off era of US industrial policy | Reuters</li>

</ul>
</details>

**Tags**: `#Intel`, `#US industrial policy`, `#semiconductor industry`, `#government equity stake`, `#corporate governance`

---

<a id="item-finance-news-2"></a>
### [US Plans New Tariffs on China, EU and 12 Other Trading Partners](https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html) ⭐️ 8.0/10

The US plans to impose country-specific tariffs on 14 trading partners, including China, the EU, Japan and India, under Section 301 of the 1974 Trade Act, targeting subsidized manufacturing capacity that undercuts US producers, according to a CNBC report. For China, the new tariff would add 20% on top of the existing 25% and could rise to 40% if China does not honor the October 2025 trade truce reached in Busan, South Korea.

telegram · zaihuapd · Nov 25, 13:59

**「Background」** The proposal follows an eight-month investigation into subsidized foreign manufacturing capacity and is intended to replace tariffs struck down by the Supreme Court earlier this year, Fox Business reported; it uses Section 301, a U.S. trade-law authority for retaliatory duties.

**「Who would be hit」** If the proposal is finalized, US importers of Chinese goods would pay an additional 20 percentage points on top of the existing 25% duty — a total of about 40% — while importers sourcing from the EU, Japan and India would also face new country-specific duties, raising their costs relative to domestic producers.

<details><summary>References</summary>
<ul>
<li><a href="https://www.cnbc.com/2026/11/25/us-tariffs-trump-section-301.html">U . S . unveils new Section 301 tariffs targeting China , EU and others</a></li>
<li><a href="https://www.foxbusiness.com/fox-news-global-economy/trump-admin-raise-tariffs-china-eu-other-trading-partners">Trump administration proposes sweeping Section 301 tariffs on China ...</a></li>
<li><a href="https://www.theguardian.com/us-news/2026/nov/25/trump-new-china-tariffs-europe">Trump proposing new tariffs on 14 partners including China ...</a></li>
<li><a href="https://thenextweb.com/news/new-tariffs-14-trading-partners-china-eu-section-301-excess-capacity">US proposes new tariffs on 14 trading partners, including ...</a></li>

</ul>
</details>

**Tags**: `#贸易政策`, `#关税`, `#中美贸易`, `#301条款`, `#全球贸易`

---