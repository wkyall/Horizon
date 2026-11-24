---
layout: default
title: "Horizon Summary: 2026-11-24 (EN)"
date: 2026-11-24
lang: en
---

> From 38 items, 12 important content pieces were selected

---

**Technology News**
1. [Ladybird independent browser engine reaches alpha for macOS and Linux](#item-tech-news-1) ⭐️ 8.0/10
2. [Z.ai&\#x27;s GLM-5.4 Debuts a Looped Transformer for Coding](#item-tech-news-2) ⭐️ 8.0/10
3. [NariQ ships 3-bit Qwen3.8-27B GGUF with custom llama.cpp fork](#item-tech-news-3) ⭐️ 7.0/10
4. [Codex2api releases suspected backdoored after account compromise](#item-tech-news-4) ⭐️ 7.0/10
5. [Claimed AI Riemann Hypothesis proof called vacuous; author admits &\#x27;garbage&\#x27; Lean code](#item-tech-news-5) ⭐️ 7.0/10
6. [Huawei says HarmonyOS 5–7 devices pass 100 million](#item-tech-news-6) ⭐️ 7.0/10
7. [Singapore&\#x27;s Wong says city-state won&\#x27;t be conduit for evading US chip curbs](#item-tech-news-7) ⭐️ 7.0/10
8. [Anthropic reports Claude-found VP≠VNP proof with Lean 4 formalization](#item-tech-news-8) ⭐️ 7.0/10

**Technology Blog**
1. [Day-0 vLLM Support for ERNIE 5.5 Flash Preview](#item-tech-blog-1) ⭐️ 6.0/10

**Financial News**
1. [AI selloff clouds Chinese AI IPO plans](#item-finance-news-1) ⭐️ 8.0/10
2. [Shanghai Sets First Metro Fare Change in 21 Years](#item-finance-news-2) ⭐️ 7.0/10
3. [报道：SpaceX 向 Anthropic 和 Google 出租算力，月入数十亿美元](#item-finance-news-3) ⭐️ 7.0/10

---

## Technology News

<a id="item-tech-news-1"></a>
### [Ladybird independent browser engine reaches alpha for macOS and Linux](https://ladybird.org/posts/alpha/) ⭐️ 8.0/10

Ladybird, an independent browser engine built largely from scratch, has released its first alpha with installable builds for macOS and Linux, so users no longer need to compile it themselves. The browser runs tabs in separate processes and already runs WebAssembly applications such as ffmpeg and Pyodide, but its service-worker support is incomplete: Datasette Lite fails with an error tied to an unimplemented \`navigator.serviceWorker.startMessages\`. The project warned that some websites will not work and that the browser will crash sometimes, and it is asking users to report broken sites and review crash reports before sending them. Ladybird also reported gaining 75,650 web-platform-tests passes in October, reaching 2,184,722 and overtaking Safari, a gain it attributed largely to AI coding agents filling in missing functionality.

hackernews · janvdberg · Nov 23, 16:13 · [Discussion](https://news.ycombinator.com/item?id=50614249)

**「Background」** Ladybird is a browser engine built largely from scratch, with its own HTML parser, CSS engine, layout, JavaScript, and WebAssembly implementations; it originated in the more ambitious SerenityOS project. It still relies on external components including HarfBuzz for text shaping, Skia for 2D graphics, ffmpeg for video, and SQLite.

**「Impact」** The alpha is usable enough for testing but not yet a dependable daily browser: users should expect occasional crashes and site failures, use Ladybird&\#x27;s built-in broken-site reporting, and review crash reports before opting to send them. The known service-worker gap means service-worker-heavy web apps may fail even when ordinary pages render correctly.

**「Community discussion」** Commenters reported that most sites they tried rendered correctly, including ProxMox and NoVNC, though one noted slightly jerky scrolling. One commenter argued that Ladybird should take fingerprinting seriously by returning spoofed or randomized JavaScript values and offering more granular permissions, while another said swapping self-developed components for production-grade libraries such as SQLite and Skia improved the browser but lost some of the original SerenityOS hacker spirit.

**Tags**: `#Ladybird`, `#browser engine`, `#open source`, `#web standards`, `#browser fingerprinting`

---

<a id="item-tech-news-2"></a>
### [Z.ai&\#x27;s GLM-5.4 Debuts a Looped Transformer for Coding](https://z.ai/blog/glm-5.4) ⭐️ 8.0/10

Z.ai released GLM-5.4, its first model built on a looped transformer architecture, in which a group of weight-shared layers runs for multiple iterations to add depth without increasing the parameter count. The model is not available as open weights; access currently requires Z.ai&\#x27;s Coding Plan subscription rather than the regular API plan or OpenRouter, although the plan&\#x27;s API key works with the same OpenAI-compatible Responses API at https://api.z.ai/api/v1. Simon Willison reported testing GLM-5.4 through that route and found its generated pelican SVGs similar in quality to GLM-5.3 and less distinctive than those from GLM-5.1 and GLM-5.2; no independent benchmark results were provided.

hackernews · foohis · Nov 23, 10:06 · [Discussion](https://news.ycombinator.com/item?id=50609685)

**「Background」** A loop transformer runs a group of weight-shared layers for several iterations instead of executing each layer once per forward pass, gaining effective depth without adding parameters; Thinking Machines Lab described the same approach for its Inkling 2 Mini model on November 20, three days before this release. GLM-5.4 is the latest point release in Z.ai&\#x27;s GLM-5 line after 5.1, 5.2 and 5.3, and Z.ai&\#x27;s developer documentation describes it as the company&\#x27;s first flagship built on the Loop Transformer architecture, claiming intelligence comparable to 2T–3T parameter models.

**「Access limited to Coding Plan」** GLM-5.4 is currently reachable only through Z.ai&\#x27;s GLM Coding Plan subscription, which starts at $18/month and exposes an OpenAI-compatible endpoint at https://api.z.ai/api/v1; the regular Model API will be enabled only after a security assessment, and no open weights have been released. Subscribers on weekly-quota plans receive 1.5× the GLM-5.4 quota they had for GLM-5.3, so developers whose clients already point at a Coding Plan key can switch models without changing endpoints, while those relying on third-party routers or the standard API must wait or move to a Coding Plan.

**「Community Discussion」** Commenters welcomed Zhipu&\#x27;s relatively detailed architecture disclosures, with one describing looped transformers as an obvious direction despite unresolved problems, while another said Chinese models&\#x27; long &quot;marathon thinking&quot; sessions make even simple tasks much slower than frontier models. A separate commenter framed the architecture as a way to reduce the memory-bandwidth cost of moving each layer through the chip during inference.

<details><summary>References</summary>
<ul>
<li><a href="https://docs.z.ai/guides/llm/glm-5.4">GLM - 5 . 4 - Overview - Z . AI DEVELOPER DOCUMENT</a></li>
<li><a href="https://z.ai/subscribe">GLM Coding Plan — AI Coding Powered by GLM-5.4 &amp; GLM-5.3 ...</a></li>
<li><a href="https://docs.z.ai/guides/llm/glm-5.4">GLM-5.4 - Overview - Z.AI DEVELOPER DOCUMENT</a></li>

</ul>
</details>

**Tags**: `#Looped Transformers`, `#LLM architecture`, `#coding models`, `#Zhipu AI`, `#model release`

---

<a id="item-tech-news-3"></a>
### [NariQ ships 3-bit Qwen3.8-27B GGUF with custom llama.cpp fork](https://huggingface.co/nari-labs/Qwen3.8-27B-NariQ-GGUF) ⭐️ 7.0/10

NariQ has published 3-bit, 2.5-bit, and 2-bit GGUF quantizations of Qwen3.8-27B, claiming near-BF16 quality on agentic, math, multilingual, and image tasks and providing a custom llama.cpp fork required to run them. In the vendor&\#x27;s benchmarks, 3-bit and 2.5-bit results stay close to BF16—DeepSWE 41.0 and 41.9 versus 39.8, Terminal-Bench 2.1 63.8 and 60.2 versus 62.6, and AIME 98.3 and 96.5 versus 97.7—while 2-bit drops more sharply, to 28.6 on DeepSWE and 86.0 on AIME. Decode throughput is comparable to other quantizations on an RTX PRO 6000, according to the release. The figures are vendor-reported and have not been independently verified, and the release does not quantify what information is lost at lower bit widths.

hackernews · toebee · Nov 23, 13:42 · [Discussion](https://news.ycombinator.com/item?id=50611402)

**「Background」** NariQ&\#x27;s files are GGUF quantizations of Qwen3.8-27B, an open-weight \(Apache 2.0\) Qwen model released in mid-August 2026 that pairs a vision encoder with 262k native context, so the target here is a multimodal base model rather than a text-only one. Quantization in this format lowers weight precision to shrink file size and memory use, normally at some cost in quality; NariQ claims its 3-bit-and-below versions avoid that loss on long-horizon agentic tasks. The release also states that running these files currently requires NariQ&\#x27;s own llama.cpp fork, meaning the low-bit formats are not yet usable with upstream llama.cpp. 

**「Compatibility and size trade-offs」** Running these files requires building nari-labs&\#x27; llama.cpp fork from source; the quantizations are not drop-in for mainline llama.cpp, so existing GGUF tooling and prebuilt binaries will not load them as-is. Users choosing a file size should also note the quality cliff at 2-bit: DeepSWE falls from 39.8 at BF16 to 28.6 and Terminal-Bench 2.1 from 62.6 to 52.4, whereas the 3-bit and 2.5-bit files stay within a few points of BF16. For comparison, standard 4-bit Qwen 3.8-27B quants are documented as needing roughly 16–19 GB of VRAM or unified memory, the size class NariQ&\#x27;s 10 GB file is positioned to undercut.

**「Community discussion」** Commenters welcomed the multiple long-horizon and held-out evaluations but remained wary of benchmark overfitting; one argued that, based on the plots, most gains come from a harness difference rather than the model, and another asked what information is actually lost as file size falls. A user reported about 3.8 tok/s decode on an 18 GB M3 Pro with the 3.0-bpw file \(4.9 tok/s at 2.0 bpw\), far slower than CUDA, and wondered whether a 16 GB Mac could run it.

<details><summary>References</summary>
<ul>
<li><a href="https://aireleasetracker.com/model/qwen/qwen3.8-27b">Qwen3.8-27B — Benchmarks, Specs &amp; Release Date</a></li>
<li><a href="https://www.yottalabs.ai/post/qwen-3-8-27b-specs-hardware-requirements-how-to-run-2026">Qwen 3.8 27B: Specs, Hardware Requirements, and How to Run It ...</a></li>
<li><a href="https://huggingface.co/Qwen/Qwen3.8-27B">Qwen/Qwen3.8-27B · Hugging Face</a></li>
<li><a href="https://unsloth.ai/docs/models/qwen3.8">Qwen 3 .8 - How to Run Locally | Unsloth Documentation</a></li>

</ul>
</details>

**Tags**: `#model quantization`, `#LLM inference`, `#Qwen`, `#llama.cpp`, `#benchmarking`

---

<a id="item-tech-news-4"></a>
### [Codex2api releases suspected backdoored after account compromise](https://github.com/WormW/codex2api-incident-2026-11) ⭐️ 7.0/10

A suspected compromise of the Codex2api GitHub account reportedly let an attacker bypass the main branch, push release tags, and publish backdoored builds; the account compromise and incident report are not independently verified here. The report says v3.1.11 removed authentication, enabling unauthenticated remote command execution, and that a workflow exfiltrated 16 GitHub Actions secrets across at least 21 repositories under the same account. Users who installed or updated versions 3.1.10–3.1.12 are advised to stop using them, roll back to 3.1.9, and rotate GitHub tokens, SSH keys, database credentials, DeepSeek and other related secrets.

telegram · zaihuapd · Nov 23, 11:21

**「Background」** GitHub Actions release pipelines are commonly triggered by pushing a tag, so branch protections applied to the main branch do not necessarily cover tag-based builds. Repository Actions secrets are injected into those workflow runs, which means code executed during a compromised build can read and exfiltrate them. That mechanism explains why the reported incident affected not only the released Codex2api version but also other repositories under the same account.

**「Who is exposed and what to do now」** Anyone who installed or auto-updated Codex2api to 3.1.10–3.1.12 should treat their host as already breached: v3.1.11 dropped authentication entirely, so the release exposes an unauthenticated remote-code-execution path, not just a theoretical backdoor. The reported exfiltration of 16 GitHub Actions secrets also means credentials belonging to the same account&\#x27;s other repositories \(at least 21\) should be considered burned, so beyond reverting to 3.1.9, operators need to rotate GitHub tokens, SSH keys, and database and DeepSeek API keys rather than only re-pulling the older version. Because the attack worked by pushing tags outside the main branch, verify the 3.1.9 rollback against a known-good commit rather than trusting the tag name — retagging a release to point at malicious code is the same mechanism used in the 2025 tj-actions/changed-files compromise \(CVE-2025-30066\).

<details><summary>References</summary>
<ul>
<li><a href="https://www.githubforensics.com/en/blog/github-actions-secrets-leak">GitHub Actions secrets leak: investigating exfiltration</a></li>

</ul>
</details>

**Tags**: `#supply-chain attack`, `#GitHub Actions`, `#secrets exfiltration`, `#remote code execution`, `#open-source security`

---

<a id="item-tech-news-5"></a>
### [Claimed AI Riemann Hypothesis proof called vacuous; author admits &\#x27;garbage&\#x27; Lean code](https://x.com/i/web/status/2124987173439209561) ⭐️ 7.0/10

Alpöge and Claude claimed to prove the Riemann Hypothesis and its generalized version, but released only 17 million lines of Lean across 175,000 files and no human-readable proof. The Lean and Mathlib community said the next day it had &quot;sufficient confidence&quot; that the code proved the proposition, but other researchers then alleged the formalization was vacuous: key definitions were written as tautologies and geometric conditions had no effect. Alpöge subsequently dismissed the 250,000-page figure as &quot;a joke&quot; and said the code was &quot;garbage but compiles,&quot; calling the criticism entirely reasonable.

telegram · zaihuapd · Nov 24, 01:29

**「Background」** Lean is a proof assistant that mechanically checks a formal proof against the definitions and statements encoded in its code. Earlier coverage described Alpöge’s release as a Lean formalization with no accompanying paper and reported that Lean/Mathlib community members certified it a day later, which is why later scrutiny focused on whether the encoded statements were meaningful rather than merely whether the code compiled.

**「Impact」** For Lean and Mathlib users, the case shows that a successful build is not evidence that a formalization proves the intended theorem: the alleged tautological definitions and inert geometric conditions had to be found by inspecting definitions and theorem statements, not compiler output.

<details><summary>References</summary>
<ul>
<li><a href="https://www.datastudios.org/post/claude-riemann-hypothesis-proof-lean-community-certifies-levent-alpoge">Claude-assisted Riemann hypothesis proof certified by Lean ...</a></li>
<li><a href="https://www.martincid.com/technology-sv/claude-riemann-hypothesis-proof-anthropic-levent-alpoge-lean/">A Riemann hypothesis proof made with Claude compiles, and no ...</a></li>

</ul>
</details>

**Tags**: `#AI`, `#Lean`, `#formal verification`, `#Riemann Hypothesis`, `#AI-generated code`

---

<a id="item-tech-news-6"></a>
### [Huawei says HarmonyOS 5–7 devices pass 100 million](https://www.xinhuanet.com/20261124/68842538167d4e59a875056d5eb885ad/c.html) ⭐️ 7.0/10

Huawei Terminal announced on November 24 that phones, tablets, and computers running HarmonyOS 5, 6, or 7 have surpassed 100 million units. The company said more than 460,000 apps and services are available for HarmonyOS and that registered developers exceed 12 million. It also said open-source HarmonyOS has more than 14,000 contributors and 120-plus industry distributions, with partner-contributed capabilities integrated into more than 1,600 apps and usage up 90-fold in a year. The figures are Huawei&\#x27;s own and were reported by state media; the announcement does not break out active devices or native HarmonyOS app counts.

telegram · zaihuapd · Nov 24, 01:46

**「Background」** HarmonyOS was first released in 2019, but the native, Android-independent line counted in this milestone — HarmonyOS 5 and later — was only released in October 2024. The 100 million figure therefore covers roughly two years of devices running the native versions, not every Huawei device shipped since 2019. The same announcement also cites contributions to the open-source OpenHarmony project, including 14,000-plus contributors and more than 120 industry distributions.

**「Impact」** For developers, the announcement sets the stated target market for HarmonyOS 5–7 at 100 million devices and 460,000 available services, but because no active-user or regional breakdown was released, teams should treat it as an ecosystem-size claim rather than a measure of engagement.

**Tags**: `#HarmonyOS`, `#Huawei`, `#operating systems`, `#open source`, `#mobile ecosystem`

---

<a id="item-tech-news-7"></a>
### [Singapore&\#x27;s Wong says city-state won&\#x27;t be conduit for evading US chip curbs](https://www.bloomberg.com/news/articles/2026-11-24/singapore-won-t-be-conduit-to-skirt-us-chip-curbs-wong-says) ⭐️ 7.0/10

Singapore Prime Minister Lawrence Wong said the country will not be used as a channel for companies to evade US chip export controls, and that authorities are investigating Megaspeed&\#x27;s purchases of Nvidia chips. The statement came a day after the US Commerce Department added Megaspeed and six other Southeast Asian firms to a trade blacklist, with the Federal Register citing a &quot;significant risk&quot; that they would transfer advanced computing products to unauthorized users; the listing includes related entities in Malaysia and Thailand. Reuters reported that Alibaba&\#x27;s Singapore subsidiary, Apex Enterprise Solutions, was also named, and Alibaba said it has never transferred controlled advanced computing chips.

telegram · zaihuapd · Nov 24, 05:03

**「Background」** US export rules restrict sales of advanced AI accelerators, including Nvidia chips, to China, and enforcement has increasingly looked at whether restricted buyers obtain such hardware through third countries. The Federal Register notice described in the report frames the Southeast Asian designations around diversion risk to unauthorized users rather than around any Singapore-specific rule.

**「Impact」** For firms handling Nvidia hardware in Singapore, Malaysia and Thailand, the immediate consequence is scrutiny of who the end users are: Singapore is investigating Megaspeed&\#x27;s chip purchases while Washington has designated the buyers, and Alibaba is already publicly disputing the listing of its Singapore unit.

**Tags**: `#semiconductor export controls`, `#AI chips`, `#Nvidia`, `#Singapore`, `#US-China tech`

---

<a id="item-tech-news-8"></a>
### [Anthropic reports Claude-found VP≠VNP proof with Lean 4 formalization](https://github.com/anthropics/formal-math/blob/main/vp-vnp/README.md) ⭐️ 7.0/10

Anthropic has published a paper titled “VP ≠ VNP over every field” and a Lean 4 formalization, saying both were written by an internal research Claude model. The claimed proof derives a superpolynomial arithmetic-circuit lower bound for the Hamiltonian-cycle polynomial and concludes that VP is a proper subclass of VNP, which, if correct, would settle Valiant’s 1979 algebraic-complexity conjecture; it does not address P versus NP. The repository reports an audit against three standard axioms and a check with the independent nanoda kernel, with no \`sorry\` outside placeholder files. No human mathematician has reviewed the work yet, and Lean cannot establish that the formal statement matches the claimed theorem; Appendix Q lists discrepancies pending independent review.

telegram · zaihuapd · Nov 24, 06:02

**「Background」** Valiant&\#x27;s 1979 algebraic-complexity conjecture asks whether VP is a proper subclass of VNP, with these classes defined through arithmetic circuits. The source notes that the claimed result concerns arithmetic circuits only and does not address P versus NP.

**「What to verify」** Complexity researchers and anyone relying on the Lean 4 artifact should treat VP≠VNP as unverified until human reviewers confirm that the formal statement matches the claimed theorem and resolve the discrepancies listed in Appendix Q. The no-sorry audit and nanoda kernel check show the proof compiles, but as alphaXiv notes, Lean verifies a proof against its formal statement, not that the statement captures the paper&\#x27;s claim. Until that review happens, the result should not be cited as establishing VP as a proper subclass of VNP.

<details><summary>References</summary>
<ul>
<li><a href="https://www.alphaxiv.org/abs/2611.vp-vnp-arithmetic-lower-bounds">VP VNP Over Every Field | alphaXiv</a></li>

</ul>
</details>

**Tags**: `#complexity theory`, `#Lean 4`, `#AI for mathematics`, `#formal verification`, `#Anthropic`

---

## Technology Blog

<a id="item-tech-blog-1"></a>
### [Day-0 vLLM Support for ERNIE 5.5 Flash Preview](https://vllm.ai/blog/2026-11-24-ernie-5-5-flash-preview) ⭐️ 6.0/10

rss · vLLM Blog · Nov 24, 00:00

**「Background」** ERNIE 5.5 Flash Preview is a 280B-parameter sparse mixture-of-experts model with 14B activated per token, a 1M-token context, and tool use for long-horizon agent tasks. Serving it on release day meant fitting new attention, MoE, quantization, and decoding choices into vLLM without a model-specific fork.

**「Solution」** The authors describe day-0 support through vLLM-ERNIE, a standalone plugin installed beside vllm==0.32.0 and auto-discovered via vllm.general\_plugins; it registers the architecture and serving components, importing model code only when needed. The 43-layer model mixes 37 Heavily Compressed Attention layers with six MLA-DSA layers, plus Multi-Router Latent MoE and new output/residual structures. Dedicated fused kernels pre-fold fixed parameters, merge router GEMMs, and fuse gating and the MultiMax head; the authors report 1.55x to 6.53x per-kernel gains over naive implementations with numerics or expert selections preserved. FlashIndexer adds a learned token-local head router and threshold pre-filtering to DSA, adapted with about 1B tokens, for a reported 40% indexing speedup \(1.4x at 1M context\). The default checkpoint uses MXFP4 W4A8 routed experts with QAT, FP8 elsewhere and for the KV cache, and FP4 for the DSA indexer; a bundled three-layer DSpark draft model proposes up to seven tokens with mean acceptance length above 4.0 on coding and agent workloads. It also supports expert parallelism, attention TP, PD disaggregation, and CPU KV offload; the reported speedups are vendor figures without benchmark methodology or independent validation.

**「Takeaway」** The authors’ thesis is that a standalone plugin can provide day-0 support and ship model-specific fixes on the model’s schedule while inheriting vLLM core improvements, if model and kernels are co-designed around inference cost.

**Tags**: `#vLLM`, `#ERNIE`, `#MoE inference`, `#kernel fusion`, `#speculative decoding`

---

## Financial News

<a id="item-finance-news-1"></a>
### [AI selloff clouds Chinese AI IPO plans](https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo) ⭐️ 8.0/10

A selloff that accelerated after Anthropic’s record $119.5 billion IPO has erased $1.7 trillion from Chinese tech stocks since late June and is clouding planned or considered share sales by DeepSeek, Moonshot and StepFun, Bloomberg reported.

telegram · zaihuapd · Nov 23, 09:31

**「Background」** Anthropic’s record $119.5 billion IPO—the largest in U.S. history—was followed by a global AI stock selloff, and Chinese tech shares have lost $1.7 trillion since late June, clouding the outlook for planned or considered share sales by DeepSeek, Moonshot AI and StepFun.

**「Impact」** The selloff could delay or lower the pricing of planned listings by DeepSeek, Moonshot and StepFun, postponing public-market exits for their private backers and reducing the capital the companies can raise.

<details><summary>References</summary>
<ul>
<li><a href="https://www.bloomberg.com/news/articles/2026-11-23/china-s-next-ai-deals-clouded-by-selloff-after-anthropic-ipo">China’s Next AI Deals Clouded by Selloff After Anthropic IPO</a></li>
<li><a href="https://www.straitstimes.com/business/chinas-next-ai-deals-clouded-by-sell-off-after-anthropic-ipo">China’s next AI deals clouded by sell-off after Anthropic IPO</a></li>
<li><a href="https://www.cnbc.com/2026/11/19/anthropic-ipo-ai-stocks-selloff.html">Anthropic IPO fails to lift AI stocks - CNBC</a></li>
<li><a href="https://www.outlookbusiness.com/deeptech/deepseek-moonshot-gigaai-why-chinas-ai-startups-are-rushing-for-ipo">DeepSeek , Moonshot , GigaAI: Why China &#x27;s AI Startups Are Rushing...</a></li>

</ul>
</details>

**Tags**: `#AI selloff`, `#China tech stocks`, `#IPO market`, `#Anthropic IPO`, `#market disruption`

---

<a id="item-finance-news-2"></a>
### [Shanghai Sets First Metro Fare Change in 21 Years](https://weibo.com/1699432410/5368461393397183) ⭐️ 7.0/10

Shanghai announced its first metro fare adjustment in 21 years, setting a starting fare of 3 yuan for trips of 0–4 km, with 1 yuan added at set distance intervals thereafter \(every 4, 4, 4, 7, 7, 10 and 10 km, then every 15 km beyond 50 km\). The new fares and accompanying discounts take effect on December 1.

telegram · zaihuapd · Nov 23, 10:45

**「Background」** The fare structure had not been changed for 21 years, and the new pricing is distance-based, so riders pay more the farther they travel.

**「Impact」** To soften the effect on frequent riders, the operator is selling four multi-ride passes — 35, 45, 60 and 90 rides priced at 190, 210, 270 and 390 yuan, on sale from November 26 — and will give a 10% discount once a rider&\#x27;s monthly spending through a single payment channel reaches 90 yuan.

**Tags**: `#上海地铁`, `#公共交通票价`, `#民生政策`, `#出行成本`

---

<a id="item-finance-news-3"></a>
### [报道：SpaceX 向 Anthropic 和 Google 出租算力，月入数十亿美元](https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html) ⭐️ 7.0/10

《纽约时报》11 月 23 日报道，自今年 5 月起，SpaceX 一直向 Anthropic、Google 等公司出租其数据中心的算力，每月收入达数十亿美元；报道援引三名知情人士称，马斯克曾向员工表示，SpaceX 在 AI 领域已经落后，出租算力比自用更赚钱。

telegram · zaihuapd · Nov 24, 02:06

**「Background」** According to the Times report relayed in the post, the arrangement dates to May and involves a trade-off over the same data-center capacity: leasing it to outside AI companies or keeping it for SpaceX’s own AI work.

**「影响」** 若上述报道属实，Anthropic 和 Google 将获得额外的数据中心算力用于 AI 开发，而 SpaceX 将获得一笔不依赖火箭发射业务的收入。

<details><summary>References</summary>
<ul>
<li><a href="https://www.nytimes.com/2026/11/23/business/elon-musk-ai-anthropic-google.html">Elon Musk Faces an A.I. Dilemma at SpaceX - The New York Times</a></li>
<li><a href="https://www.gate.com/news/detail/SPCX/spacex-rents-computing-power-to-anthropic-and-google-while-grok-ai-lags-25823949">SpaceX Rents Computing Power to Anthropic and Google While ...</a></li>

</ul>
</details>

**Tags**: `#SpaceX`, `#AI compute`, `#Anthropic`, `#Google`, `#Elon Musk`

---