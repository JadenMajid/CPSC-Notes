## Description
Composite is a design pattern where a system that can be represented as a [[Tree]] is broken into parts that are either Leaves or Composites. We can use all elements in this tree with the interface Component, which encapsulates common behaviour(like Component.execute())
- Client
	- Interacts with the subsystem(root Component)
- Component
	- [[Interface]] that [[Encapsulation|Encapsulates]] behaviour that is common to all elements of the tree.
- Leaf
	- [[Class]] that implements Component
	- Does most of the work most of the time(no sub components to delegate to)
- Composite
	- Class that is a Component that has sub-elements.
	- Doesn't know concrete class of children
	- Interacts with children through Component [[Interface]]

## Pros and Cons
- Pros
	- Encourages extension
	- Represents whole part hierarchies
- Cons
	- Can make it hard to restrict relationships 

## Application
1. Find the violation
	1. [[Duplicate Code]], [[Switch on Type]], etc
2. Find the [[Abstraction]]
	1. introduce Hierarchy and pull up all methods
3. Find the [[Polymorphism]]
	1. operation(), traverse(), etc.
4. Figure out when polymorphic methods are called
	1. ie: when the tree is walked

![[Screenshot 2025-11-21 at 1.14.35 PM.png]]