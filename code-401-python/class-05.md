# Read 05 - Intro to OOP

>## What Is Object-Oriented Programming

* ### Object-oriented programming combines a group of data attributes with functions or methods into a unit called an "object." Typically, OOP languages are class-based, which means that a class defines the data attributes and functions as a blueprint for creating objects, which are instances of the class. Popular class-based OOP languages include Java, Python and C++. Multiple independent objects may be instantiated—or represented—from the same class and interact with each other in complex ways.


>## 4 basic concepts of object-oriented programming

## 1. Encapsulation :

### The word “encapsulate” means to enclose something. Just like a pill "encapsulates" or contains the medication inside its coating, encapsulation works in a similar way in OOP: by forming a protective barrier around the information contained within a class from the rest of the code.

### In OOP, we encapsulate by binding the data and functions that operate on that data into a single unit known as the class. This hides private details of a class from the outside world and only exposes functionality important for interfacing with it. When a class does not allow calling code access to its private data directly, we say that it is well encapsulated.

## 2. Abstraction :
### Often, it’s easier to reason and design a program when you can separate the interface of a class from its implementation, and focus on the interface. This is akin to treating a system as a “black box,” where it’s not important to understand the gory inner workings in order to reap the benefits of using it.

### This process is called “abstraction” in OOP because we are abstracting away the implementation details of a class and only presenting a clean, easy-to-use interface via the class’s member functions. Carefully used, abstraction helps isolate the impact of changes made to the code so that if something goes wrong, the change will only affect the implementation details of a class and not the outside code.

## 3. Inheritance :

### Object-oriented languages that support classes almost always support the notion of “inheritance.” Classes can be organized into hierarchies where a class might have one or more parent or child classes. If a class has a parent class, we say it is derived or inherited from the parent class and it represents an “IS-A” type relationship. That is to say, the child class “IS-A” type of the parent class.

### Therefore, if a class inherits from another class, it automatically obtains much of the same functionality and properties from that class and can be extended to contain separate code and data. A nice feature of inheritance is that it often leads to good code reuse since a parent class’s functions don’t need to be re-defined in any of its child classes.

### Consider two classes: one being the superclass—or parent—and the other being the subclass—or child. The child class will inherit the properties of the parent class, possibly modifying or extending its behavior. Programmers applying the technique of inheritance arrange these classes into what is called an “IS-A” type of relationship.

## 4. Polymorphism :

### In OOP, polymorphism allows for the uniform treatment of classes in a hierarchy. Therefore, calling code only needs to be written to handle objects from the root of the hierarchy, and any object instantiated by any child class in the hierarchy will be handled in the same way.

### Because derived objects share the same interface as their parents, the calling code can call any function in that class’ interface. At run-time, the appropriate function will be called depending on the type of object passed leading to possibly different behaviors.