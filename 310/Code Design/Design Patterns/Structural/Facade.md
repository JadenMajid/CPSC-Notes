---
tags:
  - "CPSC310"
---
## Description
Facades are a design pattern where you leverage an interface for a class to hide internal implementation detail from callers. The facade decreases [[Coupling]] modules inside an [[Encapsulation|Encapsulated]] module with outside modules.
## Pros and Cons
- Pros
	- Increases code reusability, and simplicity for end users.
- Cons
	- Reduces the exposed functionality of a submodule.

## Application
1. Identify core responsibilities of a subsystem
2. Determine if simple actions require the collaboration of multiple modules within a subsystem
3. Identify abstractions that would allow the subsystem to encapsulate these behaviours more directly
4. Expose those [[Abstraction|Abstractions]] via the facade


![[Screenshot 2025-11-21 at 12.56.41 PM.png]]