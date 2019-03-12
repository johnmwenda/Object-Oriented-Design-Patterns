### Command Pattern [Behavioral Pattern]:

#### Description
The Command pattern allows a request/action to exist as an object which you can later retrieve and do operations on them. Normally the requests/actions are stored as a list of codes which the client can execute at a later time or many times. Command pattern can be used very well with systems that require undo commands. The Command Pattern involves the following components
1. Invoker - stores the collection of commands and determines which Command to execute
2. Receivers - this objects actually implement the Commands
3. Commands - objects that represent an action/request
4. Client - consumes the Commands, and determines when to use each command



#### Benefits
- Allows you to set aside a list of commands for later use
- A class is a great place to store procedures you want to be executed
- You can store multiple commands in a class to use over and over
- You can implement undo procedures for past commands. This is achieved by saving the state of the program together with the command that brought it to that state. This is achieved easily in Command pattern because we are not only able to execute commands, we can persist state inside the Command object. That is, you save actions with data

#### Scenario
- Assume we are implementing a simple GUI. Our GUI will have 4 menus. File, Edit, View and Help
- Each of the menu options will be a Command object
- Our Receiver object (which will actually perform the Commands) will be UICode class
- Our Invoker will be a mouseButton object
- The Client will be the orchestrator calling different commands at different times
