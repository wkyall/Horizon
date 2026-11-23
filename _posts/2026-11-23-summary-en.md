---
layout: default
title: "Horizon Summary: 2026-11-23 (EN)"
date: 2026-11-23
lang: en
---

> From 37 items, 11 important content pieces were selected

---

**Technology News**
1. [XNU Linux project targets full OS X GUI userspace on Linux](#item-tech-news-1) ⭐️ 7.0/10
2. [OpenAI Article Examines Perplexity as a Model-Intelligence Measure](#item-tech-news-2) ⭐️ 7.0/10
3. [O’Reilly’s ‘What Happened to Silicon Valley?’ Urges Human-Flourishing Markets](#item-tech-news-3) ⭐️ 7.0/10
4. [Google reportedly tests Chrome AI agent on simulated &\#x27;Mirror Dimension&\#x27; internet](#item-tech-news-4) ⭐️ 7.0/10
5. [Windows Server 2028 to drop WoW64 by default](#item-tech-news-5) ⭐️ 7.0/10

**Technology Blog**
1. [Skipping DRAM: NVMe KV Pool Matches DRAM Throughput](#item-tech-blog-1) ⭐️ 8.0/10
2. [Sean Goedecke on Productive Flailing Under Uncertainty](#item-tech-blog-2) ⭐️ 5.0/10
3. [What OpenAI’s Perplexity Graph Can and Cannot Show](#item-tech-blog-3) ⭐️ 5.0/10

**Financial News**
1. [US Tech Selloff Prompts Asian Market Stabilization Measures](#item-finance-news-1) ⭐️ 9.0/10
2. [Record El Niño Raises Hunger Risk as Aid Funding Falls](#item-finance-news-2) ⭐️ 7.0/10
3. [Ant Group Leads $100 Million Pre-A Round in Simplexity Robotics at $1.6 Billion Valuation](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [XNU Linux project targets full OS X GUI userspace on Linux](https://github.com/AFK-surf/xnulinux) ⭐️ 7.0/10

An experimental GitHub project called XNU Linux is presented as a way to run the full OS X graphical userspace on Linux via XNU, but the supplied item provides no implementation details, build instructions, or evidence that it works without Apple hardware. It is a compatibility effort for users and developers interested in bringing the macOS environment to Linux, rather than a shipped Apple product. The project&\#x27;s exact scope and hardware requirements remain unconfirmed in the available material.

hackernews · mmastrac · Nov 23, 03:49 · [Discussion](https://news.ycombinator.com/item?id=50607261)

**「Background」** XNU-Linux&\#x27;s approach differs from a conventional compatibility layer or a full virtual machine: the repository describes building Apple&\#x27;s open-source XNU kernel from published sources and loading it as a kernel module \(\`xnu.ko\`\) inside an unmodified arm64 Linux kernel, so macOS processes can run alongside Linux processes without a hypervisor between them. That module-based design is the prerequisite for the project&\#x27;s claim to run a macOS system disk directly on Linux; the supplied evidence does not establish how broadly it works or whether it removes the Apple-hardware dependency raised in the discussion.

**「Community discussion」** Commenters welcomed the concept but focused on constraints: gen2brain said it still requires Apple hardware and argued for improving GNUstep instead, while opengears cited another hackintosh-related project, Stela, having been removed from GitHub as a sustainability concern. pcwalton speculated that future hardware could make OS binaries runnable only on Apple chips, an analogy rather than a reported feature of this project.

<details><summary>References</summary>
<ul>
<li><a href="https://hotrepo.ai/AFK-surf/xnulinux">AFK-surf/xnulinux: Run macOS userspace on arm64 Linux via XNU ...</a></li>
<li><a href="https://snslive.uk/article/2945906">XNU Linux: Full OS X GUI Userspace on Linux — Sovereign News ...</a></li>

</ul>
</details>

**Tags**: `#macOS userspace`, `#Linux`, `#XNU`, `#OS compatibility`, `#reverse engineering`

---

<a id="item-tech-news-2"></a>
### [OpenAI Article Examines Perplexity as a Model-Intelligence Measure](https://openai.com/index/perplexity-and-intelligence/) ⭐️ 7.0/10

OpenAI published an article titled “Perplexity and Intelligence” that examines the relationship between language-model perplexity and model capability, with the supplied summary pointing to cross-entropy, compression, and evaluation benchmarks. No article text was provided, so the specific data and claims could not be verified. The Hacker News thread debated whether the metric is clearly defined and how reliably cross-entropy tracks intelligence.

hackernews · acossta · Nov 22, 17:06 · [Discussion](https://news.ycombinator.com/item?id=50601525)

**「Background」** Perplexity is the exponentiated cross-entropy loss a language model incurs predicting each next token in a text: it bottoms out at 1 for a perfect predictor and approaches the vocabulary size for a random one. Because it condenses performance into a single number that needs no task-specific harness, it is far cheaper to track across labs than benchmark suites — but comparability depends on evaluating on a shared held-out set and comparable tokenization. OpenAI chief scientist Jakub Pachocki&\#x27;s post argues for exactly that: treating perplexity, equivalently cross-entropy loss, as a common metric across model developers and as an input to shared safety standards.

**「Impact」** For developers comparing models, perplexity is not a self-contained capability score: a random predictor’s perplexity equals vocabulary size, while perfect prediction gives 1, so figures need the tokenizer or vocabulary and evaluation set stated to be comparable.

**「Community Discussion」** Commenters focused on definitional and conceptual gaps: hazrmard noted that perplexity is not defined in the article and described it as next-token surprise ranging from 1 at perfect prediction to vocabulary size for a random predictor, while d\_burfoot argued that the perplexity–intelligence link follows naturally from prediction as compression. jrflo said the apparent cross-entropy trend was surprising given the rise of RL and welcomed a simpler benchmark.

<details><summary>References</summary>
<ul>
<li><a href="https://openai.com/index/perplexity-and-intelligence/">Perplexity and Intelligence | OpenAI</a></li>

</ul>
</details>

**Tags**: `#perplexity`, `#language-model-evaluation`, `#cross-entropy`, `#AI-scaling`

---

<a id="item-tech-news-3"></a>
### [O’Reilly’s ‘What Happened to Silicon Valley?’ Urges Human-Flourishing Markets](https://www.oreilly.com/radar/what-happened-to-silicon-valley/) ⭐️ 7.0/10

O’Reilly Radar published an essay, “What Happened to Silicon Valley?,” asking what changed in the region and arguing that market mechanisms should be redesigned around human flourishing rather than shareholder value. The piece is opinion and analysis rather than a reported product, policy, or technical change; it prompted substantial Hacker News debate over mechanism design and the incentives shaping the tech industry.

hackernews · greenyouse · Nov 22, 19:20 · [Discussion](https://news.ycombinator.com/item?id=50602947)

**「The mechanism-design framing」** The essay&\#x27;s argument turns on mechanism design, which it describes as &quot;reverse game theory&quot;: rather than optimizing inside the rules currently in play, you ask which rules would produce a chosen outcome, and it proposes human flourishing as that outcome. Hacker News discussion of the piece singles out this passage as the article&\#x27;s central claim, with commenters noting the same framing is what makes the essay&\#x27;s critique of shareholder-value optimization legible as a design choice rather than a natural market result.

**「Community Discussion」** Several commenters engaged with the essay’s mechanism-design framing: one endorsed asking what game humanity ought to play, while another argued the market is a constructed machine whose designers should be held accountable. A commenter who agreed with the essay but emphasized a proximate cause said zero-interest-rate policy, not only shareholder-value norms, let companies grow to “grotesque proportions” and encouraged upstarts to chase new markets; with rates higher, they said tech is cannibalizing core competencies around AI, while conceding it is unclear whether markets will punish reckless spending.

<details><summary>References</summary>
<ul>
<li><a href="https://news.ycombinator.com/item?id=50602947">What Happened to Silicon Valley ? | Hacker News</a></li>

</ul>
</details>

**Tags**: `#Silicon Valley`, `#mechanism design`, `#tech industry`, `#shareholder capitalism`, `#AI`

---

<a id="item-tech-news-4"></a>
### [Google reportedly tests Chrome AI agent on simulated &\#x27;Mirror Dimension&\#x27; internet](https://www.landian.news/archives/128701.html) ⭐️ 7.0/10

Google has reportedly built a simulated internet, called Mirror Dimension, to test Chrome&\#x27;s AI agent in an isolated environment. According to Landian, the setup covers opening sites, searching and browsing, logging in, adding items to a cart, and completing tasks across thousands of mock websites. It is said to run more than 1,000 test cases per day, with each engineer testing separately and a focus on defending against prompt injection from malicious pages. The report is secondary and provides no primary Google confirmation or public availability details.

telegram · zaihuapd · Nov 23, 01:30

**「Background」** Chrome&\#x27;s AI agent, which Google describes as &quot;auto browse,&quot; is designed to navigate sites and carry out tasks such as searching, logging in, and adding items to a cart on a user&\#x27;s behalf, so it necessarily consumes untrusted web content. That makes hidden prompt-injection attacks a central risk: a malicious page could try to steer the agent&\#x27;s actions. Google therefore built Mirror Dimension as an isolated, fully controlled synthetic web, letting engineers evaluate the agent in realistic environments without exposing it to the live internet.

<details><summary>References</summary>
<ul>
<li><a href="https://blog.google/security/mirror-dimension-for-agents/">Mirror Dimension for Agents : Evaluating Browser-Use Agents ...</a></li>
<li><a href="https://www.wired.com/story/google-built-a-giant-mirror-dimension-internet-to-test-its-chrome-ai-agents/">Google Built a Giant ‘ Mirror Dimension ’ Internet to Test Its Chrome ...</a></li>

</ul>
</details>

**Tags**: `#Chrome AI agent`, `#prompt injection`, `#AI agent testing`, `#browser security`, `#Google`

---

<a id="item-tech-news-5"></a>
### [Windows Server 2028 to drop WoW64 by default](https://www.windowslatest.com/2026/11/23/32-bit-apps-days-are-numbered-as-microsoft-strips-support-bit-by-bit-starting-with-windows-server-2028-but-windows-11-is-safe-for-now/) ⭐️ 7.0/10

Microsoft says Windows Server 2028 will omit the WoW64 compatibility subsystem by default, so the new server OS will not run 32-bit applications out of the box. The company announced the plan at Ignite 2026 and says the release is scheduled for fall 2027 alongside Windows 11 27H2. Administrators who need 32-bit support can add WoW64 back as a Feature on Demand, typically through PowerShell or DISM on Server Core; Microsoft says the default removal is intended to reduce attack surface and block 32-bit malware. Windows 11 currently retains WoW64, and Microsoft has not announced a removal plan for it.

telegram · zaihuapd · Nov 23, 03:03

**「Background」** WoW64 is the compatibility layer that lets 64-bit Windows run 32-bit x86 applications, and Windows Server has historically included it by default. Windows Server 2028 will ship without it, so legacy 32-bit server workloads will require administrators to add the optional FoD package before they can run.

**「Impact」** Organizations that still run 32-bit server software will need to add the WoW64 optional feature—typically via PowerShell or DISM on Server Core—during Windows Server 2028 deployment, or those applications will not run on a default installation. That makes an inventory of 32-bit dependencies and an explicit compatibility step part of upgrade planning; Windows 11 retains WoW64 for now.

**Tags**: `#Windows Server`, `#WoW64`, `#32-bit compatibility`, `#Microsoft`, `#enterprise IT`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Skipping DRAM: NVMe KV Pool Matches DRAM Throughput](https://vllm.ai/blog/2026-11-23-skip-the-dram-tier) ⭐️ 8.0/10

rss · vLLM Blog · Nov 23, 00:00

**「Background」** Agentic serving keeps replaying long prefixes, so a KV-cache miss forces the prefill node to recompute them; the authors measured that a one-point gain in hit rate, from 95% to 96%, was worth about 10% more throughput. Host DRAM is the usual overflow tier, but Kimi-K3 wrote 2.3–4.6 TB of KV per hour, leaving a 1.8 TB DRAM pool only 23–47 minutes of retention.

**「Solution」** The authors therefore put vLLM’s whole 1.8 TB KV pool on local NVMe via AMD’s MoRI UMBP, with DRAM reduced to a 64 GB write buffer and 16 GiB read staging area. On AgentX traces with Kimi-K3, the NVMe pool stayed within 1% of a same-size DRAM pool at 48, 70, and 96 concurrent sessions across two pairs of machines, with hit rates within 0.08% and similar time to first token; a longer-prompt kvlab replay was also within 1% at 70 sessions. The reason is that equal-size pools with similar eviction retained the same KV, and vLLM’s asynchronous loads completed while requests waited for prefill; changing segment files from 4 GiB to 256 MiB alone added 15.6% throughput, and reporting GPU prefix hits to the pool reduced tail latency. NVMe’s economic advantage comes from charging for writes rather than held capacity—about $59,000 for a day of KV versus $76,000 for 1.8 TB of DRAM holding about 31 minutes—but every computed block is written to the drives, and at 96 sessions the test pair would wear out its rated life in roughly five and a half months, which is why the authors plan a distributed pool.

**「Takeaway」** The authors conclude that, for this agentic workload, the DRAM tier can be skipped: at equal capacity NVMe preserved hit rate and throughput while providing much longer retention at lower cost. Those claims remain tied to their AMD/MoRI/vLLM setup and to cost arithmetic at list prices, not a general proof that DRAM is unnecessary.

**Tags**: `#KV cache`, `#LLM inference`, `#NVMe`, `#vLLM`, `#benchmarking`

---

<a id="item-tech-blog-2"></a>
### [Sean Goedecke on Productive Flailing Under Uncertainty](https://seangoedecke.com/when-in-doubt-flail-about/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** In ambiguous product, engineering, or organizational situations, Sean Goedecke argues that waiting for full understanding before acting is often impractical: modern systems are too complex and fast-moving to map completely first. He asks how an engineer can become useful when no one can say clearly what will work.

**「Solution」** His answer is deliberate “flailing”: try many different things, pay close attention to feedback, and ruthlessly drop plans that are not getting positive feedback. Many attempts provide direct contact with reality, acknowledge that most plans will be bad, and prevent overinvestment in any one plan. In product work, he cites GitHub Models \(now retired\), where many features and integrations failed but allowing AI inference from a GitHub Actions token proved sticky and became the seed of “Continuous AI”; in engineering, he favors speculative changes, including several AI-agent-generated refactors, over fully mapping a large system first; in organizational work, senior and staff engineers can automate manual tasks, volunteer for work, or propose long-term plans. He warns that flailing badly can damage reputation, and that organizational flailing is riskiest: dropping a failing plan immediately can build trust, but persisting can direct others’ anger at you. Though it feels like repeated failure from the inside, he says that feeling is normal and should be ignored so long as feedback remains the guide.

**「Takeaway」** Goedecke’s broader point is that effective engineering under uncertainty is less about choosing the one correct plan in advance than generating options, reading feedback quickly, and discarding failures—while accepting the discomfort and reputational risk of appearing to flail.

**Tags**: `#engineering management`, `#decision-making under uncertainty`, `#experimentation`, `#career advice`

---

<a id="item-tech-blog-3"></a>
### [What OpenAI’s Perplexity Graph Can and Cannot Show](https://seangoedecke.com/notes-on-openais-perplexity-reveal/) ⭐️ 5.0/10

rss · Sean Goedecke · Nov 23, 00:00

**「Background」** OpenAI released a graph of perplexity over time across its models, giving unusual visibility into a frontier lab’s training metrics; the author notes that such safety-oriented disclosure is more typically associated with Anthropic.

**「Solution」** Perplexity measures how well a model predicts a particular held-out dataset, so it reflects pre-training rather than the reinforcement learning and chain-of-thought work that may consume half or more of frontier training. Cross-lab comparisons would therefore be fragile, and the metric misses capabilities such as improving with chain-of-thought. The chart suggests fewer models share a base than rumored—apparently only o1 and o3—and 4.1 and o3 share one despite very different perceived strength, while GPT-4.5’s perplexity was similar to GPT-5.3-Codex’s but its usefulness was not. The author reads the acceleration from GPT-5.2 onward as evidence that pretrained bases are still improving, contradicting the common claim that labs have given up pretraining for RL; whether OpenAI paused scaling or hit a wall at GPT-4.5 is unclear. On alignment, he welcomes the transparency but doubts it helps much unless OpenAI releases perplexity for unreleased pretrained models and specifies the held-out dataset behind any proposed thresholds. He also finds only a partial match between the graph and felt model strength: GPT-3.5 to GPT-4 was a huge jump, but he experienced o3 and GPT-5.3-Codex as the big advances, possibly because RL, chain-of-thought use, and sycophancy avoidance do not show up in perplexity.

**「Takeaway」** Perplexity is a useful but partial window: it tracks pre-training progress and exposes real shifts in OpenAI’s model lineage, yet it cannot by itself capture post-training capability or ground safety oversight without dataset details and broader releases.

**Tags**: `#perplexity`, `#LLM training metrics`, `#model evaluation`, `#AI safety transparency`, `#OpenAI`

---

## Financial News

<a id="item-finance-news-1"></a>
### [US Tech Selloff Prompts Asian Market Stabilization Measures](https://news.bjd.com.cn/2026/11/22/12039852.shtml) ⭐️ 9.0/10

US AI and technology stocks sold off sharply on Friday, with the Nasdaq falling 5.28% and the Philadelphia Semiconductor Index down nearly 11%, prompting mainland China, South Korea and Taiwan to introduce margin, short-selling and buyback measures aimed at stabilizing their markets.

telegram · zaihuapd · Nov 22, 13:24

**「Background」** Taiwan had already raised the collateral required to borrow shares for a bearish bet—its short-selling margin—from 90% at the start of November to 130% before lifting it to 150%, ZeroHedge reported. South Korea’s stabilization fund, which it is preparing for potential deployment, is a policy tool for filling liquidity gaps in the domestic equity market, according to BigGo.

**「Impact」** The measures directly affect investors and listed companies in those markets by lowering margin requirements in mainland China, easing buyback limits in South Korea and restricting short selling in Taiwan.

<details><summary>References</summary>
<ul>
<li><a href="https://www.zerohedge.com/markets/south-korea-readies-first-market-rescue-fund-deployment-2008">Asian Market Panic Continues As Korea Readies To... | ZeroHedge</a></li>
<li><a href="https://finance.biggo.com/news/41704fd7-7d88-4cb6-8773-17f6b6f5c964">South Korea Restarts Stock Market Stabilization Fund Preparations...</a></li>

</ul>
</details>

**Tags**: `#US tech selloff`, `#Asian markets`, `#market stabilization`, `#short-selling restrictions`, `#margin rules`

---

<a id="item-finance-news-2"></a>
### [Record El Niño Raises Hunger Risk as Aid Funding Falls](https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/) ⭐️ 7.0/10

A record-strength El Niño pushed a key central tropical Pacific warming measure to 3.5°C by October, above the prior roughly 2.75°C record, climate scientist Zeke Hausfather said, with a peak near 4°C forecast for early winter. The World Food Programme warned in August that the event could push an additional 49 million people into acute food insecurity by the end of 2027, with global aid funding in 2025 down 30% from its 2022 peak.

telegram · zaihuapd · Nov 22, 14:09

**「Background」** This is the third strong El Niño in 11 years, so some regions have faced repeated drought; the UN food agency says the 2015–16 event affected the food security of 60 million to 100 million people.

**「Who is affected」** Food-aid-dependent households in drought-exposed countries would be hit hardest, because a 30% drop in global aid funding since 2022 limits how many people agencies can reach even as need rises.

<details><summary>References</summary>
<ul>
<li><a href="https://news.un.org/en/story/2026/08/1168079">Strengthening El Niño to push 49 million more people into ...</a></li>
<li><a href="https://www.wired.com/story/how-this-years-super-el-nino-will-worsen-global-hunger/">How This Year’s Super El Niño Will Worsen Global Hunger | WIRED</a></li>
<li><a href="https://www.theguardian.com/global-development/2026/sep/10/global-humanitarian-aid-crisis-64m-fewer-people-received-help-report">Tens of millions of people fail to get humanitarian aid as ...</a></li>

</ul>
</details>

**Tags**: `#El Niño`, `#food security`, `#humanitarian aid`, `#climate risk`, `#global economy`

---

<a id="item-finance-news-3"></a>
### [Ant Group Leads $100 Million Pre-A Round in Simplexity Robotics at $1.6 Billion Valuation](https://www.bloomberg.com/news/articles/2026-11-22/ant-group-bets-on-simplexity-to-thrive-in-china-s-humanoid-race) ⭐️ 7.0/10

Simplexity Robotics, a Chinese humanoid-robot startup, raised $100 million in a pre-A funding round led by Ant Group at a $1.6 billion post-money valuation, its chairman confirmed to Bloomberg.

telegram · zaihuapd · Nov 23, 02:02

**「Background」** The Hangzhou-based company, founded in July 2025, said in March that it had raised 2 billion yuan across five funding rounds in its first six months, when its post-money valuation was already above $1 billion.

<details><summary>References</summary>
<ul>
<li><a href="https://www.gasgoo.com/robot/news/70449505-%E7%90%86%E6%83%B3%E5%89%8D%E9%AB%98%E7%AE%A1%E5%81%9A%E6%9C%BA%E5%99%A8%E4%BA%BA-%E5%8D%8A%E5%B9%B4%E8%9E%8D%E4%BA%8620%E4%BA%BF-%E6%80%8E%E4%B9%88%E5%81%9A%E5%88%B0%E7%9A%84/">理想前高管做机器人，半年 融 了20 亿 ，怎么做到的？ | 盖世汽车</a></li>

</ul>
</details>

**Tags**: `#humanoid robotics`, `#venture funding`, `#Ant Group`, `#China tech`, `#startup valuation`

---