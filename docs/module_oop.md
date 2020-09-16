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