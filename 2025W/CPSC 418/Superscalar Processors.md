## Parallelism Hazards
- Read after Write(RAW)
- Write after Read(WAR)
- Write after Write(WAW)
## Dependency Graphs
![[Screenshot 2026-02-02 at 15.17.15.png]]
- We can draw a graph to determine dependencies
![[Screenshot 2026-02-02 at 15.35.57.png]]
![[Screenshot 2026-02-02 at 15.36.08.png]]
- WAW & WAR for tmp1 & tmp2 is because we are looping,
- Can resolve by using new registers on loop iterations
	- Now left with only RAW which can be solved with nops
### Register Renaming
![[Screenshot 2026-02-02 at 15.43.07.png]]
### Register Lifecycle
![[Screenshot 2026-02-02 at 15.43.49.png]]

### Control Dependencies
- CPU executes instructions speculatively 
	- Tracks statistics for 
## 313 Review
![[Screenshot 2026-02-02 at 15.17.59.png]]

### RISC
- Reduced instruction set
- Generally 1 clock cycle per instruction
	- not universally true, can have multi cycle instructions and/or cache misses

### Optimization
- Focus on innermost nested loops, they are the "hottest"
