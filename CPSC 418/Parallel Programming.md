---
aliases:
tags:
  - parallel-programming/CPSC418
---
# Keywords/Definitions
- Speedup
	- $\frac{T_{seq}}{T_{par}}$
- 

# Examples
## Comparing Poems

- Definitions
	- $T_c$: Time to compare 2 poems
	- N: number of poems
	- P: number of threads
- Single Threaded: Time for 1 thread to find best poem
	- $NT_c$
- Parallel V1:
	- Time for P threads to find best poem from $N/P$ poems
		- $(N/P-1)T_c$
	- Time for original to tank P finalists
		- $(P-1)T_c$
	- Total Time:
		- $(N/P+P-2)T_c$
- Speedup from seq
	- $\frac{N}{N/P+P}=\frac{NP}{N+P^2}$
		- Perfect Speedup(assumes no parallelization overhead)
- Parallel V2(pairs of clones)
	- Speedup:$\frac{N}{N/P+P/2}$
- Parallel V3(Binary Tree Structure)
	- Every node splits input list in half unless 1 or 2 nodes left
	- Theoretically is $\Theta(\log n)$
	- Reality has overhead for each thread
		- With $P$ Processors(), $O(\frac{N}{P}+\log P)$ 
		- approaches ideal case when $N\gg P$
		- $\lambda$ used for communication cost constant
			- $O(\frac{N}{P}+\lambda\log(P)$
			- ni bu min bai zhe