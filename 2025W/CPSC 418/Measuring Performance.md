main motivation for PP is performance
- Measures of speed
	- Latency
		- time from starting task until completion
	- Throughput
		- Rate at which tasks are completed

$$\text{Throughput}_{\text{sequential}} = \frac{1} {\text{latency}} $$
$$\text{Throughput}_{\text{parallel}} \ge \frac{1} {\text{latency}} $$

## Speedup
$$\text{speedup}=\frac{\text{time sequential}}{\text{time parallel}}$$
## Efficiency
$$\text{Efficiency}=\frac{\text{speedup}}{P}$$
- Becomes more important than speedup if we're considering things like
	- Energy
	- Capital cost
## Work & Span
- Describe computation as a graph
- Vertices are operations
- Edges are dependencies
- Span ignores communication cost but gives an idea of how parallelizable an algorithm is

$$\text{Work}=\text{number of vertices}=\text{min seq. time}$$
$$\text{Span}=\text{depth of the tree}=\text{minimum parallel cost}$$

## Amdahl's Law
- given seq. program where
	- fraction $s$ of program is inherently sequential
	- fraction $f=1-s$ benefits perfectly from parallel speedup
- P processor runtime
	- $$T_{\text{parallel}}=T_{\text{sequential}}(s+\frac f P)$$
	- $$\text{speedup}=(s+\frac f P)^{-1}\le \min(P,1/s)$$

## Gustafson's Law
- Amdahl's law assumes a fixed problem size
- most computations $s$ decreases as $n$ increases
![[Screenshot 2026-02-04 at 15.35.09.png]]

## Law of Modest Returns
- Parallelism gives modest improvement unless the problem is not complex
	- Often good enough
- sometimes problems have huge $n$, with low complexity, like data mining, ML, and graphics
- if algorithm $O(?)$ is big, speedup may be kinda bad