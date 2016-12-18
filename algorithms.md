# Basic algorithms and data structures
This notes contain my personal's understanding for some basic algorithms and data structures, and how to apply them to problems.

## Data structures:
Basic data structures whose properpies can be utilized to solve algorithm problems.

### Array and Strings
####[Array](https://en.wikipedia.org/wiki/Array_data_structure)
a collection of elements, which is accessed by index. It usually has a fixed size.

It may be the first choice for most of algorithm problem. But it's not a good choice, if the size of elements can not be determined or the collection needs to do a search for values frequently.

####[String](https://en.wikipedia.org/wiki/String_(computer_science))
a squence of characters, like an array of charachers. But in some programming language String is immutable.

##### Algorithm problems about string minipulation.
String algorithms usually are similar with array problems. Differences:

* String concatenation is easier than array, but if a solution may need to frequently concatenate string, StringBuffer and StringBuilder are good choices.
* Immutable string is not mutable like array. If a solution needs to change some characters in a string, a good choice is to split string to character and array, and parse it back after minipulation.

##### String tricks.
* I'd like to use string instead of int to deal with math algorithm problems, because it can simplify overflow cases.

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
Stack is a LIFO(last in first out) data structure. Two classic problems for stack are implementing a stack and implementing min stack.

As a solution, it is used when we need to stash previous results, and then need to solve most recent problems first or need to use most recent problem's results to solve previous stashed problems.

Function calling uses stack to stash all activated functions. Thus, stack can be used to translate recursive algorithm into iteration algorithm.

Some problems need to generate results with most recent values because of rules of the problems. Then we may need to use stack to solve it, like largest rectangle in Historgram.

#### Queue



### Tree

### Graph


## Algorithms:
Baisc algorithms which can be used to solve some problems efficiently.
 
### Iteration

### Recursion

### Two Pointers

### Greedy

### Divider and Conquer

### Backtracking

### Branch bound

### Breadth first search

### Depth first search

### Dynamic programming