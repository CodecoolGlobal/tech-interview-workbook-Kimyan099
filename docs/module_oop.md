># OOP questions

## Software design

### Error handling

#### What does 'fail fast' mean in terms of exception handling? Why is it a good practice?
In unit testing there are positive and negative tests to keep you code well structured  and organized. Fail test means that you test a method with invalid input and the result should throw exception like `IllegalArgumentException` to test what you code supposed to do with wrong input.

## Computer Science

### Data structures

#### How to find the middle element of singly linked list in O(n)?
It depends on the length of the list. We have to go through the list and count all the nodes in it. If the length is odd then 
just return `count/2`. In case the length is even the we have to return the second middle element `count/2 + 1`.
#### Given an array of integers going from 1 to 100 (both inclusive) there is a duplicated entry. How to find it?
We have to iterate through the list and add every element to a `set<String>`. In case of a value can't be added to the set then we find that duplicated entry.
#### What is a linked list? 
It's a sequence of nodes. The nodes does not have a place in memory, because they just reference from the previous element of the list. In a linked list each node points to the next.
#### How to find if a linked list has a loop?
Use Hashing: Iterate through the list one by one and keep putting the nodes in a Hash Table. If NULL is reached then return false and if next of current node points to any of the previously stored nodes in Hash then return true.
#### What is the Big O time complexity of the common operations in an ArrayList, LinkedList, HashMap? And of a bubble sort, quicksort, finding items in a Binary Search tree?
*ArrayList*
```java
-   add()  – takes  _O(1)_  time
-   add(index, element)  – in average runs in _O(n)_  time
-   get()  – is always  _O(1)_  time
-   remove()  – linear time . We have to iterate through the whole array to find the element  for removal. _O(n)_  time
-   indexOf() – linear time. It goes through the array and checking every element one by one.  _O(n)_  time
-   contains()  – implementation is based on  _indexOf()_. So it will also run in _O(n)_  time
```
*LinkedList*
```java
-   add()  – constant-time insertion at any position in _O(1)_ time
-   get()  – searching for an element takes _O(n)_ time
-   remove()  – removing an element takes _O(1)_ time
-   contains()  – It takes _O(n)_ time 
```
*HashMap*

```java
Storing and retrieving elements from the  _HashMap_  takes constant  _O(1)_  time.
```

*Bubblesort*
```java
It has  average *complexity* of О(n2), Usually sorting algorithms has better worst case then bubble sort. 
```
*Quicksort*
```java
It has average O(_n_  log  _n_) time compleity.
```java
*Binary Search Tree*
```
It depends of the number of items stored in the tree. This is much better than the linear time seach , but slower than operations on hash tables. Search, insert and delete also takes average O(log _n_) time.

#### How does HashMap work?

A  HashMap   store items in "key/ value" pairs.
You can access the key by the value or the value by the key like an index.
 It can store different types:  String and Integer keys and values.

#### Why is it important for keys in a map to have an immutable type? (Consider String for example.)

Because in hashmap the key it's like an index, it points to the corresponding value. If you could change the value of the key then you couldn't find the corresponding value in the hashmap.

### Other

#### What is a garbage collector, in a nutshell?
In runtime, automatically removes unused objects to free up space in memory.

## Programming paradigms

### Procedural

#### What is casting? What is the difference between up vs downcasting?
Upcasting is casting to a supertype, while downcasting is casting to a subtype.
Upcasting is always allowed, but downcasting involves a type check and can throw a ClassCastException.

Example :
```java
//Upcasting is allowed here since every Circle is a shape.
Shape circleShape = New Circle;
Shape castShape = Shape(circleShape)
```
```java
//Downcasting is not allowed here since not every shape is a circle.The compler will throw //ClassCastException.
Shape shape = New Shape();
Shape notShape = Circle(shape);
```
#### Which order should we catch the exceptions? Why?
The order is basically that first to exception that matches then that one will be executed an so on. You should always catch the most specific first and then the most generic (as RuntimeException or Exception). 

### Object-oriented

#### What is a class?
Classes can be described as blueprints in Object Oriented Programming. You can use the same class to create multiply objects from that class. This is called instantiation that means -> to call a constructor of a Class which creates an instance or object, of the type of that Class. It allocates the initial memory for the object and returns a reference.

A class has attributes and methods.
-   Methods: Methods define behavior. A method is a collection of statements that are grouped together to perform an operation.
-   The attributes are basically variables within a class.
#### What is an object?
Objects could be described as real-world objects that consist state and behavior. In programming objects stores it's state in variables and they can reach behavior through functions (methods in some programming languages). Methods operate on an object's internal state(A set of object attributes) and serve as the primary mechanism for object-to-object communication. Hiding internal state and requiring all interaction to be performed through an object's methods is known as data encapsulation — a fundamental principle of object-oriented programming.
#### What is a constructor?
Constructors are special methods that can initialize an object. When an object is created , the constructor is also can be used to provide initial values for object attributes. You can think of constructors as methods that will set up your class by default, so you don’t need to repeat the same code every time. The constructor is called when you create an object using the new keyword. A single class can have multiple constructors with different numbers of parameters.

Sometimes there is a need of initializing an object in different ways.
If we want to have different ways of initializing an object using different number of parameters, then we must do **constructor overloading**.
#### Do we require parameter for constructors?
Not necessarily. If the object don't request needed parameters when created. Constructor parameters is used to initialize attributes.
#### What is an interface?
An interface declared with the *interface* keyword and it's methods are abstract by default. It can have parameters and methods signatures. It specifies a method that the a class has to implement so it's like a blueprint of the class. If implementing an interface all the methods has to be ```@Override``` and a class has to use the *Implements* keyword.
#### What are access modifiers?
Access modifiers are determine the class, constructor, method, data member or parameters visibility to another class.
There are four different types:
```java
  Name:							|	Visibility:
------------------------------------------------------------------------
- Default(Package-privite)	    -> Only in the same package.
- Privite 					 	-> Only withing the class.
- Protected 					-> Withing the same package or subclasses in different package.
- Public						-> Anywhere in the programm.
```
![alt text](https://media.geeksforgeeks.org/wp-content/cdn-uploads/Access-Modifiers-in-Java.png)
#### What is data hiding?
Encapsulation is a central design principle of OOP. It means that the internal structure and the implementation of a class should be hidden from the world. This can be done by restricting the access to these parts. Every Object Oriented language provides access modifiers to set the visibility of classes and its members (fields, constructors, and methods) separately. This is called data hiding.
#### Can a static method use non-static members?
Yes, a static method can access a non-static variable. This is done by creating an object to the class and accessing the variable through the object, however this is not a good practice in Object Oriented Programming.
#### What is the difference between hiding a static method and overriding an instance method?
`Overriding instance method`:  The method gets invoked from the subclass. 
`Static method`: If a subclass defines a static method with the same signature as a static method in the superclass, then the method in the subclass hides the one in the superclass.
#### Define the following terms: Instantiation, Attribute, Method
**Instantiation**: In Object Oriented programming languages , we can instantiate a class. That means to creating an object or a blueprint of that class.
When you are creating an object it means you create an instance of a class. The "new " operator instantiates a class by allocating  memory for the new object and returns the reference to that allocated memory. It also invokes the object's constructor.
**Attribute** :   It is the other therm of field. Its usually a public field that can be accessed directly.
**Method** :  A method is a collection of statements that perform some specific task and return the result to the caller. A method can perform some specific task without returning anything. A method is a block of code which only runs when it is called, and they are also known as functions. Methods allow us to reuse the code without retyping the code. In Java, every method must be part of some class which is different from languages like C, C++, and Python. A method must be declared within a class.
![alt text](https://cdn.journaldev.com/wp-content/uploads/2018/07/java-method.png)
#### Could we access a static variable (or method) from a non-static method? Why?
Yes, a non-static method can access a static variable or call a static method in Java. There is no problem with that because of static members i.e. both static variable and static methods belongs to a class and can be called from anywhere, depending upon their access modifier.
#### Could we access a non-static variable (or method) from a static method? Why?
No. A static method can only access other static methods and variables. If we need to access a non-static variable or method from within a static method, we must first instantiate the class that the non-static method or variable belongs to.
#### How many instances you have of a static variable of a given class?
Java Language Specification states the following:

If a field is declared static, there exists exactly one incarnation of the field, no matter how many instances (possibly zero) of the class may eventually be created. A static field, sometimes called a class variable, is incarnated when the class is initialized.
#### Why is it not a good practice to write a lot of static methods?
One reason that static methods aren't very OO is that interfaces and abstract classes only define non-static methods. Static methods thus don't fit very well into inheritance. Static methods do not have access to "super", which means that static methods cannot be overridden in any real sense. Actually, they can't be overridden at all, only hidden.
#### What are the features of static attributes and static methods of a class? What are the benefits, when to use them?
You can reach them from anywhere in the code and you don't have to create a blueprint to use it. If you use the class name then you can use the their methods as well. Common use for static methods is to access static variables. Another good example is the singleton pattern’s getInstance() method, which is static as well.
#### What is the ‘this’ reference?
‘this’ is a reference variable that refers to the current object. Within an instance method or a constructor, 'this' is a reference to the current object — the object whose method or constructor is being called. You can refer to any member of the current object from within an instance method or a constructor by using the 'this' keyword.
#### What are base class, subclass and superclass?
The class from which the subclass is inherited is called a superclass (also a base class or a parent class). A class that is derived from another class is called a subclass (also a derived class, extended class, or child class). Every class has one and only one direct superclass (single inheritance). In the absence of any other explicit superclass, every class is implicitly a subclass of Object. Classes can be derived from classes that are derived from classes that are derived from classes, and so on, and ultimately derived from the topmost class, Object. Such a class is said to be descended from all the classes in the inheritance chain stretching back to Object.
#### Draw an object oriented family (as entities, with relations) on the whiteboard.
#### Difference between overloading and overriding?
The difference is that overloading is about that the same function have different signatures. Overriding is about same exactly the same function, same signature but different classes connected through inheritance.
![Alt Text](https://1.bp.blogspot.com/-y1s5K8pFJJQ/W-sAyIUsT2I/AAAAAAAAA4U/aUb09Ee-UK8x-62kF5YQiJ6-RTYhw3l3gCEwYBhgL/s640/Overloading%2Bvs%2BOverriding.png)
#### What are the Object Oriented Principles? Explain the concepts with realistic examples!
**Encapsulation**
The implementation and state of each object are privately held inside a defined boundary, or class. Other objects do not have access to this class or the authority to make changes but are only able to call a list of public functions, or methods. This characteristic of data hiding provides greater program security and avoids unintended data corruption.
We can think of encapsulation as a protective wall or shield that prevents data to being accessed by a method from other class, this is known as data-hiding. The fields are only accessible via public methods of that class. Encapsulation can be achieved by Declaring all the variables in the class as private and writing public methods in the class to set and get the values of variables.
**Abstraction**
Abstraction can be defined as the process of identifying only the required characteristics of an object ignoring the irrelevant details. Consider a real-life example of a man driving a car. The man only knows that pressing the accelerators will increase the speed of car or applying brakes will stop the car but he does not know about how on pressing the accelerator the speed is actually increasing, he does not know about the inner mechanism of the car or the implementation of accelerator, brakes etc in the car. This is what abstraction is. In Java, abstraction is achieved by interfaces and abstract classes. We can achieve 100% abstraction using interfaces.

Using abstract class/Interface we express the intent of the class rather than the actual implementation. In a way, one class should not know the inner details of another in order to use it, just knowing the interfaces should be good enough. Its main goal is to handle complexity by hiding unnecessary details from the user. That enables the user to implement more complex logic on top of the provided abstraction without understanding or even thinking about all the hidden complexity. Objects in an OOP language provide an abstraction that hides the internal implementation details. Similar to the coffee machine in your kitchen, you just need to know which methods of the object are available to call and which input parameters are needed to trigger a specific operation. But you don’t need to understand how this method is implemented and which kinds of actions it has to perform to create the expected result.

**Inheritance**
Relationships and subclasses between objects can be assigned, allowing developers to reuse a common logic while still maintaining a unique hierarchy. This property of OOP forces a more thorough data analysis, reduces development time and ensures a higher level of accuracy. It is the mechanism in Java by which one class is allow to inherit the features(fields and methods) of another class.
Inheritances expresses "has-a” relationship between two objects. Using Inheritance, In derived classes we can reuse the code of existing super classes. 

**Polymorphism**
Objects are allowed to take on more than one form depending on the context. The program will determine which meaning or usage is necessary for each execution of that object, cutting down on the need to duplicate code. Polymorphism in Java are mainly of 2 types: Overloading and Overriding.

It means one name many forms. It is further of two types — static and dynamic. Static polymorphism is achieved using method overloading and dynamic polymorphism using method overriding. It is closely related to inheritance. We can write a code that works on the superclass, and it will work with any subclass type as well.
#### What is method overloading?
If a class has multiple methods having same name but different in parameters, it is known as Method Overloading. Overloading allows different methods to have the same name, but different signatures where the signature can differ by the number of input parameters or type of input parameters or both. Overloading is related to compile time (or static) polymorphism.
#### What is method overriding?
If subclass (child class) has the same method as declared in the parent class, it is known as method overriding in Java. In other words, if a subclass provides the specific implementation of the method that has been declared by one of its parent class(Inheritance), it is known as method overriding.
#### Explain how object oriented languages attempt to simplify memory management for Programmers.
In C++ has no inbuilt memory management solution. You manage memory manually, and this results in the most work for the programmer. But with often the very best levels of performance.

Java and C#  has automatic memory management, a nice and quiet garbage collector that works in the background to clean up the unused objects and free up some memory. This is painless for the programmer, but can cause performance hiccups in some applications, and the system prefers to run when there is a significant amount of spare memory to work in.

#### Explain the “Single Responsibility” principle!
Single Responsibility principle is a basic concept of programming, which means every class has only one task to do. That makes the code cleaner, more readable and easier to test or debug.
#### What is an object oriented program? Explain, show.
Object-oriented programming (OOP) is a programming language model in which programs are organized around data, or objects, rather than functions and logic. An object can be defined as a data field that has unique attributes and behavior. Examples of an object can range from physical entities, such as a human being that is described by properties like name and address, down to small computer programs, such as games. This opposes the historical approach to programming where emphasis was placed on how the logic was written rather than how to define the data within the logic.
![Alt Text](https://www.astateofdata.com/wp-content/uploads/2019/10/Python-Object-Oriented-Programming-Inheritance-Schema.png)
#### How do you make a class immutable? What do you need to watch out for?
To create an immutable class in java, you have to do following steps:

-   Declare the class as final so it can’t be extended.
-   Make all fields private so that direct access is not allowed.
-   Don’t provide setter methods for variables
-   Make all mutable fields final so that it’s value can be assigned only once.
-   Initialize all the fields via a constructor performing deep copy.
-   Perform cloning of objects in the getter methods to return a copy rather than returning the actual object reference.
#### How many instances can be created for an abstract class?
You cannot create an instance of an abstract class because it does not have a complete implementation. The purpose of an abstract class is to function as a base for subclasses. It acts like a template, or an empty or partially empty structure.