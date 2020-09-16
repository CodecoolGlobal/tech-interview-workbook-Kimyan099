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

## Programming languages

### Java

#### What is autoboxing and unboxing?
Converting a primitive value (an int, for example) into an object of the corresponding wrapper class (Integer) is called autoboxing. If Converting an object of a wrapper type to its corresponding primitive value is called unboxing. Autoboxing and unboxing lets developers write cleaner code, making it easier to read.
#### If you have a variable, that shall store a positive whole number between 0 and 200, what primitive type would you use to store it?
I would store it in 'short' as it takes numbers (-32,768 - 32,767).
![Alt Text](https://facingissuesonitcom.files.wordpress.com/2019/06/java-primitive-type-keywords-.png?w=1000)
#### What is the "golden rule" of variable scoping in Java? What is the lifetime of variables?
General rule for a variable’s scope: 'It is accessible only within the block in which it is declared'.
There are three types of variables in Java:
**Instance variables**: 
A variable which is declared inside a class and outside all the methods and blocks is an instance variable. Lifetime of an instance variable is until the object stays in memory.
**Class variables**:
A variable which is declared inside a class, outside all the blocks and is marked static is known as a class variable. The lifetime of a class variable is until the end of the program or as long as the class is loaded in memory.
**Local variables**:
Every variable that is not instance or class variable that counts as local variable including the parameters in a method.
The lifetime of a local variable is until the control leaves the block in which it is declared.
![Alt Text](https://www.learningjournal.guru/_resources/img/jpg-5x/scope-and-lifetime-of-a-variable-summary.jpg)
#### What is the purpose of the ‘equals()’ method?
The `equals()` method compares two given `String` based on a content. If all the content from both variable is the same then, it return true.
#### What is the difference between '==' and 'equals()'?
- `equals()` is a 'method' and `==` is a 'operator'.
- The operator `==` checks if both of the object is points to the same memory location. -> Reference comparison
- The method `equals()` is  checks the content of the to `String`. -> Content comparison
#### What does the ‘static’ keyword mean?
Everything in Java must have a type. `static` tells Java compiler that this is a method that is part of the class, but is not a method for any other instance of the class. We can apply java `static` keyword with variables, methods, blocks and nested class. Through the class name you can reach static methods from anywhere in the code.
#### Why is the main() method declared as static? Explain.
In Java, to start a program we need an existing public static void main(String[] args) method on a class.
-   It must be public to be reachable from the outer world.
-   It must be static to be callable before creating any objects.
-   It is void since by design it does not return anything when the program ends normally.
-   It is possible to pass (multiple) arguments after the name of the class to the java runtime – these arguments are visible by the method through the args parameter.
#### What is the default access modifier in a class?
Default – No keyword required: When no access modifier is specified for a class, method or data member – It is said to be having the default access modifier by default. Default access modifier called 'Package private since classes having default access modifier are accessible only within the same package. 
#### What is the JVM?
Java Virtual Machine: It is an abstract virtual computer runs by specification. One of it's main future is that enables a computer to run Java programs as well as programs written in other language that are converted by the compiler to byte-code. It is a software layer that secure well protected environment to run the program and provide good mobility("Write once, Run anywhere").
Any Java application can be run only inside some concrete implementation of the abstract specification of the Java virtual machine.
#### What is the difference between the JRE and the JDK?
**JRE (Java Runtime Enviroment)**: It is a software layer that runs on top of a computer’s operating system software and provides the class libraries and other resources(JVM) that a specific Java program needs to run.
**JDK(Java Developer Kit)**: It provides tool for developers to create Java programs that can be executed and run by the JVM and JRE.
![Alt Text](https://cdn.programiz.com/sites/tutorial2program/files/jdk-jre-jvm.jpg)
#### What is the difference between long and Long?
Long is a wrapper class around the primitive long. Therefore Long is an object; objects can be null, primitives can not. After auto-boxing feature is released in java the primitive long can be automatically converted to Long, which is an object.
#### Can a long store bigger numbers than a Long?
No, because long has the same maximum value like Long, 2^63-1. If you want to store bigger number you should use BigInteger.
#### What kind of packages do you know under java.util.* ? Bring at least 3 examples.
-   java.util.Arrays
-   java.util.Hashmap
-   java.util.Collections
#### What are the access modifiers in Java? Which one could we use for class?
-  Use the most restrictive access level that makes sense for a particular member. Use private unless you have a good reason not to.
- Avoid public fields except for constants.

-   **Default – No keyword required:**  When no access modifier is specified for a class, method or data member – It is said to be having the default access modifier by default. Having default access modifier are accessible only within the same package.
    
-   **Private**  - The methods or data members declared as private are accessible only within the class in which they are declared. Any other class of same package will not be able to access these members. Top level Classes or interface can not be declared as private, they apply only to nested classes.
    
-   **Protected:**  The methods or data members declared as protected are accessible within the same package or sub classes in different packages.
    
-   **Public:**  The public access modifier has the widest scope among all other access modifiers. Classes, methods or data members which are declared as public are accessible from everywhere in the program. There is no restriction on the scope of a public data members


#### Can an “enum” contain methods in Java? Explain.
You are not restricted to simple getter and setter methods. You can also create methods that make calculations based on the field values of the enum constant. If your fields are not declared `final` you can even modify the values of the fields (although that may not be so good an idea, considering that the enums are supposed to be constants).
```java
public enum Level {
    HIGH  (3), 
    MEDIUM(2), 
    LOW   (1)  

    private final int levelCode;

    Level(int levelCode) {
        this.levelCode = levelCode;
    }
    **public int getLevelCode() {
        return this.levelCode;
    }** 
}
```
#### When would you use a private/protected/public attribute? What is the difference?
I would use **private** in case of the attribute only be seen in only inside that class. 
I would use **protected **  if i want that variable to be seen inside that package so it's visible for subclasses as well.
I would use **public**  as it can be seen from everywhere.
#### How do you prevent developers from subclassing a class?
Declare the class with the final keyword so it can't be extended(inherited).
#### How do you prevent developers from overriding a method in a subclass?
You use the **final** keyword in a **method** declaration to indicate that the **method** cannot be overridden by subclasses.
#### How do you prevent developers from changing the value of a variable?
Once a **final variable** has been assigned, it always contains the same value. ... If a **final variable** holds a reference to an object, then the state of the object may be changed by operations on the object, but the **variable** will always refer to the same object (this property of **final** is called non-transitivity).
#### Think about money ;) How would you store a currency value, that shall support decimal parts? Think it through again, and try to think outside of the box!
A BigDecimal is an exact way of representing numbers. A Double has a certain precision. Working with doubles of various magnitudes (say d1=1000.0 and d2=0.001) could result in the 0.001 being dropped altogether when summing as the difference in magnitude is so large. With BigDecimal this would not happen. The disadvantage of BigDecimal is that it's slower, and it's a bit more difficult to program algorithms that way (due to + - * and / not being overloaded).
If you are dealing with money, or precision is a must, use BigDecimal. Otherwise Doubles tend to be good enough.
#### What happens if you try to call something, that you have no access to, because of data hiding?
The compiler throws an error: ". . . has private access in . . ." It is illegal to access a variable declared private outside its class.
#### What happens if you try to delete/drop an item from an array, while you are iterating over it?
The length of an array is fixed after creation, therefore it is not possible to remove any elements while iterating, or just picked by value or index. However there is a method removeElement() in class ArrayUtils. This creates a new array without the element we want to remove. This works via iterating.
#### What happens if you try to delete/drop/add an item from a List, while you are iterating over it?
If you want to delete the item you are currently at while iterating, it will cause a ConcurrentModificationException, unless you are using an iterator and say iterator.remove(). Essentially, the ConcurrentModificationException is used to fail-fast when something we are iterating on is modified.
#### What happens if you try to add an item to the end of an array, while you are iterating over it?
It is not possible, because arrays has a fixed size after they are created. It you want to add an element to the end of an array, you have to create a new array with length n + 1 (if the original list’s length was n), copy the original list elements to the new one, and add your element to the end of the new list.
#### If you need to access the iterator variable after a for loop, how would you do it?
I’d simply define the iterator variable before the loop, so after the loop I’d still have the latest value.
```java
int i;
for (i = 0; i < numbers.size(); i++) {
    sum += numbers.get(i);
}
```
#### Which interfaces extend the Collection interface in Java. Which classes?
The Java Collections Framework hierarchy consists of two distinct interface trees:

-   Collection interface
-   Map interface

The  **Collection**  interface provides the basic functionality used by all collections, such as add and remove methods. Its subinterfaces the Set, List, and Queue, provide for more specialized collections.

-   The Set interface does not allow duplicate elements.
-   SortedSet is a subinterface of Set interface, that provides for ordering of elements in the set.
-   The List interface provides for an ordered collection, for situations in which you need precise control over where each element is inserted.
-   The Queue is a collection for holding elements prior to processing. Elements in a Queue are typically ordered in on a FIFO (first-in-first-out) basis.
-   The Deque is a subinterface of Queue, a double-ended-queue. The elements can be used in both LIFO and FIFO.
![Alt Text](https://1.bp.blogspot.com/-zaLDUihyAL8/Umv9xNl7CFI/AAAAAAAAAHg/MT8sW1HA62A/s1600/java-collection-hierarchy.png)
#### What is the connection between equals() and hashCode()? How are they used in HashMap?
**equals(Object obj):**  a method provided by java.lang.Object that indicates whether some other object passed as an argument is "equal to" the current instance. The default implementation provided by the JDK is based on memory location — two objects are equal if and only if they are stored in the same memory address. If two objects are equal, they MUST have the same hash code.

**hashcode():**  a method provided by java.lang.Object that returns an integer representation of the object memory address.

HashMap uses hashCode(), == and equals() for entry lookup. The lookup sequence for a given key 'k' is as follows:

-   Use k.hashCode() to determine which bucket the entry is stored
-   If found, for each entry's key k1 in that bucket, if k == k1 || k.equals(k1), then return k1's entry
-   Any other outcomes, no corresponding entry

When you ‘put’ in a hashmap, first the map finds a place in an array(bucket) based on the hashcode of the key. All entries of keys having same hashcode are placed in the same bucket. Once the bucket is identified, the equals method of the key comes into play. It checks, if any other key in the bucket is equal, if it is equal, it overrides that entry of value, else it adds a new entry of key value pair.

When we ‘get’ from hashMap, first it finds the hashcode of the key, using hashcode, finds the location/bucket of all keys having same hashcode. Then it uses the equals method of the key to identify which key value pair to be fetched from the bucket.
#### What is the difference between checked exceptions and unchecked exceptions? Could you bring example for each?
There are two exception types, checked and unchecked (also called runtime). The main difference is that checked exceptions are checked when compiled, while unchecked exceptions are checked at runtime.
#### What is Error in Java and how does it relate to Exception?
Both errors and exceptions are subclasses of the throwable class. Exceptions are related to the application itself while errors are related to the environment (JVM) in which the application is running.

Errors cannot and should not be handled or caught. They signal severe problems during runtime that should stop execution. Two most common examples are stack overflow and out-of-memory errors.
#### When does 'finally' block run? What it is used for? Could you give an example from your projects when you would use 'finally'?
The code we defined in the finally block runs whether there was a caught exception or not. We usually use finally block to clean up the resources - e.g. we are reading from a file in the try block, we want to close the file no matter what.
#### What is the largest number you can work with in Java?
Built-in Java primitive type, Double MAX_VALUE
`public static final double MAX_VALUE`  A constant holding the largest positive finite value of type double.
#### When you use method overriding, can you change the access level of the method, from protected to public? Why?
A sub-class can always widen the access modifier, because it is still a valid substitution for the super-class. From the Java specification about Requirements in Overriding and Hiding:

The access modifier of an overriding or hiding method must provide at least as much access as the overridden or hidden method, as follows:

-   If the overridden or hidden method is public, then the overriding or hiding method must be public; otherwise, a compile-time error occurs.
-   If the overridden or hidden method is protected, then the overriding or hiding method must be protected or public; otherwise, a compile-time error occurs.
-   If the overridden or hidden method has default (package) access, then the overriding or hiding method must not be private; otherwise, a compile-time error occurs.

#### Can the main method be overridden? Explain your answer!
No, because the main is a static method and a static method cannot be overridden since they are not dispatched on the object instance at runtime.
#### When you use method overriding, can you throw fewer exceptions in the subclass than in the parent class? Why?
The overriding method must NOT throw checked exceptions that are new or broader than those declared by the overridden method. For example, a method that declares a FileNotFoundException cannot be overridden by a method that declares a SQLException, Exception, or any other non-runtime exception unless it's a subclass of FileNotFoundException.

It means that if a method declares to throw a given exception, the overriding method in a subclass can only declare to throw that exception or its subclass.
#### When you use method overriding, can you throw more exceptions in the subclass than in the parent class? Why?
The overriding method must NOT throw checked exceptions that are new or broader than those declared by the overridden method.
#### What does "final" mean in case of a variable, method or a class?
-   A final variable’s value cannot be modified or if it is a reference to an object, you cannot refer to another object with it.
-   A final method cannot be overridden.
-   A final class cannot be extended.
#### What is the super keyword?
The super keyword in Java is a reference variable which is used to refer immediate parent class object. Whenever you create the instance of subclass, an instance of parent class is created implicitly which is referred by super reference variable. We can use super keyword to access the data member or field of parent class. It is used if parent class and child class have same fields. The super keyword can also be used to invoke parent class method. It should be used if subclass contains the same method as parent class. In other words, it is used if method is overridden.
**Usage** : 
-   super can be used to refer immediate parent class instance variable.
-   super can be used to invoke immediate parent class method.
-   super() can be used to invoke immediate parent class constructor: default constructor is provided by compiler automatically if there is no constructor. But, it also adds super() as the first statement.
#### What are “generics”? When to use? Show examples.
Using java generics programmers are able to write more general methods. It means that it is not necessary to specify the input type of a method, therefore it can handle Strings, Integers, Doubles and so on. It is very useful when for example we want to implement a sorting method. If we use generics our method will handle more type of Lists. Generics also provide compile-time type safety that allows programmers to catch invalid types at compile time.
```java	
public class GenericMethodTest {
    // generic method printArray
    public static < E > void printArray ( E[] inputArray ) {
        // Display array elements
        for (E element : inputArray) {
            System.out.printf("%s ", element);
        }
        System.out.println();
    }
}
```
#### What is the benefit of having “generic” containers?

Generic containers provides that you don't have to deal with the scope type. You can add multiply different variables to generic container.

```java
public class Container<T> {
    private final T value;

    public Container(T value) {
        this.value = value;
    }

    public T getValue() {
        return value;
    }
}
```
#### Given two Java programs on two different machines. How can you communicate between the two? What are the possible ways?
#### What is an annotation? What can be annotated and how? Show examples.

Java Annotations allow us to add metadata information into our source code, although they are not a part of the program itself. Annotations can be applied to the classes, interfaces, methods and fields.

-   Instructions to the compiler: There are three built-in annotations available in Java (@Deprecated, @Override & @SuppressWarnings) that can be used for giving certain instructions to the compiler.
    
-   Compile-time instructors: Annotations can provide compile-time instructions to the compiler that can be further used by software build tools for generating code, XML files etc.
    
-   Runtime instructions: We can define annotations to be available at runtime which we can access using java reflection and can be used to give instructions to the program at runtime.