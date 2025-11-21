---
tags:
  - "CPSC310"
---
## Description
The Strategy [[Design Patterns|Design Pattern]] is a design pattern that varies behaviour of our system by [[Abstraction|Abstracting]] the specifics of behaviour into a container that executes the desired behaviour. 
Strategy is a classic application of the [[Open Closed Principle]]. Each Strategy [[Encapsulation|Encapsulates]] a single algorithm, following the [[Single Responsibility Principle]]. Context delegates behaviour to it's Strategy.

![[Screenshot 2025-11-21 at 1.59.28 PM.png]]
## Pros and Cons
- Pros
	- Can swap [[Algorithm]] used at runtime
	- Can isolate the implementation of the [[Algorithm]] from the calling context
	- Can replace [[Class]] inheritance with [[Composition]]
	- [[Open Closed Principle]]
		- Can introduce new strategies without change of Context
- Cons
	- Makes code harder to understand and more complicated if we only use a small number or one algorithm
	- Clients need to be aware of differences between strategies when choosing them
	- Behaviour may be replicable with simpler [[Anonymous Functions]]

## Application
1. Find the [[SOLID]] Violation
	1. [[Open Closed Principle]] Violation
		1. Design is not open to new algorithms
	2. [[Single Responsibility Principle]]
		1. Multiple algorithms are defined in the same [[Class]]
	3. Code smells
		1. [[Divergent Changes]], [[Switch on Type]], etc
2. Find the [[Abstraction]]
	1. Extract the violation into a Strategy [[Interface]]
3. Find the [[Polymorphism]]
	1. Move the implementations into their own classes that implement the [[Interface]]
4. Figure out when the Interface's Methods are called
	1. Invoke the strategy's methods in the container when applicable

