# Basic algorithms and data structures
This note contains my personal's understanding for some basic algorithms and data structures, and how to apply them to specifc problems.

## Data structures:
Basic data structures whose properties can be utilized to solve algorithm problems.

### Array and Strings
####[Array](https://en.wikipedia.org/wiki/Array_data_structure)
a collection of elements, which is accessed by index. It usually has a fixed size.

It may be the first choice for most of algorithm problems. But it's not a good choice, if the size of elements can not be determined or the collection frequently needs to do a search for values.

####[String](https://en.wikipedia.org/wiki/String_(computer_science))
a sequence of characters, like an array of charachers. But in some programming languages, String is immutable.

##### Algorithm problems about string minipulation.
String algorithms usually are similar with array problems. Differences:

* String concatenation is easier than array, but if a solution may need to frequently concatenate strings, StringBuffer and StringBuilder are better choices.
* Immutable string is not mutable like array. If a solution needs to change some characters in a string, a good choice is to split string into characters array, and parse it back after minipulation.

##### String tricks.
* I'd like to use string instead of int to deal with math or bit manipulation algorithm problems, because it can simplify overflow cases.

### Hash table and Hash set

Hash table is a key-value pairs collection data structure. Given a key, hash table can search the corresponding value in O(1) time complexity. It is a rock star in algorithm problems.
Hash set is a collection of values where searching for an element by value is very fast.

#### Usages of Hash set

* A bucket when you want to find if an element exists.
* Keep uniqueness of elements in a collection.

#### Usages of Hash table

* __Reverse array, value to index__
Use value to find location. _Why need this?_ Some question ask you to do some thing related to index or location(distance between two elements).

* __Word count__
Key maps to count.

* __Group elements__
Group elements by value or any other properties.

* __Graph__
One simple way to implement graph is to use hash map.

* __Trie__
Hash table can build Trie

* __Use as an object(like js) without functions__

#### Implementation of Hash table
* Collision
    * Chaining(list)
    * Open addressing(probing)
* Use BST
    1. small initial size
    2. lg(n) time
* 

### Linked List and Array List
#### Linked List
LinkedList often appears as a problem instead of a good solution to a problem.
##### Properties:
It is easy to append nodes and remove nodes from the end in linked list.

    a -> b, c
    append: b.next = c, then a -> b -> c
    remove: a.next = null, then a, b, c

But it needs iteration to locate node by value.

##### Linked List classic problems:
* Delete any node by value or node:

solution: Use previous node pointer to get the previous node. Link previous node to next node to skip current node. Remove next pointer of current node.

    Delete b from a -> b -> c.
    Iterate to find b, cache any previous node.
    prev.next = b.next, b.next = null.

* Insert node after a node or a value:

solution: link target node to next node first, then append target node to the previous node.

    Insert b after a to a -> c.
    Iterate to find a.
    b.next = a.next, a.next = b

* Reverse linked list:

Keypoint: Use dummy node as the head pointer. Keep insert node after dummy to push existing list. Don't lose the current node's next node. 

    dummy = Node.new
        t = p.next, p.next = dummy.next, dummy.next = p

* Detect loop and find loop start node:
    * __Detect__:
    A fast pointer and a slow pointer, if slow meets fast pointer, it means list constains loop.
    * __Find loop start node__:
    1. A very easy way is to use hash set cache all traversed node, find the first existing node.
    2. Draw a graph, use math to find which is loop start node.
    TODO: add CTCI Solution.

* 

#### ArrayList:
It is like a combination of array and linked list. It has dynamic length and can be accessed by index. Actually it is implemented by a redefined array.

It should be used when you don't know how many elements will be put in an array. Typically when you need to collect results.
Avoid to use it if you need to search elements many times.
Special cases include: LRU(Not the best solution.)

### Stack and Queue

#### Stack

Stack is a __LIFO__(Last in First out) data structure. Two classic problems for stack are implementing a stack and implementing min stack.

As a solution, it is used when we need to stash previous results, and then need to solve most recent problems first or need to use most recent problem's results to solve previous stashed problems.

Function calling uses stack to stash all activated functions. Thus, stack can be used to translate recursive algorithm into iteration algorithm.

Some problems need to generate results with most recent values because of rules of the problems. Then we may need to use stack to solve it, like largest rectangle in Historgram.

#### Queue

In contrast, queue is a __FIFO__(First in First out) structure. It is often used to stash results and then still pop stashed results in the original order. A well-known usage is [Bread First Search](#breadth-first-search).

Also queue is a good data structure for multithreading or tasks management.

Queue is rarely used as a solution except BFS. In my opinion, it is because we usually like to iterate a collection from the start to the end and it is simple.

### Tree



### Graph


## Algorithms:
Baisc algorithms which can be used to solve some problems efficiently.
 
### Iteration

Basic algorithm to do a repeating process to solve a problem, typically traverse a collection of elements.

#### Two Pointers

Instead of basic one pointer iteration, two pointers can really be a good solution to some problems. Two pointers can be considered as a __Window__. The __fast and slow pointers__ can be used to solve some linked list problems. Or sometimes one pointers is not enough to cache data like ___3 Sums___.

### Recursion

### Divider and Conquer

### Binary Search

Binary search is a classic algorithm which half divides problem until to an end case. Get the results for the unit subproblem and then pop up the results as the final results. A difference from other D&C algorithms or characteristic of binary search is that binary search usually get the result from one single subproblem, instead of doing futher maths or logics when returns.

### Greedy



### Backtracking

### Branch bound

### Breadth first search

### Depth first search

### Dynamic programming