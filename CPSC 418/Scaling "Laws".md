- Scaling in CS isn't really determined by laws, but laws described useful trends.

## Moore's Law
- The economics of scaling
- has been slow for the last ~10-15 years 
- Performance improvements come from:
	- Improvements to transistor performance
	- better packaging and interconnect
	- better architectures
	- better heat removal
- In 1965 Gordon Moore saw that a semi-log plot of transistors/area vs time was a straight line
- Profits would allow companies to improve processes
	- profits->more research->more profits
- Moore's law broke at 28nm
	- electrical energy per electron needs to be $\ge 20$x thermal energy or the transistor will leak
	- leads to operating voltage needing to be $\ge0.6V$ 
	- nm names for processes are now just marketing names with no connection to anything on the chip since 22nm node in 2011
## Dennard Scaling
- The physics of scaling, ended in the 90s
- if transistor dimensions divided by $\alpha$
	- delay of logic gates  ->$\alpha^{1/2}$ 
	- clock frequency -> $\alpha^{}$
	- energy per signal transition -> $\alpha^{-3}$ 
	- power -> $\alpha^{-2}$
	- number of devices on a fixed-size -> $\alpha^{2}$
	- power density is constant
- literally everything improves as transistors shrink
## Heat Removal
- The mech-eng of scaling
## Scaling Today

### GPUs
![[Screenshot 2026-01-28 at 15.30.31.png]]

### Hyperscalars
- 1.5% of global electricity consumption, growing at 12% per year
	- 4% in the US, expected to grow to 9-12% by 2030
	- 