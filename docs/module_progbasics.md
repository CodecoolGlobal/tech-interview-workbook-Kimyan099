# Programming Basics questions

## Computer science

### Data structures

#### What is the purpose of a list (array in some programming languages) data structure? Name some methods of it!
Lists [] can contain integers, strings and objects as well. A list is mutable and hence, they can be changed even after creation. The list in python are ordered, every item has it’s index so this allows you to create duplicates, because every duplicate has its own place with index inside the list. You can iterate through over it. 
Methods: append(), remove(), sort(), copy(), count(), extend(), index()

#### What is the difference between a list/array and a set?
Array() is the same as list, however if you create an array, all element of the array has to be the same type of data.(integer, string, object)
set is also have the same properties as list, but you can not create duplicates in it. Set() is a collection which is unordered and unindexed. Once set is created you can not change the items but you can add new ones, you also can iterate over with a for loop.

#### What is the purpose and methods of a dictionary/map data structure?
Dictionary {} as a list is a collection of objects. List and dict share some characteristics:
- mutable
- unordered : 
- dynamic : They can grow and shrink as its needed.
- they can be nested: list can contain list, dic can contain dic, dic can contain list and vica versa.

Dictionary items can be accessed via keys( for list its via index)
the dic consist key: value pairs and each key is mapped to its associated value.
Dic elements are not accessed by numerical index. You can refer to the key and it shows its value.

Dictionary methods:
Clear()     -     Removes all the elements from dic
copy()      -     Returns a copy of a dic
fromkeys()  -     Returns a dic with the specified keys and values
get()       -     Returns the value of the specified key
items()     -     Returns a list containing a tuple for each key value pair
keys()      -     Returns a list containing the dic's keys
pop()	    -	  Removes the elemet with the specified value
popitem()   -	  Removes the last inserted key-value pair
setdefault()-	  Returns the value of the specified key. If the key does not exist: insert the key, with the specified value
update()    -	  Updates the dictionary with the specified key-value pairs
values()    -	  Returns a list of all the values in the dictionary

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
Pseudo code :  rough documentation, readable and understandable even for a layman.

Fibonacci sequence:
This program will show for the given number “n” printed out n-th fibonacci seq.
We use recursion to count it out.

#function for fibonacci sequence

def fibonacci(number):

	if number < 0:
		then print “incorrect input”

	#if the given number is 0 then its remain 0
	elif number == 0:
		return 0
	
	#if the given number is 1 then its still remain 1, otherwise 
	#if bigger then 1 then calculate to its fibonacci number.
	elif number == 1:
		return 1
	else:
		return fibonacci(number-1) + fibonacci(number -2)

This is a simple fib program and it’s takes to much time  because there is to much repeated work, but it is still works. There are better ways to make this fuction like by storing the fib numbers that we calculated so far..

#### How do you find a max value in a list/array if you can’t use any built-in functions?
We can implement a bubble sort fuctions which is iterate over the whole list 
and if a number(n) bigger then the next one it swaps it, so in the end the biggest value will be in the end of the list and a lowest in the front of the list.

#### How do you find the average of values in a list/array if you can’t use any built-in functions?
We can iterate through the list items with a for loop and add it to each other all the items and  append it to a new list/array. We have to divide the result with the length of the basic list and we will get the average of all values.

#### What do we call an *in-place* sort?
in-place means that the algorithm does not use extra space for manipulating the input but may require a small though nonconstant extra space for its operation.  Such as bubble sort. The input gonna be the output when the sorting function executed.

#### Explain an algorithm which sorts a list!
 Bubble sort : This is one of the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they in the wrong order. 
After the sorting is executed the highest value will be in the end of the list and the lowest is in the front.

### Programming paradigms - procedural

#### What is the call stack?
The call stands for the fuction (call) and the stack stands for the stacks in the hole.  Call stack means the current function call. 

#### What is “Stack overflow”?
If there is too much func call in the block and the hole reach its maximum  then  it results a stack overflow. The computer can’t process that much operation so it is gonna overload. We can ruin our computer with it. 

#### What are the main parts of a function?
1, Key word def marks start of a func header.
2, Function name(unique) , we can identify the func with it.
3,parameters → arguments , we pass values to the func. (they are optional)
4, (:) Colon to mark the end of the header.
5, Optional documentation string (docstrings) – describe what the func does.
6, statement inside the func – they must have same indentation level.
7, Option return statement to return a value from the function.

### Programming languages - Python  
#### How do you use a dictionary in Python?
Use {} marks to construct a dict and use [] to index it. Separate the key and value with : and with , between each pari. Keys must be with "" as with list we can print out the dict by printing the reference to it. The dict maps a set of objects (keys) to another set of objects (values). So a dict is mapping of unique keys to values.
#### What does it mean that an object is immutable in Python?
It means that you can not change their state or content. An immutable object can't be changed after it is created. There are built-in types like : int, float, string, bool, unicode, tuple
#### What is conditional expression in Python?
Expressions that return value A or B depending on whether a Boolian value is True or False.
If you want the conditional expression to be evaluated first, you need to surround it with grouping parentheses.
#### What are different types of arguments in Python?
#### What is variable shadowing? (context: variable scope)
#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
#### If you need to access the iterator variable after a for loop, how would you do it in Python?
#### What type of elements can a list contain in Python?
#### What is slice operator in Python and how to use?
#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
#### What is the purpose of the in and not in membership operators in Python?
#### What does the + operator mean when used with strings in Python?
#### Explain f strings in Python?
#### Name 4 iterable types in Python!
#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
#### Does the order of the function definitions matter in Python? Why?
#### What does unpacking mean in Python?
#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
#### What does step over, step into and step out mean while using the debugger?
#### How can you start to debug a program from a certain line using the debugger?

### Version control

#### What are the advantages of using a version control system?
#### What is the difference between the working directory, the staging area and the repository in git?
#### What are remote repositories in git?
#### Why does a merge conflict occur?
#### Through what series of commands could you put a new file into a remote repository connected to your existing local repository?
#### What does it mean atomic commits and descriptive commit messages?
#### What’s the difference between git and GitHub?

## Software design

### Clean code

#### What does clean code mean?
#### What steps do we usually do during a clean code refactoring?

### Error handling

#### What is exception handling?
#### What are the basics of exception handling in Python?
#### In which case should we catch an exception? Why?
#### What can/should we do with an exception in the ‘except’ block?
#### What does the else and finally statement do in a try-except block in Python?

## Software Development Methodologies

#### What is the main goal of a retrospective meeting?

## Programming environment

### Unix

#### What is UNIX and what is Linux?
#### What do we call the shell in Linux?
#### What does root means in a Linux environment?
#### How do you access your personal files in Linux?
#### How can you install an application in Linux?
#### What is package management in Linux, what are repositories?
#### How do you navigate in the filesystem with the command line?
#### What does the following commands do: mkdir, rm, cat, cp, touch?
#### How can you look up what does a command do in Linux if you have no internet connection?
#### What does the following commands do: head, tail, more, less?
#### How do you download a file from internet using the terminal?
