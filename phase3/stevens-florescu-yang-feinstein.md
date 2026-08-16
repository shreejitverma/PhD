# Phase 3 Research Briefs — Stevens: Florescu, Yang, Feinstein

Research date: 2026-08-16. These are re-engagement briefs (alma mater, existing relationships), not cold-contact prep.

---

# BRIEF 1: IONUT FLORESCU
Research Professor; Director, Hanlon Financial Systems Lab; Director, Financial Technology and Analytics program (https://www.stevens.edu/profile/ifloresc)

## 1. CURRENT RESEARCH LINE (since ~2024)

Florescu's post-2024 output runs along three distinguishable threads, none of which is "build faster simulators" per se.

**Thread 1 - AMMs as regulated portfolio products (the live one).** "Mandate without Managers: Automated Market Makers as Verifiable Portfolio Products" (Feinstein, Florescu, O'Leary, arXiv 2608.02917, posted 2026-08-03, http://arxiv.org/abs/2608.02917) reframes geometric mean market makers (G3Ms) not as exchanges but as self-enforcing index funds. The mechanism: a fee parameter γ ∈ [0,1) charged only on the non-proportional component of reserve adjustments; Theorem 5/Corollary 6 show no-arbitrage holds iff realized weights satisfy ŵᵢ ≥ (1−γ)wᵢ, giving a verifiable compliance band with total allocation drift bounded by 2γ(1−minᵢwᵢ). Backtests against VBIAX, EQL, and EDOW (Bloomberg total-return data through mid-2026) find fee ranges where the G3M dominates the incumbent fund on both CAGR and tracking error — e.g., γ ∈ [3.22%, 7.09%] for EQL against the daily-rebalanced economic mandate. Critically, arbitrageurs are modeled as frictionless, transacting at most once per day at the close. Direct continuation of the CRAFT 2023-24 project "Decentralized Exchanges via AMMs" (PI Feinstein, Co-PI Florescu).

**Thread 2 - empirical microstructure/econometrics.** "Impact of Retail Investor Attention on Option Returns: A Nonparametric Test Approach" (Long, Lee, Florescu, Journal of Financial Econometrics, 2026); "Analysis of rare events using multidimensional liquidity measures" (Zaika, Bozdog, Florescu, IRFA Vol. 95 Part B, 2024).

**Thread 3 - RL under delays.** "Control in Stochastic Environment with Delays: A Model-based Reinforcement Learning Approach" (Yao, Florescu, Lee, ICAPS 2024, DOI 10.1609/icaps.v34i1.31529): stochastic planning for control with delayed feedback, risk preferences in policy optimization; benchmarked on Atari. The control-theoretic twin of trading under latency — the least obvious bridge to the candidate's work. Profile also lists a working paper with Frank Fabozzi: "Cut the Chit-Chat: A New Framework for the Application of Generative Language Models for Portfolio Construction".

SHIFT ("SHIFT: A Highly Realistic Financial Market Simulation Platform," arXiv:2002.11158) and its FBA study remain foundational infrastructure but show no new publications since 2023.

## 2. THE ONE PAPER TO READ

**"Mandate without Managers: Automated Market Makers as Verifiable Portfolio Products"** — Feinstein, Florescu, O'Leary; arXiv:2608.02917 [q-fin.TR], 2026-08-03; http://arxiv.org/abs/2608.02917 (full text read at https://arxiv.org/html/2608.02917v1).

- **Core question:** Can an AMM function as a verifiable portfolio product — mandate compliance enforced mechanically by arbitrage rather than by managers — and can it beat incumbent funds?
- **Method:** G3M invariant L = ∏ᵢ xᵢ^wᵢ with fee γ on non-proportional reserve adjustments; no-arbitrage weight band; simulations against VBIAX (2014-2026), EQL (2018-2026), EDOW (2024-2026) with arbitrage-only order flow once per day at close; metrics CAGR and annualized tracking error.
- **Main result:** Dominance regions exist (VBIAX monthly-TE γ ∈ [2.73%, 3.90%]; EQL γ ∈ [3.22%, 7.09%]; EDOW γ ∈ [3.32%, 9.90%] under NAV valuation vs economic mandate), from purely adversarial order flow.
- **Limitations the authors name:** comparison to legal-index funds "is, of course, not immediate"; negative autocorrelation in daily active returns overestimates daily TE; TE is non-monotonic in γ; flagged "subject to future study": realized LVR net of fees annualizes to the same order of magnitude as the incumbent fund's expense ratio.

**Why this over the FBA paper:** 13 days old, actively on his mind, shared authorship with Feinstein — one deep read serves two conversations. The FBA paper ("Insights on the Statistics and Market Behavior of Frequent Batch Auctions," Alves, Florescu, Bozdog, Mathematics 11(5):1223, 2023, DOI 10.3390/math11051223) is what his thesis infrastructure extends but reads as a closed chapter — it belongs in prep (gap 1), not as the opener. CAVEAT: MDPI blocked automated retrieval; only the abstract verified ("FBA is superior in terms of market quality measures but we also discover a potential problem in the technical implementation of FBA"). The precise implementation problem is UNKNOWN — read the full text in a browser before the meeting; it is the single most natural hook for the hardware work.

## 3. THE HONEST CONNECTION

The obvious pitch (hardware-accelerated latency-realistic tier for SHIFT) has a real but conditional fit:

- **Nothing Florescu published since 2024 needs an FPGA.** The AMM paper's arbitrage happens once per day; the econometrics papers use recorded data. "I'll make SHIFT sub-10μs" answers a question nobody in his 2024-2026 output is asking.
- **Where latency realism genuinely bites:** the Mandate paper's weakest empirical assumption is the frictionless once-daily arbitrageur. LVR — which the authors flag as the open question — is generated precisely by the race between arbitrageurs and stale AMM quotes; its magnitude depends on arbitrage frequency and latency. A simulation layer where arbitrageurs with heterogeneous realistic latencies trade between a G3M pool and an LOB venue (SHIFT with a CFMM module) turns "subject to future study" into a research program.
- **The FBA thread is the second genuine hook:** FBAs exist to neutralize the latency arms race, the 2023 paper found a technical implementation problem, and the line is dormant. "I build the latency-realistic tier that lets SHIFT answer whether FBA's advantages survive realistic latency dispersion" is a credible revival pitch — presented as extending dormant work, not current work.
- The ICAPS delays paper gives a third, quieter bridge: RL for execution under delay is mathematically the thesis problem (acting on stale state).

## 4. ONE SUBSTANTIVE QUESTION

"In Mandate without Managers you restrict arbitrage to once per day at the close, and you note both that daily tracking error is inflated by negative autocorrelation in active returns and that realized LVR net of fees lands near the incumbent's expense ratio. If arbitrageurs instead act intraday — with realistic latency and inventory constraints — LVR accrual should rise with arbitrage frequency, but the autocorrelation distortion in daily TE should wash out. Do you expect the dominating γ ranges to widen or collapse under intraday arbitrage, and is that something you'd want tested in simulation rather than closed form?"

## 5. GAPS TO CLOSE

1. Full text of the FBA paper (https://www.mdpi.com/2227-7390/11/5/1223) — specifically the technical implementation problem.
2. Budish, Cramton, Shim, "The High-Frequency Trading Arms Race: Frequent Batch Auctions as a Market Design Response" (QJE 2015) — know its latency-arms-race argument cold; it justifies the entire hardware pitch.
3. Milionis, Moallemi, Roughgarden, Zhang's LVR framework ("Automated Market Making and Loss-Versus-Rebalancing") — the Mandate paper's LVR discussion presupposes it.

---

# BRIEF 2: STEVE YANG
Associate Professor; founding Director of CRAFT (https://www.stevens.edu/profile/syang14)

## 1. CURRENT RESEARCH LINE (since ~2024)

Center of gravity has moved to LLMs-for-finance, anchored in CRAFT; the trading-behavior/high-frequency line is reduced, not dead.

**LLM/NLP thread (dominant).** "XBRL Agent: Leveraging Large Language Models for Financial Report Analysis" (ICAIF 2024); "FinLoRA: Finetuning Quantized Financial Large Language Models Using Low-Rank Adaptation" (arXiv:2412.11378, Dec 2024); "FinLoRA: Benchmarking LoRA Methods for Fine-Tuning LLMs on Financial Datasets" (arXiv:2505.19819, May 2025 — 19 financial datasets incl. four new XBRL datasets; LoRA methods average +36% over base). Both with Xiao-Yang Liu, matching CRAFT 2024-25 project "XBRL-Enhanced Foundation LLM". CRAFT 2025-26: Co-PI on "Multi-Agent AI for Accounting Estimates" (PI Arion Cheong).

**High-frequency/trading-behavior thread (alive at low volume).** "Cryptocurrency jump contagion with market sentiment events: a study of high frequency cross effect" (Yang, Pirjol, Zhang, Li, European Journal of Finance 2025, DOI 10.1080/1351847x.2025.2477696) — multivariate Hawkes on high-frequency data, VIX-jump sentiment events transmitting to Bitcoin; "Modeling Investor Sentiment Jumps Using Deep Reinforcement Learning with a Hawkes Cross-Excitation Modeling Approach" (Yu, Yang, IEEE CIFEr 2024). Verdict on the Phase 2 question: his 2015-2020 RL/trading-behavior identity survives as high-frequency jump econometrics plus RL-as-estimation-tool — NOT market making or agent-based trading. Nothing since 2024 involves order books or simulation platforms.

**CRAFT context.** CRAFT lists "market simulation and stress-testing tools" and "equitable trading platforms" among stated focus areas; 11 funded FY2025 projects — but the verified 2025-26 project list contains ZERO market-simulation or trading-latency projects (portfolio is LLM/compliance/quantum/privacy). Prudential recently added as full member.

## 2. THE ONE PAPER TO READ

**"Cryptocurrency jump contagion with market sentiment events: a study of high frequency cross effect"** — Steve Y. Yang, Dan Pirjol, Beichen Zhang, Quan Li; European Journal of Finance, 2025; DOI 10.1080/1351847x.2025.2477696 (abstract via Crossref).

- **Core question:** Do equity-market sentiment shifts (VIX jumps) transmit to cryptocurrency prices at high frequency, and with what asymmetry?
- **Method:** Multivariate Hawkes processes; cross-excitation between VIX jump events and Bitcoin price jumps.
- **Main result:** Positive sentiment triggers moderate contagion to Bitcoin; negative shows no effect. Bitcoin has stronger self-contagion than equities; "fear of missing out" pattern — positive Bitcoin jumps persist ~3x longer than negative.
- **Limitation the authors name:** UNKNOWN — paywalled; pull through Stevens library before the meeting.

**Why this over FinLoRA/XBRL:** closest to the candidate's competence, so the conversation can go deep. Still skim FinLoRA to show awareness of where Yang's effort actually goes.

## 3. THE HONEST CONNECTION

Strict: **Yang's current publications do not need a hardware-accelerated simulator, and the LLM connection is thin — do not force it.** The real conversation is the CRAFT funding channel:

- CRAFT's focus-area list includes "market simulation and stress-testing tools" and there is precedent (2023-24 Feinstein/Florescu DEX simulation project), but zero current-cycle projects touch trading/simulation — members have not been voting money at that theme. IUCRC projects live or die on member votes.
- "FPGA/kernel-bypass latency tier for SHIFT" will not carry a room of Prudential-type members. The version worth floating: "evaluation infrastructure for AI trading agents — a market simulator with realistic execution, latency, and stress dynamics, in which LLM-based and RL-based agents can be benchmarked" — ties his infrastructure to the multi-agent-AI direction CRAFT is actually funding.
- Timing risk, plainly: NSF award 2113906 runs to 12/2027; he'd arrive Fall 2027, one semester before award end. CRAFT Phase 2 renewal status is UNKNOWN — a legitimate direct question for Yang; it determines whether CRAFT RA money is real for him.
- Secondary genuine overlap: jump-contagion depends on cross-venue high-frequency timestamps (24/7 crypto vs equity-hours VIX). Hardware-timestamping background is real expertise in exactly the data-quality problem that makes or breaks Hawkes cross-excitation estimates.

## 4. ONE SUBSTANTIVE QUESTION

"In the jump contagion paper you estimate cross-excitation between VIX jump events and Bitcoin jumps, but the two series live on different clocks — crypto trades 24/7 across venues with inconsistent exchange timestamps, while VIX exists only during equity hours. At what time resolution does the cross-effect remain identifiable, and how sensitive were the FOMO-asymmetry results to timestamp alignment across venues? I ask because clock synchronization at high frequency is a problem I worked on in hardware, and mis-timestamping asymmetrically biases Hawkes causality."

## 5. GAPS TO CLOSE

1. Full text of the jump contagion paper via Stevens library — limitations and exact timestamp handling.
2. FinLoRA (https://arxiv.org/abs/2505.19819) and XBRL Agent (ICAIF 2024) — fluency about where CRAFT money goes.
3. IUCRC funding mechanics (IAB votes, CRAFT Phase 2 renewal status — UNKNOWN this session) — determines whether the simulation proposal is a funding path or a fantasy.

---

# BRIEF 3: ZACHARY FEINSTEIN
Associate Professor; Co-Director of PhD Programs (effective September 2025) (https://www.stevens.edu/profile/zfeinste)

## 1. CURRENT RESEARCH LINE (since ~2024)

Two lines: mathematical DeFi (most active) and systemic risk / vector optimization.

**DeFi/AMM line.** "The Price of Liquidity: Implied Volatility of Automated Market Maker Fees" (Bichuch, Feinstein, arXiv:2509.23222, Sept 2025) — reinterprets loss-versus-rebalancing as the implied fee stream making a risk-neutral LP indifferent to providing liquidity; constructs a fixed-for-floating fee swap to extract implied volatilities and correlations of digital assets, with empirical validation. "Liquidation Dynamics in DeFi and the Role of Transaction Fees" (Sadeghi, Feinstein, arXiv:2602.12104, Feb 2026) — optimal liquidation via dynamic programming when lending-protocol oracles read prices from CPMMs; CPMM transaction fees can make sandwich-attack/oracle-manipulation (OEV) strategies outright unprofitable — endogenous security without TWAPs. "Designing On-Chain Options: Amortizing Perpetual Options" (Bichuch, Feinstein, arXiv:2605.19146, May 2026) — perpetual-option primitive for blockchain adversarial constraints, avoiding high-frequency oracle dependence. "Mandate without Managers" (arXiv:2608.02917, Aug 2026, with Florescu, O'Leary) — see Brief 1.

**Unifying observation to internalize: all four papers use the fee parameter as the central design lever — fees as compliance enforcement (Mandate), fees as implied volatility (Price of Liquidity), fees as manipulation deterrent (Liquidation Dynamics). Feinstein's current program is, compactly, "the mathematics of what AMM fees buy you."**

**Systemic risk / optimization line.** "Dynamic clearing and contagion in financial networks" (Banerjee, Bernstein, Feinstein, EJOR 321(2):664-675, 2025); "Approximating the Set of Nash Equilibria for Convex Games" (Feinstein, Hey, Rudloff, Operations Research, 2024); "Characterizing and Computing the Set of Nash Equilibria via Vector Optimization" (OR 72(5), 2024); "Deep learning the efficient frontier of convex vector optimization problems" (JOGO 90:429-458, 2024).

CRAFT history: PI "Decentralized Exchanges via AMMs" (2023-24, Co-PI Florescu); "AI Compliance Officer" (2024-25, Co-PI Florescu); "CBDC Systemic Risk Implications" (2023-24); currently PI "Alternative Data Risk Assessment" (2025-26).

## 2. THE ONE PAPER TO READ

**"The Price of Liquidity: Implied Volatility of Automated Market Maker Fees"** — Maxim Bichuch, Zachary Feinstein; arXiv:2509.23222, 2025-09-27; http://arxiv.org/abs/2509.23222.

- **Core question:** Can AMM fee structures be inverted to extract market-implied volatility and correlation of digital assets?
- **Method:** LVR as the implied fee stream at which a risk-neutral investor is indifferent to providing liquidity; fixed-for-floating fee swap; back out implied vols/correlations; empirical validation.
- **Main result:** AMM fee dynamics link cleanly to an implied-volatility measure — a derivatives-style information channel from DEX pools.
- **Limitation the authors name:** UNKNOWN from abstract — read the full paper (open access) and extract limitations.

**Why this and not Mandate:** Mandate is the Florescu opener and bridges both; reading Price of Liquidity in addition gives the LVR machinery that Mandate's flagged open question presupposes. Fluency in both = engaging his program, not commenting on one paper.

## 3. THE HONEST CONNECTION

Demands precision — the vocabulary collision ("automated market making" at BNP vs Feinstein's AMMs) is a trap.

- **They are different objects.** BNP-style AMM = quote-driven LOB market making: inventory management, adverse selection, spread capture, latency competition (Avellaneda-Stoikov lineage). Feinstein's AMMs = constant-function market makers: passive convex invariant, no quotes, no inventory decisions; LPs earn fees and bleed LVR. Never conflate them; naming the distinction unprompted is itself credibility.
- **Where they genuinely meet:** (a) LVR is realized by arbitrageurs racing between CFMM pools and CEX order books — the arbitrageur is exactly the latency-sensitive LOB trader the candidate builds infrastructure for; LVR magnitude is a function of arbitrage frequency, block time, latency. (b) Translation dictionary: fee parameter γ ↔ half-spread; LVR ↔ adverse-selection cost of stale quotes. Speaking both languages is rarer than either alone. (c) Mandate's empirics run on frictionless once-daily arbitrage; endogenizing arbitrageur behavior with realistic latency and cross-venue execution is the natural next iteration — and the 2023-24 CRAFT DEX-simulation project shows he has wanted simulation of exactly this before.
- **What does not fit:** Feinstein is a closed-form/fixed-point/DP mathematician. He does not need FPGAs or sub-10μs anything; block times are 400ms-12s. The honest pitch: not "hardware tier" but "realistic arbitrageur microstructure" — a simulation environment coupling a CFMM pool to an LOB venue with latency-heterogeneous arbitrageurs, stress-testing the theorems against realistic execution. Candidate = empirical/computational counterpart to the theory, in a Feinstein-Florescu co-advised structure that "Mandate without Managers" proves is operating.
- As Co-Director of PhD Programs, Feinstein is also an admissions/funding gatekeeper. Both conversations happen at once; the research one must be sharp enough that the administrative one goes well.

## 4. ONE SUBSTANTIVE QUESTION

"In Mandate without Managers, arbitrage is frictionless and once-daily, and you observe — flagging it for future study — that realized LVR net of fees lands at the same order of magnitude as the incumbent fund's expense ratio in the dominating fee ranges. In The Price of Liquidity, LVR is exactly the implied fee stream. Is the expense-ratio coincidence something you expect to be provable — that competitive arbitrage under a γ-fee G3M endogenously prices mandate enforcement at the competitive cost of fund administration — or does it break once arbitrageurs face real frictions like latency and inventory? Because if it needs the frictional case, that's a simulation problem, and it's the kind I build."

## 5. GAPS TO CLOSE

1. Full text of "The Price of Liquidity" (https://arxiv.org/abs/2509.23222) — empirical validation and stated limitations.
2. Full text of "Liquidation Dynamics in DeFi and the Role of Transaction Fees" (https://arxiv.org/abs/2602.12104) — fee-deterrence result; sandwich/OEV = transaction-ordering games adjacent to latency games he understands.
3. The Milionis-Moallemi-Roughgarden-Zhang LVR paper (locate it) + one pass through "Dynamic clearing and contagion in financial networks" (EJOR 2025).

---

## SOURCE NOTES

All URLs retrieved 2026-08-16. UNKNOWN items: FBA paper's specific implementation problem (MDPI 403); EJF jump-contagion limitations (paywalled); limitations of arXiv:2509.23222 and 2605.19146 (abstracts only); CRAFT Phase 2 renewal status. Correction to Phase 2 seed: verbatim FBA title is "Insights on the Statistics and Market Behavior of Frequent Batch Auctions"; jump-contagion full title carries subtitle "a study of high frequency cross effect".
