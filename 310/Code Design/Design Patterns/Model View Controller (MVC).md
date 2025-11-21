
MVC is a gui design pattern where the data model, view, and controller are all distinct parts of the application that interact. The model is responsible for the internal data, the view is responsible for handling the layout and the controller is responsible for updating the view with relevant changes from the model.

MVC is similar to [[Model-View-Presenter(MVP)]] but has a greater [[Coupling]] between Views and Model


The view can interact with the model through the controller, pushing changes to the data through controller method calls, however is not responsible for updating itself or data validation

The Controller can be responsible for validation, but should not be responsible for storing the data. It should also be responsible for handling user interactions.

• View & Controller leverage the strategy pattern.  
• View often uses a composite pattern (for nested views).  
• View (observer) / Model (subject) use the observer pattern.

![[Screenshot 2025-11-20 at 5.21.56 PM.png]]![[Screenshot 2025-11-20 at 5.26.32 PM.png]]
#310
#310
#310