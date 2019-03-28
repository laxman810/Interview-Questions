# OOPS Interview Questions


What is OOPS?
```
OOPS is abbreviated as Object Oriented Programming system in which programs are considered as a 
collection of objects. Each object is nothing but an instance of a class.
Object means a real word entity such as pen, chair, table etc. 
Object-Oriented Programming is a methodology or paradigm to design a program using classes and objects.
It simplifies the software development and maintenance by providing some concepts:
```

Write basic concepts of OOPS?
```
Abstraction
Encapsulation
Polymorphism
Inheritance
Composition
Association
Aggregation
```

What is a class?
```
A class is simply a representation of a type of object. 
It is the blueprint/ plan/ template that describes the details of an object.
```

What is an object?
```
*	An object is an instance of a class. It has its own state, behavior, and identity.
*	Any entity that has state and behavior is known as an object. 
*	For example: chair, pen, table, keyboard, bike etc. It can be physical and logical.
*	Object Oriented Programming System is the programming technique to write programs 
	based on the real world objects. 
*	The states and behaviors of an object are represented as the member variables and methods.
*	In OOPS programming programs are organized around objects and data rather than actions and logic.
```

What is Encapsulation?
```
*	Binding (or wrapping) code and data together into a single unit is known as encapsulation.
*	For example: capsule, it is wrapped with different medicines.
*	Encapsulation is an OOPS concept to create and define the permissions and restrictions 
	of an object and its member variables and methods. 
*	A very simple example to explain the concept is to make the member variables of a class private and providing public getter and setter methods. 
*	Java provides four types of access level modifiers: public, protected,no modifier and private.
```

What is Polymorphism?
```
*	When one task is performed by different ways known as polymorphism. 
*	For example: to convince the customer differently, to draw something e.g. shape or rectangle etc.
```

What is Inheritance?
```
When one object acquires all the properties and behaviours of parent object 
It provides code reusability. It is used to achieve runtime polymorphism.
If inheritance applied on one class is called Single Inheritance, and if it depends on multiple classes, 
then it is called multiple Inheritance.
```

what is Abstraction ?
```
*	Hiding internal details and showing functionality is known as abstraction.
*	Abstraction is the concept of hiding the internal details and describing things in simple terms. 
*	For example, a method that adds two integers. 
*	For example: phone call, we don't know the internal processing.
*	The method internal processing is hidden from outer world. 
*	There are many ways to achieve abstraction in object oriented programming, such as encapsulation and inheritance.
```

What are manipulators?
```
Manipulators are the functions which can be used in conjunction with the insertion (<<) and 
extraction (>>) operators on an object. Examples are endl and setw.
```

Method Overloading
```
*	If a class has multiple methods having same name but different in parameters, 
	it is known as Method Overloading.
*	If we have to perform only one operation, having same name of the methods increases the 
	readability of the program.
*	There are two ways to overload the method in java
	1) By changing number of arguments
	2) By changing the data type
```
	
Define a constructor?
```
A constructor is a method used to initialize the state of an object, and it gets invoked 
at the time of object creation. Rules forconstructor are:
Constructor Name should be same as class name.
A constructor must have no return type.
```

Define Destructor?
```
A destructor is a method which is automatically called when the object is made of scope or destroyed. 
Destructor name is also same as class name but with the tilde symbol before the name.
```

What is an Inline function?
```
An inline function is a technique used by the compilers and instructs to insert complete body 
of the function wherever that function is used in the program source code.
```

What is a virtual function?
```
A virtual function is a member function of a class, and its functionality can be overridden in its 
derived class. This function can be implemented by using a keyword called virtual, and it can 
be given during function declaration. A virtual function can A token in C++, and it can be achieved 
in C Language by using function pointers or pointers to function.
```

What is a friend function?
```
A friend function is a friend of a class that is allowed to access to Public, private or protected data 
in that same class. If the function is defined outside the class cannot access such information.Friend 
can be declared anywhere in the class declaration, and it cannot be affected by access control 
keywords like private, public or protected.
```

What is function overloading?
```
Function overloading an as a normal function, but it can perform different tasks. It allows the creation of 
several methods with the same name which differ from each other by the type of input and output of the function.
Example
void add(int& a, int& b);
void add(double& a, double& b);
```

What is operator overloading?
```
Operator overloading is a function where different operators are applied and depends on the arguments. 
Operator,-,* can be used to pass through the function, and it has their own precedence to execute
```

What is an abstract class?
```
An abstract class is a class which cannot be instantiated. Creation of an object is not possible with an 
abstract class, but it can be inherited. An abstract class can contain only Abstract method. Java allows 
only abstract method in abstract class while for other languages allow non-abstract method as well.
```

What is a ternary operator?
```
The ternary operator is said to be an operator which takes three arguments. Arguments and results are of 
different data types, and it depends on the function. The ternary operator is also called a conditional operator.
```

What is the use of finalize method?
```
Finalize method helps to perform cleanup operations on the resources which are not currently used. 
Finalize method is protected, and it is accessible only through this class or by a derived class.
```

What are different types of arguments?
```
A parameter is a variable used during the declaration of the function or subroutine and arguments are 
passed to the an, and it should match with the parameter defined. There are two types of Arguments.
Call by Value – Value passed will get modified only inside the function, and it returns the same value whatever it is passed it into the function.
Call by Reference – Value passed will get modified in both inside and outside the functions and it returns the same or different value.
```

What is the super keyword?
```
Super keyword is used to invoke the overridden method which overrides one of its superclass methods. 
This keyword allows to access overridden methods and also to access hidden members of the superclass.
It also forwards a call from a constructor to a constructor in the superclass.
```

What is method overriding?
```
Method overriding is a feature that allows a subclass to provide the implementation of a method that 
overrides in the main class. This will overrides the implementation in the superclass by providing the 
same method name, same parameter and same return type.
```

What is an interface?
```
An interface is a collection of an abstract method. If the class implements an inheritance, 
and then thereby inherits all the abstract methods of an interface.
```

What is exception handling?
```
An exception is an event that occurs during the execution of a program. Exceptions can be of any 
type – Runtime exception, Error exceptions. Those exceptions are adequately handled through exception 
handling mechanism like try, catch and throw keywords.
```

What are tokens?
```
The token is recognized by a compiler, and it cannot be broken down into component elements. Keywords, 
identifiers, constants, string literals and operators are examples of tokens.
```

Difference between overloading and overriding?
```
Overloading is static binding whereas Overriding is dynamic binding. Overloading is nothing but the 
same method with different arguments, and it may or may not return the same value in the same class itself.
Overriding is the same method names with same arguments and return types associated with the class and its child class.
```

Difference between class and an object?
```
An object is an instance of a class. Objects hold multiple information, but classes don’t have any information. 
Definition of properties and functions can be done in class and can be used by the object.
A class can have sub-classes, and an object doesn’t have sub-objects.
```

What is an abstraction?
```
Abstraction is a good feature of OOPS, and it shows only the necessary details to the client of an object. 
Means, it shows only required details for an object, not the inner constructors, of an object. 
Example – When you want to switch On television, it not necessary to show all the functions of TV. 
Whatever is required to switch on TV will be showed by using abstract class.
```

What are access modifiers?
```
Access modifiers determine the scope of the method or variables that can be accessed from other 
various objects or classes. There are 5 types of access modifiers, and they are as follows:
Private.
Protected.
Public.
Friend.
Protected Friend.
```

What are sealed modifiers?
```
Sealed modifiers are the access modifiers where it cannot be inherited by the methods. 
Sealed modifiers can also be applied to properties, events, and methods. 
This modifier cannot be applied to static members.
```
 
How can we call the base method without creating an instance?
```
Yes, it is possible to call the base method without creating an instance. And that method should 
be “Static method”. Doing inheritance from that class.-Use Base Keyword from a derived class.
```

What is the difference between new and override?
```
The new modifier instructs the compiler to use the new implementation instead of the base class function. 
Whereas, Override modifier helps to override the base class function.
```

What are the various types of constructors?
```
–  Default Constructor – With no parameters.
–  Parametric Constructor – With Parameters. Create a new instance of a class and also passing arguments simultaneously.
–  Copy Constructor – Which creates a new object as a copy of an existing object.
```

What is early and late binding?
```
Early binding refers to the assignment of values to variables during design time whereas late binding 
refers to the assignment of values to variables during run time.
```

What is ‘this’ pointer?
```
THIS pointer refers to the current object of a class. THIS keyword is used as a pointer which 
differentiates between the current object with the global object. Basically, it refers to the current object.
```

What is the difference between structure and a class?
```
Structure default access type is public , but class access type is private. A structure is used for 
grouping data whereas class can be used for grouping data and methods. Structures are exclusively 
used for data, and it doesn’t require strict validation , but classes are used to 
encapsulates and inherit data which requires strict validation.
```

What is the default access modifier in a class?
```
The default access modifier of a class is Private by default.
```

What is a pure virtual function?
```
A pure virtual function is a function which can be overridden in the derived class but cannot be defined. 
A virtual function can be declared as Pure by using the operator =0.
```

What are all the operators that cannot be overloaded?
```
Scope Resolution (:: )
Member Selection (.)
Member selection through a pointer to function (.*)
```

What is dynamic or run time polymorphism?
```
Dynamic or Run time polymorphism is also known as method overriding in which call to an overridden 
function is resolved during run time, not at the compile time. It means having two or more methods 
with the same name, same signature but with different implementation.
```

Do we require a parameter for constructors?
```
No, we do not require a parameter for constructors.
```

What is a copy constructor?
```
This is a special constructor for creating a new object as a copy of an existing object. 
There will always be only one copy constructor that can be either defined by the user or the system.
```

What does the keyword virtual represented in the method definition?
```
It means, we can override the method.
```

Whether static method can use nonstatic members?
```
False.
```

What is a base class, sub class, and super class?
```
The base class is the most generalized class, and it is said to be a root class.
A Sub class is a class that inherits from one or more base classes.
The superclass is the parent class from which another class inherits.
```

What is static and dynamic binding?
```
Binding is nothing but the association of a name with the class. Static binding is a binding in which name 
can be associated with the class during compilation time, and it is also called as early Binding.
Dynamic binding is a binding in which name can be associated with the class during execution time, 
and it is also called as Late Binding.
```

How many instances can be created for an abstract class?
```
Zero instances will be created for an abstract class.
```

Which keyword can be used for overloading?
```
Operator keyword is used for overloading.
```

What is the default access specifier in a class definition?
```
Private access specifier is used in a class definition.
```

Which OOPS concept is used as reuse mechanism?
```
Inheritance is the OOPS concept that can be used as reuse mechanism.
```

Which OOPS concept exposes only necessary information to the calling functions?
```
Encapsulation
```

what is marker interface ?
```
=> an empty interface in java is called a marker interface
=> Marker interface is also called tag interface.
=>In java we have the following major marker interfaces as under:
Searilizable interface
Cloneable interface
Remote interface
ThreadSafe interface
```
	
What is a bit? 
```
A bit is a representation of 1 or 0. Basically OFF(0) and ON(1)
```

What is a byte?
```
=> A byte is made up of 8 bits and the highest value of a byte is 255, which would mean every bit is set.
-------------------------------------------
|      1 Byte ( 8 bits )                  |
-------------------------------------------
|Place Value | 128| 64| 32| 16| 8| 4| 2| 1|     
-------------------------------------------
|      $a    |   0|  0|  1|  0| 0| 1| 0| 0|    
-------------------------------------------
|      $b    |   0|  1|  1|  0| 0| 1| 1| 1|
------------------------------------------- 
|      &     |   0|  0|  1|  0| 0| 1 | 0| 0|
------------------------------------------- 
$a =  36;
$b = 103;
echo $a & $b;
= 36
```