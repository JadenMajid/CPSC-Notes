---
tags:
  - "CPSC310"
---
## Description
The observer [[Design Patterns|Design Pattern]] is a design pattern where a collection of [[Object Orientation|Objects]] subscribe to some publisher, with an update function that is called by the publisher when the publisher wants to update its subscribers. Subscribers need to have some update(...) function. Publishers need to have some [[Collection]] of references to their subscribers.
- Relationships can be dynamic
	- Add/Remove subscribers
- Publishers should not be tightly coupled to their subscribers
- Subscriber should be some interface that is implemented by a Concrete [[Class]](es)
- Main design question: Push or pull
	- Neither is better or worse, just context dependent
	- Push
		- Publishers should tell subscribers when new data is available
	- Pull
		- Subscribers should ask the publisher for data when required

![[Screenshot 2025-11-21 at 2.23.22 PM.png]]
## Pros and Cons
- Pros
	- [[Open Closed Principle]] is applied
		- New subscriber classes can be introduced without changing the Subject class
	- Can establish relationships at runtime
- Cons
	- Subscriber notification order may be random
	- Can be constraining when many observer types are needed

## Application
1. Identify [[SOLID]] Violations
	1. [[Duplicate Code]] can be removed from different types of watchers
	2. [[Single Responsibility Principle]] can be improved by [[Coupling|Decoupling]] Publisher/Subscriber code into its own class
	3. [[Switch on Type]] can be removed by using the subscriber interface defined
2. Find the [[Abstraction]]
	1. Subject and Observer (Publisher and Subscriber) should be pulled into their own Class and [[Interface]] respectively
3. Find the [[Polymorphism]] 
	1. observer.update(...)
4. Find when Polymorphic Methods are called
	1. When something in the subject has changed -> self.notify() -> obs.update(...)

![[Screenshot 2025-11-21 at 2.21.33 PM.png]]