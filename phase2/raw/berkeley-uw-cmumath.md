# PHASE 2 FACULTY MAPPING — Berkeley IEOR / UW AMath (CFRM) / CMU Math

Retrieved 2026-08-16.

# PROGRAM A: UC BERKELEY IEOR PhD

## A1. Thibaut Mastrolia — FIT 5 — PRIORITY DEEP DIVE

**IDENTITY**: Assistant Professor, IEOR [VERIFIED — https://ieor.berkeley.edu/people/thibaut-mastrolia/]. Personal site: https://mastrolia.ieor.berkeley.edu. Scholar: https://scholar.google.com/citations?user=Ynt7-O0AAAAJ (680 citations, h-index 14). Joined July 2021. STATUS: active, pre-tenure junior faculty — strongest structural signal in this batch.

**RESEARCH — VERBATIM (arXiv API)**
1. "Signature Methods for Optimal Market Making" — Alberto Gennaro, Thibaut Mastrolia, Francesca Primavera — arXiv 2026 — http://arxiv.org/abs/2606.19772
2. "Learning Market Making with Closing Auctions" — Julius Graf, Thibaut Mastrolia — arXiv 2026 — http://arxiv.org/abs/2601.17247
3. "Regulation or Competition:Major-Minor Optimal Liquidation across Dark and Lit Pools" — Thibaut Mastrolia, Hao Wang — arXiv 2025 — http://arxiv.org/abs/2509.03916
4. "Optimal Rebate Design: Incentives, Competition and Efficiency in Auction Markets" — Thibaut Mastrolia, Tianrui Xu — arXiv 2025 — http://arxiv.org/abs/2501.12591
5. "Clearing time randomization and transaction fees for auction market design" — Thibaut Mastrolia, Tianrui Xu — accepted at Quantitative Finance — arXiv http://arxiv.org/abs/2405.09764
Also: "Approximation of Singular-Stopping Control Driven by Hawkes Processes via Rescaled MDPs" (Agostino, Mastrolia, arXiv 2026, http://arxiv.org/abs/2602.05025); "Deep ZakaiJ: Structured Filtering for Jump-Diffusion Time Series Forecasting" (Leng, Mastrolia, Wang, arXiv 2026, http://arxiv.org/abs/2605.24548)

Current problem: optimal market making and liquidity provision under realistic market-design features — closing auctions attached to continuous LOB sessions, dark/lit pool competition, exchange fee/rebate design — via stochastic control, Hawkes processes, deep RL (DQN, actor-critic), signature methods. "Learning Market Making with Closing Auctions" abstract: "a deep reinforcement learning framework, consisting of a Deep Q-Network and its continuous-control actor-critic extensions" tested on rough Heston simulated data and S&P 500 historical data [VERIFIED — https://arxiv.org/abs/2601.17247].
Stated direction: "My research develops stochastic control, game-theoretic tools and contract theory to design resilient financial and cyber systems under risk and model uncertainty." [VERIFIED — personal site]. Sharper open-problem sentence: UNKNOWN.

**FIT**: Direct. His last 18 months is market making on LOBs with RL, validated on rough Heston simulators and daily S&P data — not live-latency queue dynamics. The candidate can build the realistic LOB/queue-position simulation and hardware-latency testbed the group's RL market-making papers currently lack. Year-one task: extend "Learning Market Making with Closing Auctions" by replacing the generative market model with a queue-reactive LOB simulator calibrated to message-level data; benchmark DQN/actor-critic policies under latency and queue-priority constraints, end-to-end C++/CUDA. Missing: no publications; no measure-theoretic BSDE/stochastic-control theory at his proof level (2BSDEs, MFGs); would enter as the empirical/computational member of a theory group.
**FIT SCORE: 5** — active market-making agenda, junior and productive, publishes with his own PhD students, candidate fills a demonstrable gap.

**FUNDING**: NSF: ZERO awards as PI [VERIFIED — API; contradicts Phase 1 assumption]. Only grant found: "France Berkeley fund 2023" with Caroline Hillairet, "Cyber risk Modeling and Insurance" [VERIFIED — professional-service page]. Group: Tianrui Xu PhD 2025 (co-advised with Steven N. Evans); active co-author students Hao Wang, Haoze Yan, Julius Graf. Junior faculty: YES. Placements: UNKNOWN (first PhD 2025). OUTLOOK: MIXED — productive with student pipeline, no NSF PI funding; Berkeley support likely fellowship/GSI-based.

## A2. Xin Guo — FIT 3
Professor and Department Chair; Coleman Fung Chair [VERIFIED — https://ieor.berkeley.edu/people/xin-guo/]. Active.
RESEARCH (verbatim from https://xinguo.ieor.berkeley.edu/publication): "Risk of transfer learning and its applications in finance" (Cao, Gu, Guo, Rosenbaum — arXiv 2311.03283, 2023); "Markov α-potential games" (arXiv 2305.12553, 2024); "Multi-agent reinforcement learning, a decentralized network approach" (Mathematics of Operations Research, 2024); "Transportation marketplace rate forecast using signature transform" (KDD 2024); "MF-OMO: an optimization framework for mean-field games" (SICON 2023). Current: mathematical foundations of RL and generative models; finance one application.
FIT: theory of learning/games, not microstructure; FPGA/LOB not differentiating. Year-one: large-scale multi-agent RL simulation infrastructure. FIT SCORE 3.
FUNDING: NSF 2602035 "Collaborative Research: MFAI: Stochastic Analysis of Reinforcement Learning and Generative Models", $250,000, 09/01/2026-08/31/2029 [VERIFIED — API; title matches her research; institution field not returned]. Chair duties reduce bandwidth [INFERRED]. OUTLOOK: STRONG on grants, MIXED on bandwidth.

## A3. Zeyu Zheng — FIT 3
Associate Professor; PhD Stanford MS&E [VERIFIED — faculty page]. Site: https://zheng80.github.io. Active.
RESEARCH (verbatim from faculty page): "A Doubly Stochastic Simulator with Applications in Arrivals Modeling and Simulation" (Operations Research, 2023); "Learning to Simulate Sequentially Generated Data via Neural Networks and Wasserstein Training" (ACM TOMACS, 2023); "Dynamic Pricing with External Information and Limited Inventory" (Management Science, 2023); "Immediacy Provision and Matchmaking" (Management Science 69(2), 2023). Simulation methodology, neural simulators, market/matching design.
FIT: neural-simulator line could use his systems skills; "Immediacy Provision and Matchmaking" touches trading design; nothing on latency. FIT SCORE 3. NSF: 0 awards [VERIFIED]. OUTLOOK: UNKNOWN.

## A4. Sweep
- Paul Grigas: Associate Professor, Head Graduate Advisor; predict-then-optimize; NSF awards expired 2021/2022. No finance. FIT 2.
- Chenyang Zhong: Assistant Professor (new, ex-Columbia Stats); optimal transport/generative modeling; no finance pubs. FIT 1.
- Svitlana Vyetrenko: LECTURER on roster [VERIFIED] — known market-simulation researcher but lecturers do not advise PhDs; environment signal only.

**PROGRAM A VERDICT**: Mastrolia (5) >> Guo (3) ~ Zheng (3) > Grigas (2) > Zhong (1). WORTH APPLYING — highest-priority of this batch. Application explicitly asks "Are there specific IEOR faculty you want to work with?" [VERIFIED — how-to-apply page]. Deadline Dec 15, 2026, 8:59 PM PT. Risk: Mastrolia has no verified federal funding; support likely fellowship/GSI.

---

# PROGRAM B: UW APPLIED MATHEMATICS PhD (CFRM)

## B1. Tim Leung — FIT 4 — PRIORITY DEEP DIVE

**IDENTITY**: Tim S.T. Leung (NSF legal name Siu-Tang Leung). Boeing Endowed Professor; Director of CFRM, Dept. of Applied Mathematics [VERIFIED — https://amath.washington.edu/people/tim-leung]. Site: https://sites.google.com/site/timleungresearch/. Scholar: https://scholar.google.com/citations?user=P40aOHIAAAAJ (1,581 citations, h-index 23). PhD Princeton ORFE 2008; JHU 2008-11; Columbia IEOR 2011-16; UW since ~2016. STATUS: active, current CFRM director.

**RESEARCH — VERBATIM (Scholar)**
1. "Short-rate-dependent volatility models" — T. Leung, M. Lorig — Annals of Finance, 2026 — arXiv http://arxiv.org/abs/2602.00858
2. "Modeling the Interactions Between Zero-Day Options and Underlying Markets Using Joint Limit Order Book Data" — J. Jung, T. Leung — SSRN, 2026 [title verbatim from Scholar; direct SSRN URL not retrieved — get link before citing in outreach]
3. "A Coupled Optimal Stopping Approach to Pairs Trading over a Finite Horizon" — Y. Kitapbayev, T. Leung — Computational Economics, 2025
4. "Interest rate derivatives in a CTMC setting: Pricing, replication and Ross recovery" — T. Leung, M. Lorig — International Journal of Financial Engineering, 2025 — arXiv http://arxiv.org/abs/2409.14193
5. Book: "Stochastic Control Approach to Futures Trading" — T. Leung, Y. Zhou — World Scientific, 2025
Current problem: optimal stopping/switching for trading strategies, regime-switching/CTMC models, and newly empirical microstructure via joint LOB data of 0DTE options and underlying. Stated active areas (verbatim from research page): "Stochastic models for market events and regimes", "Multiscale financial signal processing & machine learning", "Statistical methods for noisy high-frequency data", "Modeling intraday trading activities" [VERIFIED — https://sites.google.com/site/timleungresearch/research]

**FIT**: The 2026 Jung-Leung joint-LOB paper is the hook — he has moved into LOB datasets and intraday modeling. His group's placements are strategy/portfolio quants (AQR, Millennium, BlackRock — Columbia era); nobody shows systems-level LOB engineering. Candidate's message-level replay through a real LOB implementation with hardware timestamping gives Leung's optimal-trading models an execution-realism test rig his group lacks. Year-one: data/backtest infrastructure for the 0DTE-vs-underlying joint LOB line (KDB+/Q + C++ replay engine), quantifying queue position and latency effects. Missing: research-grade statistics; stochastic-control proofs (variational inequalities, free boundaries) above MFE level; publications.
**FIT SCORE: 4** — thematically strong, publishes constantly with students; center of mass is strategy timing, not latency/systems; 0DTE-LOB line is new and thin.

**FUNDING**: NSF: two awards, ended 2012 [VERIFIED — API "Siu Tang Leung"]. Students: 12 PhD graduates listed; UW-era only two: Yang Zhou (2021) → Parametric, Wells Fargo; Theo Zhao (2023) → Parametric, Rotella Capital, Microsoft. Columbia-era: AQR, Millennium, Barclays, BAML, Credit Suisse, KCG, BlackRock [VERIFIED — students page]. NO current students listed — intake UNKNOWN; UW throughput ~1 per 2-3 years, slower than Columbia period. FLAG.
CFRM structural fact: NO separate CFRM PhD — students enter AMath PhD, advisor determined "by the end of a student's first summer quarter" [VERIFIED — phd-program page]. 5-year departmental support. Funded like any AMath student; risk is advisor-matching after arrival, not funding class. Industry ties: CFRM Quantitative Analytics Lab (Leung-directed); "CFRM Connects" Seattle fintech events.
OUTLOOK: MIXED — endowed chair + directorship (institutional money, TA lines), zero active federal grants, thin recent PhD intake.

## B2. Matthew Lorig — FIT 3
Professor, Applied Mathematics; PhD Physics UCSB 2011; SIAG-FME Early Career Prize 2016 [VERIFIED — https://amath.washington.edu/people/matthew-lorig]. Active.
RESEARCH — VERBATIM (arXiv API): "Optimal Liquidation of Perpetual Contracts" (Donnelly, Lin, Lorig — arXiv 2026, http://arxiv.org/abs/2601.10812); "Optimal Control of the Ethena Yield-Bearing Stablecoin" (Lorig — arXiv 2026, http://arxiv.org/abs/2605.11263); "Short-Rate-Dependent Volatility Models" (arXiv 2026); "A Calculus of Variations Approach to Stochastic Control" (arXiv 2025, http://arxiv.org/abs/2509.01744); "Short-Rate Derivatives in a Higher-for-Longer Environment" (arXiv 2025, http://arxiv.org/abs/2502.21252). Derivative pricing, implied-vol asymptotics, stochastic control; recent drift toward crypto market structure.
FIT: perpetuals/optimal-liquidation and stablecoin lines touch execution; candidate could contribute crypto-exchange LOB data pipeline. More pricing/PDE than microstructure. FIT SCORE 3.
FUNDING: NSF: single $30K conference grant ended 2017. OUTLOOK: WEAK SIGNAL.

**PROGRAM B VERDICT**: Leung (4) > Lorig (3). Worth applying — solid second-priority. Two live finance faculty, 5-year AMath funding, director-level advisor moving into exactly the candidate's data regime, strong industry placement history. Negatives: advisor assignment after enrollment; Leung's UW PhD throughput low; no active federal funding — support TA-heavy.

---

# PROGRAM C: CMU MATHEMATICAL SCIENCES PhD (Mathematical Finance)

## C0. Group status and structure
- Math Finance page lists: Kramkov (MCS Professor of Mathematical Finance; Director, Center for Computational Finance), Larsson (Professor; handles "Ph. D. and Post-Doctoral Programs Inquiries", martinl@andrew.cmu.edu — CONFIRMED PhD-inquiries contact), Lehoczky (emeritus) [VERIFIED — https://www.cmu.edu/math/math-finance/index.html].
- Steven Shreve: EMERITUS confirmed. Not a target.
- NEW HIRE: Sergey Nadtochiy joined CMU as Professor in 2025 from Illinois Tech, "work at the intersection of mathematical finance, probability and partial differential equations" [VERIFIED — https://www.cmu.edu/math/news-events/articles/2025/1119_faculty-new-hire-nadtochiy.html]. Phase 1 missed him.
- Admissions: priority deadline December 20; GRE Math Subject "recommended but not required"; SOP 1-2 pages; contact math-graduate-office@andrew.cmu.edu [VERIFIED — admissions page]. Funding: "Nearly all full-time graduate students... receive some form of financial aid" [VERIFIED — financial-aid page].
- MFE-background bar: no explicit policy — UNKNOWN. [INFERRED: pure-math department; credible application needs evidence of graduate real analysis / measure-theoretic probability — a math-dept course A, GRE Math Subject score, or a letter attesting proof ability. Without at least one, likely dead on arrival.]

## C1. Martin Larsson — FIT 3
Professor; PhD Cornell ORIE; at CMU since 2019, previously ETH [VERIFIED]. Site: https://sites.google.com/view/martin-larsson. Active; designated PhD/postdoc inquiries contact.
RESEARCH — VERBATIM (personal site): "Optimal contracts for delegated order execution" (with J. Muhle-Karbe and B. Weber — Mathematical Finance, 2025); "The numeraire e-variable and reverse information projection" (with A. Ramdas and J. Ruf — Annals of Statistics 53(3), 2025); "Calibrated rank volatility stabilized models for large equity markets" (with D. Itkin — 2024); "Nonasymptotic and distribution-uniform Komlós-Major-Tusnády approximation" (with I. Waudby-Smith and A. Ramdas — 2025); "Markovian projections for functionals of Itô semimartingales with jumps" (with S. Long — Electronic Journal of Probability 31, 2024).
Current: (i) e-variables/anytime-valid inference with finance applications (active NSF grant topic); (ii) stochastic portfolio theory/semimartingale analysis; plus one 2025 microstructure-adjacent paper on delegated-execution contract design.
FIT: execution-contract paper is the only hook (principal-agent theory, not systems). BNP AMM experience gives institutional realism. Missing: measure-theoretic probability at the depth of everything he writes — largest mismatch. FIT SCORE 3.
FUNDING: NSF 2510965 "Numeraire Methods for Anytime-Valid Inference in Finance", $255,000, 08/15/2025-07/31/2028 (active); 2206062 ended 07/31/2026 [VERIFIED — API]. OUTLOOK: STRONG on grants, UNKNOWN on intake.

## C2. Sergey Nadtochiy — FIT 3 (new addition)
Professor; joined CMU 2025 (Illinois Tech 2018-2025, Michigan 2012-2018) [VERIFIED — news page]. Active; new-to-institution signal though senior rank.
RESEARCH — VERBATIM (arXiv API): "Martingales On A Euclidean Manifold With A Boundary And Reflected BSDES In Non-Convex Domains" (arXiv 2025, http://arxiv.org/abs/2512.13200); "Consistency of MLE in partially observed diffusion models on a torus" (Ekren, Nadtochiy — arXiv 2024, http://arxiv.org/abs/2412.03380); "Cascade equation for the discontinuities in the Stefan problem with surface tension" (Guo, Nadtochiy, Shkolnikov — arXiv 2024, http://arxiv.org/abs/2410.15249); "Optimal contract design via relaxation: application to the problem of brokerage fee for a client with private signal" (Alvarez, Nadtochiy — arXiv 2023, http://arxiv.org/abs/2307.07010); earlier on-point: "Optimal brokerage contracts in Almgren-Chriss model with multiple clients" (with Kevin Webster, 2022, http://arxiv.org/abs/2204.05403); "Consistency of MLE for partially observed diffusions, with application in market microstructure modeling" (2022, http://arxiv.org/abs/2201.07656).
FIT: best microstructure pedigree at CMU (2014 NSF award was "Mean-field Games for Market Microstructure and Liquidity Risk"). Execution-desk experience + LOB data engineering fit the inference-for-microstructure line. Same gap: hard analysis. FIT SCORE 3.
FUNDING: NSF 2205751 ended 08/31/2025; prior CAREER. No active PI award. New-hire startup funds [INFERRED]. OUTLOOK: MIXED.

## C3. Mykhaylo Shkolnikov — FIT 2
Professor; joined 2023 from Princeton; PhD Stanford 2012. Active. SPDE/particle systems, stochastic portfolio theory ("Universal Central Limit Theorem for non-exchangeable interacting diffusions" arXiv 2026; "Relative arbitrage problem under eigenvalue lower bounds" with Lai, Soner arXiv 2025). No microstructure, no computation the candidate would own. NSF 2108680 ended 06/30/2024; no active award. FIT SCORE 2.

## C4. Dmitry Kramkov — FIT 1
MCS Professor of Mathematical Finance; Director CCF. Active but most recent arXiv paper 2023 ("Backward martingale transport maps and equilibrium with insider" — with Mihai Sîrbu — arXiv http://arxiv.org/abs/2304.08290). NO RECENT VERIFIED WORK (2024+). Martingale optimal transport/equilibrium theory; no connection to candidate assets. NSF ended 2009. FIT SCORE 1.

**PROGRAM C VERDICT**: Larsson (3) ~ Nadtochiy (3) > Shkolnikov (2) > Kramkov (1); Shreve emeritus. MARGINAL — apply only conditionally. Nobody's agenda needs an FPGA/LOB systems builder; every plausible advisor writes measure-theoretic proofs daily. If applied: lead with concrete measure-theory preparation, name Larsson and Nadtochiy, direct inquiries to martinl@andrew.cmu.edu.

---

# CROSS-PROGRAM SUMMARY
- Fit ranking: Mastrolia 5; Leung 4; Guo 3, Zheng 3, Lorig 3, Larsson 3, Nadtochiy 3; Grigas 2, Shkolnikov 2; Kramkov 1, Zhong 1.
- Application priority: Berkeley IEOR (Dec 15, 2026) > UW AMath > CMU Math (conditional, Dec 20).
- Corrections to Phase 1: (1) No NSF awards for Mastrolia as PI. (2) CMU addition: Nadtochiy (2025 hire, microstructure-relevant). (3) Shreve emeritus confirmed. (4) No CFRM-specific PhD at UW — AMath PhD with post-arrival advisor matching.
- Caveats: Leung's 0DTE-LOB SSRN link not retrieved — get URL before outreach. Guo's 2026 NSF award matched name+topic; institution field not returned.
