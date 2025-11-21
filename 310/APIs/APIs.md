---
tags:
  - "CPSC310"
---
The unconstrained nature of software makes it easy to make decisions that will end up being ‘bad’ in the long run.

APIs(Application Programming Interfaces) are ways that applications can communicate with eachother, whether locally, or through a network.

The 'User' of an api is a developer, who creates a program that can interact with an API.

Good APIs should be completely [[Coupling|Decoupled]] from their implementations. Any dependence on specific implementation for an API is a sign of a [[Code Smells|Code Smell]]

How to Design an API
- Talk to stakeholders
- start with a one page spec to create use cases
- code tests to simulate client code
- most apis have fundamental limitations that are suboptimal

API Design Principles
- Do one thing, and do it well (kinda like [[Linux]]!)
- APIs should be as small as possible, but no smaller
- Names matter
	- Things that are hard to use, dont get used
- Documentation Matters
	- Things that are hard to learn, dont get learned
- Implementation Matters
	- Leaking implementation is a fundamental mistake
- Minimize access
	- Users should be ONLY able to do what they are meant to be able to 

APIs should hide their internal implementation details, leaving only what is necessary for end user functionality exposed to the outside world.
![[Screenshot 2025-11-20 at 5.41.05 PM.png]]

- HTTP
	- [[REST]]
	- [[SOAP]]
	- 
- 
#310
#310
#310