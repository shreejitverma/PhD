# PHASE 2 FACULTY MAPPING — Stevens FE / NYU Tandon FRE / Track 2 (MIT EECS, CMU ECE/CSD)

Retrieved 2026-08-16.

# PROGRAM A: STEVENS — PhD Financial Engineering (School of Business)

## A1. Ionut Florescu — FIT 5
IDENTITY: Research Professor, School of Business; Director of the Hanlon Financial Systems Lab; Director of Financial Technology and Analytics program [VERIFIED — https://www.stevens.edu/profile/ifloresc]. Title nuance: George Calhoun directs the Hanlon Financial Systems Center (HFSC); Florescu directs the Lab; Bozdog is Deputy Director of the Laboratories [VERIFIED — https://www.stevens.edu/school-business/faculty]. Scholar: https://scholar.google.com/citations?user=IH14Zk0AAAAJ (~1,722 citations). STATUS: active (2026 pubs). "Research Professor" = non-tenure-track research title; has nonetheless supervised many PhD students (Dan Wang, Thiago Winkler Alves, Ziwen Ye, Parisa Golbayani, Amin Salighehdar, Christopher Flynn, Dragos Bozdog) [VERIFIED — profile].

RESEARCH — VERBATIM:
1. "Mandate without Managers: Automated Market Makers as Verifiable Portfolio Products" — Zachary Feinstein, Ionut Florescu, Sean O'Leary — arXiv, Aug 3, 2026 — http://arxiv.org/abs/2608.02917v1
2. "Impact of Retail Investor Attention on Option Returns" — Long, W.; Lee, C.; Florescu, I. — Journal of Financial Econometrics, 2026
3. "Analysis of rare events using multidimensional liquidity measures" — Zaika, M.; Bozdog, D.; Florescu, I. — International Review of Financial Analysis, 2024
4. "Control in Stochastic Environment with Delays" — Yao, Z.; Florescu, I.; Lee, C. — Proceedings of ICAPS, 2024
5. "Insights on Statistics and Market Behavior of Frequent Batch Auctions" — Alves, T. W.; Florescu, I.; Bozdog, D. — Mathematics, 2023
Foundational: "SHIFT: A Highly Realistic Financial Market Simulation Platform" — Alves, Florescu, Calhoun, Bozdog — arXiv:2002.11158 / SSRN 3544308. SHIFT runs the annual Hanlon HFT competition [VERIFIED — https://fsc.stevens.edu/high-frequency-trading-simulation-system/].
Current problem: microstructure with the SHIFT exchange simulator (order-driven, FIFO matching), liquidity/rare-event measures in HF data, RL/stochastic control with delays, and (with Feinstein) on-chain AMMs as portfolio products. Open problem: UNKNOWN.

FIT: the entire MS thesis connects. Year-one task: build a hardware-accelerated / kernel-bypass matching-and-gateway tier for SHIFT to emulate realistic exchange latency distributions at microsecond fidelity, extending the frequent-batch-auction line with latency-arms-race experiments — publishable and squarely inside the lab's purpose [INFERRED]. Missing: his recent trend is econometrics/RL/DeFi, not hardware; candidate has no publication; Research Professor = soft-money funding.
FIT SCORE: 5 — existing thesis relationship at the same lab, direct artifact-to-agenda match.

FUNDING: NSF PI: only conference grants, all expired (last ended 2014) [VERIFIED — API]. Non-NSF on profile: NSF CRAFT project (2023-24) $100K; CAPCO (2020-22) $120K; CME Foundation $100K + $85K — CME project "SHIFT — Market Microstructure Testbed for Evaluating High-Frequency Electronic Markets". CRAFT industry members: Bank of America, Charles Schwab, CME, Vanguard, Prudential [VERIFIED — Stevens/RPI pages]. PhD placements: UNKNOWN. OUTLOOK: MIXED — funding flows through Hanlon industry money and CRAFT project awards, exactly the selective-RA channel that matters at Stevens.

## A2. Steve Yang — FIT 4
IDENTITY: Associate Professor; founding Director of CRAFT [VERIFIED — https://www.stevens.edu/profile/syang14]. Joined 2012, Associate 2019. Scholar: https://scholar.google.com/citations?user=X6TOecYAAAAJ (~2,021 citations). STATUS: active; CRAFT NSF award runs to 12/31/2027 with him as PI.
RESEARCH — VERBATIM (profile): "Cryptocurrency jump contagion with market sentiment events" (Yang, Pirjol, Zhang, Li — European Journal of Finance, 2025); "Does Adaptive Learning Neutralize Interbank Market Liquidity Hoarding" (Theoretical Economics Letters, 2024); "Endogenous Stock Market Participation and Wealth Accumulation" (TEL, 2024); "Financial Risk Disclosure Return Premium" (IEEE CIFEr, 2024); "Financial Semantic Textual Similarity" (IEEE CIFEr, 2024).
Current: fintech/LLM applications to financial text (XBRL-enhanced foundation LLMs), crypto contagion, RL trading-behavior identification; CRAFT portfolio ("11 funded projects").
FIT: year-one task: execution/latency-realistic testbed for CRAFT trading projects or LLM-signal-to-execution pipeline in SHIFT. Weaker artifact match than Florescu (NLP/LLM-heavy agenda); recent venues low-tier. FIT SCORE: 4 — moderate topical fit but the single best funding proxy at Stevens.
FUNDING: NSF 2113906 "IUCRC Phase I Stevens: Center for Research toward Advancing Financial Technologies (CRAFT)" — $1,034,999 — 07/01/2021 to 12/31/2027 — PI Steve Yang [VERIFIED — API]. IUCRC Phase II possible [INFERRED]. Candidate's BofA FICC history is a member-firm connection. OUTLOOK: STRONG SIGNAL.

## A3. Zachary Feinstein — FIT 4
IDENTITY: Associate Professor and Co-Director of PhD Programs, School of Business [VERIFIED — https://www.stevens.edu/profile/zfeinste]. PhD Princeton ORFE 2014. Scholar: https://scholar.google.com/citations?user=cQtnGMMAAAAJ; site https://faculty.stevens.edu/zfeinste/. STATUS: active (arXiv through Aug 2026); PhD-programs gatekeeper.
RESEARCH — VERBATIM (arXiv API): "Mandate without Managers: Automated Market Makers as Verifiable Portfolio Products" (2026-08-03, http://arxiv.org/abs/2608.02917v1); "Designing On-Chain Options: Amortizing Perpetual Options" (Bichuch, Feinstein — 2026-05-18, http://arxiv.org/abs/2605.19146v1); "Liquidation Dynamics in DeFi and the Role of Transaction Fees" (Sadeghi, Feinstein — 2026-02-12, http://arxiv.org/abs/2602.12104v1); "The Price of Liquidity: Implied Volatility of Automated Market Maker Fees" (Bichuch, Feinstein — 2025-09-27, http://arxiv.org/abs/2509.23222v1); "Dynamic clearing and contagion in financial networks" (Banerjee, Bernstein, Feinstein — EJOR, 2025).
Current: mathematical design of AMMs and on-chain derivatives + systemic risk / set-valued risk measures.
FIT: BNP AMM co-op is a literal keyword match; Feinstein-Florescu Aug 2026 AMM paper = active joint project bridging the two most relevant faculty. Year-one: implement and empirically stress the "verifiable portfolio product" AMM designs against real order-flow / SHIFT testbed. Missing: proof-driven work (fixed-point analysis); his AMMs are DeFi constant-product pools, not HFT market making. FIT SCORE: 4.
FUNDING: NSF: NO AWARDS [VERIFIED]. As PhD Co-Director he influences assistantship allocation. OUTLOOK: WEAK on grants / UNKNOWN overall.

## A4. Sweep: Ndiaye (Teaching Assoc Prof, robust opt/RL, FIT 2), Bozdog (Teaching Assoc Prof, Deputy Director Hanlon Labs, SHIFT co-author, FIT 2 as advisor but name as secondary contact), Calhoun (HFSC director, program-director profile), Hatzakis (Teaching Professor, MS director).

## PROGRAM A VERDICT
Florescu (5) - Yang (4) - Feinstein (4) - Bozdog (2) - Ndiaye (2). YES — highest-probability admit+fit on the entire list.
STEVENS FUNDING POSTURE (verified policy): funding "limited in number and awarded to exceptional candidates based on merit"; unfunded first-years can pursue assistantships later [VERIFIED — https://www.stevens.edu/graduate-funding-and-aid/phd-assistantships-and-fellowships]. Provost Doctoral Fellowship: "top one percent of applicants", 2026-27 value $31,035 stipend + $47,826 tuition/fees, year 1 fellowship then "three additional years via assistantships or departmental support"; indicate interest by March 1 [VERIFIED — same page]. FE PhD admission explicitly weighs faculty fit [VERIFIED — program page].
Realistic posture [INFERRED]: (a) real RA money = Yang's CRAFT (NSF $1.03M to 12/2027 + industry fees) and Florescu's Hanlon/CME industry funds; (b) secure a pre-application commitment in conversation with Florescu (and Yang) BEFORE applying + check the Provost Fellowship box; (c) negotiate a named multi-year RA plan (who pays years 2-4), not just year-one funding.

---

# PROGRAM B: NYU TANDON — FRE mentors via ECE PhD

Structure: "Our department offers Ph.D. training through the ECE Ph.D. program"; "mention potential FRE Ph.D. mentors in your application"; contact Tandon-ECE-Grad-Admissions@nyu.edu [VERIFIED — https://engineering.nyu.edu/academics/departments/finance-and-risk-engineering/phd]. Exactly four mentors listed: Aboussalah, Tourin, Touzi, Xin Zhang — industry-track faculty formally advise there.

## B1. Nizar Touzi — FIT 2
IDENTITY: Professor and Chair, FRE; also ECE-listed; Courant affiliate [VERIFIED — https://engineering.nyu.edu/faculty/nizar-touzi; https://nizartouzi.github.io/]. Joined Tandon as FRE chair September 2023 after École Polytechnique 2006-2023. ERC Advanced Grant (2012), Louis Bachelier Prize (2012), ICM 2010 invited; ex-president Bachelier Finance Society; co-editor Finance & Stochastics. STATUS: active, productive; chair duties tax bandwidth [INFERRED].
RESEARCH — VERBATIM (arXiv API): "Forcing and duality-corrected contracts for volatility control" (Chiusolo, Hubert, Possamaï, Touzi — 2026-07-29, http://arxiv.org/abs/2607.27039v1); "Forward Hedging Reshapes Incentive Provision" (Aïd, Touzi, Villeneuve — 2026-06-15, http://arxiv.org/abs/2606.16493v1); "Path-Dependent Ergodic Optimal Control and Backward Stochastic Differential Equations" (Lin, Lise, Touzi — 2026-06-04, http://arxiv.org/abs/2606.06757v1); "Tweedie's Formulae and Diffusion Generative Models Beyond Gaussian" (Tang, Touzi, Zhang, Zhou — 2026-05-19, http://arxiv.org/abs/2605.19391v1); "Bridging Schrödinger and Bass: A Semimartingale Optimal Transport Problem with Diffusion Control" (Henry-Labordere, Loeper, Mazhar, Pham, Touzi — 2026-03-29, http://arxiv.org/abs/2603.27712v2; companions 2601.19312, 2601.17863).
Current: stochastic control / MFG / principal-agent + heavy new push into optimal-transport-based generative diffusion models. NSF abstract (verbatim excerpt): "the project investigates ergodic optimal semimartingale transport problems... expected to outperform standard score-based procedures... Extending to continuous time poses a significant mathematical challenge." [VERIFIED — NSF 2508581]
STUDENTS: currently advising Mathieu Lise, Yuxing Huang, Xuyang Lin; completions Sauldubois (Nov 2025), Bassou (June 2024), Talbi (Oct 2022 → Asst Prof Paris City) [VERIFIED — personal site]. FRE "Full Time Scholar to work with Professor Nizar Touzi" job listing surfaced (body unretrievable — weak/unconfirmed).
FIT: only CUDA/PyTorch + C++ numerics connect. Year-one: implement/benchmark LightSBB-M samplers at scale. Missing: everything else — BSDEs, viscosity solutions at researcher level; FPGA/DPDK contributes nothing. Realistic role "numerical implementer". FIT SCORE 2 — name alongside Aboussalah/Zhang as secondary mentor, not sole.
FUNDING: NSF 2508581 "Optimal Transport for Risk Management and scenario Generation (OTRiMaGe)" — $299,057 — 09/01/2025 to 08/31/2027 — active [VERIFIED]. OUTLOOK: MIXED.

## B2. Xin Zhang — FIT 2
IDENTITY: Assistant Professor (only standard-tenure-track junior in FRE); joined 2024 (Vienna 2021-24; PhD Michigan 2021) [VERIFIED — faculty page + https://sites.google.com/umich.edu/xzhang/home]. NEW/JUNIOR FLAG. STATUS: active (Feb 2026 Columbia-NYU colloquium).
RESEARCH — VERBATIM: "Specific Wasserstein Divergence Between Continuous Martingales" (Backhoff-Veraguas, Zhang — Mathematics of Operations Research, 2026); "Reciprocal specific relative entropy between continuous martingales" (Electronic Communications in Probability 31, 2026); "Comparison for semi-continuous viscosity solutions for second order PDEs on the Wasserstein space" (Bayraktar, Ekren, He, Zhang — JDE 455, 2026); "Scaling Limits for Exponential Hedging in the Brownian Framework" (Dolinsky, Zhang — SICON 64, 2026); "A PDE Approach for Regret Bounds under Partial Monitoring" (JMLR, 2023).
NSF abstract (verbatim): "the project will establish new functional inequalities, develop numerical schemes, and explore statistical applications of these divergences... direct applications in the pricing of financial derivatives — such as Asian, lookback, and barrier options"; "Graduate students will be actively involved throughout the project" [VERIFIED — NSF 2508556].
FIT: numerical-schemes handle only; junior faculty needing productive students raises marginal value of engineering strength. Subject mismatch caps it. FIT SCORE 2.
FUNDING: NSF 2508556 "Divergence of Martingales and its Applications in Finance" — $117,090 — 09/01/2025 to 08/31/2028 [VERIFIED]. OUTLOOK: MIXED.

## B3. Amine Mohamed Aboussalah — FIT 3
IDENTITY: Industry Assistant Professor, FRE — formally listed FRE PhD mentor. Lab: Quantum Geometric Intelligence Lab [VERIFIED — faculty page]. STATUS: active (ICML 2025).
RESEARCH — VERBATIM (faculty page): "Gaussian Mixture Models Based Augmentation Enhances GNN Generalization" (ICML, 2025); "Quantum computing reduces systemic risk in financial networks" (Nature Scientific Reports 13(1):3990, 2023); "Recursive Time Series Data Augmentation" (ICLR, 2023); "A Deep Reinforcement Learning Framework For Column Generation" (NeurIPS, 2022).
FIT: RL-for-trading natural joint topic; year-one: latency-aware RL execution agents with hardware-realistic simulator (candidate supplies environment, Aboussalah the ML methodology). Strongest ML-venue record in FRE. Missing: no ML research record; industry-track prestige lower; funding UNKNOWN. FIT SCORE 3 — best topical bridge at NYU.
FUNDING: UNKNOWN (not NSF-queried).

## B4. Agnès Tourin — FIT 2
Industry Professor; FRE PhD mentor; Interim Chair 2023. "Incorporating Climate Risk into Credit Risk Modeling..." (Fintech 2(3), 2023); "A Finite Difference Scheme for Pairs Trading with Transaction Costs" (Computational Economics 60(2), 2022). Nothing 2024+ retrieved — flag. FIT 2. FUNDING UNKNOWN.

## PROGRAM B VERDICT
Aboussalah (3) - Touzi (2, anchor + funding-verified) - Zhang (2) - Tourin (2). QUALIFIED YES: engineering committee values FPGA/DPDK; department explicitly instructs mentors be named. Optimal listing: Aboussalah + Touzi (+ Zhang). Honest caveat: none of the four works on microstructure or low-latency systems — this succeeds on mechanics and NYC ecosystem, not research-agenda match. Tandon ECE PhD funding norms: UNKNOWN — manual check.

---

# PROGRAM C: TRACK 2

## C1. MIT EECS — Mohammad Alizadeh — FIT 3
NEC Professor, EECS/CSAIL; joined 2015; active [VERIFIED — https://people.csail.mit.edu/alizadeh/]. Scholar: https://scholar.google.com/citations?user=6_cxCKQAAAAJ
RESEARCH (verbatim from papers page): "Concorde: Fast and Accurate CPU Performance Modeling with Compositional Analytical-ML Fusion" (ISCA 2025, https://arxiv.org/abs/2503.23076v1); "Online reinforcement learning in non-stationary context-driven environments" (ICLR 2025 Spotlight); "m3: Accurate flow-level performance estimation using machine learning" (SIGCOMM 2024); "Practical rateless set reconciliation" (SIGCOMM 2024); "CausalSim: A causal framework for unbiased trace-driven simulation" (NSDI 2023, Best Paper). His words: "My current work centers on bringing machine learning to bear on the design and operation of computer systems". NSF 2504568 abstract names finance: "Industries such as finance, cloud computing, and large-scale AI will particularly benefit" [VERIFIED].
FIT: year-one [INFERRED]: DPDK-based traffic-generation and latency ground-truth harness feeding m3/Concorde-style learned models. Missing: no pubs, no ML-for-systems research training. FIT 3.
FUNDING: NSF 2504568 "Collaborative Research: NeTS: Medium: Learning Network Dynamics from Data" $720,000, 08/2025-07/2028 [VERIFIED]. RECRUITING VERBATIM: "Prospective students: please apply to the EECS graduate program and mention my name in your application." Placement: Venkat Arun → Asst Prof UT Austin. OUTLOOK: MIXED. Do NOT cold-email — name in application. EECS: "Decisions on support are made after decisions on admission."

## C2. MIT EECS — Daniel Sanchez — FIT 3
Elihu Thomson Professor; joined 2012; active through MICRO 2025 [VERIFIED]. Sparse-computation full stack + FHE/ZKP crypto accelerators ("Quartz" MICRO 2025; "Hopps" ASPLOS 2025; "Azul" MICRO-57 2024; "Trapezoid" ISCA-51 2024). NSF 2217099 PPoSS LARGE $2,250,000, 10/2022-09/2027 — expires the month a Fall 2027 admit arrives. 8 current students; Beckmann → CMU faculty. Trading domain irrelevant to him; Verilog skill relevant. FIT 3. OUTLOOK: MIXED.

## C3. CMU ECE — James C. Hoe — FIT 4
Professor, ECE; IEEE Fellow; joined 2000. STATUS: active — site updated 2026/03/11, teaching 18-643 Reconfigurable Logic Fall 2026, FPGA/FCCM 2026 papers with current students [VERIFIED — https://users.ece.cmu.edu/~jhoe/doku/]. AMBIGUITY: concurrently Technical Fellow at MangoBoost (DPU startup) since ~2023; "Full-Time Fellow" press title; leave status UNKNOWN.
RESEARCH (verbatim, DBLP): "Analysis and Optimization of Input-Dependent Stream Processing Pipelines on FPGAs" (FPGA 2026); "Lightweight Queueing Abstraction for Rapid Simulation and Automated Tuning of Input-Dependent Streaming Pipelines on FPGAs" (FCCM 2026); "Reconfigurable Stream Network Architecture" (ISCA 2025, https://arxiv.org/abs/2411.17966); "On Improving the HLS Compatibility of Large C/C++ Code Regions" (FCCM 2025); "Ensō: A Streaming Interface for NIC-Application Communication" (OSDI 2023, Best Paper, with Justine Sherry).
OPEN PROBLEM (his abstract, verbatim): "How can we efficiently coordinate and synchronize heterogeneous hardware resources to achieve high utilization? How can we minimize the friction of transitioning between diverse computation phases, reducing costly stalls from initialization, pipeline setup, or drain?" [VERIFIED — arXiv 2411.17966]
FIT: highest technical overlap in Track 2 — "input-dependent stream processing" is architecturally an FPGA feed handler + order book; Ensō is the candidate's DPDK/kernel-bypass territory. Year-one: extend FCCM 2026 queueing/auto-tuning work with market-data parsing as a variable-rate streaming workload class. Missing: HLS-methodology culture (group publishes HLS, not hand Verilog); newest students Fall 2023 — intake appetite uncertain. FIT 4.
FUNDING: NSF — 6 awards ALL EXPIRED (last 2020); Intel/VMware Crossroads center ended Dec 2023. 6 current students. CALCM lists no sponsors. OUTLOOK: MIXED. OUTREACH: jhoe@cmu.edu; CMU SOP guide recommends identifying 2-3 faculty in statement.

## C4. CMU CSD — Justine Sherry — FIT 3
A. Nico Habermann Associate Professor — Computer Science Department, NOT ECE [VERIFIED]. STATUS: at CMU; FLAG: "I am a research scholar at Amazon." (homepage verbatim); homepage news stale since Dec 2023.
RESEARCH (verbatim, DBLP): "FAST: An Efficient Scheduler for All-to-All GPU Communication" (NSDI 2026); "Confucius: Adapting Home Routers to Congestion Control's Reactions for Consistent Low Latency" (INFOCOM 2026); "SwitchNIC: An Hybrid Architecture for Network Functions with Fast and Consistent Shared State" (Proc. ACM Netw., CoNEXT4, 2025); "Reverse-Engineering Congestion Control Algorithm Behavior" (IMC 2024).
RECRUITING VERBATIM: "Prospective PhD Students: My home at CMU is the Computer Science Department. Please apply to CSD to work with me." NSF $1.2M ends 09/30/2026 — expiring. 2024 placements: Ware → Swarthmore faculty; Atre → Stanford faculty; Philip → Apple. FIT 3; hardware students historically co-advised with Hoe — the FPGA path runs through Hoe. Skip unless budget loose.

## C5. CMU ECE — Akshitha Sriraman — FIT 3
Assistant Professor, ECE (CS courtesy); joined ~2021-22; active; 2026 CRA Anita Borg Early Career Award + 2026 IEEE TCCA Young Computer Architect Award. Current agenda: sustainability/carbon ("Strategies and design for increasing AI sustainability" — Nature Reviews Clean Technology, July 2026; "Designing Cloud Servers for Lower Carbon" — ISCA 2024). HFT framing nearly opposite her "socially-responsible" framing — needs efficiency-per-watt repositioning.
FUNDING: NSF CAREER "Data-Driven Hardware and Software Techniques to Enable Sustainable Data Center Services" $583,323, 03/2024-02/28/2029 — active through years 1-2 [VERIFIED]. CV: "my group raised $2.2M in research funding" (Google $100K, Intel $525K, CMU Moonshot $650K, AWS $76K). RECRUITING VERBATIM: "I am always looking for highly-motivated students! Due to the volume of email I receive, I am unable to reply to each prospective student individually." 5 students, ~1/yr; first grad (2026) → Google. OUTLOOK: STRONG SIGNAL — strongest funding profile in Track 2. FIT 3.

## TRACK 2 VERDICT
Hoe (4) - Alizadeh (3) - Sanchez (3) - Sherry (3) - Sriraman (3).
Hoe: the one Track 2 case where the trading artifact maps onto the professor's own vocabulary ("input-dependent stream processing"). MIT EECS: reach, Alizadeh name-in-application route only. CMU ECE (Hoe + Sriraman named together — coherent via Ensō/MangoBoost links): best Track 2 application. CMU CSD (Sherry): separate application, highest bar — skip.

---

# CROSS-PROGRAM NOTES
1. Consensus gap: zero publications binds everywhere above Stevens tier. Highest-leverage: arXiv paper + open-source release before Dec 2026. Two framings from one artifact: (a) Hoe's vocabulary — input-dependent stream processing on FPGAs with market data as workload; (b) Florescu's vocabulary — hardware-latency-realistic extension of exchange simulation (SHIFT-compatible).
2. Outreach mechanics: Stevens — relationship-driven, talk to Florescu/Yang BEFORE applying, Provost Fellowship box by March 1. NYU — ECE PhD application, email Tandon-ECE-Grad-Admissions@nyu.edu, name FRE mentors. MIT — no cold email; name Alizadeh in application. CMU — no pre-contact channel; 2-3 faculty in SOP; Sriraman does not answer prospective-student email.
3. Verified active grants relevant to Fall 2027 start: Yang/CRAFT to 12/2027 ($1.03M); Touzi to 08/2027 ($299K); Zhang to 08/2028 ($117K); Alizadeh to 07/2028 ($720K); Sanchez to 09/2027 ($2.25M); Sriraman CAREER to 02/2029 ($583K); Sherry to 09/2026 (expiring); Hoe none; Feinstein none; Florescu none federal. No professor here holds an NSF award ending after 2029.
4. Manual-check flags: Hoe's MangoBoost status; Touzi Scholar-position posting; Tourin post-2023 output; Aboussalah funding; Tandon ECE funding norms; Stevens FE PhD placement destinations.
