### State Pattern

#### Description
Allows an object to alter its behavior when its internal state changes. The object will appear to change its class.

The state pattern is set to solve two main problems:
1. An object should change its behavior when its internal state changes
2. State-specific behavior should be defined independently. That is, adding new states should not affect the behavior of existing states.


#### Participants
1. Context: Maintains an instance of a ConcreteState subclass that defines the current states
2. IState: Defines an interface for encapsulating the behavior associated with a particular state of the Context
3. ConcreteState: Each subclass of the possible states of the Context implements a behavior associated with a state of Context


#### Scenario
Assume we are coding an ATMMachine. Think about all the possible states for the ATM
States:
HasCard:IState
    InsertCard()
    EjectCard()
    InsertPin()
    RequestCash()
NoCard:IState
    InsertCard()
    EjectCard()
    InsertPin()
    RequestCash()
HasPin:IState
    InsertCard()
    EjectCard()
    InsertPin()
    RequestCash()
NoCash:IState
    InsertCard()
    EjectCard()
    InsertPin()
    RequestCash()

Context: ATMMachine
    currentState IState
    InsertCard when method is called it calls currentState.InsertCard
    EjectCard when method is called it calls currentState.EjectCard
    InsertPin when method is called it calls currentState.InsertPin
    RequestCash when method is called it calls currentState.RequestCash


If ATMMachine is in state of NoCard, and we call InsertCard then ATMMachine changes to HasCard state. In this state if we call InsertCard again then we get an error because because the state of ATMMachine will have changed and it will not call NoCard.insertCard, but it will call HasCard.insertCard which will be an error message
