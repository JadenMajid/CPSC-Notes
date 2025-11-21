---
tags:
  - "CPSC310"
---
## Description
The Adapter [[Design Patterns|Design Pattern]] is a design pattern where an object A covers an [[Interface]] so that some object B can understand. Adapters are useful because they allow application that store or use data in different formats to interact. Adapters wrap the translatee object, taking the calls to its methods and outputting the proper format for the requestee object
- Adapters should be simple. They should simply convert the format of the data without processing it further
- Adapters should use the core class as an interface, so the client class is interacting with the core classes as closely as possible

![[Screenshot 2025-11-21 at 2.40.01 PM.png]]
## Pros and Cons
- Pros
	- [[Single Responsibility Principle]] 
		- You can separate the interface and data conversion logic from the business logic
	- [[Open Closed Principle]]
		- You can create new adapters for new formats as needed, as long as the interface you implemented follows the original core class' interface 
	- You core class can work with new data sources that it previously could not
- Cons
	- The overall complexity of your code increases. 
	- Every adapter is a liability
		- If the core class datatype changes, all of your adapters need to be changed
	- May be simpler to just change the data format of the core class

## Application
1. Identify [[SOLID]] Violations
	1. [[Open Closed Principle]] Violation
		1. The Core class is not open to new data formats
	2. [[Single Responsibility Principle]] Violation
		1. One class embodies multiple conversions
	3. Possible [[Interface Segregation Principle]] violation
		1. If Adapter is used to segregate interfaces
	4. Smells
		1. [[Divergent Changes]], [[Duplicate Code]]
2. Find the [[Abstraction]]
	1. The Adapter [[Interface]]
3. Find the [[Polymorphism]] 
	1. The Methods in the Adapter Interface
4. Find when Polymorphic Methods are called
	1. Whenever the Adapters methods are used to invoke the adaptee(core class)'s methods

![[Screenshot 2025-11-21 at 2.42.00 PM.png]]