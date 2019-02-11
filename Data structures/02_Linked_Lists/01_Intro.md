# LINKED LISTS
## Linked Lists
A linked list is a linear collection of self-referential structures, called nodes, connected by
pointer links—hence, the term “linked” list. A linked list is accessed via a pointer to the
first node of the list. Subsequent nodes are accessed via the link pointer member stored in
each node. By convention, the link pointer in the last node of a list is set to NULL to mark
the end of the list. Data is stored in a linked list dynamically—each node is created as necessary.
A node can contain data of any type including other structs. Stacks and queues
are also linear data structures, and, as we’ll see, are constrained versions of linked lists.
Trees are nonlinear data structures.

Lists of data can be stored in arrays, but linked lists provide several advantages. A
linked list is appropriate when the number of data elements to be represented in the data
structure is unpredictable. Linked lists are dynamic, so the length of a list can increase or
decrease at execution time as necessary. The size of an array created at compile time, however,
cannot be altered. Arrays can become full. Linked lists become full only when the
system has insufficient memory to satisfy dynamic storage allocation requests.
```
An array can be declared to contain more elements than the number of data items expected,
but this can waste memory. Linked lists can provide better memory utilization in
these situations.
```
> A linked list is a sequence of data structures, which are connected together via links.

Linked List is a sequence of links which contains items. Each link contains a connection to another link. 
Linked list is the second most-used data structure after array.
Following are the important terms to understand the concept of Linked List.
```
Link − Each link of a linked list can store a data called an element.

Next − Each link of a linked list contains a link to the next link called Next.

LinkedList − A Linked List contains the connection link to the first link called First.
```
