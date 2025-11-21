Component based UIs are extremely modular UIs, where single components handle everything themselves. Component based UIs are a full melding of the business logic with the UIs, where the state of the UI IS the state of the program

Every component contains its own View and Controller(ish)

Component based GUIs are very popular because they are very reusable, and support component libraries.

Parents and Children communicate through a system of databindings and callback functions that propagate changes throughout the UI
![[Screenshot 2025-11-20 at 5.36.16 PM.png]]

Smart vs Dumb components
- Smart components
	- contain business logic, state management, and presentation logic
- Dumb components
	- only render UI based on input data

\n the below example, each red box is a different element that is responsible for updating itself, handling UI interaction, and its subset of the data model. 
 ![[Screenshot 2025-11-20 at 5.34.07 PM.png]]
#310