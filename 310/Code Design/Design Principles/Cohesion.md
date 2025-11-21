- Cohesion is the interdependence between modules.
- Low cohesion means that modules accomplish one task, with minimal relations between modules
- High cohesion means that one module accomplishes many tasks that could be accomplished independently
- Cohesive classes generally have a small set of private fields that make sense to the majority of the public methods within the class; if there are fields within the class that are only used by a small fraction of the public methods it may be a sign that the functionality provided by those methods and the private field may not be cohesive with the overall functionality of the class.
	- https://ubccpsc.github.io/310/high-level-design/principles/index.html
- Since cohesive classes are smaller, they lead to a proliferation of classes within a system. While this might make it harder to find the right class within the system, it greatly eases how hard it is to understand that class and simplifies any future bug fixes or feature additions that may be required.
	- https://ubccpsc.github.io/310/high-level-design/principles/index.html
- 

Closely related with [[Coupling]]



![[Screenshot 2025-11-20 at 2.57.07 PM.png]]


#310
#310
#310