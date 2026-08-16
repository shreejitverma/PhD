# Statement of Purpose - Shreejit Verma

Markets advertise liquidity and withdraw it at exactly the moments it matters most.
I watched this from the inside on BNP Paribas's automated market-making desk, where systems quoting roughly $500 million a day in the Prime Credit market are built, quite rationally, to widen and retreat when volatility spikes - each dealer's prudence aggregating into everyone's illiquidity.
The question that has pulled me toward a PhD is whether that fragility is a fixed cost of how markets work or a design problem: how much of it lives in the economics, how much in latency and queue mechanics, and what it would actually cost to keep quoting through stress.

My master's thesis at Stevens was a first attempt at the mechanical half of that question.
I wanted to know how much of a market maker's survival in volatile conditions comes from model quality and how much from deterministic reaction time, so I built the fastest system I could and measured it: a sub-10-microsecond tick-to-quote pipeline with a custom limit order book, FPGA market-data handlers written in RTL, kernel-bypass networking through DPDK, hardware timestamping, and lock-free data structures throughout.
Getting to deterministic microsecond-level execution took months of profiling and rewriting, and it worked.

What I value most from the thesis, though, is the list of things it could not do.
The PCIe link between host and FPGA saturates before the feed parser does, so the bottleneck I spent months attacking simply moved.
On-chip LUT and DSP budgets forced a standing trade-off between order-book depth and pricing logic, which means "put the model in hardware" is a resource-allocation problem, not a slogan.
The deepest limitation is methodological: I evaluated the system against replayed market data, and replay cannot tell you how the market would have reacted to your quotes.
The counterfactual fill is unobservable.
Every latency number I produced is real; every profitability number is conditional on an assumption I cannot test from recorded data alone.
That gap between simulated and real market response is not an engineering problem, and it is the one I want to spend the next five years on.

My side projects taught me to distrust my own results, which I now consider the most useful thing they produced.
A 120-day crypto momentum strategy I built as a quant research project backtested at a 155% annualized return with a 1.94 Sharpe ratio after transaction costs - a number I learned to read as a warning rather than a result, because it survives neither regime honesty nor capacity analysis nor realistic fill assumptions.
An adaptive execution framework that switches among passive, TWAP, and aggressive strategies by volatility regime held up better - a 20% Sharpe improvement and a 20% CVaR reduction that persisted under parameter perturbation - but it grades its own homework the way every backtest does.
Working on live merger-arbitrage strategies at Versor Investments, an $8.5 billion AUM fund, showed me the difference: production is the only referee that cannot be argued with.

I came to research the long way.
Over eight years I have built trading and optimization systems in production - fixed-income trade processing on Bank of America's QUARTZ platform, three nested NP-hard vehicle-routing problems solved with constraint programming at LogiNext, and the BNP Paribas market-making stack - and industry kept generating questions it had no room to answer.
In 2021 I withdrew from Carnegie Mellon's computational finance program weeks after starting, when my father fell seriously ill; I finished a master's in financial engineering at WorldQuant University while working full time, then completed the Stevens MSFE with a 3.974 GPA.
I finish Georgia Tech's MS in computer science, specializing in computing systems, this December; C++ is my first language, and the coursework this agenda needs - market microstructure, algorithmic trading, advanced operating systems, distributed computing - is already behind me.

Three directions define what I want to work on.
First, queue- and latency-aware learning for market making: the reinforcement-learning market-making literature typically grants the agent execution priority and abstracts away latency competition - the two effects I have spent years measuring in production - and I want to build message-level, queue-reactive environments with measured latency distributions and find out how much of the published policies survive contact with them.
Second, latency as an economic choice rather than a parameter: I have measured what a marginal microsecond costs in hardware, and the curve is steeply convex; setting measured cost curves against auction-theoretic models of latency advantage would endogenize the speed arms race and give market designers actual numbers to work with.
Third, evaluation infrastructure: the field needs a market simulator with realistic execution, latency, and stress dynamics for benchmarking trading agents - reinforcement-learning-based and, increasingly, LLM-based - the way crash-test rigs exist for cars, and building one is squarely inside my competence.
These are starting points, not a contract, but they are the kind of question my background generates on its own.

Stevens is where this agenda already has roots.
Professor Florescu's SHIFT simulator is the closest existing platform to the evaluation infrastructure I describe, and extending it with a latency-heterogeneous execution tier is a concrete first project rather than a hope.
The "Mandate without Managers" line of work restricts arbitrage to a once-daily close and flags the frictional case as open; the intraday version, with latency-aware arbitrageurs and inventory constraints, is exactly the simulation problem my infrastructure was built for, and it connects directly to Professor Feinstein's treatment of loss-versus-rebalancing as an implied fee stream in "The Price of Liquidity."
Professor Yang's cross-market jump-contagion estimates rest on cross-venue timestamp alignment at the shortest lags - hardware timestamping is my specialty, and I would like to bring nanosecond-coherent joint capture to that line and to the CRAFT center's benchmarking mission.
I completed my thesis at Stevens; these are not names from a website but labs I know.

A department also gets something from me beyond the research.
I have taught at scale - I organized four data-science events at Bank of America and delivered AI/ML lectures to more than 2,500 employees - and served as president of the Stevens Graduate Financial Association, so TA work is something I would do well rather than merely tolerate.
The FPGA testbed itself is lab infrastructure: hardware-timestamped capture and a message-level book simulator that other students' experiments can run on from day one.

My goal after the PhD is a research career - a faculty position or an industrial research lab - working at the boundary between market microstructure and computer systems, where I have spent my whole career and where the open questions are the ones I keep tripping over.
I have built the fast system.
I am applying because I want to understand, with the standards of proof that only research demands, what it is actually worth.
