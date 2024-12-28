USEFUL DIAGRAM:

![](https://i.imgur.com/VvbOluC.png)


# <mark style="background: #FFB8EBA6;">01 Basic Concepts:</mark>

OOP is a way of writing programmes

An object is an abstraction of something in the **problem domain** e.g. Table

<mark style="background: #FFB8EBA6;">Purpose:</mark>
- promotes an understanding of the real world
- Provides a practical basis for computer implementation

<mark style="background: #FFB8EBA6;">Characteristics:</mark>
- State
- Behaviour
- Identity

![](https://i.imgur.com/xQzOKfN.png)


<mark style="background: #FFB8EBA6;">Three Pillars of OOP:</mark>
- Encapsulation
- Inheritance
- Polymorphism

### <mark style="background: #FFB8EBA6;">Encapsulation:</mark>

Fundamentally, <mark style="background: #FFB8EBA6;">encapsulation</mark> is a simple concept – hide the internals (data & behaviour) of an object from other objects

Fundamentally, encapsulation is a simple concept – hide the internals (data & behaviour) of an object from other objects.  

With this, we can then control the access to the object’s internals whatever way we want. Also, we can implement and modify the implementation without affecting other objects (i.e. the rest of the system)

Private variables can only be access through the methods provided

![](https://i.imgur.com/15pSpAz.png)


Client objects can be thought of as sending messages to other objects when calling methods

![](https://i.imgur.com/Lsxh5Rn.png)

<mark style="background: #FFB8EBA6;">Interfaces:</mark> Defines how one object is allowed to interact with another object.

An object’s <mark style="background: #FFB8EBA6;">interface</mark> is the set of publicly accessible operations.  

It is worth mentioning here that there is generally no need to automatically generate the accessor (getter) and mutator (setter) methods for a private member variable (something that development tools might do). They should only exist if other objects need to get/set/change the variable – this is often the case but not always.

![](https://i.imgur.com/CMgrQ9G.png)

### <mark style="background: #FFB8EBA6;">Inheritance:</mark>

A class (<mark style="background: #FFB8EBA6;">subclass</mark>) can extend another class (the <mark style="background: #FFB8EBA6;">superclass</mark>)

The subclass inherits the methods of the superclass by implementing its own version of the method.

The subclass may override a method in the superclass by implementing its own version of the method. The new version may call the method of the superclass.

Enables subtype <mark style="background: #FFB8EBA6;">Polymorphism</mark>.

![](https://i.imgur.com/avYUyRZ.png)

Methods from the superclass can be overridden in the subclass.

The superclass is a <mark style="background: #FFB8EBA6;">generalisation</mark> and the subclass is a <mark style="background: #FFB8EBA6;">specialisation</mark> "is-a" relationship.

The terms <mark style="background: #FFB8EBA6;">base class</mark> and <mark style="background: #FFB8EBA6;">derived class</mark> are also used for the superclass and subclass, respectively.
A class diagram is intended to give a clear picture of the classes in a system and the relationships between them.

<mark style="background: #FFB8EBA6;">Note:</mark> In Java, every class has the class Object as a superclass, i.e. class Object is the root of  the class hierarchy in Java. See the API documentation.

<mark style="background: #FFB8EBA6;">Note:</mark> 
- <mark style="background: #FFB8EBA6;">Statically typed</mark> languages: check types of variables at compile-time and enforce constraints.  
- <mark style="background: #FFB8EBA6;">Dynamically typed</mark> languages: check types at run-time.  
- <mark style="background: #FFB8EBA6;">Strongly typed</mark> languages: do not allow implicit conversions between types.  
- <mark style="background: #FFB8EBA6;">Weakly typed</mark> languages: will perform implicit conversions between different types.  

E.g.  
Java / C# - Statically and Strongly typed  
Python – Dynamically and Strongly typed  
C++ - Statically and Weakly typed  
JavaScript - Dynamically and Weakly typed

### <mark style="background: #FFB8EBA6;">Polymorphism:</mark>

The core of polymorphism is that objects of different types can be accessed through a single interface - they appear the same but behave differently.

![](https://i.imgur.com/oVkXdYQ.png)

<mark style="background: #FFB8EBA6;">Subtype:</mark>  
- declare a class as a subclass of another class  
- inheritance - subclass inherits attributes and operations of the superclass  
- operation overriding - subclass can override superclass operations (same name and  signature)  
- relevant to both statically typed & dynamically typed languages  
- design and code re-use - aids maintainability  

<mark style="background: #FFB8EBA6;">Parametric:</mark> 
- Generic data-types and generic operation parameters  

<mark style="background: #FFB8EBA6;">Function/operator/method overloading - Ad hoc:</mark>  
- Same name but different signatures (number and type of parameters)  
- Relevant to both statically typed & dynamically typed languages - just a matter of when the type is determined - compile-time / run-time  

<mark style="background: #FFB8EBA6;">Coercion - Ad hoc</mark>  
- implicit type conversion  
- e.g. convert integer to floating point; convert subclass type to superclass type

![](https://i.imgur.com/DOBxFKS.png)

There are various ways in which the Animal, Pig, Dog and Cat classes/interfaces could be implemented but the key illustration is that there is one interface (defined by Animal), three different concrete types (possibly sub classes of <mark style="background: #FFB8EBA6;">Animal</mark>) and different behaviour when the speak() method is invoked on an <mark style="background: #FFB8EBA6;">Animal</mark> object (method overriding).

## <mark style="background: #FFB8EBA6;">UML Review:</mark>


<mark style="background: #FFB8EBA6;">Model Views:</mark>
- **User View** - Use-case diagrams
- **Structural View** - Class Diagrams. How the system does it.
- **Behavioural View** - Sequence Diagrams. State chart diagrams.
- **Environment View** Deployment Diagrams.
- **Implementation View** - Component Diagrams

<mark style="background: #FFB8EBA6;">UML Definitions:</mark>

<mark style="background: #FFB8EBA6;">Class:</mark>
- A class is a description of a set of objects that share attribute, operations (behaviours), relationship with other objects.  
- The purpose of a class is to declare a collection of operations, and attributes that fully describe the structure and behaviour for all objects of that class.  

<mark style="background: #FFB8EBA6;">Object:</mark>  
- An Object is an instance that originates from a class; it is structured and behaves according to its class.  

<mark style="background: #FFB8EBA6;">Generalisation:</mark>  
- Taxonomic(hierarchical) relationship between a more general element and a more specific element that is fully consistent with the first element and that adds additional information

<mark style="background: #FFB8EBA6;">Generalisations in Object Classes:</mark>
- Arrange real-world object classes into hierarchies
- Models the difference and similarities between classes
- When two classes are arranged into a hierarchy the more specialised class will <mark style="background: #FFB8EBA6;">inherit</mark> all the characteristics from the more generalised class (superclass).

![](https://i.imgur.com/dwd5DbP.png)

<mark style="background: #FFB8EBA6;">Generalisation has a number of benefits:</mark>
- Reduces redundancy – if there was only an Employee class with an employeeType attribute, we would need all three attributes of the subclasses above in the Employee class. So if an instance/object represents a monthly paid employee then hourlyRate and hoursWorked may be redundant (this could depend on other factors...)  
- Reuses design artefacts – e.g. superclasses and already designed subclasses  
- Reuses compile time artefacts – existing classes  
- Reduces brittleness – adding new subclasses does not affect existing classes/code  
- Eases maintainability & understanding


### <mark style="background: #FFB8EBA6;"> Review of the Object Model:</mark>

The object model is a general way of thinking about the structure of OO programs

The fundamental property of the object model is that computation takes place in and between objects

The object model is the common computational model shared by UML and Object-Oriented Programming Languages.

Individual Objects are responsible for maintaining part of a system's data and for implementing aspects of its overall functionality.

An object supports the data stored by that object and the methods, or functions, to access and update the data it contains.

Developing an <mark style="background: #FFB8EBA6;">Object Model</mark> allows us to use the real world domain to drive the initial structure of the system. This initial “mapping” of the real world domain/concepts is then also called the <mark style="background: #FFB8EBA6;">conceptual</mark> or <mark style="background: #FFB8EBA6;">domain model</mark>.

### <mark style="background: #FFB8EBA6;">Network of Objects:</mark>

The global behaviour of the system emerges from the interaction of many distinct objects. The relationships between the data stored in the individual objects must be recorded.  

These requirements are supported by allowing objects to be linked together - this is typically achieved by enabling one object to hold a reference to another.  

The object model views a running program as a  network, or graph of objects. The objects form  the nodes in the graph, and the arcs connecting the objects are known as <mark style="background: #FFB8EBA6;">links</mark>. 

The object network represents relationships between data entities - Objects can be created and destroyed at run-time and the links between them can also be changed - the structure, or topology, of the object network is therefore highly dynamic, changing as a program runs.

# <mark style="background: #FFB8EBA6;">02 Implementing Classes:</mark>

### <mark style="background: #FFB8EBA6;">Associations:</mark>

Associations are <mark style="background: #FFB8EBA6;">one type of relationship</mark> that can be modelled between classes (others are Dependencies, Generalisations, Realisations).  

Associations <mark style="background: #FFB8EBA6;">describe the reason</mark> for the relationship between the classes and the rules that govern it (e.g. Multiplicities).  

Associations can be termed <mark style="background: #FFB8EBA6;">Aggregate</mark> (one class is part-of or sub-ordinate to the other).  

Associations can be termed <mark style="background: #FFB8EBA6;">Composite</mark> (one class is considered the whole and the other is considered part-of the whole, the part-of class has a lifetime that is dependent on the other).  

Associations can be <mark style="background: #FFB8EBA6;">Directed</mark> – the relationship only goes one way (uni-directional). If not, they are considered bi-directional.

<mark style="background: #FFB8EBA6;">Implementing Associations:</mark>
- We can implement a simple association using a <mark style="background: #FFB8EBA6;">class member variable</mark> that holds a reference  
- A <mark style="background: #FFB8EBA6;">reference member variable only allows one direction of navigability</mark> (from the object holding the reference to the object being referenced)  
- If we keep the navigability to one direction (if possible) then the <mark style="background: #FFB8EBA6;">implementation will be less complicated</mark> – it keeps the responsibility of maintaining the association to one class

Associations provide relationships between the classes as defined in the real-world problem domain. 

They dictate how instances of the classes (the objects) can be linked at runtime and are implemented as class attributes.  

Dependencies are another type of class relationship that can be modelled at design time (denoted by a dashed arrow). These relationships show that one class is dependent on another. 

An example of this maybe that an instance of one class acquires a link to an instance of the other at some point in its lifetime (possibly a return parameter from an operation call) and uses it to perform an operation. If that operation were to change, it could affect the class that is dependent on it. The links between these objects are not modelled/implemented as class attributes (member variables).

### <mark style="background: #FFB8EBA6;">Implementing Uni-directional Associations:</mark>

<mark style="background: #FFB8EBA6;">One to One – 0..1 (optional association)</mark>
 
A reference variable in an instance of a class (object) can hold a reference to another object OR It can hold the null reference

This means the “default” multiplicity for such an association is “0..1”

![](https://i.imgur.com/pof8QGD.png)

The association is implemented by a member variable in the ‘``Account``’ class holding a reference to an instance of the ‘``DebitCard``’ class.

Remember the reason that 0..1 is the default multiplicity here is that if the “``theCard``” reference can be null (in the code) it means there is no ``DebitCard`` object associated with the Account object. The association 0..1 dictates that this is correct as it means none or one ``DebitCard`` object may be associated with an Account object. We will see later that the situation can be different for one-to-one associations (i.e. not optional).

![](https://i.imgur.com/SVp8UXL.png)

Here the ``Account`` class has the responsibility to  
maintain the association because it has the  
reference member variable.  

In this example, there is a simple accessor (getter) and mutator (setter) but also a business method ``removeCard()``

We can also make this association <mark style="background: #FFB8EBA6;">immutable</mark>:
![](https://i.imgur.com/7KaVU5t.png)

There are a number of ways this could be implemented. The getter and setter are commonly implemented but methods like ``removeCard``, ``addCard`` or ``cancelCard`` might be modelled as part of the design and be more appropriate. These kind of methods might be identified through the business use cases.  

For the immutable example, we can see that the ``setCard()`` will only work if a card is  
not currently assigned. In this case, in order to change the card on an account, the  
``removeCard()`` must be invoked first – in this way we can encapsulate any business  
logic that needs to be executed when a card is removed from an account.

<mark style="background: #FFB8EBA6;">One to One – 1..1 (mandatory association):</mark>

![](https://i.imgur.com/OQqm5cr.png)

Consider the above model – in this case the <mark style="background: #FFB8EBA6;">Guarantor is mandatory</mark>  

A <mark style="background: #FFB8EBA6;">null reference</mark> to a Guarantor in the Account  
class <mark style="background: #FFB8EBA6;">cannot be allowed to exist</mark>.

This needs to be handled in the code implementing the association.

![](https://i.imgur.com/n0sl4Ay.png)

For a one to one mandatory association the 1..1 is denoted just by the single digit 1 meaning there must be 1 and only one Guarantor object linked to the Account object.  

This is implemented in the code of the constructor – a non null reference must be given to the constructor or an exception will be thrown.

<mark style="background: #FFB8EBA6;">One to Many – 1..M Associations:</mark>

![](https://i.imgur.com/hVKfMb9.png)

Consider the above model – in this case a Manager object can be linked with many Account objects  

A Manager object will need to hold multiple references to Account objects

This needs to be handled in the code implementing the association. We will need some sort of Collection object.
- In Java we can use an ``ArrayList`` object  
- This object gives us all the facilities to handle a collection of references  
- The Manager object then just concentrates on the business operations

![](https://i.imgur.com/QWMOINI.png)

<mark style="background: #FFB8EBA6;">Note 1:</mark> “0..\*” can be denoted as just “\*”. This would be an optional association – the Manager object may not have any Account objects linked to it (but can have many). “1..*” means the Manager object must have one Account object linked to it. Also remember, something like “0..5” is also possible if the business requirements dictate it.  

<mark style="background: #FFB8EBA6;">Note 2:</mark> This is a unidirectional association – the system requirements here would lead us to model that it needs to identify all the accounts for a manager but it doesn’t need to be able to identify the manager for a specific account. I.e. the Manager object knows the accounts its linked to but Account objects do not know what manager object they are linked to.  

<mark style="background: #FFB8EBA6;">Note 3:</mark> The code above is simplified for illustrative purposes. E.g. we would need to make sure that we don’t add duplicate references to the ``ArrayList``.

### <mark style="background: #FFB8EBA6;">Implementing Bi-directional Associations:</mark>

<mark style="background: #FFB8EBA6;">Bidirectional Links:</mark>  

Some associations need to be navigated in both directions 
- remember references are unidirectional – this means it will take two references to implement a link in each direction  
- the association can be implemented by including a suitable reference field in each of the associated classes

![](https://i.imgur.com/6UOG61u.png)

<mark style="background: #FFB8EBA6;">Note</mark> - above is a conceptual diagram showing the domain model. Conceptual diagrams define the association and not how that association might be implemented.

<mark style="background: #FFB8EBA6;">One-to-one Association traversed in both directions:</mark>

![](https://i.imgur.com/6XNaGW4.png)

<mark style="background: #FFB8EBA6;">Note</mark> – the diagram above would be considered a specification diagram as it contains additional information on how the model might be implemented. It shows two role-names which would correspond to the class attributes (member references) that might be implemented. It also show these classes as business classes.

<mark style="background: #FFB8EBA6;">One-to-Many Association traversed in both directions:</mark>

![](https://i.imgur.com/eAfVMvx.png)

![](https://i.imgur.com/1WAB9JO.png)

![](https://i.imgur.com/3e5zES1.png)

The concept is the same as one-to-one but in this case we can see that the Member  class will need to hold a collection of references to Book objects but the Book object only needs to hold one reference to a Member object

### <mark style="background: #FFB8EBA6;">Referential Integrity:</mark>

![](https://i.imgur.com/dddekWa.png)

With <mark style="background: #FFB8EBA6;">bi-directional associations</mark>, we need to consider how an operation of one class may effect the other associated class.  

E.g. If we had a member object with a set of <mark style="background: #FFB8EBA6;">book</mark> objects – each book object will have a reference to the <mark style="background: #FFB8EBA6;">member</mark> object. If we removed a book from the <mark style="background: #FFB8EBA6;">set of books</mark> in the <mark style="background: #FFB8EBA6;">member</mark> object’s <mark style="background: #FFB8EBA6;">set</mark>, then we should also set the reference to the member object in the <mark style="background: #FFB8EBA6;">book</mark> object to null to maintain <mark style="background: #FFB8EBA6;">referential integrity</mark>.

Essentially we don’t want objects with references to other objects that don’t have a reference back to them (for bi-directional relationships).

<mark style="background: #FFB8EBA6;">Referential Integrity Example (Member Class):</mark>

When borrowing a  book, we will create the bi-directional link between the Member object and the Book object  

As well as adding the book to its Set, it sets the member attribute of the book object to itself.
![](https://i.imgur.com/yulkpnE.png)

When returning a book, we will remove the link between the Member object and the Book object (in both directions)

As well as removing the book from its Set, it removes the member reference of the book object.

![](https://i.imgur.com/AgSkMAs.png)

Note the checks in the code to stop an infinite loop from occurring.  

As each object is calling back onto the other object when setting up and removing the links, we need these checks to stop an infinite loop happening. E.g. in the ``borrowBook()`` method in the Member class, there is a check to see if the book already exists in the set, if it does then it just returns.

<mark style="background: #FFB8EBA6;">Referential Integrity Example (Book Class):</mark>

As well as setting the member reference, it adds the book to the member object’s Set of books

![](https://i.imgur.com/Tu7Iqqh.png)

As well as removing the member reference it removes the book reference from the member object’s list

![](https://i.imgur.com/WzZcytJ.png)

Note again, the checks in the code to stop an infinite loop from occurring. In the ``setMember()`` operation, the member variable must be null before it will continue.

### <mark style="background: #FFB8EBA6;">Sequence Diagrams Revisited:</mark>

<mark style="background: #FFB8EBA6;">Object Links:</mark>
Consider an instance of the above class - it will contain two references to two Circle objects. This means that at runtime it will be linked to those objects.

![](https://i.imgur.com/JY5TeYm.png)

Vice versa, the two instances of this class (circleA and circleB) are linked to the client object

![](https://i.imgur.com/dekQZBg.png)

The actual <mark style="background: #FFB8EBA6;">link</mark> is provided by the references (``circleA`` and ``circleB``) within the client object – interestingly, this means that only the client object “knows” about the link. In this sense, the link is uni-directional.

Here we see the (java) code for an interaction between two objects. We can see that the ``SomeClient`` object invokes the ``setRadius()`` method on each of the Circle objects.

### <mark style="background: #FFB8EBA6;">Object Links:</mark>

<mark style="background: #FFB8EBA6;">Note</mark> when we talk about links we are referring to connections between objects <mark style="background: #FFB8EBA6;">at runtime</mark>. We have previously discussed modelling those <mark style="background: #FFB8EBA6;">at design time</mark> through associations.

![](https://i.imgur.com/hnuqeDk.png)

### <mark style="background: #FFB8EBA6;">Sequence Diagram:</mark>

Depicting how the code executes.

![](https://i.imgur.com/evsNZXV.png)

The client object first sends a synchronous message (``setRadius``) to ``circleA`` and then another to ``circleB``.

```Java
public class SomeClient {  
	SomeClient (Circle circleA,Circle circleB)  
	{  
		circleA.setRadius(10);  
		circleB.setRadius(12);  
	}  
}
```

### <mark style="background: #FFB8EBA6;">Collaborations:</mark>

![](https://i.imgur.com/HtleBkZ.png)

Model a set of classes that are capable of interacting for a set of purposes.  
- Collaboration / Communication Diagrams  
- <mark style="background: #FFB8EBA6;">Sequence Diagrams</mark>

A Collaboration is a UML artefact that is used to model how a set of classes can interact in order to realise a use case. Sequence diagrams play an important role as part of this.

### <mark style="background: #FFB8EBA6;">Types of Messages:</mark>

<mark style="background: #FFB8EBA6;">Synchronous:</mark>

![](https://i.imgur.com/uiYiWJs.png)

A message with a solid arrowhead at the end. If the message is a return message it appears as a dashed line rather than solid.

<mark style="background: #FFB8EBA6;">Asynchronous:</mark>

![](https://i.imgur.com/TGtBCoa.png)

A message with a line arrowhead at the end. If the message is a return message it appears as a dashed line rather than solid.

<mark style="background: #FFB8EBA6;">Lost:</mark>

![](https://i.imgur.com/zZMAWRu.png)

A lost message is one that gets sent to an object that is not modelled in the diagram. The destination for this message is a black dot.

<mark style="background: #FFB8EBA6;">Found:</mark>

![](https://i.imgur.com/tF1hr3y.png)

A found message is one that arrives from an unknown sender, or from an object that is not modelled in the diagram. The unknown part is modelled as a black dot.

<mark style="background: #FFB8EBA6;">Self-message:</mark>

A self message is usually a recursive call, or a call to another method belonging to the same object.

### <mark style="background: #FFB8EBA6;">Sequence Diagrams - Types of Frames:</mark>

![](https://i.imgur.com/2DgClPN.png)

<mark style="background: #FFB8EBA6;">alt</mark> models if / else / switch alternatives

<mark style="background: #FFB8EBA6;">opt</mark> models if conditions

A frame can be used to show how messages are sent between objects and are closely related to control flow / conditional branching in the code. <mark style="background: #FFB8EBA6;">loop</mark>, <mark style="background: #FFB8EBA6;">alt</mark> and <mark style="background: #FFB8EBA6;">opt</mark> are widely used.  

The above example shows the use of all three. We can see the use of <mark style="background: #FFB8EBA6;">alt</mark> dictates that the dispatch message is sent to different objects depending on the value of a variable.

### <mark style="background: #FFB8EBA6;">Dependencies & Associations:</mark>

<mark style="background: #FFB8EBA6;">Paths of Communication:</mark>

An association or dependency between two classes can be thought of as a <mark style="background: #FFB8EBA6;">path of communication</mark> between instances (objects) of those classes.

![](https://i.imgur.com/6mI0Ry7.png)

In the diagram above, objects of class A may talk to (i.e. send messages to) objects of class B and objects of class B may talk to objects of class A.  

Likewise, objects of classes B and C may also communicate. As there is no direct line of communication between A and C, objects of these classes <mark style="background: #FFB8EBA6;">may not communicate directly</mark>. If they do communicate, then there is an inconsistency in the model.

<mark style="background: #FFB8EBA6;">Note:</mark> Associations are implemented as member reference variables. Dependencies can also be implemented as reference variables (just not member variables). So in both cases, they set up the possibility for links to exist between objects and so the ability for those objects to communicate (send messages) with other.

### <mark style="background: #FFB8EBA6;">Principle of Least Knowledge:</mark>

<mark style="background: #FFB8EBA6;">Law of Demeter:</mark>

In response to a message M, an object O should send messages only to the following objects:  
1. O itself  
2. Objects which are sent as arguments to the message M  
3. Objects which O creates as part of its reaction to M  
4. Objects which are directly accessible from O, that is, using values of attributes of O.

In principle:  
- Each unit should have only limited knowledge about other units: only units "closely" related to the current unit.  
- Each unit should only talk to its friends; don't talk to strangers.  
- Only talk to your immediate friends.

The Principle of Least Knowledge is also known as the Law of Demeter. Essentially we want to decouple objects from each other as much as possible. This supports the goal of developing robust software. The less objects need to know about other objects the better, if things change or problems occur, the effects are then localised and should have much less of an knock-on effect on the rest of the system.

### <mark style="background: #FFB8EBA6;">Law of Demeter 1:</mark>

![](https://i.imgur.com/gaMQgJi.png)

![](https://i.imgur.com/vtU0xPQ.png)

In response to the message ``doSomething()``, object a sends a message to itself (invokes one of its own methods)

![](https://i.imgur.com/IO0o95i.png)

On the left we can see the structural (class diagram) and behavioural (sequence diagram) modelling that illustrates the first Law of Demeter. On the right we can see the implementation of it in java.

### <mark style="background: #FFB8EBA6;">Law of Demeter 2:</mark>

In response to a message M, an object O should send messages to objects which are sent as arguments to the message M

![](https://i.imgur.com/fHycGr9.png)

![](https://i.imgur.com/A10647D.png)

In response to the message ``doSomething()``, object c sends a message to object b (which was passed to it by the message).

![](https://i.imgur.com/LcdIcNb.png)

Note the dependency (dashed) arrow, stereotyped by ``<<parameter>>``. Recall that a dependency means the objects may be linked at runtime but an explicit association is not modelled at design time.

### <mark style="background: #FFB8EBA6;">Law of Demeter 3:</mark>

In response to a message M, an object O should send messages to objects which O creates as part of its reaction to M.

![](https://i.imgur.com/3zw7mGu.png)

![](https://i.imgur.com/OwSN80j.png)

In response to the message ``doSomething()``, object d sends a message to object b which is a locally scoped reference (instantiated by d) to an object of type B.

![](https://i.imgur.com/MJp1IOn.png)

Note the dependency (dashed) arrow, stereotyped by ``<<local>>``. In this case, the model tells us that an instance of D will hold a locally scoped reference to an object of type B. It is not an association which would be implemented as the B object being a member reference variable (attribute) of class D. We can see in the code that the D object gets a reference to the B object by creating it.

### <mark style="background: #FFB8EBA6;">Law of Demeter 4:</mark>

In response to a message M, an object O should send messages to objects which are directly accessible from O, that is, using values of attributes of O.

![](https://i.imgur.com/NBTktrM.png)


Note, an association (solid) arrow is modelled. b is a member variable of E which implements the association.
![](https://i.imgur.com/73sQWrR.png)

In response to the message ``doSomething()``, object e sends a message to object b which is a which is as attribute (member variable) of e.

![](https://i.imgur.com/5jTGuzv.png)

![](https://i.imgur.com/Wo9fNSF.png)

Note that in this scenario, there is an association between classes E and B (solid arrow). The implementation shows that b will be a member variable (attribute) of E.  

Also note that in the model (class diagram) we do not see b (E’s member attribute) in the diagram. This is normally the case as the association already defines it.

### <mark style="background: #FFB8EBA6;">Illustration of the principle of Least Knowledge:</mark>

Consider the following classes:
![](https://i.imgur.com/4FQ4X2L.png)

An object of class Person may talk to (i.e. send messages to) an object of class Oracle  

An object of class Oracle may talk to an object of class Knowledge.  

As there is no direct line of communication between Person and Knowledge, an object of class Person may not communicate directly with an object of class Knowledge.  

If they need to communicate directly, then there is a problem with the diagram.

Next we will illustrate the principle using a somewhat contrived example to ensure an understanding of it.

![](https://i.imgur.com/pPF8Vv6.png)

The problem here is that the ``Person`` object is <mark style="background: #FFB8EBA6;">“reaching inside”</mark> the ``Oracle`` object to get access to the ``Knowledge`` object. The Person object then ‘talks’ to the ``Knowledge`` object. This would work fine but it is inconsistent with the model above. This breaks the principle of least knowledge as there is no need for Person objects to know anything about, or even the existence of, ``Knowledge`` objects.  

It should be the responsibility of the Oracle class (and <mark style="background: #FFB8EBA6;">only</mark> the Oracle class in this case) to communicate with the Knowledge class. We should change this implementation to decouple the Person class from the Knowledge class.

### <mark style="background: #FFB8EBA6;">Current Implementation:</mark>

![](https://i.imgur.com/oeoTSki.png)

![](https://i.imgur.com/cTnS7iA.png)

<mark style="background: #FFB8EBA6;">Sequence Diagram of the existing implementation:</mark>

![](https://i.imgur.com/V0kDmyF.png)

Direct communication between a Person object and a Knowledge object

Above is a sequence diagram of the current implementation. The diagram clearly shows the inconsistency between the structural model (class diagram) and the behavioural model (as seen by the message from the Person object to the Knowledge object).

<mark style="background: #FFB8EBA6;">What to do?</mark>

![](https://i.imgur.com/GolHZus.png)

Person object now calls the new “wrapper” method, i.e. it no longer reaches inside the Oracle object to get the Knowledge object.

A new “wrapper” method (``answerToLife``) is added to the Oracle class. It now communicates with the Knowledge object.

Note here, that in the ``Oracle`` class, the “getter” method has been removed.  

According to the current model there is no need for it. Removing it stops other objects from getting direct access to the ``Knowledge`` object (which, remember, is a private attribute of the ``Oracle`` class), i.e. the ``Oracle`` class has sole responsibility for communication with the ``Knowledge`` object.

<mark style="background: #FFB8EBA6;">Better Implementation:</mark>

![](https://i.imgur.com/PnUomsa.png)

![](https://i.imgur.com/DEWAD5N.png)

<mark style="background: #FFB8EBA6;">Sequence Diagram of the new implementation:</mark>

![](https://i.imgur.com/h4Iya85.png)

This diagram is now consistent with the class diagram. The communication between the objects now adheres to the <mark style="background: #FFB8EBA6;">Law of Demeter</mark>.

Above is the sequence diagram of the new implementation. Any changes made to the Knowledge class will have no effect on the Person object.

### <mark style="background: #FFB8EBA6;">Letting Company Use Case Example:</mark>

A letting company operates a service whereby they provide apartment block properties for rent. Each apartment would have a specific rent associated with it and may or may not be occupied.  

We want to model a system which can realise the following use case...

![](https://i.imgur.com/wbeWzAy.png)

Example of the Principle of Least Knowledge where the initial solution would execute correctly from a business perspective and would pass tests etc. but where there would be inconsistencies between the structural and behavioural models that could lead to brittleness in the software.

<mark style="background: #FFB8EBA6;">Letting Company - Class diagram:</mark>

A letting company operates a service whereby they provide apartment block properties for rent. Each apartment would have a specific rent associated with it and may or may not be occupied.

![](https://i.imgur.com/PWiawFo.png)

A simplified example for illustrative purposes. Above is the structural model based on  
the use case brief description.

<mark style="background: #FFB8EBA6;">Letting Company - Sequence Diagram:</mark>

Junior developer’s attempt

![](https://i.imgur.com/4fxJZDt.png)

Above is a design (behavioural model) that would realise the use case based on the structural model. This would work fine from a business perspective and would pass tests etc. 

However, there is an inconsistency – the sequence diagram clearly shows communication between the ``lettingCompany`` object and the ap object which is inconsistent with the structural model. In this solution, the ``LettingCompany`` class needs to know everything about the Apartment class and makes them tightly coupled. 

There is no need for this, the structural model shows that we should keep these decoupled and reduce potential brittleness.

<mark style="background: #FFB8EBA6;">Letting Company - Sequence Diagram:</mark>

2nd attempt:
![](https://i.imgur.com/BlJiUPl.png)

We create a new method to fix the issue

Note the use of the opt and loop frames

Note no messages sent between the ``lettingCompany`` and ``ap`` objects

The first attempt did not comply with the association model

We introduce a new method to fix this issue. This gives the responsibility of calculating the rent for a property to the Property class rather than the ``LettingCompany`` object needing to know about Apartments, occupation and rent – these are business attributes that it does not need to know about.  

The 2nd attempt decouples the LettingCompany and Apartment classes which is the way it should be according to the model. Now, any future changes or issues with the Apartment class will not affect the LettingCompany class. By following this principle in our design and coding, we end up with a much more robust system which leverages the OO design and development paradigm well.

### <mark style="background: #FFB8EBA6;">Company Department Use Case Example:</mark>

A (company) department has many employees, each of which may have a number of jobs assigned to them. Each job would require a set number of hours to be associated with it.  

We want to model a system which can realise the following use case...

![](https://i.imgur.com/Jr4biCO.png)

Another example of the Principle of Least Knowledge where the initial solution would execute correctly from a business perspective and would pass tests etc. but where there would be inconsistencies between the structural and behavioural models that could lead to brittleness in the software.

<mark style="background: #FFB8EBA6;">Department - Sequence Diagram:</mark>

Junior developer’s attempt:
![](https://i.imgur.com/R9LpPcf.png)

Similar to the previous example – the department object is communicating with the job object...

<mark style="background: #FFB8EBA6;">Department - Sequence Diagram:</mark>

![](https://i.imgur.com/pBgp9N5.png)

Note no messages sent between department and job

New operation introduced – ``getTotalHours()`` – decouples Department and Job classes.

# <mark style="background: #FFB8EBA6;">03 Object Types within Software Engineering</mark>

### <mark style="background: #FFB8EBA6;">Interface Class:</mark>

Note here that we are discussing the concept of an interface (not to be confused with user interfaces) - interfaces can be implemented in a number ways and may depend on the programming language being used.

<mark style="background: #FFB8EBA6;">Definition:</mark> An <mark style="background: #FFB8EBA6;">Interface</mark> is a selection of externally visible public operations

<mark style="background: #FFB8EBA6;">Two modelling requirements arise:</mark>
1. A class may be required to present more than one external interface to other collaborating classes  
2. Several classes may be required to present the same interface.

An <mark style="background: #FFB8EBA6;">Interface Class</mark> provides for this design. It specifies the externally-visible (public) operations of another class.

Again, note that we are defining what a interface means in terms of classes and objects. We can leverage interfaces in our software design/engineering to create robust solutions to modelling requirements.

It provides a mechanism for a class to communicate with a <mark style="background: #FFB8EBA6;">restricted view</mark> of another class  

An interface class has:
- no internal structure 
- no attributes  
- no implementation of its own  
- It compares to an abstract class (no instances). 

An interface class typically <mark style="background: #FFB8EBA6;">specifies only a limited part of the behaviour</mark> of another class.

An interface (class) allows us to specify a particular operation or set of operations that would be required (invoked) by other objects in certain contexts. Any object that provides an implementation of those operations is said to realise the interface. In Java, we can say that a class <mark style="background: #FFB8EBA6;">implements</mark> an interface.  

One typical use of interfaces is to specify a subset of operations of a class so that other objects can only utilise those operations when working with an instance of that class – see next slide.

![](https://i.imgur.com/tsgGiET.png)

<mark style="background: #FFB8EBA6;">Modelling requirement:</mark> A class may be required to present more than one external interface to other collaborating classes e.g. a restricted view.

<mark style="background: #FFB8EBA6;">Dependency</mark> relationship – a customer object will “see” a Viewable object and so will only be able to invoke the ``display()``  operation.

<mark style="background: #FFB8EBA6;">Realisation</mark> relationships between two classes - one class offers the interface of the other.  

The <mark style="background: #FFB8EBA6;">Advert</mark> class provides the implementation of the operations specified in both interfaces.

![](https://i.imgur.com/ljZfQfw.png)

In this case, there are two interfaces defined. The Advert class realises (implements) both interfaces. We can see the Viewable interface only allows a Customer object to utilise the ``display()`` method of an Advert object (the Customer objects only “sees” a Viewable object).

<mark style="background: #FFB8EBA6;">Modelling requirement:</mark>  Several classes may be required to present the same interface e.g. an API specification

<mark style="background: #FFB8EBA6;">Java Database Connectivity:</mark>

![](https://i.imgur.com/YyB6fBs.png)

Most major RDBMS providers supply JDBC code libraries to allow java developers to  
easily connect to their database.

In this case, interfaces are defined for a set of classes that need to be implemented/supplied by the vendor of an RDBMS.  

Different RDBMS’s will have different implementations of the set of interfaces. In this case, Java code that needs to communicate with a particular RDBMS will be “coded to the interface” - the code just “sees” an interface it can use and not an instance of the implementing class) and so does not even know which implementation of the interfaces it is using (Oracle, MySQL, Postgres etc.). This provides a very loose coupling between the application code and the database.  

An example of a benefit is that we could replace the RDBMS with a completely different one and not have to alter our system in anyway except perhaps some configuration.

![](https://i.imgur.com/Db2gEtk.png)

<mark style="background: #FFB8EBA6;">JDBC:</mark>
- Each RDBMS has its own implementation of the JDBC Java Interfaces  
- E.g. Each JDBC library must have a class that implements the ``Statement`` interface  
- ``Statement`` - the object used for executing a static SQL statement and returning the results it produces.

JDBC code libraries referred to as JDBC Drivers.  

Essentially consist of a single jar file containing all the necessary java classes. E.g. mysql-connector-java-x.x.xx.jar.  

Once the jar file is included in the classpath, the specific JDBC classes can be used by your own code.

<mark style="background: #FFB8EBA6;">e.g JDBC Connection Interface:</mark>

![](https://i.imgur.com/t2t7XrB.png)

Specific JDBC libraries (Oracle, MySQL, PostgreSQL, etc.) each have their own implementation of this interface (among others...) i.e. we have many different implementing objects that provide the same interface.

<mark style="background: #FFB8EBA6;">Sample Java code to retrieve data from an RDBMS:</mark>

![](https://i.imgur.com/vrd0a8U.png)

The <mark style="background: #FFB8EBA6;">url</mark> giving the location of the database (would not normally hard-code this here).

The <mark style="background: #FFB8EBA6;">SQL</mark> query to execute against the database

The <mark style="background: #FFB8EBA6;">ResultSet</mark> object contains the data returned from the database

The ``DriverManager`` class is used to obtain an appropriate ``Connection`` object.  When JDBC implementations (jar files) are included in a project – they register  themselves with the ``DriverManager`` class. When our code asks the ``DriverManager`` to get a Connection object , it uses the URL we give it to find the appropriate Driver for that URL (i.e. type of database). That Driver object is an implementation of the JDBC Driver interface – in this case it is MySQL implementation. Oracle, Postgres etc. would have their own Driver interface implementations. So we have many different classes providing the same interface(s) to our code.  

You might see legacy java code like this:  
``Class.forName( "com.mysql.jdbc.Driver" ); `` 

We can write this in our code above the ``DriverManager.getConnection()`` call, which explicitly tells the ``DriverManager`` what Driver implementation to use.  

This works fine but is no longer necessary since JDBC 4.


### <mark style="background: #FFB8EBA6;">Boundary & Controller Classes:</mark>

Boundary and Controller classes are two other common types of objects found in software architecture.

<mark style="background: #FFB8EBA6;">Three-Tier Architecture:</mark>

The aim is to separate the classes that have the responsibility for the interface with the user, or with other systems, (boundary classes) from the business classes (entity classes) and the classes that handle the application logic (control classes)

![](https://i.imgur.com/tYt1LaI.png)


<mark style="background: #FFB8EBA6;">Reasons for separating classes:</mark>
- <mark style="background: #FFB8EBA6;">Logical:</mark> Enables presentation designs that are independent of the physical hardware and the software technology 
- <mark style="background: #FFB8EBA6;">Interface Independence:</mark> Object attributes may be input/displayed in several ways and this responsibility is assigned to the presentation classes  
- <mark style="background: #FFB8EBA6;">Reuse:</mark> Of classes from all 3 layers

Note that there may be more than three tiers, and that the logical layers can map to physical platforms in a number of ways.

<mark style="background: #FFB8EBA6;">Presentation Layer:</mark>
- Handles the interface with users and other connected systems 
- Formats and presents data at the interface  
- Provides a mechanism for data entry by the user, but the events are handled by control classes
- Presentation can be many forms:  
	- for display as text or charts  
	- printing on a printer  
	- speech synthesis  
	- formatting in JSON/XML for transferral  
	
- Does not contain the business logic—rules like ‘A Campaign must have one and only one Campaign Manager’.  
- Does not handle validation, beyond perhaps simple checks on formatting, value ranges and lookup list.

The combination of boundary and controller classes often provide the architecture to support external access to the software system.

![](https://i.imgur.com/N0UMVve.png)

This is a simple illustration of an external request. The UI boundary class provides the user interface through which the user can make a request, the request is then handled by the controller where it coordinates the invocation of the business logic.

# <mark style="background: #FFB8EBA6;">04 Patterns in Design:</mark>

### <mark style="background: #FFB8EBA6;">Design Patterns:</mark>

Have you ever encountered a design problem and silently thought: <mark style="background: #FFB8EBA6;">I wonder if anyone has developed a solution to this?</mark>

What if there was a standard way of describing a problem (so you could look it up), and an organized method for representing the solution to the problem?

<mark style="background: #FFB8EBA6;">Design patterns</mark> are a codified method for describing problems and their solution that allows the software engineering community to capture design knowledge in a way that enables it to be reused.  

Each pattern describes a problem that occurs over and over again in our environment and then describes the core of the solution to that problem. “a three-part rule which expresses a relation between a certain <mark style="background: #FFB8EBA6;">context</mark>, a <mark style="background: #FFB8EBA6;">problem</mark>, and a <mark style="background: #FFB8EBA6;">solution</mark>.”

### <mark style="background: #FFB8EBA6;">Basic Concepts:</mark>

Context allows the reader to understand the environment in which the problem resides and what solution might be appropriate within that environment.  

A set of requirements, including limitations and constraints, acts as a system of forces that influences how the problem can be interpreted within its context and how the solution can be effectively applied.

### <mark style="background: #FFB8EBA6;">Categories of Patterns:</mark>

<mark style="background: #FFB8EBA6;">Creational patterns</mark> focus on the creation, composition, and representation of objects, e.g.  
- <mark style="background: #FFB8EBA6;">Abstract factory pattern:</mark> centralize decision of what factory to instantiate  
- <mark style="background: #FFB8EBA6;">Factory method pattern:</mark> centralize creation of an object of a specific type choosing one of several implementations  

<mark style="background: #FFB8EBA6;">Structural patterns</mark> focus on problems and solutions associated with how classes and objects are organized and integrated to build a larger structure, e.g.,  
- <mark style="background: #FFB8EBA6;">Adapter pattern:</mark> 'adapts' one interface for a class into one that a client expects  
- <mark style="background: #FFB8EBA6;">Aggregate pattern:</mark> a version of the Composite pattern with methods for aggregation of children  

<mark style="background: #FFB8EBA6;">Behavioural patterns</mark> address problems associated with the assignment of responsibility between objects and the manner in which communication is effected between objects, e.g.,  
- <mark style="background: #FFB8EBA6;">Command pattern:</mark> Command objects encapsulate an action and its parameters  
- <mark style="background: #FFB8EBA6;">Chain of responsibility pattern:</mark> Command objects are handled or passed on to other objects by logic-containing processing objects

### <mark style="background: #FFB8EBA6;">Other Collections of Patterns:</mark>

<mark style="background: #FFB8EBA6;">Architectural patterns</mark> describe broad-based design problems that are solved using a structural approach.  

<mark style="background: #FFB8EBA6;">Data patterns</mark> describe recurring data-oriented problems and the data modelling solutions that can be used to solve them.  

<mark style="background: #FFB8EBA6;">Component patterns</mark> (also referred to as design patterns) address problems associated with the development of subsystems and components, the manner in which they communicate with one another, and their placement within a larger architecture  

<mark style="background: #FFB8EBA6;">Web App patterns</mark> address a problem set that is encountered when building WebApps and often incorporates many of the other patterns categories just mentioned.

### <mark style="background: #FFB8EBA6;">Frameworks:</mark>

Patterns themselves may not be sufficient to develop a complete design.  
- In some cases it may be necessary to provide an implementation-specific skeletal infrastructure, called a <mark style="background: #FFB8EBA6;">framework</mark>, for design work.  
- That is, you can select a “reusable mini-architecture that provides the generic structure and behavior for a family of software abstractions, along with a context ... which specifies their collaboration and use within a given domain.”  

A framework <mark style="background: #FFB8EBA6;">is not an architectural pattern</mark>, but rather a skeleton with a collection of “plug points” (hooks and slots) that enable it to be adapted to a specific problem domain.  

The plug points enable you to integrate problem specific classes or functionality within the skeleton.

### <mark style="background: #FFB8EBA6;">Describing a Pattern:</mark>

<mark style="background: #FFB8EBA6;">Pattern name:</mark> describes the essence of the pattern in a short but expressive name  

<mark style="background: #FFB8EBA6;">Intent:</mark> describes the pattern and what it does  

<mark style="background: #FFB8EBA6;">Problem:</mark> describes the problem that the pattern addresses  

<mark style="background: #FFB8EBA6;">Motivation:</mark> provides an example of the problem  

<mark style="background: #FFB8EBA6;">Context:</mark> describes the environment in which the problem resides including application domain  

<mark style="background: #FFB8EBA6;">Forces:</mark> lists the system of forces that affect the manner in which the problem must be solved (including limitations / constraints)  

<mark style="background: #FFB8EBA6;">Solution:</mark> provides a detailed description of the solution proposed for the problem  

<mark style="background: #FFB8EBA6;">Collaborations:</mark> describes how other patterns contribute to the solution  

<mark style="background: #FFB8EBA6;">Consequences:</mark> describes the potential trade-offs that must be considered when the pattern is implemented and consequences of its use  

<mark style="background: #FFB8EBA6;">Implementation:</mark> identifies special issues that should be considered when implementing the pattern  

<mark style="background: #FFB8EBA6;">Known uses:</mark> provides examples of actual uses of the design pattern in real applications  

<mark style="background: #FFB8EBA6;">Related patterns:</mark> cross-references related design patterns

### <mark style="background: #FFB8EBA6;">Thinking in Patterns:</mark>

Shalloway and Trott suggest the following approach that enables a designer to think in patterns:  
1. Be sure you understand the big picture—the context in which the software to be built resides. The requirements model should communicate this to you.  
2. Examining the big picture, extract the patterns that are present at that level of abstraction.  
3. Begin your design with ‘big picture’ patterns that establish a context or skeleton for further design work.  
4. “Work inward from the context” looking for patterns at lower levels of abstraction that contribute to the design solution.  
5. Repeat steps 1 to 4 until the complete design is fleshed out.  
6. Refine the design by adapting each pattern to the specifics of the software you’re trying to build.

### <mark style="background: #FFB8EBA6;">Design Tasks</mark>

Examine the requirements model and develop a problem hierarchy.

Beginning with a broad problem, determine whether one or more architectural patterns are available for it.

Using the collaborations provided for the architectural pattern, examine subsystem or component level problems and search for appropriate patterns to address them.

Repeat until all broad problems have been addressed

Be certain to refine the design as it is derived from patterns using design quality criteria as a guide.

### <mark style="background: #FFB8EBA6;">Common Design Mistakes</mark>

Not enough time has been spent to understand the underlying problem, its context and forces, and as a consequence, you select a pattern that looks right, but is inappropriate for the solution required.  

Once the wrong pattern is selected, you refuse to see your error and force fit the pattern.  

In other cases, the problem has forces that are not considered by the pattern you’ve chosen, resulting in a poor or erroneous fit.  

Sometimes a pattern is applied too literally and the required adaptations for your problem space are not implemented.

### <mark style="background: #FFB8EBA6;">DAO Pattern:</mark>

Recall our discussion on database connectivity...

![](https://i.imgur.com/N6Zw4RG.png)

Most major RDBMS providers supply JDBC code libraries to allow java developers to easily connect to their database

![](https://i.imgur.com/Vmpufox.png)

Each RDBMS has its own implementation of the JDBC Java Interfaces  

E.g. Each JDBC library must have a class that implements the Statement interface  

<mark style="background: #FFB8EBA6;">Statement</mark> - the object used for executing a static SQL statement and returning the results it produces.

![](https://i.imgur.com/P5NDyuk.png)

The url giving the location of the database (would not normally hard-code this here).

The SQL query to execute against the database

The ``ResultSet`` object contains the data returned from the database

### <mark style="background: #FFB8EBA6;">Managing Data:</mark>

Consider a table in a database called ``customer`` with the following columns:  
```SQL
custNumber (integer)  
custName (varchar)  
contactLastName (varchar)  
contactFirstName (varchar)  
phone (varchar)  
creditLimit (double)
```

![](https://i.imgur.com/bIjAIDX.png)

### <mark style="background: #FFB8EBA6;">The Data Access Object (DAO) Pattern:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Isolate the application/business layer from the persistence layer using an abstract API.

![](https://i.imgur.com/Eh5ugrh.png)

Encapsulates all the activity required to connect to the database and retrieve the data. It creates a Customer object, fills it with the data and returns it to the client.

![](https://i.imgur.com/kZUiWmJ.png)

### <mark style="background: #FFB8EBA6;">Example DAO code:</mark>

![](https://i.imgur.com/sH0OppO.png)

This example illustrates the methods that our DAO class might have

Note, we still need to add database connection handling code to this.

<mark style="background: #FFB8EBA6;">Example client code using the DAO object:</mark>
![](https://i.imgur.com/sDaUDfl.png)

### <mark style="background: #FFB8EBA6;">For reference: JDBC PreparedStatement:</mark>

We have used the <mark style="background: #FFB8EBA6;">Statement</mark> class to send SQL to the DBMS.  

SQL is sent to the DBMS which has to compile it before execution.  

``PreparedStatement`` objects are given the SQL on creation of the object which is then normally sent to the DBMS at that time.  

When our code wants to execute the statement – the DBMS does not have to compile it.  

We can re-use our ``PreparedStatement`` object without requiring re-compilation by the DBMS

![](https://i.imgur.com/9SUykju.png)

![](https://i.imgur.com/SBwm9yJ.png)

# <mark style="background: #FFB8EBA6;">05 Exploring Patterns:</mark>

### <mark style="background: #FFB8EBA6;">Client - Server(Static):</mark>

![](https://i.imgur.com/7HArCaY.png)

<mark style="background: #FFB8EBA6;">HTTP</mark> – Hypertext Transfer Protocol, rules used to transfer data across the internet  

<mark style="background: #FFB8EBA6;">Client</mark> – Any software – PC, Laptop, Smartphone, Tablet  

<mark style="background: #FFB8EBA6;">Web Server</mark> – Computer system that provides the service of responding to HTTP requests, can “serve” web site pages, images etc. using an HTTP response

### <mark style="background: #FFB8EBA6;">Client – Server (Dynamic):</mark>

![](https://i.imgur.com/ltmvYBb.png)

Web Server – as well as static content serving, the server provides an execution environment for application code to return dynamic content.

<mark style="background: #FFB8EBA6;">Servlet Container:</mark>  
- A servlet is a java class that can be directly invoked by a http client – e.g. a web browser.  
- The java code executing in the servlet, for example, may access a relational database and retrieve information that can either directly returned to the http client or processed further into html and then returned to the client.

### <mark style="background: #FFB8EBA6;">Example Servlet:</mark>

```Java
public class UserController extends HttpServlet {  
	public UserController() {  
		super();  
	} 
	//HTTP GET from client handled here
	protected void doGet( HttpServletRequest request, HttpServletResponse response)  
	throws ServletException, IOException  
	{  
		// code...  
	}  
	//HTTP POST from client handled here
	protected void doPost( HttpServletRequest request, HttpServletResponse response)  
	throws ServletException, IOException  
	{  
		//code...  
	}  
}
```

### <mark style="background: #FFB8EBA6;">We can use the DAO's and other classes from a Servlet:</mark>

![](https://i.imgur.com/R737R6t.png)

What do we do with the data retrieved / result of request?

### <mark style="background: #FFB8EBA6;">The Model View Controller (MVC) Pattern</mark>

![](https://i.imgur.com/df8I2Im.png)

A pattern for designing an architecture that separates the application logic from the user interface logic

This allows development, testing and maintenance to be achieved independently

### <mark style="background: #FFB8EBA6;">MVC Applied to Web Applications:</mark>

![](https://i.imgur.com/oLcmvVP.png)
![](https://i.imgur.com/Wl5X6R2.png)

### <mark style="background: #FFB8EBA6;">Using JSP for the View:</mark>

<mark style="background: #FFB8EBA6;">JSP:</mark> Java Server Pages

Writing a JSP source file

<mark style="background: #FFB8EBA6;">static_example.html:</mark>
```html
<html>  
	<body bgcolor="yellow">  
		<center>  
			<h2>Hello World</h2>  
		</center>  
	</body>  
</html>
```

<mark style="background: #FFB8EBA6;">static_example.jsp</mark>
```JSP
<html>  
	<body bgcolor="yellow">  
		<center>  
			<h2>Hello world</h2>  
		</center>  
	</body>  
</html>
```

<mark style="background: #FFB8EBA6;">dynamic_example.jsp</mark>
```JSP
<html>  
	<body bgcolor="yellow">  
		<center>  
			<h2>Hello World</h2>  
			//View accesses an object to display some information
			<p> <%= new java.util.Date() %> </p>  
		</center>  
	</body>  
</html>
```

### <mark style="background: #FFB8EBA6;">Requesting a JSP file:</mark>

Browser requests a ``.jsp`` file instead of a ``.html`` file from the server  

If you just renamed a .html to a ``.jsp`` file, the first time you loaded/requested the file it would take longer to load than the HMTL version...  

What’s happening?  
The first time the .jsp page is requested by the browser, the server reads the file and converts it to a java class and compiles it. Once compiled, it is executed completely as a java program.  

This generated java class is a <mark style="background: #FFB8EBA6;">servlet</mark>

![](https://i.imgur.com/HqL0bno.png)

### <mark style="background: #FFB8EBA6;">Service Layer:</mark>

A set of classes, each of which provide a set of application operations.  

E.g. ``UserService`` class provides a login operation. A typical implementation is a Service class that has a corresponding DAO attribute.  

E.g. ``UserService`` has an attribute ``userDao`` which is of type ``UserDao``.

![](https://i.imgur.com/o3RHbLt.png)

![](https://i.imgur.com/CXZzvRZ.png)

### <mark style="background: #FFB8EBA6;">Singleton Pattern:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Ensure that a class has only one instance, and provide a global point of access to it  

Only one object will ever exist in memory. It is not possible to create a second object of the same class in memory

```Java
public class MyServer {  
	//Must be static, as static methods can only access static attributes. Only one myServer object created, even if some other member method created another object of MyServer.
	private static MyServer myServer = null; 
	
	//private constructor ensures only methods of the class can call the constructor.
	private MyServer() {}  
	
	public static synchronized MyServer getInstance() {  
		if (myServer == null){ 
			//Creates object first time. Returns the same myServer object each time the method is called. 
			myServer = new MyServer();  
		}  
		return myServer;  
	}  
	// other attributes, methods etc.  
}
```

```Java
public class MyServerTest { 
	//Line below is not permitted as constructor is private.
	// MyServer myServer = new MyServer() ;  
	MyServer server1 = MyServer.getInstance() ;  
	MyServer server2 = MyServer.getInstance() ;  
	//As clients cannot create objects, getInstance() must be a static method. This static method provides a global point of access. It always returns reference to the same object.
	if (server1 == server2)  
		System.out.println("Same server") ;  
	else  
		System.out.println("Different servers") ;  
	}  
}
```

### <mark style="background: #FFB8EBA6;">Command Pattern:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Encapsulate a request as an object, thereby letting you  parameterise clients with different requests, queue or log requests.  

E.g. Request from client browser to the server to list all users – we can encapsulate the code to handle this request on the server into a  single object.

<mark style="background: #FFB8EBA6;">Recall - Example Servlet</mark>
```Java
public class UserController extends HttpServlet {  
	
	public UserController() {  
		super();  
	}  
	
	protected void doGet( HttpServletRequest request, HttpServletResponse response)  
	throws ServletException, IOException  
	{  
	// code...  
	}  
	
	protected void doPost( HttpServletRequest request, HttpServletResponse response)  
	throws ServletException, IOException  
	{  
	//code...  
	}  
}
```

### <mark style="background: #FFB8EBA6;">Using the Command Pattern with JSP/Servlets Example snippet from a simple Servlet</mark>

<mark style="background: #FFB8EBA6;">Code inside doGet() method:</mark>
```Java
//Action requested from web page.
else if ( request.getParameter("action").equalsIgnoreCase("listUsers") ) {  

	//The user wants a list if all users...  
	//Use the UserService class to get all Users...  
	List<User> users = new ArrayList<User>();  
	users = userService.getAllUsers();  
	//Put the list of users into the session so that JSP(the View) can display them...  
	session.setAttribute("users", users);  
	forwardToJsp = "/listUsers.jsp";  
}
```

### <mark style="background: #FFB8EBA6;">New Servlet Code:</mark>

```Java
if ( request.getParameter("action").equalsIgnoreCase("listUsers") ) 
{  
	//The user wants a list of all users...  
	//Code to handle this is moved to the ListUsersCommand object. Note the use of a Command Interface
	Command command = new ListUsersCommand();  
	forwardToJsp = command.execute(request, response);  
}
```

```Java
public interface Command {  
	
	public String execute(HttpServletRequest request, HttpServletResponse response);  
}  

public class ListUsersCommand implements Command {  

	public String execute(HttpServletRequest request, HttpServletResponse response) {  
		UserService userService = new UserService();  
		String forwardToJsp = "";  
		HttpSession session = request.getSession();  
		//Make the call to the 'Model' by using the UserService class to get all Users...  
		List<User> users = new ArrayList<User>();  
		users = userService.getAllUsers();  
		//Put the list of users into the session so that JSP(the View) can pick them up and display them...  
		session.setAttribute("users", users);  
		forwardToJsp = "/listUsers.jsp";  
		return forwardToJsp;  
	}  
}
```

### <mark style="background: #FFB8EBA6;">The Simple Factory Pattern:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Provide a class for creating an instance of one of several possible classes depending on the data provided to it. Usually all classes that it returns have a common parent interface or class, but each performs a task differently.  

E.g. a <mark style="background: #FFB8EBA6;">CommandFactory</mark> object that can instantiate and return <mark style="background: #FFB8EBA6;">Command</mark> objects to the calling code.  

The objects that it returns are specific Command objects like <mark style="background: #FFB8EBA6;">ListUsersCommand</mark> – however, they are treated as <mark style="background: #FFB8EBA6;">Command</mark> objects because all specific <mark style="background: #FFB8EBA6;">Command</mark> objects (e.g. ``ListUsersCommand``) implement the ``Command Interface``.

```Java
public class CommandFactory {  
	... 
	//Implemented as a singleton – private constructor 
	private CommandFactory() 
	{}  
	...  
	//Note, this method returns the object as a Command, however, the specific Command implementation is what is returned (e.g. ListUsersCommand)
	public synchronized Command createCommand(String commandStr) {  
	Command command = null;  
	//Instantiate the required Command object...  
	if (commandStr.equals("LoginUser")) {  
	command = new LoginUserCommand();  
	}  
	//Depending on what information is passed to the createCommand method, the factory will create the specific command
	if (commandStr.equals("ListUsers")) {  
	command = new ListUsersCommand();  
	}  
	if (commandStr.equals("ViewUserProfile")) {  
	command = new ViewUserProfileCommand();  
	}  
	//Return the instantiated Command object to the calling code...  
	return command;// may be null  
}
```

### <mark style="background: #FFB8EBA6;">Using the CommandFactory from our Servlet:</mark>

```Java
if ( request.getParameter("action").equalsIgnoreCase("listUsers") ) {  
	//The user wants a list if all users...  
	CommandFactory factory = CommandFactory.getInstance();  
	Command command = factory.createCommand("ListUsers");  
	forwardToJsp = command.execute(request, response);  
}
```

### <mark style="background: #FFB8EBA6;">Front Controller Pattern:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Provide a centralised point of access for handling client requests in a web application.  

Our <mark style="background: #FFB8EBA6;">servlet</mark> acts as <mark style="background: #FFB8EBA6;">Front Controller</mark> – it accepts all <mark style="background: #FFB8EBA6;">User</mark> related requests from the client (browser), calls the relevant ``command.execute()`` method and forwards the server to the next page.

### <mark style="background: #FFB8EBA6;">UserController Servlet:</mark>

```Java
protected void doGet(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {  
	processRequest (request, response);  
}  

protected void doPost(HttpServletRequest request, HttpServletResponse response) throws ServletException, IOException {  
	processRequest(request, response);  
}  
/**  
* Common method to process all client requests (GET and POST)  
*/  
private void processRequest(HttpServletRequest request, HttpServletResponse response) {  
	//Execute the appropriate command...  
}
```

### <mark style="background: #FFB8EBA6;">Sending a request through doGet() / doPost()</mark>

<mark style="background: #FFB8EBA6;">This sends the data using Http POST:</mark>
```JSP
<form action="UserController" method="post">  
	<input type="hidden" name="action" value="listUsers" />  
	<input type="submit" value="List Users" />  
</form>
```

<mark style="background: #FFB8EBA6;">This sends the data using Http GET:</mark>
```JSP
<a href="UserController?action=listUsers">List All Users</a>
```

### <mark style="background: #FFB8EBA6;">Application Example using multiple patterns:</mark>

Web Application example  

Start with a Login User use case  
1. User enters username and password  
2. User clicks Login button  
3. System validates username / password  
4. 4a Normal flow - user presented with options page
4. 4b Alternative flow - if invalid, authentication message displayed with option to return to login page

![](https://i.imgur.com/O1i4zYO.png)

### <mark style="background: #FFB8EBA6;">Login Page - Static html</mark>

![](https://i.imgur.com/u05kcwO.png)

This action (command) drives the request through the back end

### <mark style="background: #FFB8EBA6;">Front Controller:</mark>

![](https://i.imgur.com/7gUvsPk.png)

This method processes any http POST requests.

For completeness, here is the ``forwardToPage`` method implementation.

![](https://i.imgur.com/NhS8rTU.png)

### <mark style="background: #FFB8EBA6;">Command Factory:</mark>

![](https://i.imgur.com/Etp0cWu.png)

Implements the singleton pattern

![](https://i.imgur.com/L4Vl3N8.png)

The ``CommandFactory`` object itself still has no explicit knowledge of the command implementation it is instantiating.  

It uses the reflective method ``theClass.newInstance()`` which invokes the zero argument constructor.

### <mark style="background: #FFB8EBA6;">LoginUserCommand:</mark>

![](https://i.imgur.com/hgLTBIW.png)

Accepts the client request and invokes the business service

### <mark style="background: #FFB8EBA6;">User Service:</mark>

![](https://i.imgur.com/Gny3y6K.png)

In this instance, the service just calls through to the DAO object.

### <mark style="background: #FFB8EBA6;">UserDao:</mark>

![](https://i.imgur.com/gRenAmN.png)

In this example, we are simply using JDBC, however, we could implement code here that utilises an Object Relational Mapping framework.

### <mark style="background: #FFB8EBA6;">Login Successful View – loginSuccess.jsp</mark>

![](https://i.imgur.com/JfkF6AV.png)

The view accesses the data made available by the model

### <mark style="background: #FFB8EBA6;">This gives us a separation of the layers:</mark>

![](https://i.imgur.com/Vk3kBPO.png)

### <mark style="background: #FFB8EBA6;">Eclipse Dynamic Web Project:</mark>

![](https://i.imgur.com/qPLVJYz.png)

Our package structure reflects our layered design

Each package contains the set of classes appropriate to that layer

![](https://i.imgur.com/TvdBWHi.png)

# <mark style="background: #FFB8EBA6;">06 Exploring Patterns 2:</mark>

### <mark style="background: #FFB8EBA6;">Context Object Pattern:</mark>

![](https://i.imgur.com/YbB0MRL.png)

<mark style="background: #FFB8EBA6;">Intent:</mark> Avoid using protocol-specific system information outside of its relevant context.  

The Command classes we used in our Web Application were <mark style="background: #FFB8EBA6;">protocol dependent</mark>.  

```JSP
public interface Command 
{  
	String execute(HttpServletRequest request, HttpServletResponse response);  
}
```

### <mark style="background: #FFB8EBA6;">Context Object Pattern:</mark>

This makes it <mark style="background: #FFB8EBA6;">difficult to test</mark> these classes outside of their context or to re-use them in another context.  

The <mark style="background: #FFB8EBA6;">Context Object</mark> pattern may be used to write these classes in a <mark style="background: #FFB8EBA6;">protocol-independent way</mark>.  

The simplest implementation of <mark style="background: #FFB8EBA6;">Context Object</mark> in this case involves using a Map (e.g. a HashMap) for storing the relevant data  

This can make it <mark style="background: #FFB8EBA6;">easy to test</mark> these new Command classes.

```Java
package command ;  
import java.util.Map;  

public interface Command {  
	String execute(Map<String, Object> map) ;  
}
```

``HttpServletRequest`` is replaced by Map  

Examine the Map interface in the Java documentation.

![](https://i.imgur.com/xxt6z7G.png)

``HttpServletRequest`` is replaced by ``Map``

``request.setAttribute( /* etc. */ )``  
is replaced by  
``myMap.put( /* etc. */ )``

As the ``ListUsersCommand`` class is <mark style="background: #FFB8EBA6;">no longer protocol-dependent</mark>, it is a simple matter to test the class without starting the web server (e.g. Tomcat).

### <mark style="background: #FFB8EBA6;">Context Object Pattern - makes testing easier:</mark>

![](https://i.imgur.com/WD52tI5.png)

![](https://i.imgur.com/qjacRZy.png)

### <mark style="background: #FFB8EBA6;">getParameterMap():</mark>

This method returns a ``java.util.Map`` of the parameters of this request. Request parameters are extra information sent with the request. For HTTP servlets, parameters are contained in the query string or posted form data.  

Note: for the map returned from the method `getParameterMap()` the <mark style="background: #FFB8EBA6;">key</mark> is of type String and the <mark style="background: #FFB8EBA6;">value</mark> is of type String[].

### <mark style="background: #FFB8EBA6;">Wrapper Patterns:</mark>

- Adapter  
- Decorator  
- Proxy  
- Bridge

### <mark style="background: #FFB8EBA6;">Adapter</mark> 

<mark style="background: #FFB8EBA6;">Intent:</mark> Convert the interface of a class into another interface that clients expect. Adapter lets classes work together that couldn't otherwise because of  
incompatible interfaces.  

Provide an Adapter class which wraps the class that will ultimately perform the requested logic. The Adapter class provides a different interface to that provided by the wrapped class.

![](https://i.imgur.com/y0IqfTB.png)

![](https://i.imgur.com/cuEQNRu.png)

### <mark style="background: #FFB8EBA6;">Adapter Example:</mark>

![](https://i.imgur.com/3bBTjhy.png)

This class implements the interface that the client is expecting and an instance of this class converts the invocation onto the wrapped object.

### <mark style="background: #FFB8EBA6;">Decorator:</mark> 

<mark style="background: #FFB8EBA6;">Intent:</mark> add additional responsibilities dynamically to an object  

Used when you want to add functionality to an object, but not by extending that object's type  

Note, with the <mark style="background: #FFB8EBA6;">Adapter</mark> pattern, the intent was not add additional responsibility (decorations) as it is here but just to provide a different interface

![](https://i.imgur.com/zQySi4b.png)

### <mark style="background: #FFB8EBA6;">Decorator Example:</mark>

![](https://i.imgur.com/SZfJN5k.png)

### <mark style="background: #FFB8EBA6;">Proxy:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Provide a Placeholder for an object to control  
references to it.  

<mark style="background: #FFB8EBA6;">Used to:</mark>
- lazy-instantiate an object  
- hide call to a remote service  
- control access to an object

![](https://i.imgur.com/9hDf9X2.png)
![](https://i.imgur.com/4Ff1Ped.png)

### <mark style="background: #FFB8EBA6;">Proxy Example:</mark>

![](https://i.imgur.com/VVccG2l.png)

### <mark style="background: #FFB8EBA6;">Bridge:</mark>

<mark style="background: #FFB8EBA6;">Intent:</mark> Decouple abstraction from implementation so that the two can vary independently  

Define both the abstract interface and the underlying implementation – can swap out different implementations

![](https://i.imgur.com/OioX033.png)

### <mark style="background: #FFB8EBA6;">Bridge Example:</mark>

![](https://i.imgur.com/syxr1Gv.png)
![](https://i.imgur.com/QTWm7Wg.png)

### <mark style="background: #FFB8EBA6;">Bridge Example – using Inheritance</mark>

![](https://i.imgur.com/oQa6DUI.png)

### <mark style="background: #FFB8EBA6;">Bridge Example – using Aggregation</mark>

![](https://i.imgur.com/jvMa5mw.png)

### <mark style="background: #FFB8EBA6;">REST:</mark>

<mark style="background: #FFB8EBA6;">Architectural Style or Design Pattern?</mark>

W3C - A software system designed to support interoperable machine-to-machine interaction over a network  

<mark style="background: #FFB8EBA6;">Two implementations:</mark>  
- <mark style="background: #FFB8EBA6;">SOAP:</mark> Defines the runtime message that contains the service request and response – the <mark style="background: #FFB8EBA6;">envelope</mark>. SOAP is independent of any particular transport and implementation technology. 
- <mark style="background: #FFB8EBA6;">REST:</mark> Representational State Transfer. REST is an architectural style which is based on web-standards and the HTTP protocol.  REST was first described by Roy Fielding in 2000. Seen as an alternative to SOAP.

### <mark style="background: #FFB8EBA6;">REST:</mark>

In a REST based architecture <mark style="background: #FFB8EBA6;">everything is a resource</mark>. A  
resource is accessed via a common interface based on the HTTP standard methods.  

In an REST architecture you typically have a REST server which provides access to the resources and a REST client which accesses and modify the REST resources. Every resource should support the HTTP common operations. <mark style="background: #FFB8EBA6;">Resources are identified by global ID's</mark>.  

REST allows that <mark style="background: #FFB8EBA6;">resources have different representations</mark>, e.g. text, xml, json etc. The rest client can ask for specific representation via the HTTP protocol (Content Negotiation).

### <mark style="background: #FFB8EBA6;">HTTP Methods:</mark>

The ``HTTP`` standards methods which are typically used in ``REST`` are ``PUT``, ``GET``, ``POST``, ``DELETE``.  
- <mark style="background: #FFB8EBA6;">GET</mark> defines a reading access of the resource without side-effects. The resource is never changed via a GET request, e.g. the request has no side effects.  
- <mark style="background: #FFB8EBA6;">PUT</mark> updates an existing resource or creates a new resource.  
- <mark style="background: #FFB8EBA6;">DELETE</mark> removes the resources.  
- <mark style="background: #FFB8EBA6;">POST</mark> creates a new resource.

### <mark style="background: #FFB8EBA6;">Resources:</mark>

Data and functionality are considered resources and are accessed using <mark style="background: #FFB8EBA6;">Uniform Resource Identifiers (URIs)</mark>  

The resources are acted upon by using a set of simple, well-defined operations (the HTTP methods)  

E.g. GET http://localhost:8080/RestExample/rest/hello  
E.g. POST http://localhost:8080/RestExample/rest/hello

### <mark style="background: #FFB8EBA6;">JAX-RS:</mark>

<mark style="background: #FFB8EBA6;">JAX-RS</mark> - The Java API for <mark style="background: #FFB8EBA6;">RESTful</mark> Web Services  

<mark style="background: #FFB8EBA6;">JAX-RS</mark> is a Java programming language API designed to make it easy to develop applications that use the REST architecture.  

<mark style="background: #FFB8EBA6;">Jersey</mark> (http://jersey.java.net/) is a reference implementation of the JAX-RS specification (JSR 311).

### <mark style="background: #FFB8EBA6;">Implementing a REST Web Service:</mark>

All incoming requests from clients are received by a servlet.  

The servlet analyses the request and <mark style="background: #FFB8EBA6;">selects the correct class and method to execute</mark> based on the request.  

How does it know what class/method to execute?

### <mark style="background: #FFB8EBA6;">Java Annotations:</mark>

Within our server side code, we use annotations to specify what code should be executed for specific client requests.

### <mark style="background: #FFB8EBA6;">JAX-RS Hello World Example - No Annotation:</mark> 

```Java
public class HelloWorld {  
	public String sayPlainTextHello() {  
		return "Hello World";  
	}  
	public String sayXMLHello() {  
		return "<?xml version=\"1.0\"?>" + "<hello> Hello World" + "</hello>";  
	}  
	
	public String sayHtmlHello() {  
		return "<html> " + "<title>" + "Hello World" + "</title>"  + "<body>" + "Hello World" + "</body>" + "</html> ";  
	}  
}
```

### <mark style="background: #FFB8EBA6;">JAX-RS Hello World Example - Annotated</mark>

```Java
@Path("/helloworld")  
public class HelloWorld {  
	// HTTP GET with TEXT_PLAIN request...  
	@GET  
	@Produces(MediaType.TEXT_PLAIN)  
	public String sayPlainTextHello() {  
		return "Hello World";  
	}  
	// HTTP GET with TEXT_XML request...  
	@GET  
	@Produces(MediaType.TEXT_XML)  
	public String sayXMLHello() {  
		return "<?xml version=\"1.0\"?>" + "<hello> Hello World" + "</hello>";  
	}  
	// HTTP GET with TEXT_HTML request...  
	@GET  
	@Produces(MediaType.TEXT_HTML)  
	public String sayHtmlHello() {  
		return "<html> " + "<title>" + "Hello World" + "</title>" + "<body>" + "Hello World" + "</body>" + "</html> ";  
	}  
}
```

### <mark style="background: #FFB8EBA6;">Configuration File - web.xml:</mark>

```XML
<display-name>RestExample</display-name>  

<servlet>  
	<servlet-name>Jersey REST Service</servlet-name>  
	<servlet-class>...REST handling servlet class...</servlet-class>  
	<init-param>  
		<param-name>...packages...</param-name>  
		<param-value>com.restexample</param-value>  
	</init-param>  
	<load-on-startup>1</load-on-startup>  
</servlet>  
<servlet-mapping>  
	<servlet-name>Jersey REST Service</servlet-name>  
	<url-pattern>/rest/</url-pattern>  
</servlet-mapping>
```

### <mark style="background: #FFB8EBA6;">REST Requests:</mark>

![](https://i.imgur.com/0bXVrr8.png)

### <mark style="background: #FFB8EBA6;">REST Request – Java Client:</mark> 
```Java
public void sendPostHelloWorldExample() throws ClientProtocolException, IOException {  
	CloseableHttpClient client = HttpClients.createDefault();  
	HttpPost httpPost = new HttpPost("http://localhost:8080/RestExample/rest/hello");  
	List<NameValuePair> params = new ArrayList<NameValuePair>();  
	params.add( new BasicNameValuePair("greeting", "Here is my message...") );  
	httpPost.setEntity(new UrlEncodedFormEntity(params));  
	CloseableHttpResponse response = client.execute(httpPost);  
	//Do something with response...  
	client.close();  
}
```

### <mark style="background: #FFB8EBA6;">REST Request – Java (server side):</mark>

```Java
@POST  
@Produces(MediaType.TEXT_HTML)  
@Consumes(MediaType.APPLICATION_FORM_URLENCODED)  
public void postHelloWorld(  
@FormParam(“greeting") String greeting,  
@Context HttpServletResponse servletResponse  
) throws IOException {  
...  
//Do something with greeting...  
...  
}
```

### <mark style="background: #FFB8EBA6;">More Annotations:</mark>

![](https://i.imgur.com/1zZK7ij.png)

### <mark style="background: #FFB8EBA6;">Passing Parameters – in true REST style:</mark>

<mark style="background: #FFB8EBA6;">True REST style:</mark>
```HTTP
http://localhost:8080/RestExample/rest/hello/tom
```

Although you can see this type of usage
```HTTP
http://localhost:8080/RestExample/rest/hello?name=tom
```

```Java
@Path("/hello")  
public class HelloWorld {  
	....  
	@Path("{name}")  
	@GET  
	@Produces(MediaType.TEXT_PLAIN)  
	public String sayPlainTextHello(@PathParam(“name") String name) {  
	return "Hello " + name;  
}
```

### <mark style="background: #FFB8EBA6;">Benefits of REST:</mark>
- Familiar Simple Architecture  
- Modularity  
- OO Design  
- Abstraction

# <mark style="background: #FFB8EBA6;">07 Testing OO Systems:</mark>

### <mark style="background: #FFB8EBA6;">Introduction:</mark>

<mark style="background: #FFB8EBA6;">Testing conventional structured software use strategies:</mark>  
- Top down  
- Bottom up  
- White box  
- Black Box  

<mark style="background: #FFB8EBA6;">Top down and bottom up do not apply to the architecture of OO:</mark>  
- The architecture of OO software is a network of   collaborating classes.  
- Therefore it is necessary to test an OO system at a variety of different levels in an effort to uncover errors that may occur as classes collaborate with one another and the subsystems communicate across architectural layers.

### <mark style="background: #FFB8EBA6;">Approach to testing OO systems:</mark>

While black box and white box strategies are applied to OO systems as to conventional structured systems the <mark style="background: #FFB8EBA6;">tactics</mark> are different.  

As a class evolves through analysis and design to the coded stage, it becomes a target for <mark style="background: #FFB8EBA6;">test case design</mark>.  

Once classes are coded, a series of tests are designed that exercise class operations and examine whether errors exist as objects of one class collaborates with those of other classes.  

Attributes and operations are <mark style="background: #FFB8EBA6;">encapsulated</mark>  

Encapsulation produces test obstacles such as the reporting of the attribute values.  

<mark style="background: #FFB8EBA6;">Inheritance leads to additional challenges:</mark>  
- each level in the hierarchy produces a new context/environment of usage and requires retesting of the class at each level.  
- Each subclass in its own domain will require it’s own specific test cases.

White box testing can be applied to individual operations in isolation but the effort is sometimes better applied to these tests at the class level.  

Black box testing is also appropriate to OO and the Use Case is a natural source of the test case.

### <mark style="background: #FFB8EBA6;">Testing OO Analysis and Design Models:</mark>

Because OO analysis and design models align more closely in structure and content to the resultant OO software, testing can begin with a <mark style="background: #FFB8EBA6;">review of these models</mark>.  

<mark style="background: #FFB8EBA6;">These models iteratively evolve</mark> from informal representations of system requirements to detailed models of classes, attributes, operations, associations, messages and sequencing, events ..  

Therefore problems that are <mark style="background: #FFB8EBA6;">detected</mark> in these <mark style="background: #FFB8EBA6;">properties</mark> at the <mark style="background: #FFB8EBA6;">early iteration stages</mark> of <mark style="background: #FFB8EBA6;">analysis</mark> and <mark style="background: #FFB8EBA6;">design</mark> stage will circumvent problems at the later stages of development.  

Technical reviews of these models are considered as important as final testing

<mark style="background: #FFB8EBA6;">Correctness of OOA and OOD Models:</mark>  
- Syntactic Correctness: The notation and syntax should conform to the methodology  
- Semantic Correctness: The model is examined by expert users (domain experts) to check if it conforms to the real world problem as specified in use cases.

<mark style="background: #FFB8EBA6;">Consistency of OOA and OOD Models:</mark>  
- This involves cross-checking the class diagram with the detailed use-case descriptions, object collaboration diagram/interaction sequence diagrams and state transition diagrams to ensure that the associations and collaborations and responsibilities are consistent.

### <mark style="background: #FFB8EBA6;">Test Cases and the Class Hierarchy:</mark>

Inheritance does not remove the need to test all derived classes.  

Example:  
Class Derived redefines ``redefined()`` to serve in a local context.  

``Derived::redefined()`` must also be tested but does ``Derived::inherited()`` need to be tested?  

If ``Derived::inherited()`` calls ``Derived::redefined()`` then ``Derived::inherited()`` could misuse the new behaviour of ``Derived::redefined()`` and therefore must be tested as part of Derived.

![](https://i.imgur.com/z287VBd.png)

``Base::redefined()`` and ``Derived::redefined()`` are different as each implements different requirements and therefore require a separate set of test cases.  

The similarities in the operation will lead to similarities in the test cases.  

The better the OO design, the better the overlap in the inherited features.  

New test will be required only for the <mark style="background: #FFB8EBA6;">additional</mark> ``Derived::redefined()`` requirements.

### <mark style="background: #FFB8EBA6;">Test Cases for a Class:</mark>

The test should drive a selection of objects from the class through its states and for each test, the following characteristics should be tested for
- List of states for the class
- List of messages / operations invoked
- List of exceptions occurring

### <mark style="background: #FFB8EBA6;">Class/Unit Testing:</mark>

The classical strategy for testing structured software is <mark style="background: #FFB8EBA6;">unit testing</mark> (smallest indivisible module, subroutine etc.) leading progressively up to integration testing

These tests require regression testing to check for the effects of adding new components, major bug fixes, finishing with system testing and validation.  

In an OO context, <mark style="background: #FFB8EBA6;">encapsulation</mark> of <mark style="background: #FFB8EBA6;">attributes</mark> and <mark style="background: #FFB8EBA6;">operations</mark> into a class dictates that a class should be tested as an indivisible unit in conjunction with other collaborating classes.

Testing the operationX() in isolation may not uncover the subtle differences that it encounters with the environment of each subclass and the private attributes of its  
environment.  

Class testing is driven by the operations and attributes encapsulated within the class along with the state behaviour.

![](https://i.imgur.com/nqsY8gC.png)

### <mark style="background: #FFB8EBA6;">Scenario-Based Test Design:</mark>

Scenario-based testing concentrates on what the user does (rather than what the built product does).  

This means capturing the tasks (<mark style="background: #FFB8EBA6;">via use-cases</mark>) that the user has to perform, then applying them and their variants as tests. (essentially <mark style="background: #FFB8EBA6;">black box</mark>)

### <mark style="background: #FFB8EBA6;">Integration Testing:</mark>

Because OO software does not consist of a hierarchy of program modules as in classical structured design, top down and bottom up testing is not applicable.  

Further, adding operations one at a time and testing the class after each addition (incremental testing) can sometimes be ruled out due to the complexity of the collaborations required.

### <mark style="background: #FFB8EBA6;">Thread Based integration Testing:</mark>

The classes involved in one incoming event or input message (taken from the Interaction Sequence Diagram) for the thread and are assembled and tested.  

As threads are integrated, regression tests are done to check for any side effects of the integration.

![](https://i.imgur.com/fu4sQYR.png)

### <mark style="background: #FFB8EBA6;">Cluster Testing:</mark>

Grouping together cooperating classes that have similar functions or work together to accomplish a particular goal.  
- Typically the functionality of these classes would have already been tested using dummy drivers or test harness software.  
- This cluster may be modelled as a referenced sequence diagram.

![](https://i.imgur.com/ivLsCTX.png)

![](https://i.imgur.com/48Mxzog.png)

### <mark style="background: #FFB8EBA6;">Final steps of OO Testing:</mark>

As classes are integrated to form subsystems, thread-based, use-based and cluster-based testing along with fault-based approaches are applied to fully exercise collaborating classes.  

Collaboration or Interaction errors are targeted by exercising multiple subsystems in a single test case.

### <mark style="background: #FFB8EBA6;">Unit Testing:</mark>

<mark style="background: #FFB8EBA6;">Goal:</mark> Isolate individual parts of the program and show that they behave correctly  

<mark style="background: #FFB8EBA6;">Benefits:</mark> 
- A unit test explicitly specifies conditions that the individual program parts must satisfy.  
- This facilitates uncovering issues at an early stage and also ease in testing future modifications to ensure existing tests are still successful.  

<mark style="background: #FFB8EBA6;">Limitations:</mark> Testing cannot be expected to catch every error in the program

### <mark style="background: #FFB8EBA6;">Traditional Approach to Unit Testing:</mark>

<mark style="background: #FFB8EBA6;">Write the code:</mark>  
- Write your implementation
- e.g. java methods  

<mark style="background: #FFB8EBA6;">Test the code:</mark>  
- Write a class that instantiates an object of the class and tests the methods by executing them and checking results etc.  
- Fix any problems encountered...

### <mark style="background: #FFB8EBA6;">Test Driven Development (TDD):</mark>

Test Driven Development (TDD) is a design technique that drives the development process through testing. In essence you follow three simple steps repeatedly:  
1. Write a test for the next bit of functionality you want to add.  
2. Write the functional code until the test passes.  
3. Refactor both new and old code to make it well structured.

![](https://i.imgur.com/Vr1jE0g.png)

### <mark style="background: #FFB8EBA6;">Why TDD:</mark>
- Code Modularisation, Flexibility, Extensibility  
- Clean code  
- Leads to better design  
- Better code documentation 
- Well tested codebase

### <mark style="background: #FFB8EBA6;">What to do:</mark>

A design model will have defined our classes (attributes and <mark style="background: #FFB8EBA6;">operations</mark>).  

Tools can generally automatically create the skeleton code from the class diagram (e.g MyClass.java) – where methods have return values, one line of code is inserted which returns a null.  

Next we can write a test class (e.g. ``MyClassTest.java``) within which we write methods that test instances of our actual class.  

Remember, none of our methods actually have any code – so the tests should all fail.  

Take one test at a time and go back to our actual class and write just enough code to pass that test.

### <mark style="background: #FFB8EBA6;">Using Mock Objects in Testing:</mark>

When writing Unit tests, there can be a number of collaborating objects that are required to be available in order to test a given class.  
- Objects can be passed as parameters to the method under test.  
- The method under test may use objects which are attributes of its class.  

The test class needs to create the necessary instances of these objects so that the method under test can be called in an appropriate context  

This can be a challenging obstacle when testing non-trivial classes (object creation, attribute setting etc.).

Remember – when we are writing unit tests, we are only interested in testing the unit and not any other units that it requires to perform its function.  

What if we could ‘mock up’ any other objects that our object under test requires.  

This would free us up from being dependent on those other objects.

![](https://i.imgur.com/td4KrQy.png)

### <mark style="background: #FFB8EBA6;">Test Code - creating a mock object:</mark>

![](https://i.imgur.com/5mPYPHm.png)

![](https://i.imgur.com/lJhj2oR.png)

### <mark style="background: #FFB8EBA6;">Development Methodology:</mark>

<mark style="background: #FFB8EBA6;">TDD</mark> and <mark style="background: #FFB8EBA6;">Mock Objects</mark> can help in a number of ways when it comes to design and development.  

Once the domain model has been defined and behavioural models developed:  
- A set of interfaces can be defined and created  
- Different development teams can work on different aspects concurrently through the use of those interfaces  
- Unit tests can be written independent of required objects  

Think of a Service class that uses a <mark style="background: #FFB8EBA6;">Dao</mark> class...

# <mark style="background: #FFB8EBA6;">08 Object Relational Mapping:</mark>

The relational model does not equal the object-oriented model.

![](https://i.imgur.com/xqORCMB.png)

### <mark style="background: #FFB8EBA6;">ORM Introduction:</mark>

A technique for converting data between a relational database and an object-oriented programming language.  

A data persistence strategy  

Data persistence code/package  

The result of an ORM implementation is often likened to that of a ‘virtual object database’.  

ORM provides database independence  

The ability to seamlessly manipulate data stored in a relational database using an object programming language  

It provides a way to resolve the object-relational impedance mismatch.  

This object-relational impedance mismatch is considered to be the core problem.

### <mark style="background: #FFB8EBA6;">Object-relational Mismatch Issues:</mark>

How to map columns, rows, and tables to objects?  

How to deal with relationships?  

How to deal with associations?  

How to map object inheritance to relational tables?  

How to deal with the different design goals  
- The relational model is designed for data storage and retrieval. Its focus is in terms of how to best manage data.  
- The OO model is all about how to best model behaviour.  

How to make objects persistent?

![](https://i.imgur.com/EKJ5lFc.png)

### <mark style="background: #FFB8EBA6;">The Goals of ORM:</mark>

Take advantages of the things that Relational Database technologies do well  

Use the rich features of Object Technologies

![](https://i.imgur.com/vxx06VQ.png)

### <mark style="background: #FFB8EBA6;">Database Connectivity:</mark>

<mark style="background: #FFB8EBA6;">Open Database Connectivity</mark> (ODBC) - standard software API for using RDBMS.  
- ODBC spec. offers a procedural API for using SQL queries to access data.  
- Programmer can write applications without concern for the specifics of each RDBMS encountered.  

<mark style="background: #FFB8EBA6;">Java Database Connectivity</mark> (JDBC)

![](https://i.imgur.com/OMS9vfR.png)

Most major RDBMS providers supply JDBC code libraries to allow java developers to easily connect to their database.

![](https://i.imgur.com/VXwqF4Y.png)

Each RDBMS has its own implementation of the JDBC Java Interfaces  

E.g. Each JDBC library must have a class that implements the ``Statement`` interface  

``Statement`` - The object used for executing a static SQL statement and returning the results it produces

### <mark style="background: #FFB8EBA6;">JDBC Approaches:</mark>

<mark style="background: #FFB8EBA6;">Write SQL conversion methods by hand:</mark>  
- Tedious and requires lots of code  
- Extremely error-prone  
- Non-standard SQL ties the application to specific databases  
- Vulnerable to changes in the object model  
- Difficult to represent associations between objects

![](https://i.imgur.com/bYb7ZHJ.png)

### <mark style="background: #FFB8EBA6;">Other Approaches:</mark>

<mark style="background: #FFB8EBA6;">Object Oriented Database Systems:</mark>
- No complete query language implementation exists  
- RDMS standards more stable

<mark style="background: #FFB8EBA6;">NoSQL Database Systems:</mark>
- E.g. Document data stores  
- Relatively new and disparate  
- Performance variances

### <mark style="background: #FFB8EBA6;">A Common & Popular Solution:</mark>

Use an <mark style="background: #FFB8EBA6;">Object-Relational Mapping System</mark> (e.g. EclipseLink, Hibernate)  

Provides a simple API for storing & retrieving Java objects directly to and from the database  

<mark style="background: #FFB8EBA6;">Transparent:</mark> object model is unaware

![](https://i.imgur.com/GQZGpcF.png)

### <mark style="background: #FFB8EBA6;">ORM Architecture:</mark>

Middleware that manages persistence  

Provides an abstraction layer between the domain model and the database.

![](https://i.imgur.com/U6Z5J5H.png)

1) Data objects passed to DAO layer  
2) Method: SQL conversion  
3) Method: ORM using data/transfer objects

### <mark style="background: #FFB8EBA6;">Advantages of ORM:</mark>

<mark style="background: #FFB8EBA6;">Make RDBMS look like ODBMS:</mark> Data are accessed as objects, not rows and columns  

<mark style="background: #FFB8EBA6;">Simplify many common operations e.g.</mark>  ``manager.find(Company.class, "name = 'Mitsubishi'")``  

<mark style="background: #FFB8EBA6;">Improve portability:</mark> Separate DB specific SQL statements from application code  

<mark style="background: #FFB8EBA6;">Productivity:</mark>  
- Eliminates lots of repetitive code – focus on business logic  
- Database schema is generated automatically  

<mark style="background: #FFB8EBA6;">Maintainability:</mark>  
- Fewer lines of code –easier to understand  
- Easier to manage change in the object model  

<mark style="background: #FFB8EBA6;">Performance:</mark>  
- Lazy loading –associated/linked objects are fetched only when needed  
- Caching  

<mark style="background: #FFB8EBA6;">Database vendor independence:</mark>  
- The underlying database is abstracted away  
- Can be configured outside the application

### <mark style="background: #FFB8EBA6;">Mapping Objects to an RDBMS:</mark>

<mark style="background: #FFB8EBA6;">Two Approaches to Mapping:</mark>
![](https://i.imgur.com/IMbNMMn.png)

![](https://i.imgur.com/xweO7zo.png)

### <mark style="background: #FFB8EBA6;">Map Hierarchy to a Single Table:</mark>

The attributes from all the classes are extracted into a single table.  

An additional attribute is added to indicate the type of Department

![](https://i.imgur.com/6XNfU2t.png)

<mark style="background: #FFB8EBA6;">Advantages:</mark>  
- approach is simple  
- easy to add new classes.  
- only one table - no need for table joins giving efficient data retrieval.  

<mark style="background: #FFB8EBA6;">Disadvantages:</mark>  
- Not all attributes are relevant resulting in many null or empty attributes  
- The tables may not comply with normalization practices.

### <mark style="background: #FFB8EBA6;">Map Each Concrete Class to a Table:</mark>

![](https://i.imgur.com/F6EpP71.png)

A table is created for each concrete class. 

The attributes of the base class are included for each table.  

<mark style="background: #FFB8EBA6;">Advantages:</mark>  
- Good performance in terms of accessing a single object’s data.  

<mark style="background: #FFB8EBA6;">Disadvantages:</mark>  
- A class change requires a change to its corresponding table and any corresponding tables of its child classes.  
- Can result in much repeating data

### <mark style="background: #FFB8EBA6;">Map All Classes to a Table:</mark>

Every class has an associative table in the database.  

<mark style="background: #FFB8EBA6;">Advantages:</mark>
- Easy to add or modify subclasses  
- Easy to modify base class  
- The one-to-one mapping makes this approach easy to  understand

<mark style="background: #FFB8EBA6;">Disadvantages:</mark>  
- Data access in terms of a reads and writes can be slow because there are more tables involved.  
- More table joins may be required in order to perform a data related operation.  
- Ad-hoc reporting can be difficult

![](https://i.imgur.com/LXAY70N.png)

### <mark style="background: #FFB8EBA6;">Mapping Object Relationships in Tables:</mark>

<mark style="background: #FFB8EBA6;">Class Associations</mark>  
- One to One  
- One to Many  
- Many to Many  
- Uni-directional Association  
- Bi-directional Association

### <mark style="background: #FFB8EBA6;">Types of Class/Object Associations:</mark>

<mark style="background: #FFB8EBA6;">One to One:</mark> Employee to Role  

<mark style="background: #FFB8EBA6;">One to Many:</mark> Department to Employee  

<mark style="background: #FFB8EBA6;">Many to Many:</mark> Employee to Task  

<mark style="background: #FFB8EBA6;">Uni-directional Association:</mark> Employee to Role  

<mark style="background: #FFB8EBA6;">Bi-directional:</mark> Employee <-> Department

![](https://i.imgur.com/YniBfvS.png)

### <mark style="background: #FFB8EBA6;">Implementing Class/Object Associations:</mark>

Use of References and operations  

One-to-one uses a reference with getters/setters  

One to many uses a collection (``ArrayList``, ``Vector``) with ``add()``, ``remove()``, etc.

### <mark style="background: #FFB8EBA6;">Mapping Object Associations as Joins in Relational DB:</mark> 

Joins implemented using foreign keys FKs  

One to Many implemented by FK in the Many table  

Many to many implemented using a join or associative table

![](https://i.imgur.com/0AxyFPh.png)

### <mark style="background: #FFB8EBA6;">Retrieving an Object and Relationships from Database:</mark>

<mark style="background: #FFB8EBA6;">Example – Retrieving a Department from the DB:</mark>  
1. Read Department row from the database  
2. Instantiate a Department object and set the attributes – remember one of the attributes is a Collection  
3. Read all related Employees from the database  
4. Instantiate an Employee object for each and set the attributes  
5. Add a reference to each Employee object to the Collection (attribute of the Department object)

### <mark style="background: #FFB8EBA6;">Saving Objects and Relationships:</mark>

<mark style="background: #FFB8EBA6;">Example:</mark>  
- Create a SQL transaction to ensure referential integrity 
- Add update/insert statements for each object to the transaction.  
- Update/insert statement includes both the attributes and the key values.  
- Submit and commit the transaction

### <mark style="background: #FFB8EBA6;">Some ORM Tool Vendors:</mark>

Hibernate http://www.hibernate.org/  

Oracle TopLink http://www.oracle.com/technetwork/middleware/toplink/overview/index.html  

CocoBase http://www.thoughtinc.com/cber_index.html  

MyBatis www.mybatis.org  

EclipseLink http://www.eclipse.org/eclipselink/  

### <mark style="background: #FFB8EBA6;">Java Specifications</mark>  

<mark style="background: #FFB8EBA6;">Java Data Object (JDO):</mark>  
- One of the initial object mapping Java specifications  
- Flexible persistence options: RDBMS, OODBMS, files etc.  

<mark style="background: #FFB8EBA6;">Java Persistence API (JPA):</mark>  
- Targeted ORM feature set  
- Some implementations also offer NoSQL mapping  
- Hibernate 3.2 onwards supports the JPA

### <mark style="background: #FFB8EBA6;">ORM Tools Features:</mark>  

<mark style="background: #FFB8EBA6;">Basic features:</mark>  
- Be able to use inheritance, create hierarchies between entities  
- Handle any type of relations (1-1, 1-n, n-n)  
- Support for transactions  

<mark style="background: #FFB8EBA6;">Support various databases:</mark>  
- A big advantage of mapping tools is that they provide an abstraction of the underlying database engine.  
- Most of them allow switching easily between RDBMSs  

<mark style="background: #FFB8EBA6;">Be able to map a single object to data coming from multiple tables </mark>
- (joins, views).  
- Most of the tools handle a direct mapping of a class to one table.  

<mark style="background: #FFB8EBA6;">GUI to set up the mapping:</mark> Such a graphical tool presents the relational data model and lets you specify the objects to be created or at least the links between the objects and the tables.  

<mark style="background: #FFB8EBA6;">Generation of the classes:</mark>
- This can speed up the development  
- In some cases the database is mapped to hand-coded classes which may be a preference  

<mark style="background: #FFB8EBA6;">Generation of the database schema:</mark>  
- Some tools work only with a database they generated.  
- Big issue for legacy databases

Support for stored procedures in SQL  

<mark style="background: #FFB8EBA6;">Lazy loading:</mark> the loading of some of the related data as it is needed  

Cache dynamically generated queries so that they don't get rebuilt at each call.  

<mark style="background: #FFB8EBA6;">Cache some data:</mark> to avoid too many calls to the data source.  

<mark style="background: #FFB8EBA6;">Optimised queries:</mark> update only the modified columns;  

Bulk updates or deletions.  

When thousands of records to be updated, avoid loading all the objects in memory  

Use a query (DELETE FROM Customer WHERE Balance < 0).

# <mark style="background: #FFB8EBA6;">09 Review:</mark>

### <mark style="background: #FFB8EBA6;">Module Content:</mark>

<mark style="background: #FFB8EBA6;">Part One:</mark>
- Class Diagrams  
- Associations  
- Sequence Diagrams  
- Principle of least Knowledge  
- Interfaces / Boundary Classes  

<mark style="background: #FFB8EBA6;">Part Two:</mark>
- Design Patterns  

<mark style="background: #FFB8EBA6;">Part Three:</mark>
- OO Testing 
- ORM

### <mark style="background: #FFB8EBA6;">Class Diagrams:</mark>

<mark style="background: #FFB8EBA6;">Associations / Referential Integrity:</mark>
![](https://i.imgur.com/M3ozCFh.png)

<mark style="background: #FFB8EBA6;">Object Links:</mark>

![](https://i.imgur.com/2lMHdAt.png)

Consider an instance of the above class - it will contain two <mark style="background: #FFB8EBA6;">references</mark> to two Circle objects. This means that at runtime it will be <mark style="background: #FFB8EBA6;">linked</mark> to those objects.

![](https://i.imgur.com/gSlepCa.png)

Vice versa, the two instances of this class (``circleA`` and ``circleB``) are <mark style="background: #FFB8EBA6;">linked</mark> to the client object

The actual <mark style="background: #FFB8EBA6;">link</mark> is provided by the references (``circleA`` and ``circleB``) within the client object – interestingly, this means that only the client object “knows” about the link. In this sense, the link is uni-directional.

Note, when we talk about links we are referring to connections between objects at <mark style="background: #FFB8EBA6;">runtime</mark>. We have previously discussed modelling those at <mark style="background: #FFB8EBA6;">design time</mark> through associations.

![](https://i.imgur.com/ThgQtMo.png)

<mark style="background: #FFB8EBA6;">Unidirectional links:</mark> These links act as a communication pathways for the client object to send <mark style="background: #FFB8EBA6;">messages</mark> to the circle objects e.g. ``setRadius``

### <mark style="background: #FFB8EBA6;">Sequence Diagram:</mark>

Depicts how the code executes.

![](https://i.imgur.com/gEf3gjy.png)

The client object first sends a synchronous message (``setRadius``) to ``circleA`` and then another to ``circleB``.

```Java
public class SomeClient {  
	SomeClient (Circle circleA,Circle circleB)  
	{  
		circleA.setRadius(10);  
		circleB.setRadius(12);  
	}  
}
```

### <mark style="background: #FFB8EBA6;">Dependencies & Associations:</mark>

An association or dependency between two classes can be thought of as a <mark style="background: #FFB8EBA6;">path of communication </mark>between instances (objects) of those classes.

![](https://i.imgur.com/udi6Wtr.png)

In the diagram above, objects of class A may talk to (i.e. send messages to) objects of class B and objects of class B may talk to objects of class A.  

Likewise, objects of classes B and C may also communicate. As there is no direct line of communication between A and C, objects of these classes <mark style="background: #FFB8EBA6;">may not communicate directly</mark>. If they do communicate, then there is an inconsistency in the mode.

### <mark style="background: #FFB8EBA6;">Principle of Least Knowledge - Law of Demeter</mark>  

<mark style="background: #FFB8EBA6;">In response to a message M, an object O should send messages only to the following objects:</mark>  
1. O itself  
2. Objects which are sent as arguments to the message M  
3. Objects which O creates as part of its reaction to M  
4. Objects which are directly accessible from O, that is, using values of attributes of O.