# Phase 3 Research Briefs — Mastrolia (Berkeley), Leung (UW), Moallemi (Columbia CBS)

Research date: 2026-08-16. SSRN hard-blocks automated access (HTTP 403), limiting one item (Leung's 0DTE paper conclusion).

---

## 1. THIBAUT MASTROLIA (Berkeley IEOR)

### 1.1 Current research line

Mastrolia's stated foundation is "backward stochastic differential equations, high-frequency trading and market design with model and volatility uncertainty, principal-agent problems, mean-field games, Hawkes processes and dynamic cyber-risk management" (https://mastrolia.ieor.berkeley.edu). Around 2024-2025 his market-microstructure work was mechanism design in the classical stochastic-control idiom: "Clearing time randomization and transaction fees for auction market design" (accepted Quantitative Finance, arXiv http://arxiv.org/abs/2405.09764), "Optimal Rebate Design: Incentives, Competition and Efficiency in Auction Markets" (http://arxiv.org/abs/2501.12591), and "Regulation or Competition: Major-Minor Optimal Liquidation across Dark and Lit Pools" (http://arxiv.org/abs/2509.03916) — how exchanges should set clearing rules, fees, and rebates, via HJB/mean-field/major-minor formulations.

The 2026 preprints show a deliberate turn toward learning-based numerics for the same problems. "Signature Methods for Optimal Market Making" (Gennaro, Mastrolia, Primavera, arXiv June 2026, https://arxiv.org/abs/2606.19772) linearizes a mean-variance market-making problem via path signatures into a pseudo-linear optimization over the expected signature of an augmented market path, proposing Sig-REINFORCE for bid/ask quotes, tested under Poisson and self-exciting Hawkes arrivals against a PPO baseline. "Learning Market Making with Closing Auctions" (below) does deep RL over a full session ending in a closing auction. "Deep ZakaiJ" and "Approximation of Singular-Stopping Control Driven by Hawkes Processes via Rescaled MDPs" continue the pattern: problems he would previously attack with BSDEs/HJB, now built as structured deep-learning or MDP approximations with provable scaffolding.

Through-line for the candidate: Mastrolia now needs simulators and learning environments that respect real market mechanisms (continuous LOB + auctions, Hawkes flow), and his papers currently generate that environment from stylized generative models.

### 1.2 The one paper to read

**"Learning Market Making with Closing Auctions"** — Julius Graf and Thibaut Mastrolia, arXiv:2601.17247 (submitted Jan 24, 2026; v2 July 30, 2026). No venue listed. https://arxiv.org/abs/2601.17247

- **Core question**: How should a market maker quote across a session combining a continuous LOB phase and a closing auction, replacing the artificial terminal inventory penalty with explicit modeling of auction liquidity.
- **Method** (full PDF read): finite MDP with two phases. Continuous phase: agent sells down inventory via a limit order (tick level k_t, volume v_t) against Poisson market-taker arrivals on an emulated CLOB. Auction phase: agent submits a supply schedule (slope K_t, price S_t), may cancel at a cost; receives a "fictive" reward K_t·H_t(H_t − S_t) against the anticipated clearing price H_t — interpreted as "a rebate proposed by the exchange for shaping the clearing price" (cites SGX, Cboe RM Integrated Book, Xetra clearing-time randomization). Wrong-side dealing and terminal inventory penalized. Agents: DQN + DDPG/TD3/SAC on a continuous relaxation. Benchmarks: Avellaneda-Stoikov (Guéant-Lehalle-Fernandez-Tapia closed form) and TWAP. Environments: rough Heston mid-price and historical S&P 500 data.
- **Main result**: all RL methods beat both benchmarks on mean returns in both settings. The reward decomposition (Figure 6) shows the RL edge comes "nearly all... from the fictive reward, as the benchmarks do not/barely post an order during the auction." Cancellations concentrate near clearing time.
- **Author-named limitations (verbatim)**: Assumption 1: "The agent is always executed with priority at a fixed depth of the CLOB... assumed to be the fastest participant at that level," justified as: "To abstract from queue-position dynamics and latency competition, we adopted the favorable execution convention that the 'market maker' has execution priority with respect to other participants." And: "Developing a theoretical benchmark for optimal market making on a closing auction is left for future work" (stated twice).

### 1.3 The honest connection

Strong, and unusually precise. **The paper assumes away exactly what the candidate has built.** Assumption 1 (execution priority, fastest participant, no queue-position dynamics, no latency competition) is the load-bearing idealization of the continuous phase, and the authors say so in those words. The candidate's message-level LOB with real queue dynamics, measured tick-to-trade latency, and hardware timestamps can turn Assumption 1 into an experimental variable: retrain the same DQN/SAC agents in a queue-reactive, latency-constrained fill model and measure how much of the continuous-phase policy and PnL survives. Secondary: their historical S&P evaluation replays data with no market reaction to the agent's orders; a queue-reactive simulator (Huang-Lehalle-Rosenbaum style) is the standard remedy, and building a fast one is a systems problem. Caveat to state honestly: the paper's headline finding is about the auction phase, where latency matters less; the candidate's contribution targets the continuous phase and the realism of the training environment, not the auction theory.

### 1.4 One substantive question

"Figure 6 shows the RL agents' edge over Avellaneda-Stoikov and TWAP comes almost entirely from the fictive auction reward, and you note the benchmarks barely post in the auction. Two-part: (a) if you score only realized clearing PnL — fictive reward zeroed at evaluation — how much outperformance remains? (b) Have you tried extending the AS benchmark with even a naive auction-participation rule, so the comparison isolates learning quality rather than auction access?"

(Backup, infrastructure-flavored: "How sensitive is the learned continuous-phase policy to Assumption 1? I can provide a message-level queue-reactive fill model with measured latency distributions if you want to test it.")

### 1.5 Gaps to close before contact

1. Guéant, Lehalle, Fernandez-Tapia, "Dealing with the inventory risk" — the exact source of their AS benchmark closed form.
2. Huang, Lehalle, Rosenbaum, "Simulating and analyzing order book data: The queue-reactive model" (JASA 2015) — the standard framework for the simulator he would propose; speak its language, not just "my FPGA LOB."
3. Mastrolia's "Clearing time randomization and transaction fees for auction market design" (http://arxiv.org/abs/2405.09764) — the fictive-reward-as-rebate design is downstream of this; reading it shows he understands the agenda.

---

## 2. TIM LEUNG (UW Applied Math, CFRM director)

### 2.1 Current research line

Leung runs a broad applied-stochastics portfolio (research page: https://sites.google.com/site/timleungresearch/research). Stated areas include "Statistical methods for noisy high-frequency data" and "Modeling intraday trading activities" alongside regimes, multiscale signal processing/ML, ETFs, trading strategies, commodities, crypto, ESOs, optimal stopping/control. Three strands: (1) classical derivatives/control — "Short-Rate-Dependent Volatility Models" with Lorig (arXiv https://arxiv.org/abs/2602.00858, 2026), "A Coupled Optimal Stopping Approach to Pairs Trading over a Finite Horizon" (Computational Economics 2025), CTMC interest-rate derivatives, books "Stochastic Control Approach to Futures Trading" (World Scientific — his site lists 2024) and "Multiscale Financial Data Analytics and Machine Learning" (World Scientific, 2025). (2) High-frequency statistics — "A Noisy Fractional Brownian Motion Model for Multiscale Correlation Analysis of High-Frequency Data" (Mathematics, 2024, w. Zhao); "Multiscale Volatility Analysis for Noisy High-Frequency Prices" (Risks, 2023). (3) Newest: event-level microstructure with PhD student Jiwon Jung — the 2026 SSRN paper below takes this to joint options-and-underlying LOB data with multivariate Hawkes — the closest his group has come to the candidate's world.

Honest note: Leung is a stochastic-control and statistics person; nothing retrieved suggests he builds or needs low-latency systems. The fit is through data and point-process estimation, not control of fast trading.

### 2.2 The one paper to read

**"Modeling the Interactions Between Zero-Day Options and Underlying Markets Using Joint Limit Order Book Data"** — J. Jung, T. Leung, SSRN working paper, 2026. https://papers.ssrn.com/sol3/papers.cfm?abstract_id=7097018 (ID located via Google Scholar).

- **Core question**: quantify intraday cross-market interactions between 0DTE options and their underlying ETFs at the event level.
- **Method** (abstract; SSRN full text 403-blocked): joint LOB data as event streams; joint LOB model with multivariate Hawkes processes estimating event intensities across the two markets.
- **Main findings**: "statistically significant cross-market excitation and strong same-market clustering, with interactions that are asymmetric and highly time-varying over the trading day"; shifts around macro announcements; identifies microstructure-level drivers.
- **Author-named limitations**: UNKNOWN — conclusion unretrievable (SSRN 403). READ THE FULL PAPER MANUALLY BEFORE CONTACT — the one brief where the limitation section is unverified.

### 2.3 The honest connection

Moderate, and on the data/estimation side, not his core stochastic-control agenda. The genuine link: multivariate Hawkes cross-excitation at short lags is notoriously sensitive to timestamp quality and cross-feed clock alignment. Options events (OPRA) and ETF LOB events arrive through different feeds with different, time-varying latencies; misalignment at the scale of the fastest cross-market responses manufactures spurious "excitation" or masks real causality. The candidate has built hardware-timestamped, feed-handler-level capture — he understands exactly where event-time error enters the data this paper depends on, and could produce nanosecond-coherent joint capture for this line. Be honest about the asymmetry: it strengthens their measurement, it does not intersect Leung's pricing/optimal-stopping work, and the candidate lacks the point-process econometrics that is the paper's methodology. Frame: "I can tell you where your event timestamps lie, and I want to learn the estimation theory."

### 2.4 One substantive question

"In the joint-LOB Hawkes framework, the cross-excitation kernels at the shortest lags are only as good as the relative timestamp alignment between the options feed and the ETF feed — direct feeds versus SIP timestamps can differ by milliseconds, the same scale as the fastest cross-market responses you are trying to measure. What timestamp source did you use for each leg, and did the estimated cross-market kernels change qualitatively at short lags when you varied the alignment assumption? I ask because I have built hardware-timestamped capture and have seen feed-latency skew masquerade as lead-lag structure."

### 2.5 Gaps to close before contact

1. **Read the actual 0DTE paper** — download from SSRN manually. Non-negotiable.
2. Bacry, Mastromatteo, Muzy, "Hawkes processes in finance" (Market Microstructure and Liquidity, 2015) — Hawkes estimation basics (MLE, kernel nonparametrics, branching ratio).
3. Leung-Zhao "A Noisy Fractional Brownian Motion Model for Multiscale Correlation Analysis of High-Frequency Data" (Mathematics, 2024) — connect the 0DTE paper to his "noisy high-frequency data" area; see the program, not one paper.

---

## 3. CIAMAC MOALLEMI (Columbia Business School, DRO)

### 3.1 Current research line

Moallemi's publications page (https://moallemi.com/ciamac/research-interests.php) shows a program dominated by the economics and design of decentralized markets, run through the Briger Family Digital Finance Lab, with a persistent secondary line in RL/ML systems. The DeFi core descends from "Automated market making and loss-versus-rebalancing" (Milionis, Moallemi, Roughgarden, Zhang; initial Aug 2022, revised May 2024; https://arxiv.org/abs/2208.06046) — the "Black-Scholes formula for AMMs," identifying LVR as the running cost LPs pay to arbitrageurs trading against stale AMM prices. Follow-ups: "Automated market making and arbitrage profits in the presence of fees" (FC 2024); "A Myersonian framework for optimal liquidity provision in automated market makers" (ITCS 2024); "am-AMM: An auction-managed automated market maker" (FC 2025); "Uniform-loss automated market making for prediction markets" (accepted AFT 2026, http://arxiv.org/abs/2607.17428). 2026: "Quantifying sub-optimality in routing for automated market makers" (Xi, Moallemi; DeFi@FC 2026; https://arxiv.org/abs/2607.20762) — 2.98M WETH-USDC swaps, 2.02bp average routing loss (~$24M), heavy-tailed, sandwich attacks a significant driver; "Risk-based auto-deleveraging" (accepted ACM EC 2026); layer-2 transaction pricing (FC 2025). Critically: latency economics runs through both eras — the canonical "The Cost of Latency in High-Frequency Trading" (Moallemi and Saglam, Operations Research 61(5), 1070-1086, 2013; PDF https://moallemi.com/ciamac/papers/latency-2009.pdf) derived closed-form latency cost and estimated it on NYSE data 1995-2005; "Latency Advantages in Common-Value Auctions" (below) revives the theme for on-chain auctions. The ML systems line — "Tail-optimized caching for LLM inference" (NeurIPS 2025), liar's poker self-play RL (2025), "OS-Pruner" (2026) — means the candidate's ML/systems depth is legible to him.

### 3.2 The one paper to read

**"Latency Advantages in Common-Value Auctions"** — Ciamac C. Moallemi, Mallesh M. Pai, Dan Robinson. Accepted to FC 2026; arXiv v1 April 2025, v2 May 2026. https://arxiv.org/abs/2504.02077 (PDF read in full via https://moallemi.com/ciamac/papers/latency-auctions-2025.pdf).

**Why this one**: the routing paper is empirical DeFi measurement — thin connection. The 2013 OR paper is the deepest thematic match but 13 years old; leading with it signals he hasn't read the current agenda. This paper is both current and the direct heir of the latency-cost line, bridging to where the lab now works.

- **Core question**: What is the economic value of a latency advantage — "the ability to make decisions later than others, even without the ability to see what others have done" — in a common-value auction with a reserve price, and what does that imply for on-chain auction design?
- **Method**: two bidders; the last mover observes the realized common value (the asset price at his later bid time), the early mover does not; neither sees the other's bid (footnote: if they did, "the auction degenerates due to an extreme lemons problem"). Equilibrium: early mover mixes; last mover bids max of a conditional-expectation bid and the reserve; zero reserve recovers Engelbrecht-Wiggans et al. (1983). Last mover's profit = a portfolio of options; under GBM with no reserve it is a Margrabe exchange option, giving closed-form profit and its time-derivative — the "theta" of the timing advantage.
- **Main results**: the auction does not degenerate — the seller retains value. With L = 0 the game is constant-sum between seller and last mover: as timing advantage T grows, last mover's payoff grows at the seller's expense. Last mover's timing pressure exceeds a monopolist's call-option theta, converging as the reserve approaches the current price. Application: on-chain auctions (DEX order routing, AMM arbitrage-right auctions per LVR, oracle extractable value), where "incentives to increase timing advantages can put pressure on the decentralization of the system" — connecting to timing games in proof-of-stake.
- **Author-named limitations**: no formal conclusion section (FC format) — verified by full-text extraction. Framing sentence states the open field: "the economics and comparative statics of latency advantages remain unexplored." In-text flagged assumptions: bidders do not observe each other's bids; risk-neutral, zero rate, GBM; the uncertain-timing extension assumes no reserve (L = 0).

### 3.3 The honest connection

Real, with a caveat up front. The candidate built the machine whose value this literature prices: his sub-10μs tick-to-trade path is a purchased latency advantage, and he has hardware-timestamped measurements of what each marginal microsecond costs and buys. Two precise offers: (a) the 2013 OR model's empirical section calibrates latency cost on 1995-2005 NYSE data at human-to-millisecond scales; a modern re-estimation at microsecond scale, with realistic queue dynamics from a message-level LOB, is a well-posed project the candidate is unusually equipped to run. (b) In the FC 2026 paper, T is exogenous; in real markets it is an endogenous, convex-cost investment, and the candidate has actual cost-of-latency curves — the missing empirical input to any arms-race extension. Caveat: Moallemi's current domain is blockchain, where "latency" means bid timing in slot auctions, not FPGA engineering; connect via the economics (which transfers), don't oversell hardware relevance to on-chain settings. Genuine and mid-strength: strongest of the three on shared subject matter, but he would be joining a DeFi-centric agenda, not an HFT-infrastructure one.

### 3.4 One substantive question

"In Section 5 you quantify the last mover's timing pressure — the theta of extending T — and show it exceeds the monopolist's call-option theta. That gives the marginal value of latency advantage, but T is exogenous. Have you considered endogenizing it with a convex cost of acquiring latency advantage, so equilibrium investment in timing is pinned down by your theta formula against the cost curve — effectively a quantitative version of the Budish-Cramton-Shim arms race for on-chain auctions? I ask because I have measured such cost curves in traditional markets, and the marginal cost per microsecond is steeply convex, which your comparative statics would bite on."

### 3.5 Gaps to close before contact

1. "Automated market making and loss-versus-rebalancing" (https://arxiv.org/abs/2208.06046) — the intellectual center of the current lab; be able to state what LVR is and why it is option-theoretic.
2. Moallemi and Saglam, "The Cost of Latency in High-Frequency Trading" (OR 61(5), 2013) — read fully; his strongest connection runs through it and Moallemi will expect it cold.
3. Budish, Cramton, Shim, "The High-Frequency Trading Arms Race" (QJE 2015) — cited in the paper's opening; the substantive question assumes familiarity.

---

## Cross-cutting notes

- **Best structural fit**: Mastrolia. His 2026 papers need exactly what the candidate has (realistic LOB/latency environments for RL market making), and the authors name the gap themselves (Assumption 1). Missing BSDE/measure-theoretic depth — flag honestly as coursework to be done.
- **Best subject-matter overlap**: Moallemi (latency economics + market making + ML), but the lab's center of gravity is DeFi; decide whether he wants that before contact.
- **Thinnest**: Leung — real but narrow (event-data quality for Hawkes estimation), orthogonal to most of Leung's portfolio; the only brief with an unverified conclusion section (SSRN blocked).
- **Data discrepancies vs Phase 2**: Leung's futures-trading book listed as 2024 on his own page (seed said 2025). Mastrolia closing-auctions paper shows no venue on arXiv.
