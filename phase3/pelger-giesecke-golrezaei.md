# Phase 3 Research Briefs — Pelger (Stanford), Giesecke (Stanford), Golrezaei (MIT)

Research date: 2026-08-16.

---

# BRIEF 1: MARKUS PELGER (Stanford MS&E)

**Verified status (https://mpelger.people.stanford.edu/):** Associate Professor, MS&E; Chambers Faculty Scholar; Director of Stanford's Advanced Financial Technology Laboratory; Associate Professor of Finance (by courtesy), GSB; NBER Research Associate. Note: Giesecke's page simultaneously lists Giesecke as "Founder and Director" of the same lab; exact directorship arrangement UNKNOWN — do not assert either is sole director.

**Phase 2 corrections:** "Missing Financial Data" is RFS **2025**, 38(3), 803-882 (not 2024). "Deep Learning in Asset Pricing" is Management Science **2024**, 70(2), 714-750 (not 2023). "Deep Learning Statistical Arbitrage" is now **Management Science, accepted**. "Shrinking the Term Structure" is Review of Finance, accepted.

## 1. Current research line

The econometrics of large financial panels, pushed toward ML and increasingly toward trading. Three connected strands.

First, latent factor models for high-dimensional return panels: conditional factor structures when the cross-section is large, characteristics drive loadings, and data are dirty. "Forest Through the Trees: Building Cross-Sections of Stock Returns" (Journal of Finance, 2025, 80(5), 2447-2506) uses decision trees to build interpretable test-asset portfolios spanning the SDF; "Target PCA: Transfer Learning Large Dimensional Panel Data" (Journal of Econometrics, 2024, 244(2), 105521) and "Missing Financial Data" (RFS, 2025) handle transfer learning and systematic missingness — over 70% of firms have missing fundamentals, and imputation choices materially move risk-premia estimates.

Second, deep learning with economic structure: "Deep Learning in Asset Pricing" (Management Science, 2024) imposes the no-arbitrage moment condition as the training criterion with an adversarial choice of test assets — economic constraints rescue estimation in low signal-to-noise data.

Third, most relevant: the statistical arbitrage line. "Deep Learning Statistical Arbitrage" (Management Science, accepted; arXiv:2106.04028) and successor "Attention Factors for Statistical Arbitrage" (ICAIF 25; arXiv:2510.11616, https://arxiv.org/abs/2510.11616), which jointly learns arbitrage factors and the trading policy to maximize performance net of transaction costs — net Sharpe 2.3 on the 500 largest US equities, 1998-2021. The frontier is explicitly frictions: turnover-aware estimation, cost-adjusted objectives. Adjacent WIP moves into microstructure proper: "The Microstructure of Cryptocurrency Markets: Men vs. Machine" (with G. Zanotti — Work in Progress, **no public draft exists** — do not claim to have read it) and "Do Algorithmic Traders Lead to Market Instability? A Multi-Agent Reinforcement Learning Approach" (with Y. Fan and X. Yu; Fan's first position: Cubist). Verified student placements: Two Sigma, Hudson River Trading, Citadel, Cubist, BlackRock.

## 2. The one paper to read

**"Deep Learning Statistical Arbitrage"** (with J. Guijarro-Ordonez and G. Zanotti), **Management Science, accepted**. arXiv: https://arxiv.org/abs/2106.04028; SSRN 3862004. Full text read at https://ar5iv.labs.arxiv.org/html/2106.04028. (Chosen over the crypto-microstructure paper — no retrievable draft — and over the JoF factor paper, because stat-arb-with-frictions is where the candidate's execution expertise bites. Read Attention Factors, arXiv:2510.11616, immediately after.)

- **Core question:** how much statistical arbitrage opportunity exists, decomposed into three design choices: similar-asset portfolio formation, signal extraction from residuals, and mapping signals to allocations.
- **Method:** arbitrage portfolios are residuals of conditional latent factor models (Fama-French, PCA, IPCA with 46 characteristics); signals via CNN+Transformer over a 30-day residual lookback; allocations from a feedforward net trained end-to-end to maximize Sharpe with L1=1 leverage constraint; rolling 1,000-day estimation.
- **Main result:** ~550 largest US stocks, OOS 2002-2016, annual Sharpe ~4.2 gross (IPCA-5 residuals), roughly 2-4x all benchmarks; signal extraction matters far more than factor-model choice once ≥5 factors; profitable after 5-10bp round-trip costs and short fees.
- **Author-named limitations/open threads:** universe restricted to largest ~550 stocks explicitly "to avoid trading and market friction issues"; daily-close trading with no intraday execution model; ~1-week signal persistence ("around half of the Sharpe ratio can persist for a holding period of one week", Section III); flat per-trade bp costs (Section III.J), not impact- or queue-dependent. In Attention Factors the cost model is still linear (5bps × L1 turnover + 1bp short-fee), no market impact or latency; its conclusion flags the slow 8-year rolling window's adaptation during COVID.

## 3. The honest connection

Genuine, but be precise. Pelger's stat-arb line has reached the point where the binding research question is frictions: the entire delta from DLSA to Attention Factors is moving transaction costs inside the estimation objective. Yet the cost model remains linear bp on turnover — no market impact, no queue position, no fill uncertainty, no latency. The candidate's sub-10μs LOB/FPGA system and BNP AMM experience is exactly the machinery to answer "what do these net Sharpe numbers become under realistic execution?": queue-aware fill simulation, participation-scaled impact, alpha decay against actual time-to-fill rather than close-to-close. That is a real, articulable contribution to something they currently idealize away. The MARL market-instability project and the crypto-microstructure WIP show the group moving toward market dynamics where a high-fidelity exchange/LOB simulator is a credible research instrument.

Strict caveat: Pelger is fundamentally an econometrician. His methodological papers require exactly what the candidate lacks — research-level econometric and probability theory. The connection runs through the applied stat-arb/microstructure strand, not the theory strand; present accordingly and expect to close the econometrics gap in coursework.

## 4. One substantive question

"In Attention Factors you move transaction costs inside the estimation objective, but the cost is linear — 5bps times L1 turnover. In DLSA you showed about half the Sharpe survives a one-week holding period, so the model has slower signals available to it. Do you have a decomposition of how much of the 84% net-Sharpe improvement from one-step estimation comes from the factors rotating toward lower-turnover signals versus genuinely better mispricing identification — and does that decomposition survive if the cost function becomes concave in trade size (square-root impact) or queue-dependent, where the gradient signal to the factor layer changes sign for small trades?"

## 5. Gaps to close before contact

1. **Attention Factors for Statistical Arbitrage** (arXiv:2510.11616) — read in full; the current version of the agenda.
2. **IPCA**: Kelly, Pruitt, Su's instrumented PCA — DLSA's best residuals come from IPCA; be able to say what a conditional latent factor model is and why loadings-as-functions-of-characteristics matters.
3. **Deep Learning in Asset Pricing** (Management Science 2024; SSRN 3350138) — the no-arbitrage-as-loss-function idea; also skim "Forest Through the Trees" enough to explain why test-asset construction matters.

---

# BRIEF 2: KAY GIESECKE (Stanford MS&E)

**Verified status (https://giesecke.people.stanford.edu/):** Professor, MS&E; Founder and Director, Advanced Financial Technologies Laboratory; Director of the Mathematical and Computational Finance Program; ICME member. Founded Infima Technologies 2020 (CEO, then Chief Scientist "upon his return to Stanford"; as Chairman led it through 2024 acquisition). Former Editor of Management Science, Finance Area, 2018-2025. Stated areas verbatim: "risk management, market surveillance, fair lending, and sustainable investing." Currently co-advises two students with Pelger (Adam Rebei, Jason Pan).

## 1. Current research line

Giesecke built his reputation on the stochastics of correlated default: self-exciting point processes, exact simulation of jump-diffusions, large-portfolio asymptotics (JFE, Mathematical Finance, OR, AAP, 2004-2019). That machinery remains in the pipeline ("Unbiased Simulation Estimators for Multivariate Jump-Diffusions," "Asymptotically Optimal Importance Sampling for Event Timing," both with Shkolnik).

The current center of gravity is ML methodology for financial prediction with statistical guarantees, plus data infrastructure. Four live threads: (a) **"AICO: Feature Significance Tests for Supervised Learning"** (Horel, Jirachotkulthorn) — **PNAS, forthcoming** (arXiv:2506.23396) — exact finite-sample p-values for feature importance in any trained model, no retraining, no distributional assumptions; continues "Significance Tests for Neural Networks" (JMLR 2020). The interpretability/trust agenda underlying fair-lending and model validation. (b) **"A Set-Sequence Model for Time Series"** (Epstein, Sadhwani; arXiv:2505.11243, ICLR 2025 Workshop on Financial AI) — learned cross-sectional dynamics for large panels: equity portfolios and mortgage risk. (c) **"Online Conformal Prediction for Non-Exchangeable Panel Data"** (Tu, arXiv:2605.17705) — distribution-free uncertainty quantification with dependent panel units. (d) **"The Stanford EDGAR Filings Dataset"** (arXiv:2606.18192) + "Don't Discard, Repair" — LLM-scale pretraining corpora from corporate disclosures. Plus mortgage/fixed-income empirics carried from Infima ("Learning Illiquid Asset Prices" with Duan and Fan — both Pelger-lineage; "Specified Pool Pay-Ups"; climate-mortgage papers).

**On market surveillance (Phase 2 flag):** it is in his bio but there is **no recent surveillance paper** on his publications page. Closest artifacts: "Explainable clustering and application to wealth management compliance" (ICAIF 2020) and the AICO interpretability line. Historical microstructure adjacency: "Dynamic Portfolio Execution" (Management Science 65(5), 2019, with Tsoukalas and Wang); Tsoukalas's 2012 thesis was "Stochastic Models of Limit Order Books." Treat surveillance as an interest area, not an active paper trail. Do not build the pitch on it.

## 2. The one paper to read

**"A Set-Sequence Model for Time Series"** (Epstein, Sadhwani, Giesecke), arXiv:2505.11243, **Workshop on Financial AI at ICLR 2025**. https://arxiv.org/abs/2505.11243 (full text read at https://arxiv.org/html/2505.11243v2).

- **Core question:** learn cross-sectional dependence in large panels of correlated units (loans, stocks) without hand-designed aggregate features, at cost that scales to tens of thousands of units.
- **Method:** permutation-invariant set module computes a low-dimensional cross-sectional summary each period (mean-pooled embeddings: F_t = ρ((1/M)Σφ(X^i))), concatenated to each unit's features, fed to any sequence backbone (Transformer, S4, LongConv). Complexity Θ(TMd), linear in M, vs Θ(T[M²d+Md²]) for cross-unit attention; variable unit counts at inference.
- **Main results:** synthetic contagion — learned summaries correlate 0.951 with the true latent factor; equity portfolio (CRSP daily, top-500, 79 characteristics, 5bp+1bp costs) — Sharpe 4.82, beating S4 (3.94), LongConv (3.64), and the DLSA-style CNN-Transformer by 42% on 2002-2016; mortgage risk (5M loan-months) — beats Sadhwani et al. on 22 of 25 transitions, AUC 0.683 vs 0.669.
- **Author-named limitation:** the Section 8 conclusion names no formal limitations — itself worth knowing. Honest threads in the body/appendix: mean pooling implicitly assumes exchangeable units; the appendix's "Gated Selection" layer for stronger cross-unit dependence costs quadratic time. Notably his own Tu paper is titled around **non-exchangeable** panel data — the tension between the pooling assumption and non-exchangeable reality is a live thread across his own current papers.

## 3. The honest connection

Moderate, and it runs through engineering rather than trading latency. Strict: nothing in Giesecke's current pipeline needs sub-10μs latency, and the surveillance angle has no active paper to attach to. Genuine overlaps: (a) his lab's identity is computational — exact simulation, importance sampling, large-scale ML systems, LLM-scale data pipelines — and a candidate who writes production C++/CUDA and has built real data-plane infrastructure fits the builder profile in a way most MFE applicants do not; (b) the Set-Sequence equity application inherits the DLSA-style idealization (daily close trading, flat 5bp costs), so the realistic-execution critique applies verbatim, and Epstein bridges both groups (coauthor on Attention Factors); (c) Giesecke co-advises with Pelger right now — a joint-advising pitch is realistic; (d) BNP credit market-making gives dealer-market intuition relevant to "Learning Illiquid Asset Prices." Missing for the stochastics half: measure-theoretic probability and point-process theory at research depth — say it plainly if asked; closable with Stanford coursework.

## 4. One substantive question

"The Set-Sequence model gets linear scaling from mean pooling, which treats the cross-section as exchangeable, and the appendix's Gated Selection alternative buys stronger dependence back at quadratic cost. Your separate work with Tu is precisely about panels that are non-exchangeable. For a panel where dependence is structured but sparse — say dealer-market assets that share funding or collateral links — is there a middle ground you have considered, like pooling within learned clusters, that keeps near-linear cost, and would the conformal wrapper from the Tu paper still give valid coverage on top of a Set-Sequence point predictor?"

## 5. Gaps to close before contact

1. **AICO** (arXiv:2506.23396, PNAS forthcoming) — state the null hypothesis it tests and why finite-sample validity without retraining matters; his current flagship.
2. **"Deep Learning for Mortgage Risk"** (Sirignano, Sadhwani, Giesecke — Journal of Financial Econometrics 19(2), 313-368, 2021) — ancestor of Set-Sequence's mortgage application and the bridge to the Infima story.
3. **Point-process basics**: "Affine Point Processes and Portfolio Credit Risk" (SIAM J. Financial Mathematics, 1, 642-665, 2010) — the lab's stochastic heritage; Hawkes processes are also the standard model for order-flow clustering, the candidate's home turf.

---

# BRIEF 3: NEGIN GOLREZAEI (MIT Sloan / ORC)

**Purpose: this brief prepares (a) the Statement of Objectives paragraph for the MIT ORC application and (b) a post-admission conversation. NOT a cold email.** Her homepage (https://www.mit.edu/~golrezae/): apply directly to the ORC and include her name in application materials; she invites candidates to "reach out to me directly" **after MIT admission**. Title verified: Theresa Seley Associate Professor of Management Science, MIT Sloan; ORC and MIT-IBM Watson AI Lab affiliated.

**Phase 2 corrections:** "Learning to bid in discriminatory auctions with budget constraints" is **AISTATS 2026, accepted for a Spotlight presentation**. "Online Resource Allocation with Convex-set Machine-Learned Advice" is **Operations Research, Minor Revision** — do not cite as "OR 2026." Confirmed: "Optimal Contest beyond Convexity," STOC 2026; "Nash equilibria in uniform price auctions: Theory, computation," ACM SIGMETRICS 2026.

## 1. Current research line

Online decision-making and mechanism design for digital marketplaces: how agents should learn to act in repeated strategic environments (auctions, pricing, resource allocation), and how platforms should design mechanisms knowing agents learn. Technical signature: adversarial online learning with structure — regret bounds exploiting combinatorial action spaces, resource constraints via primal-dual methods, information structures (bandit feedback, cross-learning) taken seriously.

Hottest strand: **learning to bid in multi-unit auctions**, with student Sourav Sahoo: "Learning in Repeated Multi-Unit Pay-As-Bid Auctions" (with Galgana, M&SOM, forthcoming); "Learning Safe Strategies for Value Maximizing Buyers in Uniform Price Auctions" (Sahoo, ICML 2025; Management Science Major Revision; INFORMS Jeff McGill Student Paper Award First Place 2025); SIGMETRICS 2026 Nash-equilibria paper; the AISTATS 2026 Spotlight below. Motivating markets: treasury auctions and electricity markets — repeated, multi-unit, discretized bids, budget-constrained bidders. Parallel strand: **autobidding and constrained buyers** in online advertising ("Multi-channel Autobidding with Budget and ROI Constraints," Management Science forthcoming; "Auction Design for ROI-Constrained Buyers," WWW 2021; "Contextual Bandits with Cross-learning," MOR 2023 — the methodological seed of the cross-learning idea). Third strand: **algorithms with ML advice and fairness** (OR Minor Revisions; IJCAI 2024 Distinguished Paper; STOC 2026 contest paper). Her students prove theorems; empirical systems work is not the product, though market realism motivates the models.

## 2. The one paper to read

**"Learning to Bid in Discriminatory Auctions with Budget Constraints"** (Golrezaei, Sahoo), **AISTATS 2026, Spotlight**; arXiv:2606.29252, https://arxiv.org/abs/2606.29252 (full text read at https://arxiv.org/html/2606.29252v1).

- **Core question:** how should a single budget-constrained bidder with cost-of-capital preferences bid repeatedly in multi-unit pay-as-bid auctions against adversarial competing bids, under full-information or bandit feedback?
- **Method:** valuations arrive i.i.d. as contexts; bids on an ε-grid, non-increasing, no-overbidding. Key structural result (Theorem 3.1): the offline optimal no-overbidding strategy is a shortest path in a polynomial-size DAG (nodes = (unit index, bid level, cumulative bid), O(M²/ε³) edges). Online: exponential-weights over paths gives O(M^{3/2}√(T log 1/ε)) full-information regret; under bandit feedback with known context distribution, "complete cross-learning" — the affine utility structure lets one observed outcome yield unbiased counterfactual estimates for all contexts — preserves √T regret independent of context count; unknown distribution degrades to T^{2/3}. Budgets: coupled primal-dual (dual price λ_t via online gradient descent on spend) achieves ρ-approximate sublinear regret, ρ = B/(TM). Lower bound Ω(M√T).
- **Main result:** polynomial-time algorithms with sublinear, context-count-independent regret in all feedback regimes, plus the primal-dual extension for hard budgets.
- **Author-named open threads (Section 6):** closing the T^{2/3} vs √T gap when the context distribution is unknown; moving beyond purely adversarial competing bids; extending to uniform-price and other formats; empirical validation on real auction data.

## 3. The honest connection — how far does "market maker as budgeted bidder" hold?

Partly; know exactly where it breaks. **Where it holds:** (a) BNP work was automated market making in Prime **Credit** — a dealer/RFQ market. RFQ quoting is structurally close: submit a price ladder (non-increasing bid vector across size tiers ≈ her bid vector across units), win or lose against competing dealers whose quotes you never observe — precisely her **bandit feedback** setting; competing dealer quotes plausibly adversarial; tick sizes = her ε-grid; funding cost = her cost-of-capital α; balance-sheet limits map loosely to budgets. A genuinely strong SOP framing: he has operated the system her model abstracts. (b) Treasury auctions — her headline application — are the primary market for instruments he market-made at BNP and BofA FICC.

**Where it breaks — be able to say this:** (a) her budget depletes monotonically; dealer inventory is a replenishable stock entering utility through risk (variance/adverse selection), not just feasibility — the primal-dual analysis leans on monotone spend; (b) her rounds are payoff-independent given the budget, with i.i.d. contexts; a market maker's state (inventory, fair value) is persistent and autocorrelated, and today's fills change tomorrow's optimal quotes through adverse selection; (c) a lit LOB is a continuous double auction with time priority and queue position — none of that exists in a sealed-bid repeated auction; the FPGA/latency work is about winning the queue, which her model has no analog for. So: the sub-10μs system does **not** give her something she lacks for her theory — her open thread is "empirical validation on real auction data," and his contribution would be as the rare student who can both prove regret bounds (after coursework) and build the empirical/simulation side of exactly that validation, plus bring the RFQ-censored-feedback problem as a new model variant. State it that way. Remaining honest gap: her work needs proof skills in online learning; ORC coursework is the credible path; the SOP should acknowledge the trajectory.

## 4. One substantive question (post-admission conversation)

"In the budgeted setting your primal-dual algorithm gets ρ-approximate regret with a dual price on cumulative spend, which works because the budget only ever depletes. In dealer markets — the RFQ version of your bandit setting, where I ran automated quoting — the constrained resource is inventory: it is consumed and replenished, and it enters the objective through risk rather than feasibility. Is there a version of the primal-dual analysis that tolerates a replenishable resource, or does the ρ-approximate benchmark fundamentally rely on monotone depletion — and if the latter, is the right move a different benchmark rather than a different algorithm?"

Secondary: whether complete cross-learning survives **censored** feedback — in RFQ you learn a one-sided bound on the best competing quote on losses — since the affine-utility trick needs exact counterfactual reconstruction.

## 5. Gaps to close before the SOP / conversation

1. **"Learning Safe Strategies for Value Maximizing Buyers in Uniform Price Auctions"** (ICML 2025) — why uniform-price and pay-as-bid demand different techniques; "extension across formats" is her own named open thread.
2. **Bandits-with-knapsacks / primal-dual online learning**: Badanidiyuru-Kleinberg-Slivkins; Balseiro-Gur's dual mirror descent for repeated auctions with budgets; "Contextual Bandits with Cross-learning" (MOR 48(3), 2023).
3. **Adversarial online learning fundamentals**: exponential weights / EXP3 and combinatorial bandits over paths — sketch why regret is √T in full information and what breaks under bandit feedback. The single highest-leverage preparation before writing the SOP paragraph.

---

## Cross-cutting notes

- **Pelger-Giesecke are one ecosystem**: same AFT Lab, two co-advised students, shared student lineage (Epstein coauthors with both). Treat as a joint target; the realistic-execution/frictions angle serves both.
- **The crypto-microstructure paper is not readable** — Work in Progress with no public draft. Do not claim to have read it; he may say he noticed it is in progress and ask about it.
- **Verified placements (Pelger students page)**: Two Sigma, HRT, Citadel, Cubist, BlackRock — safe to reference.
- SSRN blocks direct fetches; SSRN IDs extracted from Pelger's own site HTML.
