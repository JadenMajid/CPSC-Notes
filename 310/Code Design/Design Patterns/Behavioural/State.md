## Description
State is a [[Design Patterns|Design Pattern]] where the state of a system is stored as its own [[Object Orientation|Objects]]. This design pattern helps [[Abstraction|Abstract]] change of state functionality a set of [[Class|Classes]] that manage state specific behaviour, such as State transition. 

State is closely related with [[Strategy]]. The State strategy is an extension of the [[Strategy]] Design pattern, but differs in that States are aware of each other, while Strategies should be completely ignorant of each other.
- States accomplish different goals, while Strategies accomplish the same goal
	- States [[Encapsulation|Encapsulate]] completely different behaviours
- Strategies are normally(but not always) static during runtime, while States are meant to be changed




![[Screenshot 2025-11-21 at 2.06.06 PM.png]]
## Pros and Cons
- Pros
	- [[Single Responsibility Principle]] is upheld, we remove the responsibility of state management from the container class.
	- [[Open Closed Principle]] is upheld, we can introduce new states without modifying the container class
	- Eliminates bulky state machine conditionals
- Cons
	- Applying the pattern may be overkill if we only have a few states, or it rarely changes


## Application
1. Find the [[SOLID]] Violation
	1. [[Open Closed Principle]] Violation
		1. Context is not open to change
	2. [[Single Responsibility Principle]] Violation
		1. Context is responsible for handling many different states
	3. [[Code Smells]]
		1. [[Divergent Changes]], [[Switch on Type]], etc
2. Find the [[Abstraction]]
	1. Identify where the state management code within Context lives
3. Find the [[Polymorphism]]
	1. Identify what behaviours are state dependent, add them to that [[Interface]]
4. Figure out when those Polymorphic methods are called
	1. When state transitions

![[Screenshot 2025-11-21 at 2.05.56 PM.png]]