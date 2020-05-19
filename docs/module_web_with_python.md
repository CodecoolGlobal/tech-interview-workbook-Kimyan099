# Web with Python questions

## Software design

### Clean code

#### Point out 5 suggestions, how to format an SQL query!
- Naming objects - naming rules
- Alignment - keyword on the left and the rest of the code to the right.
- Indentations help a lot with readability.
- Indentation - newline for each query to make it more readable.
- Commenting 
- Using Join for multiply tables

#### What layers can you name in a simple web application?
-  Controllers - entry point of request(http, Action Authorization, response)
-  Services - like Resource Authorization. Resource permission stored inside the database
- Repositories*database) - This simply makes the code easier to read. The method you use to persist data (writing to file, DB, etc.) has nothing to do with the business logic that we are executing and so it would only get in the way.
- Domain

### Error handling
#### What error can occur, when an array does not have an element on the requested index?
We get *IndexError*.
#### What is the “finally” block, and how would you use it?
The *finally* statement lets you execute code, after try and catch, regardless of the result.
- I would use it for example in a board game, the finally block could would do the board clear so whatever is happening in the try/catch block, the board would be re-writed.

#### Why should we catch special exception types?
If an error occurs we can handle it with a meaningful error message to the call on the user what could be the problem.(like login, not existed web page etc.)
### Security
#### What is SQL injection? How to protect an application against it?
- SQL injection is a type of *injection* attack. This  occurs when maliciously crafted inputs are submitted by an attacker, causing an application to perform an unintended action.
- *Parameterized statements* make sure that the parameters passed into SQL statements are treated in a safe manner. The parameterized string(query) and the parameters are passed to the database separately and get called in the executeQuery(sql, email)

#### What is XSS? How to protect an application against it?
Cross-Site Scripting attacks occur when:
1.  Data enters a Web application through an untrusted source, most frequently a web request.
2.  The data is included in dynamic content that is sent to a web user without being validated for malicious content.

 transmitting private data, like cookies or other session information, to the attacker, redirecting the victim to web content controlled by the attacker.

Against it we can use the XSS prevention rules:
- removing support for HTTP TRACE on all web servers.
- Never Insert Untrusted Data in your HTML documents
- Escape the following characters with HTML entity encoding to prevent switching into any execution context, such as script, style, or event handlers.
- Prevent DOM-based XSS
- Properly use modern JS frameworks

#### How to properly store passwords?
Use bycript. Bycript use salt code next to the password to get the bycripted password. This is the most secure way to store password.
#### What is HTTPS?
*Hypertext Transfer Protocol Secure* :  is an extension of the (HTTP). It is used for secure communication over a computer network and is widely used on the Internet(uses TLS-secure connection between users).
HTTP is not encrypted and thus is vulnerable to "man-in-the-middle" and "eavesdropping attacks" which can let attackers gain access to website accounts and sensitive information, and modify web pages . HTTPS is designed to withstand such attacks and is considered secure against them.
#### What is encryption and decryption?
*Encryption* is the process of converting normal message (plaintext) into meaningless message (Ciphertext). Whereas *Decryption* is the process of converting meaningless message (Ciphertext) into its original form (Plaintext).
#### What is hashing?
The hash function takes a variable length message input and produces a fixed-length hash output. they insure the integrity of transmitted data. A formula generates the hash, which helps to protect the security of the transmission against tampering.(H256)
#### What is the difference between encryption and hashing? When would you use which?
- You encrypt information with the intention of decrypting it later. So is for protecting your cloud data or transmitting financial data etc. *The key is that encryption is reversible. Hashing is not.* Hashing is one-way.For a Login  i would use hasing the passwords. I would use encryption for privite data that maybe i share somewhere. 
#### What encryption methods do you know?
*Asymmetric Encryption* –  One key encrypts, the other key decrypts. The encryption only goes one way.
*Symmetric Encryption* – This is closer to a form of private key encryption. Each party has its own key that can both encrypt and decrypt.
**modern**: 
- *AES* – AES stands for Advanced Encryption Standard. It puts plaintext through a number of “transformation rounds” determined by key size, each round consists of several processing steps.
- *RSA* – RSA stands for Rivest-Shamir-Adlemen, after its creators, it is a public key encryption algorithm (asymmetric). It uses the factorization of prime numbers to encipher plaintext.
#### What hashing methods do you know?
- *SHA* – stands for Security Hashing Algorithm and it’s probably best known as the hashing algorithm used in most SSL/TLS cipher suites.
- *MD4* – is a self-loathing hash algorithm. The 128-bit hashing algorithm has security problems.
#### How/where would you store sensitive data (like db password, API key, ...) of your application? 
 I would store it with salt and hashed with authentication key. I would store it in a rented local storage that many companies use nowadays.

## Computer science

### Algorithms

#### What is the difference between Stack and Queue data structure?
- Stack : A stack follows the **LIFO** (Last In First Out) principle, i.e., the element inserted at the last is the first element to come out.
In stack we always keep track of the last element present in the list with a pointer called **top**.

- Queue: The queue data structure follows the **FIFO** (First In First Out) principle, i.e. the element inserted at first in the list, is the first element to be removed from the list.
In queue we always maintain two pointers, one pointing to the element which was inserted at the first and still present in the list with the **front** pointer and the second pointer pointing to the element inserted at the last with the **rear** pointer.
#### What is BubbleSort? Describe the main logic of this sorting algorithm.
The Bubble sort takes the first element of the list and it iterates trough the list. If the element bigger then the next one , it swaps it and so on. When  sort is end the highest element will be in the end of the list and the smallest in front. 
#### Explain the process of finding the maximum and minimum value in a list of numbers!
Let name a variable and make it equal to the list first element. After with a for loop iterate trough the list and if the actual element bigger/smaller then the variable then we make the variable equal to it's new element. At the end we get the maximum/minimum element of the list.
#### Explain the process of calculating the average value in an array of numbers!
Let name a variable and make it equal to 0. Iterate trough the list with a for loop and add every element to this variable. After just dividing that variable with the list length. We get the average value of the list.
#### What is Big O complexity? Explain time and space complexity!
Big O is essentially an equation that describes how the runtime changes, how the scales goes up. When we talk about complexity we express how the growth of some input/condition affects the consumption of some resource. This resource can be either _time_ or _memory_.
'n' is always a length of the input in Big O Notation.
Space complexity is the amount of memory used by the algorithm.
An algorithm is a set of instructions designed to perform a specific task.
#### Explain the process of calculating the average value in a linked list of numbers!
i would create a Value and counter variable. Iterate trough the n long  list with a for loop and make another for loop  for every x element in the list. add all the n and x value to the Value variable and with every iteration the counter increased by 1. At the end just divide the Value with the counter and we get the average value of the list.


### Procedural
#### How the CASE condition works in SQL?
The CASE statement goes through conditions and returns a value when the first condition is met. So, once a condition is true, it will stop reading and return the result. If no conditions are true, it returns the value in the ELSE clause.
#### How the switch-case condition works in JavaScript?
-   The switch expression is evaluated once.
-   The value of the expression is compared with the values of each case.
-   If there is a match, the associated block of code is executed.
-   If there is no match, the default code block is executed.
#### How to achieve a switch-case-like structure in Python?
Dictionary mapping
`def` `numbers_to_strings(argument):`

		`switcher` `=` `{`

			`0``:` `"zero"``,`
			`1``:` `"one"``,`
			`2``:` `"two"``,`
	`}
	`return` `switcher.get(argument,` `"nothing"``)`
This will return one of the value if one of the key is match with the argument , it goes line by line till don't find one.
#### Explain variable scoping in Python!
A variable created in the code body it's called the scope. 
The local scope only can used inside a function or in the function inner function. 
A global scope can be used anywhere in the code.
Mention variable shadowing.
#### What’s the difference between const and var in JavaScript?
*var* declarations are globally scoped or function scoped while *const* are block scoped. *var* variables can be updated and re-declared within its scope; *const* variables can neither be updated nor re-declared. 
The problem with var :
```
var greeter = "hey hi";
    var times = 4;

    if (times > 3) {
        var greeter = "say Hello instead"; 
    }

    console.log(greeter) //"say Hello instead"

Once you re-defined greeter in the code everywhere is gonna change
 and make bugs in your code.
```

#### How the list comprehension looks like in Python?
x = [i * 2 for i in range 10]
print(x)
Output: [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
#### How the “ternary expression” looks like in Python?
`
is_nice = True
state = "nice" if is_nice else "not nice"
`
It allows to quickly test a condition instead of a multiline if statement
#### How the ternary expression looks like in JavaScript?
```js
var age = 26;
var beverage = (age >= 21) ? "Beer" : "Juice";
console.log(beverage); // "Beer"
```
This operator is frequently used as a shortcut for the if statement.
#### How to import a function from another module in Python?
Import data_handler
x = data_handler.get_all_user()
#### How to import a function from another module in JavaScript?
import {dataHandler} from "./data_handler.js";


### Functional
#### What is recursion?
recursive algorithms break down a problem into smaller pieces which you either already know the answer to, or can solve by applying the same algorithm to each piece, and then combining the results.
#### Write a recursive function which calculates the Fibonacci numbers!
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
	print(fib(k))
```

#### How to store a function in a variable in Python?
```
def func(n):
	print(n)

func2 = func
func2()
```
#### List the ways of defining a callable logical unit in JavaScript!
We break code down, starting with the functions. Rather than having one function that does everything, strive to have many functions, with each function only doing one thing.
Comments may help explain what the code is doing,

#### What is an event listener? How to attach one?
An event listener is a method attaches an event handler to the specified element.
```
let button = document.queryselectorAll("button");
button.addEventListener("click", buttonClick);
```
#### How to trigger an event in JavaScript?
It depends what is the event listener triggered on. It could be a click or key press or any other impulse that you attached for it.
#### What is a callback function? Tell some examples of its usage.
A callback function is a function passed into another function as an argument, which is then invoked inside the outer function to complete some kind of routine or action like another function. When that function ends the the main function can start running.
It can be synchronous or asynchronous.
```
function createQuote(quote, callback){ 
  var myQuote = "Like I always say, " + quote;
  callback(myQuote); // 2
}

function logQuote(quote){
  console.log(quote);
}

createQuote("eat your vegetables!", logQuote); // 1

// Result in console: 
// Like I always say, eat your vegetables!
```
#### What is a Python decorator? How does it work? Tell some examples of its usage.
Decorators are very powerful and useful tool in Python since it allows programmers to modify the behavior of function or class. Decorators allow us to wrap another function in order to extend the behavior of wrapped function, without permanently modifying it.

In Decorators, functions are taken as the argument into another function and then called inside the wrapper function.
Function can be passed as argument to another function.
```
def first(msg):
    print(msg)    

first("Hello")

second = first
second("Hi")

Output:
Hello
Hi
```

#### What is the difference between synchronous and asynchronous execution?
The synchronous execution is executing immediately like forEach in js. 
In an asynchronous function like fetch is not waiting for executing everything line by line, when it start to fetch the data the function goes toward and the fetch is executing outside the function and when it ends the result goes to the end of the function. 

## Programming languages

### SQL

#### How can you connect your application to a database server? What are the possible ways?
Using environment variables. We have to define these variables first and use a database adapter like psycopg2 to make it secure. Whit these we can connect our sql database to out application.
#### When do you use the DISTINCT keyword in SQL?
Inside a table, a column often contains many duplicate values; and sometimes you only want to list the different (distinct) values. With the distinct keyword it's only give us one row even if there is more with the same properties.
#### What are aggregate functions in SQL? Give 3 examples.
An aggregate function performs a calculation one or more values and returns a single value. The aggregate function is often used with the group by clause and having clause of the SELECT statement.
Select max(rating) as max_rating From table
Select rating from table group by max(rating)
Select rating from table group by rating Having rating < 5
#### What kind of JOIN types do you know in SQL? Could you give examples?
FULL, INNER , RIGHT , LEFT 
SELECT rating from table FULL JOIN another_table on table_id = another_table table_id
#### What are the constraints in sql?
Constraints are used to limit the type of data that can go into a table. This ensures the accuracy and reliability of the data in the table. If there is any violation between the constraint and the data action, the action is aborted.
INDEX, NOT NULL, UNIQUE, PRIMARY KEY
#### What is a cursor in SQL? Why would you use one?
Cursor is to  hold the result of a query that retrieves data.
A database cursor is an object that enables traversal over the rows of a result set. It allows you to process individual row returned by a query.
This is what cursor.execute does.  
Modify data base indexes 
#### What are database indexes? When to use?
Indexing is a way to optimize the performance of a database by minimizing the number of disk accesses required when a query is processed.
 It is a data structure technique which is used to quickly locate and access the data in a database.
Indexing is a way of sorting a number of records on multiple fields. Creating an index on a field in a table creates another data structure which holds the field value, and a pointer to the record it relates to. This index structure is then sorted, allowing Binary Searches to be performed on it.
 
 Now, imagine you want to find a particular Chapter that contains a word "**Alchemist**". Without an index page, you have no other option than scanning through the entire book/Chapters. i.e: 1000 pages.

This analogy is known as **"Full Table Scan"** in database world.

[![enter image description here](https://i.stack.imgur.com/Mnuvr.jpg)](https://i.stack.imgur.com/Mnuvr.jpg)

But with an index page, you know where to go! And more, to lookup any particular Chapter that matters, you just need to look over the index page, again and again, every time. After finding the matching index you can efficiently jump to that chapter by skipping the rest.
#### What are database transactions? When to use?
A transaction is a unit of work that you want to treat as "a whole." It has to either happen in full or not at all.

A classical example is transferring money from one bank account to another. To do that you have first to withdraw the amount from the source account, and then deposit it to the destination account. The operation has to succeed in full. If you stop halfway, the money will be lost, and that is Very Bad.

In modern databases transactions also do some other things - like ensure that you can't access data that another person has written halfway. But the basic idea is the same - transactions are there to ensure, that **no matter what happens, the data you work with will be in a sensible state**. They guarantee that there will NOT be a situation where money is withdrawn from one account, but not deposited to another.
#### What kind of database relations do you know? How to define them?
There is many database relations nowadays such as one to one, one to many and back, many to many and self reflecting relations.  When selecting data from multiply tables we can use the Join query like Cross, Natural, Inner, Left and Right Joins.
The relations can be bond by Primary-key.
#### You have a table with an “address” field which contains data like “3525, Miskolc, Régiposta 9.” (postcode, city, street name and address). How would you query all records related to Miskolc?
SELECT * FROM table WHERE city = 'Miskolc'
#### How would you keep track of what kind of data has changed after an UPDATE or DELETE operation in a table?
I would create two tables delete and update and when data has been changed it would also append the changes to the appropriate table, so i can keep track all the data.


### HTML & CSS

#### What’s the difference between XML, XHTML and HTML?
**XML**(EXtensible  Markup Language) and **HTML**(Hypertext Markup Language) are both of web and markup languages. They originated from **SMGL**(Standardized General Markup Language). Tags are basic building blocks of HTML and XML documents.

- *XML* grew out of a desire to be able to use more than just the fixed vocabulary of HTML on the web. It is a meta-markup language.
- *HTML* as actually used on the web is best described as a custom language influenced by SGML.
 
 
 Differences between HTML and XML
 1. HTML tags are predefined tags where as XML tags are user defined tags.
 2. HTML tags are limited number of tags where as XML tags are extensible.
 3. HTML tags are case insensitive where as XML tags are sensitive.
 4. HTML tags are meant for displaying the data but not for describing the data where as XML tags are meant for describing the data.
 5. HTML focuses on how data looks where as XML focuses on what data is.


**XHTML**( Extensible HyperText Markup Language) is a reformulation of HTML in XML syntax. While very similar in many respects, it has a few key differences such as XHTML is stricter than HTML.

#### How to include a JavaScript file in a webpage?
```
<script src="{{ url_for('static', filename='js/main.js') }}" defer></script>
```
#### How to include a CSS file in a webpage?
```
<link rel="stylesheet" href="{{ url_for('static', filename='css/mystyle.css') }}">
```
#### How to select an element using its id in CSS?
```
#card-container {
	display: block;
}
```
#### How to select elements using their class in CSS?
```
.card-container {
	display: block;
}
```
#### How to select elements which have the ‘alpha’ and ‘beta’ classes in CSS?
```
.card-container.paragraph {
	display: block;
}
```
#### How to select all list items in all ordered lists on the page in CSS?
```
ol {
	/*code;*/
}
```
#### How to select elements using their attributes in CSS?
There are a few way to do that:
```
[data-value] {
  /* Attribute exists */
}

[data-value="foo"] {
  /* Attribute has this exact value */
}

[data-value*="foo"] {
  /* Attribute value contains this value somewhere in it */
}

[data-value~="foo"] {
  /* Attribute has this value in a space-separated list somewhere */
}

[data-value^="foo"] {
  /* Attribute value starts with this */
}

[data-value|="foo"] {
  /* Attribute value starts with this in a dash-separated list */
}

[data-value$="foo"] {
  /* Attribute value ends with this */
}
```
#### What are UX and UI?
**UX**(User Experience Design) is focused on the user's journey to solve a particular problem.
It refers to any interaction a user has with a product or service.
*UX* design considers each and every element that shapes this user experience like how
does it make the user feel or how easy is it for the user to accomplish their desired task while using the product. They insure user experiences. 

**UI**(User Interface Design) is focused on how product surfaces or interfaces look and function like what happens if the user clicks a button. User interface design is a purely digital practice. It considers all the visual, interactive elements of a product interface—including buttons, icons, spacing, typography, color schemes, and responsive design.

#### Please list some points that an application should fulfill to have good UX.
- The user overall feel has to be good about the application.
- The user feel excited or satisfied with the product.
- The site must be easy to use
- Content needs to be accessible to people with disabilities (example:colorblind)
#### What is XML, XSLT, DTD?

**XML** is a simplified subset of SGML. It stands for *Extensible Markup Language*. 
*XML* grew out of a desire to be able to use more than just the fixed vocabulary of HTML on the web. It is a meta-markup language.

**XSLT** stands for *Extensible Stylesheet Language Transformation*. It is a strong versions of CSS that formats the XML page for viewing.

**DTD** stands for Document Type Declaration. It is a set of instructions that states what tags are usable and what (re)action they create. Each browser has a DTD set in it's programming set by the browser companies. This is how some tags will work in only one type of browser or version. It has the tags stated in it's DTD. XML makes it possible to create unique tag sets by applying it's own DTD. This makes the DTD more compatable with more browsers.

#### What is the difference between HTML and XML?

 1. HTML tags are predefined tags where as XML tags are user defined tags.
 2. HTML tags are limited number of tags where as XML tags are extensible.
 3. HTML tags are case insensitive where as XML tags are sensitive.
 4. HTML tags are meant for displaying the data but not for describing it where as XML tags are meant for describing the data.
 5. HTML focuses on how data looks where as XML focuses on what data is.

### Javascript

#### What is javascript?
JavaScript is a scripting or programming language that allows you to implement complex features on web pages — every time a web page does more than just sit there and display static information for you to look at — displaying timely content updates, interactive maps, animated 2D/3D graphics etc. — you can bet that JavaScript is probably involved. It is the third layer of the layer cake of standard web technologies, two of which HTML(Hypertext Markup Language) and CSS(Cascading Style Sheets)
#### When to use AJAX? Bring examples of its usage.
Ajax programming is that you can exchange data in the background without actually disturbing the user experience.

 And when you want render the access of data more efficiently and effectively.
-  Fetching data from a url with fetch API.
- Retrieve database information.
- Request XML files.
- Load an XML file.
- Lightboxes instead of pop-ups.

#### What is DOM and how to manipulate it from Javascript?
A **DOM**(Document Object Model) connects web pages to scripts or programming languages by representing the structure of a document.
The *DOM* represents a document with a logical tree. Each branch of the tree ends in a node, and each node contains objects. *DOM* methods allow programmatic access to the tree. With them you can change the document's structure, style, or content.

*Example*:
Let's say we have cards filled in a row in the whole page containing imdb ratings for film titles. We want to change the color of the card if we click on it.

Firstly we need an eventListener() to attach to an event like click, keydown etc. When it is fired the function triggers.
```
/*Javascript*/

let cards = document.querySelectorAll('.cards');  
for (let card of cards) {  
    card.addEventListener('click', () => {  
        card.classList.add('selected');
```
In the *css* below the .card.selected  keyword we can copy the .card attributes and change the background color to any color we would like to.
#### What are events and how/why to use them in Javascript?
*What:*
Events can represent everything from basic user interactions to automated notifications of things happening in the rendering model.
There are many type of events such as Mouse, keyboard, form, Css transaction, Websocket, Resource events etc.

*Why:
Because ,JavaScript in the browser uses an event-driven programming model. Everything starts by following an event !**
#### What is event bubbling/capturing? How would you use it?
Event bubbling and capturing are two ways of event propagation in the HTML DOM API, when an event occurs in an element inside another element, and both elements have registered a handle for that event. The event propagation mode determines in which order the elements receive the event

With bubbling, the event is first captured and handled by the innermost element and then propagated to outer elements.

With capturing, the event is first captured by the outermost element and propagated to the inner elements.
Capturing is also called "trickling", which helps remember the propagation order:
`trickle down, bubble up`

## Example

```
<div>
    <ul>
        <li></li>
    </ul>
</div>
```

In the structure above, assume that a click event occurred in the `li` element.

In capturing model, the event will be handled by the `div` first (click event handlers in the `div` will fire first), then in the `ul`, then at the last in the target element, `li`.

In the bubbling model, the opposite will happen: the event will be first handled by the `li`, then by the `ul`, and at last by the `div` element.

the performance of event bubbling may be slightly lower for complex DOMs.
#### What is JSON and how do we use it?
**JSON**(Javascript Object Notation) is a lightweight format for storing and transporting data. It is user friendly, easy to understand. 

How to use it:
- It is often used when data is sent from the server to the web page. 
- Since you are forced to communicate data using key-value pairs and arrays this is where Json come into picture.
## Software engineering

### Version control

#### What type of branching strategy would you use?
Github workflow:
The working code is always on a separate branch from master usually called development branch. If You start working with a new task just crate another separate branch from development and when is it finished it can merged back. If the sprint is over and we make sure that the development branch runs perfectly we can merge it to the master or rebaseing it(cleaner). 
#### What would you do if you find a bug on the production code (master branch)?
I would create a bugg fix branch and start working with that problem. When is it solved just merge it back to the master.
#### How can you move changes from one branch to another in GIT?
`
~git checkout master
`
#### How does a VCS help with code reviews?
Version control systems are a category of software tools that help a software team manage changes to source code over time. Version control software keeps track of every modification to the code in a special kind of database. If a mistake is made, developers can turn back the clock and compare earlier versions of the code to help fix the mistake while minimizing disruption to all team members. Version control helps teams solve these kinds of problems, tracking every individual change by each contributor and helping prevent concurrent work from conflicting.
#### What is your favorite git command? Why?
`
~git stash
`
Because the command saves your local modifications away and reverts the working directory to match the `HEAD` commit.
Basically you start whit a clear working directory and your local changes are saved as well.
#### What does remote/local mean in Git? 
Git Remote repository is belongs to a server, if you push files it can be seen for your team. 
Git Local repository is the one on which we are make local changes. It can not be seen by other developers.
### DevOps

#### Why is it good to use a package manager software?
Because it updates a newest package always and we don't have to care much about it. When a package is out it call upon us to do we want to install that package. It is good for software maintenance. Some package managers provide additional features during installation. 
#### Why is it good to use a virtual environment for a project?
Virtual environment usually has a requirements.txt file  which contains all the software with the current dependencies on it. Without it the code probably will crash somewhere. 
It is one of the most important tools for that most of the python developers use.
### Networks

#### What kind of HTTP status codes do you know?
-   200 OK
-   301 Moved Permanently
-   302 Found
-   400 Bad Request
-   403 Forbidden
-   404 Not Found
-   405 Method Not Allowed
-   408 Request Timeout
-   500 Internal Server Error
-   504 Gateway Timeout
#### What is a API?
**API**(Application programming interface) is a way of for apps to borrow functionality and data from each other. An API is a code that allows two software to communicate with each other. One program call another program API to get access to data or functionality of the other program. An API is  a messenger that takes a request and tells the system what you want to do and then returns the response back to you like a waiter in a restaurant. You ask for a meal(data) , the waiter  writes down the order(processing it) as ask that meal from the chef(another program which has the data) and it returns it by time to your program by the waiter. You take a request and will get a response for it even when the meal(data) it is not available.
#### What is REST API?
Rest stands for Representational State Transfer. 
RESTful API is an application program interface (API) that uses HTTP requests to GET, PUT, POST and DELETE data.
#### What is JSON? When to use?
**JSON**(Javascript Object Notation) is a lightweight format for storing and transporting data. It is user friendly, easy to understand. 

When to use it:
- It is often used when data is sent from the server to the web page. 
- Since you are forced to communicate data using key-value pairs and arrays this is where Json come into picture. 

JSON is used when data has to be send to another application. 
#### What is TCP/IP? What layers does it define, what are they responsible for?
-**TCP/IP**(Transmission Control/Internet Protocol) is a language that computer uses to access to the internet. It consist of a suit of protocols designed to establish a network of networks to provide  a host with access to the internet like a set of rules to allow to communicate with each other.

It is like a layered sandwich:

- Application - what your programs like web browser directly interact with. This layer has protocols like `HTTP(Hypertext transfer protocol)`.
- Transport - It is where `TCP` lives along with another schema called `UDP`. This layer controls of the flow of information between the application program running on server and client side.
- Internet - This layer uses `IP(Internet protocols)` to attach both the origin and destination IP addresses so the layer knows where it is came from and where it is going.
- Data link - This is that moves data within  a local  area network using Ethernet, ATP.
- Physical - 
#### What’s the difference between TCP and UDP?
**TCP**(Transmission Control Protocol)  is connection oriented – once a connection is established, data can be sent bidirectional. As a message makes its way across the internet) from one computer to another. This is connection based. It is for applications that require 
high reliability.
**UDP** (User Datagram Protocol)  is a simpler, connectionless Internet protocol. Multiple messages are sent as packets in chunks using UDP. UDP is also a protocol used in message transport or transfer. This is not connection based which means that one program can send a load of packets to another and that would be the end of the relationship. It is Fast and gives efficient transmissions that programs like games needed.
#### How does an HTTP Request look like? What are the most relevant HTTP header fields?
A simple request from the server contains the following components:

1, An HTTP method  a verb like `GET` or `POST` that describes the action to be performed.
2.  An optional set of _HTTP headers_ specifying the request, or describing the body included in the message. (Example - Accept-Language: EN).
3. An empty line
4.  Optional message body
#### How does an HTTP Response look like? What are the most relevant HTTP header fields?
A simple response from the server contains the following components:

1  HTTP Status Code (For example HTTP/1.1 301 Moved Permanently, means the requested resource was permanently moved and redirecting to some other resource).
2  Headers (Example – Content-Type: html)
3  An empty line.
4  A message body which is optional.

#### What is DNS? How does it work?
The Domain Name System (DNS) is the phonebook of the Internet. Humans access information online through domain names, like `google.com` or `espn.com`. Web browsers interact through Internet Protocol (IP) addresses. DNS translates domain names to IP addresses so browsers can load Internet resources. It is for users. It much easier to memorize `google.com` then `2001:4860:4860::8888`
#### What is a web server?
On the `hardware side`, a web server is a computer that stores web server software and a website's component files (e.g. HTML documents, images, CSS stylesheets, and JavaScript files). It is connected to the Internet and supports physical data interchange with other devices connected to the web.

On the `software side`, a web server includes several parts that control how web users access hosted files, at minimum an _HTTP server_. An HTTP server is a piece of software that understands URLs (Uniform Resource Locator). URL is a text string that specifies where a resource (such as a web page, image, or video) can be found on the Internet.") 
#### Explain the client-server architecture.
The providers of a resource or service, called servers and service requesters called clients.
Often clients and servers communicate over a computer network on separate hardware, but both client and server may reside in the same system. A server host  runs one or more server programs, which share their resources with clients. A client does not share any of its resources, but it requests content or service from a server. Clients, therefore, initiate communication sessions with servers, which await incoming requests.
#### What would you use a session for?
Session is used for creating a login . It prevents that a user can get access only his data that is secured with salted password , email and username mostly. Session use cookies a a key of sorts, to associate with the data that is stored on the server side.
#### What would you use a cookie for?
**Cookies** are most commonly used to track website activity. When you visit some sites, the server gives you a *cookie* that acts as your identification card. Upon each return visit to that site, your browser passes that *cookie* back to the server. Servers can use cookies to provide personalized web pages.

## Software Development Methodologies

#### What kind of software development methodologies do you know? What are the main features of these?
*Agile Development Methodology:*
![enter image description here](https://www.synopsys.com/blogs/software-security/wp-content/uploads/2017/03/agile-development.jpg)



Teams use the agile development methodology to minimize risk (such as bugs, cost overruns, and changing requirements) when adding new functionality. 
Main Futures:

- User stories -> backlog
- Scrum team(with lead) 
- Sprint planning
- production deployment
- Sprint Retrospective
- Product review
- 

*WaterFall Development Methodology:*
It is a  linear model that consists of sequential phases (requirements, design, implementation, verification, maintenance) in which distinct goals are accomplished. Each phase must be 100% complete before the next phase can start, and **traditionally there is no process for going back to modify the project or direction**.

#### What are the SCRUM roles?
- One of the most important things for the success of scrum is the role of the `Product Owner`, who serves as an interface between the team and other involved parties (stakeholders).
- The `Scrum Master` does not interfere into the decisions of the team regarding specifically the development, but rather is there for the team as an advisor. He `only interferes` actively `when anybody` of the team or any other participant of a project (Stakeholder) `does not obey the rules of Scrum.`
- The `Development Team` in Scrum a team is not just the executive organ that receives its tasks from the project leader, it rather decides self dependent, which requirements or User Stories it can accomplish in one sprint.
#### What are the SCRUM ceremonies?
*Ceremonies :*

- Sprint planning
- Sprint review
- Sprint retrospective
- Daily Scrum
#### What are the SCRUM artifacts?
*Artifacts :*

- Product backlog - With the dynamic nature of product development, the Product Backlog is constantly being updated and refined.
- Sprint backlog - The Sprint Backlog is a highly visible, real-time picture of the work that the Development Team plans to accomplish during the Sprint
- Product increment - In Scrum, the Development Team works to deliver a new Increment of the product every Sprint.
#### What is the main goal of a retrospective meeting?
The *retrospective meeting* is for the team members to discuss among themselves about how the work went during the last sprint so that better ways can be found to *meet* the project's *goals*. They talk about what and how could have been better during the sprint to handle this problem for the next sprint. It can be individual or shared problem. 
#### Explain, when would you recommend to use the waterfall methodology?
*Waterfall methodology* could be used when :

- The project is simple
- The project is huge -> This is particularly well suited to large teams that may see members come and go throughout the life cycle of the project, allowing the burden of design to be placed on the core documentation and less on any individual team member.