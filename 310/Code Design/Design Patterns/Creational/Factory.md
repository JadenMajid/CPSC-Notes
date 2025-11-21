---
tags:
  - "CPSC310"
---
## Description
The Factory [[Design Patterns|Design Pattern]] is a pattern that [[Abstraction|Abstracts]] the creation of [[Object Orientation|Objects]]. The new FactoryClass returns new objects of type [[Class]] with some method. Factories remove the dependence on specific constructors, abstracting away with the Factory class.

Factories 
## Pros and Cons
- Pros
	- Useful when we don't know the types and dependencies of the objects we are working with
	- Useful when we want to let other developers extend components that are internal types of our library/framework
	- Can save system resources when instantiating expensive objects
		- [[Database]] Connections
		- File Systems
		- Network Connections
	- Avoids tight [[Coupling]] between creator and concrete products
	- Can solve [[Single Responsibility Principle]] Violations
		- Can move product creation code into one place within the program
	- Can solve [[Open Closed Principle]] Violations
		- Can introduce new types of the program without needing breaking changes
- Cons
	- Introduces tight [[Coupling]] between the Factory and Product classes
	- Need to create new Factory class for every new Product subclass
## Application
1. Find the [[SOLID]] Violation
	1. [[Switch on Type]] -> [[Single Responsibility Principle]] Violation because too much construction code ([[Divergent Changes]])
2. Find the [[Abstraction]]
	1. Factory at the top of its Hierarchy
	2. MAYBE Product at the top of its Hierarchy
3. Find the [[Polymorphism]]
	1. make the thing
	2. ie: factory.makeProduct(...)
4. Figure out when the Polymorphic methods are called
	1. In the client, replace Constructor calls with factory.makeProduct(...) calls

![[Screenshot 2025-11-21 at 1.34.29 PM.png]]![[Screenshot 2025-11-21 at 1.37.42 PM.png]]