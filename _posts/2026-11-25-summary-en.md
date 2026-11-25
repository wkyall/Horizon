---
layout: default
title: "Horizon Summary: 2026-11-25 (EN)"
date: 2026-11-25
lang: en
---

> From 27 items, 6 important content pieces were selected

---

**Technology News**
1. [Simon Willison identifies three LLM coding-agent inflection points](#item-tech-news-1) ⭐️ 8.0/10
2. [Broadcom patches 23 VMware flaws, including 9.8 vCenter vmdir auth bypass](#item-tech-news-2) ⭐️ 8.0/10
3. [Preprint claims exact Θ\(n^2.25\) matrix multiplication exponent](#item-tech-news-3) ⭐️ 7.0/10
4. [GreyNoise Reports Active Check Point Management Server Intrusion Campaign](#item-tech-news-4) ⭐️ 7.0/10
5. [Ternary Bonsai 2.5 27B draws local-model speed reports](#item-tech-news-5) ⭐️ 7.0/10

**Financial News**
1. [Xiaomi Q3 adjusted net profit falls 56.8% as EV deliveries top 100,000](#item-finance-news-1) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Simon Willison identifies three LLM coding-agent inflection points](https://simonwillison.net/2026/Nov/24/llm-inflection-points/) ⭐️ 8.0/10

Marking the first anniversary of Claude Opus 4.5, Simon Willison argues in a retrospective that LLM coding agents crossed three capability inflections in twelve months. The first, in November 2025, was Opus 4.5 and OpenAI&\#x27;s GPT-5.1 family making agents such as Claude Code and Codex reliably useful for his daily coding work. The second was the June/July arrival of &quot;Fable class&quot; models—Claude Fable 5, which he says was briefly blocked by US export controls—that can pursue a stated goal with supplied tools; the third was September/October proficiency in 3D modeling and game development, capped by Opus 5.5&\#x27;s ability to rebalance a game over 12 hours. He now treats Fable 5/5.1/5.2, Opus 5.5, GPT-6 Astra, and possibly Gemini 4 Neon as the frontier baseline.

rss · Simon Willison · Nov 24, 23:02

**「Background」** Coding agents such as Anthropic&\#x27;s Claude Code pair an LLM with tools for reading, editing, and running code. Claude Code launched alongside Claude 3.7 Sonnet on February 24, 2025, giving the agent nine months of use before Claude Opus 4.5 shipped on November 24, 2025—the anniversary Willison uses as his retrospective starting point.

**「Impact」** For developers, Willison&\#x27;s account raises the practical baseline for coding agents from fixing frequent mistakes to giving a model a goal and the necessary tools and expecting a usable result; his examples include Blender/Three.js 3D scenes and a 12-hour game-rebalancing run. It also adds an access-risk caveat: Fable 5 was placed under US export controls days after release, so teams should not assume a chosen frontier model will remain available.

**Tags**: `#LLM coding agents`, `#AI engineering`, `#Claude Opus`, `#model capabilities`, `#industry analysis`

---

<a id="item-tech-news-2"></a>
### [Broadcom patches 23 VMware flaws, including 9.8 vCenter vmdir auth bypass](https://thehackernews.com/2026/11/vmware-vcenter-hit-by-another-critical.html) ⭐️ 8.0/10

Broadcom released patches covering 23 vulnerabilities across its VMware product line, centered on an authentication bypass in vCenter&\#x27;s directory service \(vmdir\) tracked as CVE-2026-123903 with a CVSS score of 9.8. According to the report, anyone who can reach vCenter over the network can skip authentication and enter the system directly. The flaw was reportedly exploited as a zero-day in the days before the patch was published. The source does not list affected or fixed vCenter versions, so administrators should confirm applicability against Broadcom&\#x27;s advisory before scheduling upgrades.

telegram · zaihuapd · Nov 24, 14:50

**「Background」** vCenter&\#x27;s vmdir component is the directory service tied to authentication for the management platform. CVE-2026-123903 bypasses that authentication layer, so reachability to vCenter—rather than valid credentials—becomes the key exposure condition.

**「Impact」** Because exploitation requires only network reach to vCenter, the practical exposure is any internet-facing or attacker-reachable vCenter instance: a failed LDAP SASL bind plants the claimed identity&\#x27;s access token on the connection, so subsequent plaintext LDAP operations run as that identity without credentials. BleepingComputer reported that Chinese-linked attackers had exploited this authentication bypass in zero-day attacks since September 2026, meaning administrators should treat unpatched appliances as potentially already compromised rather than simply pending an update — patching alone does not evict an intruder who has established persistence. Patching is the immediate required action; the source gives no mitigation or detection guidance beyond applying Broadcom&\#x27;s fixed builds.

<details><summary>References</summary>
<ul>
<li><a href="https://github.com/dinosn/CVE-2026-123903">dinosn/ CVE - 2026 - 123903 : CVE - 2026 - 123903 : VMware vCenter vmdir ...</a></li>
<li><a href="https://www.bleepingcomputer.com/news/security/vmware-patches-vcenter-zero-day-exploited-in-attacks-since-september/">VMware patches vCenter zero - day exploited in attacks since...</a></li>

</ul>
</details>

**Tags**: `#VMware vCenter`, `#security vulnerability`, `#authentication bypass`, `#zero-day`, `#CVE-2026-123903`

---

<a id="item-tech-news-3"></a>
### [Preprint claims exact Θ\(n^2.25\) matrix multiplication exponent](https://github.com/openai/math/blob/main/preprints/The-matrix-multiplication-exponent-is-nine-fourths-November-24-2026/paper.pdf) ⭐️ 7.0/10

A preprint in OpenAI&\#x27;s math GitHub repository claims an exact Θ\(n^2.25\) bound for matrix multiplication, with the title describing the exponent as nine-fourths. The supplied item provides only the PDF link, with no abstract, proof details, peer review, or independent verification, so the result should be treated as an unverified claim rather than a confirmed breakthrough. The Hacker News discussion adds context but does not resolve the claim.

hackernews · E-Reverance · Nov 25, 01:19 · [Discussion](https://news.ycombinator.com/item?id=50637220)

**「Background」** The matrix multiplication exponent ω is the asymptotic exponent governing the arithmetic cost of multiplying n×n matrices: an O\(n^α\) algorithm establishes ω ≤ α. For decades, theorists narrowed the possible range for ω without proving that it equals any single value, which is the gap the Nov. 24, 2026 preprint claims to close by asserting ω = 9/4 over every field.

**「Impact」** Researchers evaluating the claim should wait for the proof to be checked and for an explicit algorithm or replication; the item itself does not provide enough technical detail to assess correctness or practical relevance.

**「Community Discussion」** Commenters dispute the framing of the result: orlp argues the title was incorrect as written at the time, saying O\(n^2.25\) was already known and the result should be stated as Θ\(n^2.25\), while brandonb says the paper proves a lower bound of Ω\(n^2.25\) and that an O\(n^2.25\) algorithm was published recently but is far from practical. Other comments speculate about OpenAI withholding stronger models and about the paper&\#x27;s provenance; those claims are not established by the supplied item.

<details><summary>References</summary>
<ul>
<li><a href="https://cryptobriefing.com/openai-matrix-multiplication-exponent-9-4/">OpenAI preprint claims the matrix multiplication exponent is ...</a></li>

</ul>
</details>

**Tags**: `#matrix multiplication`, `#algorithms`, `#AI for mathematics`, `#OpenAI`, `#preprint verification`

---

<a id="item-tech-news-4"></a>
### [GreyNoise Reports Active Check Point Management Server Intrusion Campaign](https://www.greynoise.io/blog/check-point-security-management-servers-intrusion-campaign) ⭐️ 7.0/10

GreyNoise reports an active intrusion campaign against Check Point security management servers, in which the actor exploited an HFS loginSrp1 endpoint and used repeated signed session-cookie outputs to reconstruct the internal state of Node.js&\#x27;s V8 PRNG, recover a cookie-signing key, and forge a signed admin session cookie. The report timeline quoted in the discussion places the scanning and exploitation at 2026-10-02 13:17:45 UTC. The supplied material does not establish the initial-access path or identify affected Check Point versions or fixes.

hackernews · louiereederson · Nov 24, 16:32 · [Discussion](https://news.ycombinator.com/item?id=50630594)

**「Background」** The campaign follows Check Point&\#x27;s handling of CVE-2026-16232, an authentication bypass that lets a remote attacker obtain an application login token and reach SmartConsole with full administrative privileges; Check Point disclosed and patched it in July 2026 and issued a further update in September, and its advisory states that remote exploitation requires the Management Server IP address to be reachable from the internet with no restrictions on Trusted Clients. The cookie-forgery step rests on a separate weakness: the affected login endpoint drew its signed session identifier from JavaScript&\#x27;s Math.random\(\), which is not a cryptographic generator, so a series of observed values can be used to reconstruct the generator&\#x27;s internal state.

**「Exposure depends on management-server configuration」** Check Point&\#x27;s advisory says exploitation of CVE-2026-16232 requires the Management Server to be reachable from the internet with no restrictions on Trusted Clients, so administrators should restrict that exposure or configure Trusted Clients rather than assume every deployment is affected. Check Point also says its IPS protection against exploitation only takes effect after Security Gateways are updated to the latest IPS update.

**「Community Discussion」** Commenters debated the root cause, with one arguing that Math.random\(\) should be fixed rather than requiring hundreds of applications to use it correctly, and another asking why all random number generators should not be at least somewhat secure. Another commenter noted that initial access is unclear and speculated—without confirmation—that internet-exposed management servers and CVE-2026-16232 may be involved, while a further comment predicted wider LLM-driven attacks.

<details><summary>References</summary>
<ul>
<li><a href="https://support.checkpoint.com/results/sk/sk185169">sk185169 - CVE-2026-16232 - Authentication bypass with ...</a></li>
<li><a href="https://www.cybersecuritydive.com/news/ai-enabled-campaign-targets-check-point-security-management-servers/875622/">AI-enabled campaign targets Check Point Security Management ...</a></li>
<li><a href="https://support.checkpoint.com/results/sk/sk185169">sk185169 - CVE-2026-16232 - Authentication bypass with ...</a></li>
<li><a href="https://blog.checkpoint.com/security/security-advisory-action-required-active-exploitation-of-check-point-smartconsole-authentication-bypass-cve-2026-16232">Security Advisory - Action Required - July 2026 Security ...</a></li>
<li><a href="https://advisories.checkpoint.com/defense/advisories/public/2026/cpai-2026-9895.html">CPAI-2026-9895 - Check Point Software</a></li>

</ul>
</details>

**Tags**: `#cybersecurity`, `#Check Point`, `#PRNG`, `#session-cookie forgery`, `#threat intelligence`

---

<a id="item-tech-news-5"></a>
### [Ternary Bonsai 2.5 27B draws local-model speed reports](https://prismml.com/news/bonsai-2-5-27b) ⭐️ 7.0/10

The Hacker News item covers Ternary Bonsai 2.5 27B, a 27B ternary/Q2 GGUF local model, but no announcement text was supplied, so its official context limit, benchmark conditions, and licensing could not be verified. One commenter reported 22–25 tokens/s on a Mac Mini M5 Pro with 24 GB RAM and said a 128k context fit in memory, which they said made it potentially usable for agentic coding. Those are single-machine observations, not vendor-published or independently replicated results.

hackernews · b0m · Nov 24, 20:08 · [Discussion](https://news.ycombinator.com/item?id=50633922)

**「Background」** Ternary Bonsai is PrismML&\#x27;s line of ternary-weight models, an aggressive quantization approach that lets a 27B-parameter model fit in roughly 5.9 GB. The 2.5 release follows the September 2026 Bonsai 2 build; PrismML says it keeps the same footprint while improving agentic coding and multi-turn tool use.

**「Local-agent trade-off」** Developers running local coding agents can fit the 5.93 GB GGUF into a 24 GB Mac and use long context, but PrismML&\#x27;s reported 75.6 SWE-bench Verified score trails the 80.6 of the full-precision Qwen3.8 27B base model, so the quantized release should be validated against the intended tasks rather than treated as equivalent. Compatibility is listed for llama.cpp and MLX, with vLLM usage also documented.

**「Community discussion」** Commenters treated the model’s efficiency as the main draw: one measured 22–25 tokens/s and 128k context on a Mac Mini, while another said a self-built long-horizon test improved from Bonsai2’s 107 minutes and 358 steps to Bonsai2.5’s 76 minutes and 296 steps at the same 5-of-8 pass rate. A separate commenter claimed SWE-bench Verified parity with Opus 4.6 but questioned how much reflects benchmark tuning, benchmark drift, or genuine small-model progress, and another asked for comparisons against similarly sized Qwen quants.

<details><summary>References</summary>
<ul>
<li><a href="https://prismml.com/news/bonsai-2-5-27b">PrismML — Introducing Ternary Bonsai 2.5 27B: Powering ...</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism-ml/Ternary-Bonsai-2.5-27B-GGUF · Hugging Face</a></li>
<li><a href="https://huggingface.co/prism-ml/Ternary-Bonsai-2.5-27B-GGUF">prism-ml/ Ternary - Bonsai - 2 . 5 - 27 B -GGUF · Hugging Face</a></li>
<li><a href="https://tproger.ru/news/prism-ml-vypustila-ternary-bonsai-2-5-27b-model-v-5-9-gb-dlya-a">Ternary Bonsai 2 . 5 27 B : тернарная модель для агентного кодинга</a></li>

</ul>
</details>

**Tags**: `#local LLMs`, `#model quantization`, `#ternary models`, `#agentic coding`, `#SWE-bench`

---

## Financial News

<a id="item-finance-news-1"></a>
### [Xiaomi Q3 adjusted net profit falls 56.8% as EV deliveries top 100,000](https://ir.mi.com/static-files/3d372aaa-8ff8-4e33-ba01-68c8d7975a0b) ⭐️ 7.0/10

Xiaomi&\#x27;s third-quarter 2026 adjusted net profit fell 56.8% year on year to RMB 4.884 billion, slightly above the RMB 4.746 billion market expectation cited in the report, while revenue dropped 5.2% to RMB 107.24 billion. The company said higher memory-chip and component prices plus increased research spending weighed on margins, even as quarterly electric-vehicle deliveries reached 100,975 units.

telegram · zaihuapd · Nov 24, 10:09

**「Background」** Xiaomi&\#x27;s EV business is newer than its core smartphone unit, and the company says higher memory-chip prices and increased R&amp;D spending are weighing on near-term profit.

**「Who is affected」** Xiaomi phone buyers are paying more on average: after the company deliberately scaled back low- and mid-range models, its average selling price reached a record high in the quarter.

**Tags**: `#Xiaomi`, `#quarterly earnings`, `#adjusted net profit`, `#EV deliveries`, `#smartphone shipments`

---