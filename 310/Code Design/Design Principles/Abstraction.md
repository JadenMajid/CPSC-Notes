Abstraction is when we encapsulate the internal workings of things, and expose the minimal complexity to the outside in order to the get desired effects

- Abstraction manages complexity by removing irrelevant implementation details.
	- However, too much or too little can inhibit understanding
- [[Magic Numbers]] are an example where abstraction reduced complexity, and increases locality of change. 
	- If a magic number is reused multiple times, it may be difficult to locate where it is used and differentiate it from other uses. By abstracting it to a constant, we localize changes to the magic number to a single local change

In order to abstract, we can use [[Decomposition]] to reduce apparent complexity of a class into subpieces that have the same functionality, but hide use [[Information Hiding]] to reduce apparent complexity to the end user

[[Encapsulation]] Lets use group these decompositions into tidy boxes that are easier to reason about.






Abstraction is the core principle of [[OOP]]

#310
#310
#310