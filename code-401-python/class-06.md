# Read 06 - OOP Part02

>## dependency injection

## what is types of dependency injection?

1. constructor injection: the dependencies are provided through a class constructor.
2. setter injection: the client exposes a setter method that the injector uses to inject the dependency.
3. interface injection: the dependency provides an injector method that will inject the dependency into any client passed to it




## Benefits of using dependency injection
1. Helps in Unit testing.
2. Boiler plate code is reduced, as initializing of dependencies is done by the injector component.
3. Extending the application becomes easier.
4. Helps to enable loose coupling, which is important in application programming.



## Disadvantages of dependency injection
1. It’s a bit complex to learn, and if overused can lead to management issues and other problems.
2. Many compile time errors are pushed to run-time.
3. Dependency injection frameworks are implemented with reflection or dynamic programming. This can hinder use of IDE automation, such as “find references”, “show call hierarchy” and safe refactoring.



>## Software Design Patterns Simplified

## There is 3 major types of design patterns:

### 1. Creational Patterns:

### Some Creational Patterns:

* #### Factory Method :  The factory pattern is used to replace class constructors, abstracting the process of object generation so that the type of the object instantiated can be determined at run-time.

* #### Singleton : The singleton pattern ensures that only one object of a particular class is ever created. All further references to objects of the singleton class refer to the same underlying instance.

* #### Abstract Factory : The abstract factory pattern is used to provide a client with a set of related or dependent objects. The “family” of objects created by the factory are determined at run-time.


### 2. Structural Patterns:

#### Some Structural Patterns:

* #### Facade : The facade pattern is used to define a simplified interface to a more complex subsystem.

* #### Adapter : The adapter pattern is used to provide a link between two otherwise incompatible types by wrapping the “adaptee” with a class that supports the interface required by the client.

* #### Decorator : The decorator pattern is used to extend or alter the functionality of objects at run-time by wrapping them in an object of a decorator class. This provides a flexible alternative to using inheritance to modify behavior.

### 3. Behavioral Patterns:

#### Some Behavioral Patterns:
* #### Observer : The observer pattern is used to allow an object to publish changes to its state. Other objects subscribe to be immediately notified of any changes.

* #### Mediator : The mediator pattern is used to reduce coupling between classes that communicate with each other. Instead of classes communicating directly, and thus requiring knowledge of their implementation, the classes send messages via a mediator object.
* #### Chain of Responsibility : The chain of responsibility pattern is used to process varied requests, each of which may be dealt with by a different handler.

>## What is Risk Analysis in Software Testing and how to perform it?

### The probability of any unwanted incident is defined as Risk. In Software Testing, risk analysis is the process of identifying the risks in applications or software that you built and prioritizing them to test. After that, the process of assigning the level of risk is done. The categorization of the risks takes place, hence, the impact of the risk is calculated.

## Why use Risk Analysis?
### In any software, using risk analysis at the beginning of a project highlights the potential problem areas. After knowing about the risk areas, it helps the developers and managers to mitigate the risks. When a test plan has been created, risks involved in testing the product are to be taken into consideration along with the possibility of the damage they may cause to your software along with solutions.
