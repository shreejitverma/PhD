# Phase 4 — Outreach Drafts (Fall 2027 cycle, US programs)

Written 2026-08-16 from the Phase 3 briefs. Every claim about a professor's work traces to a brief in `../phase3/`.
These are SKELETONS. Rewrite in your own voice before sending (see the rewrite checklist at the bottom).
Channel rules from Phase 2 are binding: **do NOT email Golrezaei or Alizadeh** (both explicitly say name-in-application instead); Sriraman does not answer prospective-student email.

Prerequisites before ANY send:
1. The arXiv preprint of the thesis must exist — every email leans on it implicitly, and "CV attached" is far stronger when the CV's first line links a paper.
2. Per-professor mandatory reads flagged in Phase 3 (Hoe: the paywalled FPGA 2026 paper; Leung: the SSRN 0DTE paper; all: the "one paper").
3. Verify figure/section numbers against the paper version current at send time (Mastrolia "Figure 6", Moallemi "Section 5" — preprints get revised).

---

## COLD EMAILS

### 1. Thibaut Mastrolia (Berkeley IEOR) — send first, week of Sept 7

Subject: **Queue-reactive testbed for your closing-auction market-making RL**

Dear Professor Mastrolia,

I am a quantitative developer: I built a sub-10-microsecond FPGA market-making system with a custom limit order book for my MS thesis, and worked on BNP Paribas's automated market-making desk.

I read "Learning Market Making with Closing Auctions" with Julius Graf. Assumption 1 gives the agent execution priority to abstract from queue-position dynamics and latency competition — the two effects I have spent the last several years measuring in production. I would like to know how much of the continuous-phase policy survives when fills are queue-reactive: I can build a message-level LOB environment with measured latency distributions and re-run the DQN/SAC agents against it.

I am also curious whether scoring only realized clearing PnL — the fictive reward zeroed at evaluation — preserves the RL edge over the Avellaneda-Stoikov benchmark, since Figure 6 attributes most of it to auction participation.

I am applying to Berkeley IEOR for Fall 2027 and will name you in the application. Are you planning to take a student that cycle?

CV attached.

Shreejit Verma

*(~170 words. His own paper names the gap; the email only points at it.)*

### 2. Ciamac Moallemi (Columbia CBS DRO) — week of Sept 7 (different school than #1, OK same week)

Subject: **Endogenizing T in your latency-auctions model — measured cost curves**

Dear Professor Moallemi,

I build low-latency trading systems: a sub-10-microsecond FPGA market-making pipeline for my MS thesis, and hot-path work on BNP Paribas's automated market-making desk.

In "Latency Advantages in Common-Value Auctions," the timing advantage T is exogenous, and the timing-pressure result gives the marginal value of extending it. In practice T is a convex-cost investment: I have measured what each marginal microsecond costs in hardware, and the curve is steeply convex. Setting your theta formula against an empirical cost curve would pin down equilibrium investment in timing — a quantitative, on-chain version of the Budish-Cramton-Shim arms race. Is that an extension you would want pursued?

The same infrastructure supports a microsecond-scale re-estimation of the latency cost in your 2013 Operations Research paper, with queue dynamics replacing the idealized execution.

I am applying to the CBS DRO doctoral program for Fall 2027. Are you expecting to take a student in that cycle?

CV attached.

Shreejit Verma

*(~160 words.)*

### 3. Agostino Capponi (Columbia IEOR) — week of Sept 14 (NOT the same week as Moallemi: same university, and the no-two-in-one-department rule extends sensibly to overlapping Columbia networks)

Subject: **A rebate term in your blockchain-viability condition**

Dear Professor Capponi,

I am a C++ quantitative developer: I built a sub-10-microsecond FPGA market-making system with a custom limit order book for my MS thesis, and worked on automated market making for BNP Paribas's Prime Credit desk.

In "The Viability of Blockchain Markets under Discrete Clearing and Paid Priority," viability fails when informed losses exceed noise-trader fee revenue, and your conclusion points to within-block organization as the design lever. Since priority-fee revenue currently leaves the trading ecosystem: if a protocol rebated part of PGA revenue to the liquidity supplier, as several MEV-redistribution designs propose, would that relax the viability condition at long block times — or does the participation-cutoff channel survive any rebate, because it operates through selection rather than the supplier's budget?

I can contribute the continuous-market counterfactual from the inside, plus empirical pipelines for the Timeboost latency-race line.

I am applying to Columbia IEOR for Fall 2027. Are you taking students that cycle?

CV attached.

Shreejit Verma

*(~165 words.)*

### 4. Markus Pelger (Stanford MS&E) — week of Sept 14

Subject: **Queue-dependent costs in Attention Factors**

Dear Professor Pelger,

I am a C++ quantitative developer: my MS thesis was a sub-10-microsecond FPGA market-making system with a custom limit order book, and I worked on BNP Paribas's automated market-making desk.

In Attention Factors you move transaction costs inside the estimation objective, but the cost stays linear in turnover. DLSA showed roughly half the Sharpe survives a one-week holding period, so slower signals are within the model's reach. Do you have a decomposition of how much of the net-Sharpe improvement from one-step estimation comes from factors rotating toward lower-turnover signals versus better mispricing identification — and does it survive a concave (square-root impact) or queue-dependent cost, where the gradient to the factor layer changes sign for small trades? Measuring alpha decay against actual time-to-fill rather than close-to-close is what my infrastructure does.

I am applying to Stanford MS&E for Fall 2027, ranking Quantitative Finance first. Will you be taking students that cycle?

CV attached.

Shreejit Verma

*(~160 words. Giesecke is handled in the Stanford SOP, not a separate email — they co-advise; one well-aimed email to the pair's active thread is enough.)*

### 5. Bartolomeo Stellato (Princeton ORFE) — week of Sept 21

Subject: **Fixed-point arithmetic in your MILP verification of first-order methods**

Dear Professor Stellato,

I build hard-real-time decision systems: a sub-10-microsecond FPGA trading pipeline for my MS thesis (hand RTL, hardware timestamping), and constraint-programming optimization in industry.

In "Exact Verification of First-Order Methods via Mixed-Integer Linear Programming," iterations are encoded in exact real arithmetic. On an FPGA target the iterates live in fixed-point, so each step is the nominal operator plus a bounded quantization perturbation. Since the encoding already handles piecewise-affine steps via big-M, could the verification absorb a per-step bounded-error term — worst case over both the parameter set and the quantization ball — to certify iteration counts for fixed-point implementations directly? Or does the added dimensionality break the bound tightening that gets you from K of 15 to 60?

A fixed-K unrolled solver on FPGA would turn your residual certificate into a deterministic worst-case latency in clock cycles — the direction RSQP pointed, carried through verification.

Per your group page, I am applying to ORFE for Fall 2027 and will name you. Are you planning to take a student then?

CV attached.

Shreejit Verma

*(~175 words. His page says apply-and-name; this email is optional but defensible since it asks a technical question, not for a favor.)*

### 6. Tim Leung (UW CFRM) — week of Sept 21 — THIS IS THE WEAK-FUNDING VARIANT

Phase 2 rated Leung's funding outlook MIXED (no active federal grants, thin UW-era intake). The ask is therefore about the group's outlook, without putting him on the spot, leaving the door open for a different year.

Subject: **Timestamp alignment in your 0DTE joint-LOB Hawkes estimates**

Dear Professor Leung,

I am a quantitative developer specializing in market-data infrastructure: hardware-timestamped capture, custom limit order books (sub-10-microsecond FPGA market-making system, MS thesis), and automated market making at BNP Paribas.

In your paper with Jiwon Jung on 0DTE options and underlying markets using joint limit order book data, the cross-excitation kernels at the shortest lags depend on relative timestamp alignment between the options and ETF feeds — direct-feed and SIP timestamps differ by milliseconds, the same scale as the fastest cross-market responses. Did the short-lag kernels change qualitatively when you varied the alignment assumption? I have watched feed-latency skew masquerade as lead-lag structure, and building nanosecond-coherent joint capture for this line is something I could do.

I am considering the UW Applied Mathematics PhD for Fall 2027. Is the joint-LOB line one you expect your group to be growing in the next couple of years — whether that means 2027 or later?

CV attached.

Shreejit Verma

*(~165 words. The last question invites an honest signal about capacity without demanding a commitment.)*

### 7. James C. Hoe (CMU ECE) — week of Sept 28 — CONDITIONAL: only after reading the full FPGA 2026 paper

Subject: **Feed handlers as input-dependent streaming: tail-latency objectives for FaaS**

Dear Professor Hoe,

I built a sub-10-microsecond FPGA market-data and market-making pipeline for my MS thesis — feed parsing and order-book maintenance in RTL with kernel-bypass I/O — and worked on BNP Paribas's automated market-making systems.

Your FPGA 2026 paper with Shashank Obla tunes input-dependent streaming pipelines against trace-driven queueing simulation to a throughput target. Trading feed handlers are the same workload shape with the spec inverted: a tail-latency bound (p99.9 under burst) with self-exciting, regime-switching arrivals, where the trace slice that matters — an open, a volatility spike — is a tiny fraction of wall-clock time. Does the queueing abstraction admit percentile-latency objectives, and how sensitive was the string-matching configuration to which portion of the trace it was tuned on? I have production-grade workloads and traces from this class and could bring them as benchmarks.

I am applying to CMU ECE for Fall 2027 and will name you in my statement. Are you taking students that cycle?

CV attached.

Shreejit Verma

*(~160 words. HOLD until the paywalled paper is read — if it already treats latency percentiles, the question collapses and must be replaced.)*

---

## WARM RE-ENGAGEMENT (Stevens — existing relationships; the no-meeting-request rule is deliberately relaxed here)

### 8. Ionut Florescu — early September, before any cold email goes out

Subject: **Intraday arbitrage in Mandate without Managers — and a SHIFT latency tier**

Dear Professor Florescu,

Since the thesis I have completed the BNP Paribas automated market-making co-op and am finishing Georgia Tech's OMSCS (December). I am planning to apply to the FE PhD for Fall 2027 and wanted to reconnect on research first.

I read Mandate without Managers. You restrict arbitrage to once daily at the close, and flag that realized LVR net of fees lands near the incumbent's expense ratio. Under intraday arbitrageurs with realistic latency and inventory, LVR accrual should rise with arbitrage frequency while the daily tracking-error autocorrelation distortion washes out — do you expect the dominating gamma ranges to widen or collapse? That is testable in simulation: a SHIFT extension coupling a G3M pool to the LOB with latency-heterogeneous arbitrageurs, which is squarely what I build. It would also give the frequent-batch-auction line its latency-dispersion answer.

Could we find time to talk about whether this fits the lab's plans, and what a funded path would look like?

Best,
Shreejit

*(~165 words. The funding conversation is explicitly on the table — correct for a warm contact at a school with selective funding.)*

### 9. Steve Yang — mid September, after Florescu has replied

Subject: **Timestamp alignment in your jump-contagion estimates, and a CRAFT question**

Dear Professor Yang,

Since graduating in May I completed the BNP Paribas automated market-making co-op; I am applying to the Stevens FE PhD for Fall 2027.

In the jump-contagion paper with Pirjol, Zhang, and Li, the cross-excitation between VIX jumps and Bitcoin jumps rests on cross-venue timestamp alignment — crypto trades around the clock on venues with inconsistent clocks, while VIX exists only in equity hours. At what resolution does the cross-effect stay identifiable, and how sensitive was the FOMO asymmetry to alignment? Hardware timestamping is my specialty, and mis-timestamping asymmetrically biases Hawkes causality.

Separately: I am sketching an evaluation-infrastructure proposal for CRAFT — a market simulator with realistic execution, latency, and stress dynamics for benchmarking LLM- and RL-based trading agents, extending SHIFT. Is that a theme the IAB could support, and is a Phase 2 renewal in motion beyond December 2027?

Happy to come by the lab.

Best,
Shreejit

*(~155 words. The renewal question is the one that decides whether CRAFT RA money is real for him.)*

### 10. Zachary Feinstein — late September, ideally after a Florescu conversation

Subject: **LVR versus expense ratio in Mandate without Managers**

Dear Professor Feinstein,

I am a Stevens MSFE alum (May 2026 — the FPGA market-making thesis in the Hanlon orbit), since then through the BNP Paribas automated market-making co-op, and applying to the FE PhD for Fall 2027.

In Mandate without Managers, arbitrage is frictionless and once daily, and you flag for future study that realized LVR net of fees lands at the order of the incumbent's expense ratio. In The Price of Liquidity, LVR is exactly the implied fee stream. Is the expense-ratio coincidence something you expect to be provable — competitive arbitrage under a gamma-fee G3M endogenously pricing mandate enforcement at the competitive cost of fund administration — or does it break once arbitrageurs face latency and inventory frictions? If it needs the frictional case, that is a simulation problem, and it is the kind I build: a CFMM pool coupled to an LOB venue with latency-heterogeneous arbitrageurs.

I would value your view on whether this direction fits the PhD program.

Best,
Shreejit

*(~165 words. Note: at BNP "automated market making" meant quote-driven LOB dealing, not CFMMs — if he asks, name the distinction unprompted; the Phase 3 brief calls this the credibility test.)*

---

## STATEMENT-OF-OBJECTIVES PARAGRAPHS (for professors who must NOT be emailed)

### Golrezaei — for the MIT ORC Statement of Objectives (the application REQUIRES naming faculty)

"At BNP Paribas I ran automated quoting in a dealer market — operationally the bandit-feedback version of the budgeted pay-as-bid bidding Professor Golrezaei studies: price ladders across size tiers, wins and losses against competing dealers whose quotes are never observed, funding costs, balance-sheet limits. Her AISTATS 2026 paper with Sourav Sahoo assumes a monotonically depleting budget; the dealer version has a replenishable inventory that enters the objective through risk rather than feasibility, and loss feedback is censored — a one-sided bound on the best competing quote — which challenges the complete cross-learning construction. I want to work with Professor Golrezaei on extensions of this kind, and on the empirical validation against real auction data that her paper names as an open direction, where my systems background lets me build what the theory needs tested."

### Giesecke — one paragraph inside the Stanford SOP (alongside the Pelger paragraph)

"Professor Giesecke's Set-Sequence model buys linear scaling in the cross-section through mean pooling, which implicitly treats units as exchangeable — while his concurrent work with Tu develops conformal prediction precisely for non-exchangeable panels. That tension, between computational scaling and dependence structure, is the kind of systems-statistics tradeoff I want to work on, and the lab's builder culture — exact simulation, code, patents — is where a production C++/CUDA background contributes from day one."

### Alizadeh — one sentence option for an MIT EECS application (only if that application is kept)

Name him per his instruction; frame the feed-handler workload as a stress case for learned network-performance models (m3/Concorde line). Phase 2 rated this application marginal — cut it unless the application budget is loose.

---

## WHAT TO PERSONALLY REWRITE BEFORE SENDING (the machine-written tells)

1. **The identical opener.** Every cold email starts "I am a C++ quantitative developer: I built a sub-10-microsecond FPGA..." — vary the first clause per email or the pattern shows if any two recipients compare notes (Capponi and Moallemi are one floor apart institutionally; Mastrolia and Capponi co-move in the same community).
2. **The closing formula.** "I am applying to X for Fall 2027. Are you taking students that cycle? CV attached." is the same in seven emails. Keep the substance, break the rhythm.
3. **The question density.** Each email carries a two-clause technical question. In your voice, one clause can go. Read each aloud; anywhere you would not say it to a person's face in one breath, split or cut it.
4. **"is what my infrastructure does" / "is the kind I build"** — this construction appears in four drafts. Keep it in at most ONE email (recommend Mastrolia, where the fit is strongest); everywhere else replace with something plainer.
5. **Add the one thing no model can write:** a single sentence of why-PhD-now in your own words. Every one of these professors will silently ask why someone with a bank seat and an FPGA system wants five years at a stipend. One honest sentence — in your voice, not mine — beats anything drafted here.
6. **Verify live before each send:** the named figure/section numbers; that the target paper has not been updated on arXiv; that the professor has not posted new work (a 2-minute Scholar check — referencing a superseded version is worse than no reference).
7. **Attachment discipline:** one CV, one page if possible, thesis/arXiv link in the header. No transcripts, no thesis PDF unless asked.
