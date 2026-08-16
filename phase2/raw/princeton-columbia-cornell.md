# PHASE 2 FACULTY MAPPING — Princeton ORFE / Columbia IEOR (+CBS DRO) / Cornell ORIE

Data collected 2026-08-16. Titles verbatim from arXiv API, Google Scholar, DBLP, publisher CVs, or faculty pages fetched this session. NSF data from api.nsf.gov this session.

## SESSION-LEVEL STATUS ALERTS
1. **Emma Hubert HAS LEFT PRINCETON.** Since September 2025 she is Maitresse de Conferences at CEREMADE, Université Paris Dauphine-PSL; Princeton ORFE appointment was 2021-2025 [VERIFIED — https://sites.google.com/view/emmahubert]. Do not name her in a Princeton application.
2. **Sasha Stoikov is NOT Cornell ORIE graduate field faculty** — Senior Research Associate only, absent from the Graduate Field Faculty directory; Cornell PhD special committees are composed of graduate field faculty [VERIFIED — https://www.duffield.cornell.edu/orie/field-faculty-directory + gradschool.cornell.edu committee rules]. He cannot chair or formally sit on committees. Recent output has drifted to music recommendation.
3. **Bartolomeo Stellato (Princeton ORFE)** — sweep discovery; arguably the single best technical match in all three departments (real-time embedded optimization, OSQP author, NSF CAREER through 2028, explicit recruiting statement).
4. **Wenpin Tang (Columbia IEOR)** — sweep discovery with the strongest funding trajectory found anywhere (NSF CAREER 2026-2031 + second grant to 2029).

---

# (A) PRINCETON ORFE PhD

## A1. Bartolomeo Stellato — FIT 5
IDENTITY: Assistant Professor, ORFE. Personal site https://stella.to/, group https://stella.to/group/ [VERIFIED — fetched]. Scholar: https://scholar.google.com/citations?user=imapg7oAAAAJ. Developer of the OSQP solver. Joined ~2021. STATUS: active, running a group with 2026 students.
RESEARCH: "Data-Driven Performance Guarantees for Classical and Learned Optimizers", Sambharya, R and Stellato, B, Journal of Machine Learning Research [VERIFIED — cited in NSF award 2239771 record]. Other 2023+ titles not retrieved verbatim — manual Scholar check flag. Current problem: making optimization solvers run reliably in real time on embedded platforms with limited compute, using ML to design and verify algorithms (learned optimizers, data-driven convergence guarantees).
OPEN PROBLEM (his NSF CAREER abstract, verbatim): "ensuring real-time algorithm convergence on embedded platforms with limited computational resources (e.g., embedded microcontrollers)... We will develop data-driven tools to design and numerically verify real-time optimization algorithms, with tight convergence guarantees" [VERIFIED — NSF 2239771].
FIT: direct hit on the FPGA thesis and sub-10μs mindset — his agenda is literally optimization under hard real-time and hardware constraints, and the candidate has shipped that. Also connects CP-SAT/convex-opt and CVXPY/OSQP-adjacent tooling. Year-one: build/benchmark an FPGA/embedded code-generation backend or hardware-aware first-order solver variant with verified worst-case iteration bounds; or extend learned-optimizer benchmarks to latency-constrained financial control. MISSING: group is not finance-facing (energy, robotics, aerospace) — reframe market making as real-time decision systems; his papers need real/convex analysis beyond MFE level. FIT 5 — the systems asset is scarce in his applicant pool and his stated problems need it.
FUNDING: NSF CAREER 2239771 "Learning for Real-Time Embedded Optimization", $500,000, 03/21/2023 → 05/31/2028, ACTIVE [VERIFIED]. RECRUITING VERBATIM: "apply to ORFE or ORFE-affiliated PhD program at Princeton if you would like to work with me" [VERIFIED — https://stella.to/group/]. Group: 1 postdoc, 4 PhD students (2 co-advised with Ahmadi). PLACEMENTS: Irina Wang (PhD '26) → incoming Assistant Professor MIT Sloan 2027; Rajiv Sambharya (PhD '24) → Assistant Professor Texas A&M ISE; Vinit Ranjan (PhD '26) → postdoc MIT Sloan; postdoc Aras Selvi → UCL faculty [VERIFIED — group page]. OUTLOOK: STRONG SIGNAL.

## A2. Ronnie Sircar — FIT 3
IDENTITY: Eugene Higgins Professor of ORFE; currently CHAIR of ORFE [VERIFIED — search snippets]. Site sircar.princeton.edu (403 to bots). At Princeton since ~2000. STATUS: active, chairing.
RESEARCH — VERBATIM (arXiv API):
- "Trading Electrons: Predicting DART Spread Spikes in ISO Electricity Markets" — Emma Hubert, Dimitrios Lolas, Ronnie Sircar, 2026, http://arxiv.org/abs/2601.05085
- "Optimal Trading under Instantaneous and Persistent Price Impact, Predictable Returns and Multiscale Stochastic Volatility" — Patrick Chan, Ronnie Sircar, Iosif Zimbidis, 2025, http://arxiv.org/abs/2507.17162
- "A Mean Field Game for Capacity Expansion Modeling" — Hubert, Lolas, Sircar, 2025, http://arxiv.org/abs/2507.10604
- "Fare Game: A Mean Field Model of Stochastic Intensity Control in Dynamic Ticket Pricing" — Aydin, Parmaksiz, Sircar, 2025, http://arxiv.org/abs/2506.13088
- "Mean Field Games of Control and Cryptocurrency Mining" — Garcia, Sircar, Soner, 2025, http://arxiv.org/abs/2504.15526
Current: MFGs and stochastic control in energy markets, price impact and optimal trading under multiscale stochastic volatility, crypto mining games.
FIT: price-impact/optimal-trading line (2507.17162) is the touchpoint; candidate's LOB/execution infrastructure gives empirical grounding for impact-model calibration. Year-one: data/backtest infrastructure for electricity-market or impact papers. MISSING: asymptotic analysis, viscosity solutions, MFGs — measure-theoretic depth; ORFE generals risk. FIT 3.
FUNDING: co-PI-style on 2307736 (the Hubert award, $260K, ends 06/30/2026 — and Hubert left); prior awards ended 2016-2021. No active post-2026 award under his name [VERIFIED — API]. OUTLOOK: MIXED (departmental funding; chair duties).

## A3. H. Mete Soner — FIT 2
Norman John Sollenberger Professor; at Princeton since 2019 (ETH 2009-2019). Late-career flag — a 2027 entrant needs him active to ~2033; no retirement statement found. Active (2025 arXiv; NSF to 2027).
RESEARCH — VERBATIM: "Relative arbitrage problem under eigenvalue lower bounds" (Lai, Shkolnikov, Soner, 2025, http://arxiv.org/abs/2512.17702); "Iterative Schemes for Markov Perfect Equilibria" (Höfer, Laurière, Soner, Yan, 2025, http://arxiv.org/abs/2507.20898); "Markov Perfect Equilibria in Discrete Finite-Player and Mean-Field Games" (2025, http://arxiv.org/abs/2507.04540); "Learning algorithms for mean field optimal control" (Soner, Teichmann, Yan, 2025, http://arxiv.org/abs/2503.17869).
FIT: "Learning algorithms for mean field optimal control" is the only realistic entry (CUDA/PyTorch solver engineering). Everything else assumes measure-theoretic probability + functional analysis — bluntest gap. FIT 2.
FUNDING: NSF 2406762 "Mean Field Optimal Control", $320,000, 07/01/2024 → 06/30/2027 [VERIFIED]. OUTLOOK: MIXED.

## A4. Ludovic Tangpi — FIT 2
Associate Professor; Director of Graduate Studies. NOT moved (NYU Tandon lists him only as "FRE Boot Camp Instructor" while noting he is Princeton faculty). RESEARCH: propagation of chaos, BSDEs, MFGs, Schrödinger bridges — probability proper ("Marginal flows of non-entropic weak Schrödinger bridges" 2025; "Particle system approximation of Nash equilibria in large games" with Touzi 2025, http://arxiv.org/abs/2510.19211; "Conditional McKean-Vlasov control" with Carmona, Zhang 2025). NSF CAREER 2143861, $400,000, 07/01/2022 → 06/30/2027 [VERIFIED]. FIT 2 — theorem-proving stochastic analysis; DGS role makes him a useful program-level contact.

## A5. Sweep
- Emma Hubert — DEPARTED (alert 1).
- Jianqing Fan — active NSF: 2210833 ($500K, to 06/30/2027) and 2412029 (2026-2029). FIT 2: high-dimensional statistics theory; candidate lacks econometrics research depth.
- Jason Altschuler — Assistant Professor, joined ORFE recently from UPenn; teaching ORF 309 Fall 2026 [VERIFIED — search + https://jasonaltschuler.github.io/]. NEW FACULTY FLAG. "Stepsize Hedging: an Alternative Mechanism for Accelerating Gradient Descent" (with Parrilo, 2026, http://arxiv.org/abs/2605.31386). No NSF award yet. FIT 2 — pure optimization/sampling theory; secondary mention only.
- René Carmona — EMERITUS (Senior Scholar) [VERIFIED]. Exclude.
- Mykhaylo Shkolnikov — moved to CMU (verified in the other batch).

**PRINCETON VERDICT: YES, apply, with a repositioned pitch.** Financial-math core (Sircar/Soner/Tangpi) is measure-theory-heavy; Hubert's departure thinned the applied side. The application is justified by Stellato (fit 5, funded to 2028, explicit recruiting, hires this exact skill profile) with Sircar as credible secondary and Altschuler/Fan as breadth. Princeton admits to the department, reducing single-PI risk. SOP must say something concrete about measure-theory preparation.

---

# (B) COLUMBIA IEOR PhD (+ CBS DRO, separate application)

## B1. Agostino Capponi — FIT 5
IDENTITY: Professor of IEOR; Director, Center for Digital Finance and Technologies; courtesy CBS; PECASE; 2018 NSF CAREER; JP Morgan AI Research Faculty award [VERIFIED — search snippets engineering.columbia.edu + datascience.columbia.edu]. Scholar: https://scholar.google.com/citations?user=TO0W3mUAAAAJ [VERIFIED — fetched]. STATUS: active, prolific through Aug 2026.
RESEARCH — VERBATIM (arXiv API + Scholar):
- "Multi-Credit Calibration via Elastically Stopped Lévy Processes" — Graeme Baker, Agostino Capponi, 2026, http://arxiv.org/abs/2608.10321
- "The Viability of Blockchain Markets under Discrete Clearing and Paid Priority" — Agostino Capponi, Álvaro Cartea, Fayçal Drissi, 2026, http://arxiv.org/abs/2605.17425
- "SmartEval: A Benchmark for Evaluating LLM-Generated Smart Contracts from Natural Language Specifications" — Goel, Capponi, Gliozzo, Shah, 2026, http://arxiv.org/abs/2605.09610
- "Virtual Trading in Multi-Settlement Electricity Markets" — Capponi, Iyengar, Yang, Bienstock, 2025, http://arxiv.org/abs/2508.11979
- "Price discovery on decentralized exchanges" — with R. Jia, S. Yu — The Review of Financial Studies, 2026
- "Liquidity provision on blockchain-based decentralized exchanges" — with R. Jia — The Review of Financial Studies, 2025
- "Maximal extractable value and allocative inefficiencies in public blockchains" — with R. Jia, K.Y. Wang — Journal of Financial Economics, 2025
Current: market design and microstructure of blockchain trading venues (discrete clearing, priority fees, DEX liquidity, MEV), LLM/AI-agent reliability in finance, supply-chain networks. OPEN PROBLEM (NSF 2428786 abstract): "game-theoretical algorithms for determining optimal firms' levels of investment in production capacity" + efficiency-resilience trade-offs.
FIT: best all-around Track 1 match. BNP AMM + FPGA LOB thesis speak directly to the AMM/DEX microstructure agenda (CEX LOB vs AMM comparison is live in "The Viability of Blockchain Markets..."); C++/systems depth supports blockchain data pipelines; SmartEval line can use a production engineer. Year-one: build the discrete-clearing/batch-auction market simulator with a real LOB implementation, or the empirical MEV/DEX pipeline. MISSING: no publications; RFS/JFE/MS demand economic modeling + econometrics; game theory beyond MFE. FIT 5.
FUNDING: NSF 2428786 "SupplyChainDCL...", $414,909, 09/01/2024 → 08/31/2027 [VERIFIED]; CAREER ended 2024; CDFT center = industry channel. Students: Graeme Baker, Ruizhe Jia (repeat), Steven Campbell (also with Moallemi/Nutz) [INFERRED — co-authorship]. Placements: not retrieved — manual flag. OUTLOOK: STRONG SIGNAL.
OUTREACH: no statement retrieved (pages bot-blocked). Whether IEOR app asks to name faculty: UNKNOWN — check portal.

## B2. Xunyu Zhou — FIT 3
Liu Family Professor; Director, Nie Center for Intelligent Asset Management. At Columbia since 2016 (Oxford 2007-16). Scholar: https://scholar.google.com/citations?user=wHwW0ZAAAAAJ — 21,803 citations, h-index 68. Active.
RESEARCH — VERBATIM: "Reinforcement Learning for Jump-Diffusions, With Financial Applications" (with X. Gao, L. Li — Mathematical Finance, 2026); "Learning to optimally stop diffusion processes, with financial applications" (with M. Dai, Y. Sun, Z.Q. Xu — Management Science, 2026); "Reward-directed score-based diffusion models via q-learning" (with X. Gao, J. Zha — JMLR, 2025); "ART for Diffusion Sampling: Continuous-Time Control and Actor-Critic Learning" (Huang, Tang, Zhou, 2026, http://arxiv.org/abs/2607.02137); "Dynamic mean-variance portfolio selection with no-shorting constraints and unknown investment opportunity sets" (2026, http://arxiv.org/abs/2607.16625).
Current: continuous-time RL theory (exploration, q-learning) for quant finance and diffusion generative models.
FIT: PyTorch/CUDA + trading-systems fit the empirical side; year-one: implement/stress continuous-time RL on real market data (group papers largely simulation-validated). MISSING: researcher-level stochastic calculus. FIT 3.
FUNDING: NSF: NO AWARDS [VERIFIED]. Nie Center industry money. OUTLOOK: MIXED.

## B3. Wenpin Tang — FIT 3.5 (sweep addition)
Faculty, Columbia IEOR (exact rank UNKNOWN — manual flag). Active 2026.
RESEARCH — VERBATIM: "A Continuous-Time Reinforcement Learning Framework for Fine-Tuning Discrete Diffusion Models" (Zhang, Sheng, Yao, Tang, 2026, http://arxiv.org/abs/2607.14522); "Proof of Stake economy under centralized exchanges--a mean field model" (Tang, 2026, http://arxiv.org/abs/2606.09003); "Tweedie's Formulae and Diffusion Generative Models Beyond Gaussian" (Tang, Touzi, Zhang, Zhou, 2026, http://arxiv.org/abs/2605.19391).
FIT: ML pipelines/CUDA apply to diffusion fine-tuning; PoS economics loosely connects to AMM exposure. Missing: stochastic analysis depth. FIT 3.5; funding signal exceptional.
FUNDING: NSF CAREER 2538791 "CAREER: Taming and exploiting uncertainty in complex systems: mean field games and diffusion generative models", $253,570, 05/15/2026 → 04/30/2031; PLUS 2602038 "Collaborative Research: MFAI: Stochastic Analysis of Reinforcement Learning and Generative Models", $249,884, 09/01/2026 → 08/31/2029 [VERIFIED — API]. Strongest raw funding signal in the entire mapping. CAREER-stage. OUTLOOK: STRONG SIGNAL.

## B4. Garud Iyengar — FIT 3
Professor, IEOR. Active (Aug 2026 arXiv). RESEARCH: RL theory/bandits ("Variance-Adaptive Optimal Algorithm for Reinforcement Learning with Multinomial Logit Function Approximation", 2026, http://arxiv.org/abs/2605.28364), optimization/games ("On the $O(1/T)$ Convergence of Alternating Gradient Descent-Ascent in Bilinear Games", 2025), electricity-market trading with Capponi/Bienstock. Historically co-advises with finance faculty. FIT 3 — best as named secondary/co-advisor. NSF: no active awards. OUTLOOK: UNKNOWN.

## B5. Ali Hirsa — FIT 2 (as primary advisor)
Professor of Professional Practice; Director MSFE; Director, Columbia Center for AI in Business Analytics & FinTech; also CSO ASK2.ai, Managing Partner Sauma Capital. Scholar: 2,221 citations. Active.
RESEARCH — VERBATIM (Scholar): "Generating Multivariate Financial Time Series with MSSTD-Diff..." (JFDS 8(2), 2026); "Explainable Asset Allocation" (SSRN 5384437, 2025); "Approximate risk parity with return adjustment..." (Journal of Risk, 2025); "Robust rolling regime detection (R2-RD)" (SSRN, 2024); "Predicting status of pre-and post-M&A deals" (Digital Finance 7(1), 2025). CAUTION: "PolyModel for Hedge Funds' Portfolio Construction Using Machine Learning" (arXiv 2412.11019) is NOT a Hirsa paper (Zhao, Wang, Douady) — do not cite it to him.
FIT: topically closest to ML-for-trading, but Professional Practice rank — sole-chair rights doubtful [INFERRED — manual flag]; output heavily SSRN/practitioner. FIT 2 as advisor; high value as contact/committee member. NSF: none ("Amir Hirsa" at RPI = different person, fluid dynamics).

## B6. Ciamac C. Moallemi — CBS DRO (SEPARATE APPLICATION) — FIT 5 (throughput caveat)
IDENTITY: William von Mueffling Professor of Business, DRO Division, CBS; Director, Briger Family Digital Finance Lab; at Columbia GSB since 2007 [VERIFIED — https://moallemi.com/ciamac/ + resume]. Email public: ciamac@gsb.columbia.edu. STATUS: active, very current.
RESEARCH — VERBATIM (arXiv API):
- "Quantifying Sub-Optimality in Routing for Automated Market Makers" — Weiye Xi, Ciamac C. Moallemi, 2026, http://arxiv.org/abs/2607.20762
- "Uniform-Loss Automated Market Making for Prediction Markets" — Moallemi, Dan Robinson, Brian Zhu, 2026, http://arxiv.org/abs/2607.17428
- "Volatility in Prediction Markets: A Structural Approach" — Xi, Moallemi, Pai, Wang, 2026, http://arxiv.org/abs/2607.08199
- "Risk-Based Auto-Deleveraging" — Campbell, Hey, Moallemi, Nutz, 2026, http://arxiv.org/abs/2603.15963
- "Outbidding and Outbluffing Elite Humans: Mastering Liar's Poker via Self-Play and Reinforcement Learning" — Dewey, Botyanszki, Moallemi, Zheng, 2025, http://arxiv.org/abs/2511.03724
Current: AMM design/analysis for DeFi and prediction markets (loss-vs-rebalancing, routing sub-optimality, auto-deleveraging), RL for games, LLM inference optimization. Core market-making/latency literature (canonical earlier latency-cost work).
FIT: substantively the closest match to the thesis anywhere: candidate built a market maker in hardware, worked AMM at BNP, and brings real LOB/latency engineering to AMM-vs-LOB comparisons. Year-one: empirical measurement of AMM routing sub-optimality using onchain + CEX LOB data, or hardware-realistic latency modeling in AMM/LOB hybrids. MISSING: CBS DRO economics/operations modeling sophistication. CAVEAT: CV shows one completed PhD advisee 2018-2024 (Utkarsh Patange, PhD 2024 → Verition Fund Management) [VERIFIED — CV; possibly incomplete]; current students Weiye Xi, Brian Zhu [INFERRED]. Tiny DRO cohort. Low-probability, high-value bet. FIT 5.
FUNDING: NSF only 1235023, ended 2016. CBS funds doctoral students centrally [INFERRED]; Briger Family Digital Finance Lab named funded lab [VERIFIED]. OUTLOOK: STRONG via school/lab.
OUTREACH: public email, no do-not-email statement. CBS DRO = separate application.

## B7. Paul Glasserman — FIT 3
Jack R. Anderson Professor, CBS, 2000-; courtesy IEOR 1996-. NOT emeritus; active [VERIFIED — CV Sep 2025 PDF]. RESEARCH — VERBATIM (CV): "Assessing Look-Ahead Bias in Stock Return Predictions Generated By GPT Sentiment Analysis" (with C. Lin — JFDS 6(1), 2024); "Dynamic Information Regimes in Financial Markets" (with Mamaysky, Shen — Management Science 70(9), 2024); "Linear Classifiers Under Infinite Imbalance" (with M. Li — Operations Research 73(2), 2025); "Should Bank Stress Tests Be Fair?" (Management Science 71(1), 2025); "Stress Testing Spillover Risk in Mutual Funds" (Capponi, Glasserman, Weber — Management Science 71(5), 2025).
Late-career (PhD 1988), low supervision rate — most recent advisee Mike Li, PhD 2024 → Optiver [VERIFIED — CV]. Placements historically excellent (Goldman, Two Sigma, HKUST, Northwestern). FIT 3 — CBS DRO name alongside Moallemi. NSF ended 2012.

**COLUMBIA VERDICT: YES — strongest Track-1 application of the three.** Capponi (5) anchor whose agenda actively needs the skill set; Zhou, Tang, Iyengar as credible alternates = redundancy an unpublished applicant needs. Separate CBS DRO application for Moallemi (+Glasserman) justified on fit, treated as lottery.

---

# (C) CORNELL ORIE PhD

## C1. Sasha Stoikov — FIT 2 (resolved negative)
Senior Research Associate, CFEM/Cornell Tech [VERIFIED — https://people.orie.cornell.edu/sfs33/]. NOT in Graduate Field Faculty directory → cannot chair/sit on PhD committees [VERIFIED — field-faculty directory + gradschool committee rules]. RESEARCH — VERBATIM: "Music as an Asset Class" (Stoikov, Singla, Cetin, Cendra Villalobos, 2026, http://arxiv.org/abs/2602.05007); "Picky Eaters Make For Better Raters" (2024, http://arxiv.org/abs/2401.03193); "Interface Design to Mitigate Inflation in Recommender Systems" (2023, http://arxiv.org/abs/2307.12424). Site self-describes "high-frequency trading and music recommendation algorithms" but verified recent output is music/recommenders. Avellaneda-Stoikov legacy ≠ current agenda. Value: CFEM industry projects + email relationship. FIT 2. NSF: none.

## C2. Andreea Minca — FIT 3
Professor, ORIE [VERIFIED — https://people.orie.cornell.edu/acm299/]. Active (teaching "Advanced Financial Derivatives with AI" Spring 2025).
RESEARCH — VERBATIM (publications page): "Approximations of semi-Markov processes and insurance policy valuation" (Bladt, Minca, Peralta-Gutierrez — Finance and Stochastics, 2025); "Blockchain Adoption and Optimal Reinsurance Design" (Amini, Deguest, Iyidogan, Minca — EJOR, 2024); "Clustering heterogeneous financial networks" (Chen, Minca, Qian — Mathematical Finance, 2023); working paper "Reinforcement Learning for SBM Graphon Games with Re-Sampling" (Huo, Peralta, Xie, Minca).
Current: financial/insurance networks, stablecoin/DeFi risk, graphon games with RL. A claimed 2025 NSF EAGER "Risk Methodology for Supply Chain Networks" could NOT be verified in the API — UNVERIFIED.
FIT: stablecoin/DeFi risk + RL-for-games hooks; large-scale simulation + onchain data engineering contribution. Missing: network/random-graph probability. FIT 3.
FUNDING: CAREER ended 08/31/2023; nothing active found [VERIFIED — API]. OUTLOOK: WEAK SIGNAL.

## C3. Sweep (brief)
- Jamol Pender — active queueing ("The Amplitude Dynamics of Impulsive Queues" 2026; "Queues with Rechargeable Servers" 2026); NSF 2510768 $200K to 07/31/2027. No finance in verified recent output. FIT 2.
- Gennady Samorodnitsky — heavy tails; NSF 2310974 ends 07/31/2026; late career. FIT 2.
- Sid Banerjee — market/mechanism design; CAREER ends 02/28/2026. No finance. FIT 2.
- David Goldberg — at ORIE, advising; no finance. Not profiled.
- Robert Jarrow — SC Johnson-based, very senior; manual flag only for committee.
- Victoria Averbukh — Professor of Practice, CFEM director; not a PhD advisor; MEng/CFEM industry gateway.
- Program structure: PhD concentrations are Applied Probability and Statistics, Manufacturing Systems Engineering, Mathematical Programming — financial engineering is NOT a PhD concentration [VERIFIED — phd-operations-research page].

**CORNELL VERDICT: NO for this candidate's agenda — deprioritize or drop.** Microstructure asset lands on nobody with committee rights; Minca is the only plausible chair (fit 3) with no verified active funding; no FE concentration. Application slot better spent on CBS DRO.

---

# CROSS-PROGRAM RANKING (fit × feasibility)
1. Capponi (Columbia IEOR) — 5, funded, active, agenda needs his skills
2. Stellato (Princeton ORFE) — 5, funded to 2028, explicit recruiting, non-finance framing required
3. Moallemi (CBS DRO, separate app) — 5 fit, low-throughput/lottery
4. Wenpin Tang (Columbia IEOR) — 3.5, best funding runway anywhere (to 2031)
5. Sircar 3; Zhou 3; Iyengar 3; Minca 3; Glasserman 3
6. Hirsa 2; Soner 2; Tangpi 2; Stoikov 2; Altschuler/Fan/Pender/Samorodnitsky/Banerjee 2

# UNIVERSAL GAPS (blunt)
- No publications/preprints: every profiled group's students publish on arXiv within 1-2 years; convert the thesis to a preprint BEFORE outreach.
- Measure-theoretic probability: disqualifying for Soner/Tangpi/Samorodnitsky-style groups; remediation plan helps everywhere at Princeton and for Zhou/Tang at Columbia.
- No econometrics research: rules out the Fan/empirical-finance route; do not pitch it.
- Bot-blocked this session: orfe.princeton.edu, gradschool.princeton.edu, ieor.columbia.edu, columbia.edu personal pages, cdft.engineering.columbia.edu. Whether each application asks applicants to name faculty is UNKNOWN for all three — check manually in the portals.
