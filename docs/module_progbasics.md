


># Programming Basics questions

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
Clear()     -     Removes all the elements from dictionary
copy()      -     Returns a copy of a dictionary
fromkeys()  -     Returns a dictionary with the specified keys and values
get()       -     Returns the value of the specified key
items()     -     Returns a list containing a tuple for each key value pair
keys()      -     Returns a list containing the dic's keys
values()    -	  Returns a list of all the values in the dictionary
pop()	    -	  Removes the element with the specified value
popitem()   -	  Removes the last inserted key-value pair
setdefault()-	  Returns the value of the specified key. If the key does not exist: insert the key, with the specified value
update()    -	  Updates the dictionary with the specified key-value pairs

### Algorithms

#### Fibonacci sequences. Write a method (or pseudo code), that generates the Fibonacci sequences.
Pseudo code :  rough documentation, readable and understandable even for a layman.

Fibonacci sequence:
This program will show for the given number “n” printed out n-th fibonacci seq.
We use recursion to count it out.
```
def fib(n):
	a = 0
	b = 1
	for i in range(0, n):
		c = a+b
		a = b
		b = c
	return b

for k in range(0, 10):
	print(k)
```


#### How do you find a max value in a list/array if you can’t use any built-in functions?
write get_max(n)
#### How do you find the average of values in a list/array if you can’t use any built-in functions?
We can iterate through the list items with a for loop and add it to each other all the items and  append it to a new list/array. We have to divide the result with the length of the basic list and we will get the average of all values.
write get_average(n)

#### What do we call an *in-place* sort?
in-place means that the algorithm does not use extra space for manipulating the input but may require a small though nonconstant extra space for its operation.  Such as bubble sort. The input gonna be the output when the sorting function executed.

#### Explain an algorithm which sorts a list!
 Bubble sort : This is one of the simplest sorting algorithm that works by repeatedly swapping the adjacent elements if they in the wrong order. 
After the sorting is executed the highest value will be in the end of the list and the lowest is in the front.

### Programming paradigms - procedural

#### What is the call stack?
The call stands for the function (call) and the stack stands for the stacks in the hole.  Call stack means the current function call. 

#### What is “Stack overflow”?
If there is too much function call in the block and the hole reach its maximum  then  it results a stack overflow. The computer can’t process that much operation so it is gonna overload. We can ruin our computer with it. 

#### What are the main parts of a function?
1, Key word def marks start of a function header.
2, Function name(unique) , we can identify the function with it.
3, parameters → arguments , we pass values to the function. (they are optional)
4, (:) Colon to mark the end of the header.
5, Optional documentation string (docstrings) – describe what the function does.
6, statement inside the function – they must have same indentation level.
7, Option return statement to return a value from the function.

### Programming languages - Python

#### How do you use a dictionary in Python?
Use {} marks to construct a dict.  Separate the key and value with : and with , between each par. Keys must be with "" as with list we can print out the dict by printing the reference to it. The dict maps a set of objects (keys) to another set of objects (values). So a dict is mapping of unique keys to values.

#### What does it mean that an object is immutable in Python?
It means that you can not change their state or content. An immutable object can't be changed after it is created. There are built-in types like : int, float, string, bool, unicode, tuple

#### What is conditional expression in Python?
Expressions that return value A or B depending on whether a Boolian value is True or False.
If you want the conditional expression to be evaluated first, you need to surround it with grouping parentheses.

#### What are different types of arguments in Python?
Default arguments - with using the assignment operator in python(=)

keyword arguments - like def myfunc(a, b) --> myfunc(1, 3)

Arbitrary arguments - in case you not know how many arg in the function, use (*). When function call python takes args into tuple and we can iterate over them with a for loop.

#### What is variable shadowing? (context: variable scope)
When there is a global variable and in the function you add  a new argument to the same variable name. When you call the function the variable arg will be that you named inside the function not the global one.

#### What can happen if you try to delete/drop/add an item from a List, while you are iterating over it in Python?
Remove and drop raises an index error because the loop can not iterate over all the item.
To add new item is possible. Remove is also possible if you not indexing the range.


#### What is the "golden rule" of variable scoping in Python (context: LEGB)? What is the lifetime of variables?
LEGB: Local, Enclosed, Global, Built-in
This is the hierarchy when you call a function with (x) arg. First it search the value inside the function (local) if there isn't goes to the outer function if there is after the global and finally the built-in which contains	special variables reserved for python itself. Built-in variable like math module import Pi.

Lifetime of variables:

-Local variables including function parameters have a life from the start of the execution of the function to the end of execution - i.e. the end of the function or the return statement.
-enclosed - from the variable created in the function till the function end.
-Global variables live from when the module is imported until the end of the application - unless the variable is explicitly deleted or changed.
-Built-in - from the module created till you end the script



#### If you need to access the iterator variable after a for loop, how would you do it in Python?
```
empty_list = []
for i in x:
	empty_list.append(i)
	print(empty_list)
```



#### What type of elements can a list contain in Python?
- integers, strings, objects

#### What is slice operator in Python and how to use?
The slice operator is used to slice a given object(string,bytes,tuple,list or range)
slice(1,2,-1) = slice(start, stop, step)

#### What arithmetic operators (+,*,-,/) can be used on lists in Python? What do they do?
"+" - You can add together to lists but you can not add together a list with a number it gives TypeError
"*" - you can not multiply list with a list but you can multiply it with number like lst * 2
"-" - It gives TypeError anyway
"/" - It gives TypeError as well.

You can use all if you iterate through the list and when you append it to a new list you can use
them what they meant to be.


#### What is the purpose of the in and not in membership operators in Python?
 It test for membership in a sequence, such as strings, lists, or tuples.
 The ‘in’ operator is used to check if a value exists in a sequence or not. Evaluates to true if it finds a variable in the specified sequence and false otherwise, 'not in' vica-versa.


#### What does the + operator mean when used with strings in Python?
It adds the strings to each other to make one string in the given order.
#### Explain f strings in Python?
F string is more readable, more concise, and less prone to error than other ways of formatting and they are also faster!
better then %formating() or str.format() this is the upgrade of %formating - You can reference variables in any order by referencing their index, but still looks messy when you use multiply parameters and longer strings.

"F-strings" aka "Formatted string literals". Because f-strings are evaluated at run time, you can put any and all valid Python expressions in them. You can also call function or call method directly. You can have multi line string using f""" hello {expression i.e. name} - expressions replaced with their values.


#### Name 4 iterable types in Python!
list, string, tuple, dictionary, file objects

#### What is the difference between list/set/dictionary comprehension and a generator expression in Python?
Generator expression is similar to list comprehensions, but it doesn't construct a list	object, it generates the next element in demand. It allows us to create a generator without yield keyword.(yield saves the state of the function and can be picked up from the same state when next function call). The generator yields one item at a time and generates item only when in demand. Generator expression create files one by one and it save it in the same memory as the last one.
Generator expressions are more memory and time efficient then list comprehensions. 

#### Does the order of the function definitions matter in Python? Why?
It depends when you call the function. If you call the function before the function the it gives an error. 
Function order doesn't matter in python.


#### What does unpacking mean in Python?
You can unpack a list with * and a dict with ** in the function parameter.

#### What happens when you try to assign the result of a function which has no return statement to a variable in Python?
result --> None 

## Software engineering

### Debugging

#### What techniques can you use while debugging a program in Python?
use debugger, or Thonny. Make breaking point and go line by line. See what function does. Also print() can help with debugging.
In terminal there is a program called GDB. You can make break point as with VSC debugger.
#### What does step over, step into and step out mean while using the debugger?

Step over - goes to next function call
Step into - you can go line by line , step by step inside function.
Step out  - quits from the current function and goes to where the function was called.

#### How can you start to debug a program from a certain line using the debugger?
Make a break point. The function will stop at the break point and after with step into you can go line by line.

### Version control

#### What are the advantages of using a version control system?
The main advantage is that if you working in a group VCS is help you to work freely on any file at any time. And later it allows you to merge all the changes into a common version.  It easier to handle merge a conflicts.  It saves all you latest saves but you currently use only one. You can see what changes you make.

#### What is the difference between the working directory, the staging area and the repository in git?
Working directory - This is where you create the files and they are currently untracked.
Staging area - You can add the files to the staging area where it starts tracking the file and saving changes in the file.collect files.
Repository in git - When commit you can save the collected files. And finally commit them. Finalizing staging area files.

#### What are remote repositories in git?
When you push it to cloud from the local repository.

#### Why does a merge conflict occur?
Because there was a new update in the file and in your local repository you have the older version. When you want to pull it is gonna cause a merge conflict, but you can handle locally.

#### Through what series of commands could you put a new file into a remote repository connected to your existing localrepository?
git add . -> git commit -m "message" -> git push

#### What does it mean atomic commits and descriptive commit messages?
Atomic commit means that you should commit wisely and separately by futures, function. You should do it frequently. 
Commit message should be meaningful and short , to understand what that actual function, future does. Easily readable and understandable.

#### What’s the difference between git and GitHub?
Git is a revision control system, a tool to manage your source code history. tool
Github is a webpage and company, a hosting service for Git repositories. service to manage projects that use Git.

## Software design

### Clean code

#### What does clean code mean?
It means that your code is readable and understandable for person whose read the code. It also follows the clean code basic rules.
#### What steps do we usually do during a clean code refactoring?
1, - Variable names meaningful
2, - No code lines duplicated
3, - No dead code
4, - Avoid magic numbers
5, - A function does one thing
6, - long method block < 30
7, - Wrong comment usage

### Error handling

#### What is exception handling?
Exception handling is the process of responding to exceptions when a computer program runs. An exception error occurs when an unexpected event happens that requires special processing.(Examples include a user providing abnormal input, a file system error being encountered when trying to read or write a file, or a program attempting to divide by zero.) Exception handling attempts to gracefully handle these situations so that a program (or worse , an entire system) does not crash.

#### What are the basics of exception handling in Python?
To handle possible exceptions, we use a try - except block. Python will try to process all the statements inside the try block.
If an error occurs at any point as it is executing them, the flow of control will immediately pass to the except block, and any remaining statements in the try block will be skipped.

#### In which case should we catch an exception? Why?
Examples include a user providing abnormal input, a file system error being encountered when trying to read or write a file, or a program attempting to divide by zero. ---> These causes an error.

#### What can/should we do with an exception in the ‘except’ block?
We should write out an informative message about the error and why was it occurred.

#### What does the else and finally statement do in a try-except block in Python?
Else - The statements inside the else block will be executed only if the code inside the try block doesn’t generate an exception.

Finally - This code always executes after the other blocks, even if there was an uncaught exception (that didn’t cause a crash, obviously) or a return statement in one of the other blocks. Code executed in this block is just like normal code: if there is an exception, it will not be automatically caught (and probably stop the program). This block is also optional.
It executes whatever it happens, even when except block happens or try block doesn't generate an exception.


## Software Development Methodologies

#### What is the main goal of a retrospective meeting?
The goal of the retrospective is for the team members to discuss among themselves about how the work went during the last sprint so that better ways can be found to meet the project’s goals. The team is looking for how it could have executed better. In short, what do they as an individual or team need to change or alter to have a better chance of progress the next week.

## Programming environment

### Unix

#### What is UNIX and what is Linux?
UNIX is an operating system written in C in the late 60s and it works on CLI(Command line interface). Its a 3 layer system.
Linux is an operating system. It has a built-in software called Kernel which is controls the resources of the machine. It gives instructions from applications to the OS. It's free and there is many new distributions today such as Ubuntu.

#### What do we call the shell in Linux?
Shell is an interface between the users and the kernel part that waits for you to type commands and it interprets them . like a nut shell is wrapped around a nut kernel.

#### What does root means in a Linux environment?
The root user, also known as the superuser or administrator, is a special user account in Linux used for system administration. It is the most privileged user on the Linux system and it has access to all commands and files. The root user can do many things an ordinary user cannot, such as installing new software, changing the ownership of files, and managing other user accounts.
In some Linux distributions, most notably Ubuntu, the root account password is locked by default. Instead, the sudo command is used for commands that require root privileges.

#### How do you access your personal files in Linux?
Files --> Home --> mydocuments/ mypictures/ mymusic

#### How can you install an application in Linux?
via shell with a command. Check out the web for proper command.

#### What is package management in Linux, what are repositories?
 Package managers typically maintain a database of software dependencies and version information to prevent software mismatches and missing prerequisites. 
 Repositories are servers which contain sets of packages.

#### How do you navigate in the filesystem with the command line?
With cd .../.../..   cd .. - goes back one folder.  cd - goes to homepage
with ls - list files

#### What does the following commands do: mkdir, rm, cat, cp, touch?

mkdir - Make directory 

rm    - Remove file or files

cat   - It reads data from the file and gives their content as output. It helps us to create, view, concatenate files. There are lot of option for it. It can be used to join multiple files together and print the result on screen 

cp    - This command is used to copy files or group of files or directory. It creates an exact image of a file on a disk with different file name.

touch - It is used to create a file without any content. The file created using touch command is empty. there are many more options such as check file is created or change access time.

#### How can you look up what does a command do in Linux if you have no internet connection?
with command help you can check it out what you need.

#### What does the following commands do: head, tail, more, less?

more - shows the file page by page, should use in. Once you go to the next page you can't go back

less - does the same as 'more' except it can go back the previous page, it's much more handly.

head - Shows the first 10 lines of a file, unless otherwise stated. 

tail - Shows the last part of the file / with tail -n shows the last n lines of the file.

#### How do you download a file from internet using the terminal?
Install Curl - $ curl –o [filename] [URL] there are many additional commands like downloads from FTP server or get multiply files.

Install wget - it supports recursive download feature. This feature is very useful if you want to download an entire website for offline viewing or for generating a backup for static website. In addition, you can use it to retrieve content and files from various web servers.

$ wget [URL] - download file or webpage by URL
$ wget -O [filename] [URL] - download files with different name
$ wget –r [URL] - download everything under the specified directory whether a website or FTP sit(recursively download file)
