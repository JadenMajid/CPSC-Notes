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

