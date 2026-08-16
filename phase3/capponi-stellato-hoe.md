# Phase 3 Research Briefs — Capponi (Columbia), Stellato (Princeton), Hoe (CMU)

Research date: 2026-08-16. ACM DL, Columbia IEOR faculty page, and USENIX page returned 403; workarounds noted inline.

---

## PROFESSOR 1: AGOSTINO CAPPONI (Columbia IEOR)

### 1. Current research line

Capponi's active line is the market design of blockchain-based trading venues, treated with the tools of theoretical market microstructure: adverse selection, price discovery, and liquidity provision under the specific frictions blockchains impose. Three published anchors (via https://scholar.google.com/citations?user=TO0W3mUAAAAJ): "Liquidity provision on blockchain-based decentralized exchanges" (with Ruizhe Jia, RFS 38(10), 3040-3085, 2025); "Maximal extractable value and allocative inefficiencies in public blockchains" (with Jia, Wang, JFE 172, art. 104132, 2025); "Price discovery on decentralized exchanges" (with Jia, Yu, RFS, 2026). Early foundation: "The Adoption of Blockchain-based Decentralized Exchanges" (arXiv:2103.08842).

The 2025-2026 frontier pushes from "how do DEXs behave" to "can blockchains be primary markets at all": "The Viability of Blockchain Markets under Discrete Clearing and Paid Priority" (arXiv:2605.17425, with Cartea and Drissi, May 2026) and "Auctioning Time to Mitigate Latency Races: Theory and Evidence from Blockchains" (arXiv:2512.10094, with Brian Zhu, Dec 2025). The latter studies Arbitrum's Timeboost time-priority auction as a natural experiment: auctioning artificial time priority redirects wasteful speed-race expenditure into auction payments; duplicate transaction submissions fall and platform revenue rises post-Timeboost relative to comparable networks. This is the latency-arms-race question from Budish-style CEX debates, with observable on-chain data.

A second stream is applied AI in finance (agentic AI for smart contracts, portfolio screening, DAO governance; arXiv:2605.24462, arXiv:2603.23300), plus classical credit ("Multi-Credit Calibration via Elastically Stopped Lévy Processes," arXiv:2608.10321). The blockchain-market-design stream is the one that touches the candidate.

### 2. The one paper to read

**"The Viability of Blockchain Markets under Discrete Clearing and Paid Priority"** — Capponi, Cartea, Drissi. arXiv, May 17, 2026. https://arxiv.org/abs/2605.17425 (full text read at https://arxiv.org/html/2605.17425). Venue beyond arXiv: UNKNOWN.

- **Core question:** Can blockchains serve as the sole venue for price formation, given discrete clearing at block time and sequential execution ordered by priority fees?
- **Method:** Three-stage game: (1) traders decide whether to acquire costly information; (2) a representative liquidity supplier sets DEX reserves; (3) M informed traders compete in priority gas auctions (PGAs) and submit orders alongside price-sensitive noise traders. The venue is an AMM with a linear price schedule; within-block execution is sequential, functioning as a batch auction with discriminatory pricing where queue position is bought.
- **Main results:** An endogenous participation cutoff: only high-valuation traders enter, the cutoff rises with competition, so "price formation is driven by an increasingly thin upper tail of the distribution" and expected prices are biased toward the upper valuation bound. Liquidity supply DECREASES with competition (reverse of traditional markets) — the supplier absorbs the full adverse-selection risk of aggregate volume in a single decision. Viability requires noise-trader fee revenue to cover informed losses (M·S_M ≤ πN/θ form). Longer block times decrease liquidity, deter entry, impair price efficiency, and beyond a critical duration cause shutdown. Conclusion thrust: "the very features that secure decentralization, most notably block time to conduct consensus and priority fees to compensate block builders, can undermine market viability"; "In general, under these design features, blockchains are not viable for price discovery."
- **Author-named open thread:** "if blockchains are to become a credible infrastructure for price discovery, protocol design must carefully address how transactions are organized and prioritized within each block" — within-block ordering mechanism design is the open problem. Model caveat: informed traders assumed to know the sign of valuations.

### 3. The honest connection — strict

Real but asymmetric; do not oversell the FPGA angle. The paper is pure equilibrium theory; a sub-10μs order book gives Capponi nothing for the RFS/JFE line per se. What the candidate genuinely has:

- **The continuous-market counterfactual, from the inside.** The paper's whole exercise is "discrete clearing + paid priority vs. continuous trading." The candidate has built the continuous side and worked AMM at BNP at ~$500M ADV. He can speak concretely about what continuous clearing actually buys (queue priority dynamics, adverse selection at microsecond horizons, cancel-replace behavior) — texture most economics PhD students lack.
- **The latency-race paper is the bridge.** arXiv:2512.10094 is theory plus empirics about exactly the arms race the thesis hardware participates in. Someone who has spent money on FPGA timestamping to win races is a credible empiricist of race behavior (duplicate-submission measurement, mempool/relay data engineering).
- **What it costs him:** joining this agenda means becoming a blockchain-markets economist. The FPGA work becomes biography, not research. Verdict: viable but requires a full pivot; the honest pitch is microstructure intuition plus empirical horsepower, not hardware.

### 4. The substantive question

"In the viability model, priority fees are a transfer out of the trading ecosystem to block builders, and viability fails when informed losses can't be covered by noise-trader fee revenue. Your conclusion points to within-block organization as the design lever. If a protocol rebated a fraction of PGA revenue to the liquidity supplier — MEV redistribution to LPs, which several protocol designs now propose — does that relax the viability condition enough to restore markets at long block times, or does the participation-cutoff mechanism (price formation from a thinning upper tail) survive any rebate scheme because it operates through selection rather than through the supplier's budget?"

Answerable within their framework (modifies the supplier's revenue side, leaves the PGA selection stage intact); shows he understood the two damage channels are distinct.

### 5. Gaps to close before contact

- Read "Auctioning Time to Mitigate Latency Races" (https://arxiv.org/abs/2512.10094) in full — the paper where his expertise is most legitimate; be able to discuss Timeboost mechanics and the duplicate-submission measurement.
- Read "Liquidity provision on blockchain-based decentralized exchanges" (RFS 2025; working version arXiv:2103.08842) and the MEV paper (JFE 2025) — the LP loss framework this literature is built on.
- Budish, Cramton, Shim (QJE 2015) — the CEX-side ancestor. Also: Kyle/Glosten-Milgrom adverse-selection models beyond MFE coursework — Capponi's group is model-heavy and the measure-theory gap is a real conversation risk.

---

## PROFESSOR 2: BARTOLOMEO STELLATO (Princeton ORFE)

### 1. Current research line

Verified from https://stella.to/. Program sits at the interface of optimization, ML, and optimal control, organized around the NSF CAREER "Learning for Real-Time Embedded Optimization" (2023, to ~2028), a 2025 Sloan Fellowship, and a 2025 ONR Young Investigator award ("Data-Driven Analysis and Design of Mathematical Optimization Algorithms"). Three threads, 2024-2026:

**(a) Verification and performance analysis of first-order methods.** "Exact Verification of First-Order Methods via Mixed-Integer Linear Programming" (accepted, SIAM Journal on Optimization; arXiv:2412.11330); "Verification of First-Order Methods for Parametric Quadratic Optimization" (Mathematical Programming); "Data-Driven Performance Guarantees for Classical and Learned Optimizers" (JMLR, with Sambharya); "Data-driven Analysis of First-Order Methods via Distributionally Robust Optimization" (arXiv:2511.17834). Theme: replace loose asymptotic convergence rates with exact or statistically valid worst-case bounds after K iterations over a parametric problem family.

**(b) Learning to optimize.** "Learning to Warm-Start Fixed-Point Optimization Algorithms" (JMLR); "End-to-End Learning to Warm-Start for Real-Time Quadratic Optimization" (L4DC 2023); "Learning Algorithm Hyperparameters for Fast Parametric Convex Optimization" (SIMODS, arXiv:2411.15717); "Distributionally-Robust Learning to Optimize" (arXiv:2605.06585). ICML 2026: "Batched First-Order Methods for Parallel LP Solving in MIP" (arXiv:2601.21990); "Conformal Prediction for Early Stopping in Mixed Integer Optimization" (arXiv:2602.01476).

**(c) Solvers and embedded deployment.** Lead author of OSQP (MPC 2021; Beale-Orchard-Hays Prize 2024); maintains CVXPY; "Embedded Code Generation with CVXPY" (IEEE L-CSS/CDC 2022); "Online mixed-integer optimization in milliseconds" (INFORMS JoC 2022). Hardware: co-author of **"RSQP: Problem-specific Architectural Customization for Accelerated Convex Quadratic Optimization," ISCA 2023** (with Maolin Wang, Ian McInerney, Stephen P. Boyd, Hayden Kwok-Hay So; https://dblp.org/rec/conf/isca/WangMSBS23.html, DOI 10.1145/3579371.3589108) — an FPGA architecture for OSQP-style QP solving. **Critically, the FPGA expertise there came from So's group (HKU); his own Princeton group page (https://stella.to/group/ — Park, Deza, Clarke, Liu, Hua, Baicev) lists no one identified with hardware, FPGA, or embedded implementation.** Per-member topics: UNKNOWN (page doesn't list them).

### 2. The one paper to read

**"Exact Verification of First-Order Methods via Mixed-Integer Linear Programming"** — Ranjan, Park, Gualandi, Lodi, Stellato. Accepted, SIAM Journal on Optimization; arXiv:2412.11330. Read at https://arxiv.org/html/2412.11330v3.

- **Core question:** For a first-order method run for exactly K iterations on a parametric family of LPs/QPs (parameters in X, initial iterates in S), what is the exact worst-case fixed-point residual — can you certify K iterations suffice for tolerance ε for every instance in the family?
- **Method:** Encode the K unrolled iterations as a MILP. Affine steps become linear equalities; piecewise-affine operators (projections, soft-thresholding, saturation) become binaries with big-M, with exact convex-hull formulations and polynomial-time separation for cutting planes. Objective maximizes the infinity-norm residual after K steps. Scalability via interval propagation, operator-theoretic bounds, optimization-based bound tightening — vanilla dies at K≈15; enhanced reaches K=60.
- **Main results:** On ISTA/FISTA for Lasso, projected gradient for min-cost network flow, and MPC for a 12-state quadcopter (horizon 8), exact bounds are 2-3 orders of magnitude tighter than performance-estimation-problem (PEP) worst-case bounds; solve times 10 min - 2 hrs per verification to 5% gap.
- **Author-named limitation/open thread:** near verbatim: "While our analysis was restricted to QPs in this work, we believe it motivates similar studies in parametric convex settings." Implicit: MILP cost grows with K and dimension; verified problem dimensions are small (tens of variables) — consistent with the embedded framing.

### 3. The honest connection — strict

The strongest of the three, and precise. Stellato's CAREER agenda is literally "learning for real-time embedded optimization"; his verification line produces certified iteration counts K; his code-generation line targets embedded deployment; RSQP proves he wants QP solvers in silicon — but the silicon expertise was borrowed from HKU and **his current Princeton group has no hardware builder. The candidate is exactly that missing person**: production RTL, sub-10μs pipeline with hardware timestamping and lock-free structures, first-order methods as a practitioner.

The concrete contribution: **a verified solver-on-chip.** MILP verification gives an exact worst-case residual after K iterations over a parametric family; an FPGA implementation of a fixed-K, fully unrolled or pipelined first-order method converts that into a deterministic worst-case latency in clock cycles — a certificate composed end to end, from optimization theory to timing closure. Market making becomes the motivating application (a parametric QP re-solved every tick under a hard latency budget), reframed as a real-time embedded decision system — the correct framing for a group that is not finance-facing. The CP-SAT/routing background touches the ML-for-MIP thread as domain familiarity.

Weakness to flag: the group's output is proof-heavy (convex-hull formulations, operator theory, DRO). The candidate lacks research-level convex analysis and Stellato will probe this. The hardware pitch differentiates only if he can hold his own on the math within a year.

### 4. The substantive question

"The MILP verification encodes each iteration in exact real arithmetic — affine maps plus exact convex hulls of the piecewise-affine operators. On an embedded or FPGA target the iterates live in fixed-point, so each step is the nominal operator plus a bounded quantization perturbation. Since your encoding already handles piecewise-affine set-valued steps via big-M, could the verification absorb a per-step bounded-error term — verifying the worst case over both the parameter set and the quantization error ball — to certify iteration counts for fixed-point implementations directly? Or does the added dimensionality per iteration break the bound-tightening pipeline that currently gets you from K≈15 to K≈60?"

### 5. Gaps to close before contact

- Read RSQP (ISCA 2023, DOI 10.1145/3579371.3589108) carefully — know exactly what has already been done in FPGA QP solving in his orbit and what RSQP left open, before pitching hardware.
- Read the OSQP paper (MPC 2021, arXiv:1711.02282) and "Embedded Code Generation with CVXPY" (CDC 2022) — ADMM mechanics and the embedded toolchain are assumed background.
- Learn PEP basics (Drori-Teboulle; Taylor, Hendrickx, Glineur) plus the JMLR data-driven-guarantees paper — the verification line defines itself against PEP.

---

## PROFESSOR 3: JAMES C. HOE (CMU ECE)

### 1. Current research line

Homepage (https://users.ece.cmu.edu/~jhoe/doku/): computer architecture, reconfigurable computing, "high-level hardware description and synthesis"; teaches 18-643 Reconfigurable Logic (Fall 2026); highlights an HLS-based log-monitoring project. dblp shows two active 2023-2026 streams.

**(a) Input-dependent stream processing on FPGAs** — most relevant. Lineage: "Exploiting the Common Case When Accelerating Input-Dependent Stream Processing by FPGA" (IEEE Transactions on Computers 72(5), 2023, DOI 10.1109/TC.2022.3200576), then two 2026 papers with PhD student Shashank Obla and Bin Li: "Analysis and Optimization of Input-Dependent Stream Processing Pipelines on FPGAs" (FPGA 2026, DOI 10.1145/3748173.3779555) and "Lightweight Queueing Abstraction for Rapid Simulation and Automated Tuning of Input-Dependent Streaming Pipelines on FPGAs" (FCCM 2026, DOI 10.1109/FCCM68464.2026.00068), plus an FCCM 2026 challenge paper on RapidScan (HLS-based streaming string matching). Thesis of the stream: for pipelines whose per-element work depends on the data, the optimal buffer/throughput configuration depends on input statistics that vary "by deployment site and even time of day"; FPGAs can be re-tuned per deployment if you abstract performance from RTL via queueing models.

**(b) Stream network architectures and NIC interfaces.** "Reconfigurable Stream Network Architecture" (ISCA 2025, with Wang, Zhang, Cong; arXiv:2411.17966): ISA-level abstraction modeling the datapath as a circuit-switched network of stateful functional units; on DNN workloads on VCK190, 6.1x latency reduction vs SOTA, matching NVIDIA T4 latency at 18% of its memory bandwidth. NOTE: RSN "does not support prediction or speculative execution... The order of execution and data dependencies is known at compile time" — deterministic workloads, the opposite regime from stream (a). Earlier: "Ensō: A Streaming Interface for NIC-Application Communication" (OSDI 2023, Best Paper, with Sadok, Atre, Zhao, Berger, Panda, Sherry, Wang). FLAG: the Phase 2 quote "How can we efficiently coordinate and synchronize heterogeneous hardware resources..." could NOT be found in the arXiv v2 HTML — treat as unverified.

### 2. The one paper to read

**"Analysis and Optimization of Input-Dependent Stream Processing Pipelines on FPGAs"** — Obla, Li, Hoe. FPGA 2026. DOI: https://doi.org/10.1145/3748173.3779555. **Full text paywalled (ACM DL 403; no open PDF/arXiv version found).** Verbatim abstract via Semantic Scholar.

- **Core question:** How to tune input-dependent streaming FPGA pipelines — whose optimal configuration depends on deployment-specific input characteristics — without RTL-level design turnaround on every re-tune.
- **Method:** The "FPGA-as-a-System (FaaS) queueing-based performance model" — decouples input-dependent performance behavior from low-level functional detail; a fast queueing-based performance simulator incorporates input characteristics and guides tuning to meet performance targets with fewer resources.
- **Main result:** Tuning a multi-string-matching pipeline for network security/log monitoring: starting from an implementation already manually tuned to the throughput target, FaaS "uncovers previously overlooked bottlenecks and underutilization"; revised implementation cuts resource footprint >40% at unchanged throughput. The FCCM 2026 companion (RapidQ): trace model drives queueing simulation across buffer sizes and module throughput configurations without repeating functional simulation, 7x faster than SOTA, up to 42% resource savings.
- **Author-named limitation:** UNKNOWN — conclusion behind the ACM paywall. What the abstracts concede: trace-driven (claims relative to input characteristics captured in the trace); stated targets are throughput and resources — latency, specifically tail latency, is not mentioned in either abstract. READ THE FULL PAPER (CMU library or email Obla) BEFORE CONTACT.

### 3. The honest connection — strict

A genuine two-way fit at the workload level. A market-data feed handler is, exactly, an input-dependent stream processing pipeline: per-message work depends on message type and book state, and the arrival process is the most hostile input distribution in the FaaS problem class — self-exciting bursts, auction spikes, volatility-regime shifts: the "varies by deployment site and even time of day" phenomenon pushed to its extreme. What the candidate gives them:

- **A workload class where the objective breaks their framing.** FaaS/RapidQ tune to a throughput target with minimal resources. Trading feed handlers are specified by tail-latency bounds (p99.9 under burst) with correlated, non-stationary arrivals. Trace-driven queueing simulation with calm-period traces will systematically miss the moments that matter. Whether their queueing abstraction can express percentile-latency targets under regime-switching arrivals is a real, testable extension — and the candidate owns real workloads and traces to stress it.
- **A production-grade streaming pipeline as a benchmark.** Their case study is string matching for log monitoring. A hardware LOB + feed handler is a richer, stateful, latency-critical benchmark.
- **Caveat, honestly:** Hoe does not need help building fast RTL; his group's methodology bet is that hand-RTL turnaround is the disease and higher-level abstraction (HLS, queueing models) is the cure. The candidate's hand-RTL instinct is, in this group's worldview, the thing to be abstracted away. The connection is the workload and its statistics, not the Verilog.

### 4. The substantive question

"FaaS tunes buffer sizes and module throughputs against a trace-driven queueing simulation to hit a throughput target with minimal resources. For feed handlers in trading systems the workload is the same shape — input-dependent parsing and matching — but the spec is inverted: a tail-latency bound under arrival processes that are bursty and self-exciting, where the trace is nonstationary and the regime that matters (an open, a volatility spike) is a tiny fraction of wall-clock time. Does the queueing abstraction admit percentile-latency objectives, and in your string-matching case study how sensitive was the tuned configuration to which portion of the trace you tuned on — would you re-tune per regime, exploiting FPGA reconfigurability, or size buffers for the worst regime and pay the resource cost?"

HONESTY NOTE: built on the two verbatim abstracts plus TC 2023 lineage; if the full paper already treats latency percentiles or trace sensitivity, the question collapses — reading the full paper first is mandatory.

### 5. Gaps to close before contact

- **Obtain and read the full FPGA 2026 and FCCM 2026 papers** (library access; DOIs above) and the TC 2023 predecessor — the common-case/rare-case decomposition there is the intellectual root; conclusions contain the author-named open threads not retrievable this session.
- **The HLS cultural gap, explicitly.** His group is HLS-centric; the candidate writes hand RTL. Before contact, work through Vitis HLS on a small streaming kernel (e.g., reimplement a slice of the feed handler) to discuss the abstraction trade-off from experience instead of defending hand RTL — which would read as opposing the group's thesis. Audit 18-643 materials.
- **Read Ensō (OSDI 2023)** — DPDK/kernel-bypass experience maps directly onto it; the natural second conversation topic. Plus enough queueing theory (trace-driven simulation methodology, G/G/1 tail behavior, burstiness metrics) to discuss FaaS on its own terms.

---

## Cross-cutting honesty notes

- Strongest fit by contribution gap: **Stellato** (missing hardware person for an existing verified-embedded-solver agenda; RSQP proves appetite, group page shows no in-house builder). Strongest fit by workload: **Hoe** (feed handler is literally his problem class; but his cure is abstraction, not faster RTL). Weakest direct fit: **Capponi** (theory agenda; candidate's value is microstructure texture and empirics for the latency-race line, and it requires a full pivot into blockchain markets).
- Unverifiable this session: FPGA 2026 conclusion (paywalled); Hoe's Phase 2 "coordinate heterogeneous resources" quote (not found in arXiv v2); per-member topics of Stellato's group; venue of Capponi's viability paper.
- Recurring candidate-side gaps: measure-theoretic probability (Capponi), research-level convex analysis (Stellato), HLS methodology (Hoe). None fatal for a conversation; all three would surface in a PhD.
