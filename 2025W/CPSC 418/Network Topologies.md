network topologies are to the message passing community what cache-coherence is to shared-memory community
- message passing machine can have multiple networks
- Performance considerations
	- Latency
	- Bandwidth
		- Bisection-width
			- The worse way to divide the processors into sets of $\sim P/2$ processors each
			- Always an integer

![[Screenshot 2026-01-26 at 15.47.35.png]]

## Cross Bar Switch
generally pretty cheap devices
![[Screenshot 2026-01-23 at 15.12.58.png]]
# Types of Networks
## Ring Networks
![[Screenshot 2026-01-23 at 15.12.07.png]]
## Star Networks
![[Screenshot 2026-01-23 at 15.12.34.png]]

## Mesh
![[Screenshot 2026-01-26 at 15.06.13.png]]
- Good for nearest neighbour communication but more limited for non local communication
![[Screenshot 2026-01-26 at 15.24.47.png]]
## Toroid
![[Screenshot 2026-01-26 at 15.05.38.png]]

## Hypercube
![[Screenshot 2026-01-26 at 15.05.23.png]]
- Need insane amount of connections, can be infeasible for larger systems
- Works well for small $d$ networks
![[Screenshot 2026-01-26 at 15.24.35.png]]
![[Screenshot 2026-01-26 at 15.27.53.png]]

## Trees
![[Screenshot 2026-01-26 at 15.07.31.png]]
## Fat-Trees
![[Screenshot 2026-01-26 at 15.07.10.png]]

## Dragonfly Networks
- easy to build high radix crossbar routers
- optimized for random traffic
- 1/2 of links used within group, 1/4 to processors, 1/4 to other groups
![[Screenshot 2026-01-30 at 15.27.16.png]]