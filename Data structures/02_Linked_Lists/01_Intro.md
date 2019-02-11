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
Performance note:
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
## Linked List Representation
Linked list can be visualized as a chain of nodes, where every node points to the next node.
![image](https://user-images.githubusercontent.com/47218880/52578719-6a44c600-2dea-11e9-8ec2-a1d93e7ab384.png)


Linked List
As per the above illustration, following are the important points to be considered.
```
Linked List contains a link element called first.

Each link carries a data field(s) and a link field called next.

Each link is linked with its next link using its next link.

Last link carries a link as null to mark the end of the list.
```
## Types of Linked List
```
Following are the various types of linked list.

Simple Linked List − Item navigation is forward only.

Doubly Linked List − Items can be navigated forward and backward.

Circular Linked List − Last item contains link of the first element as next and the first element has a link to the last element as previous.
```
## Basic Operations
Following are the basic operations supported by a list.
```

Insertion − Adds an element at the beginning of the list.

Deletion − Deletes an element at the beginning of the list.

Display − Displays the complete list.

Search − Searches an element using the given key.

Delete − Deletes an element using the given key.
```
## Insertion Operation
Adding a new node in linked list is a more than one step activity. We shall learn this with diagrams here. First, create a node using the same structure and find the location where it has to be inserted.

![image](https://user-images.githubusercontent.com/47218880/52578771-86486780-2dea-11e9-8be2-861f1020ca61.png)


Imagine that we are inserting a node B (NewNode), between A (LeftNode) and C (RightNode). Then point B.next to C −
```
NewNode.next −> RightNode;
```
It should look like this −
![image](https://user-images.githubusercontent.com/47218880/52578877-b4c64280-2dea-11e9-91ef-370cbb25e6fc.png)


Now, the next node at the left should point to the new node.
```
LeftNode.next −> NewNode;
```
![image](https://user-images.githubusercontent.com/47218880/52578927-d1627a80-2dea-11e9-839f-6fc85a2c299c.png)

This will put the new node in the middle of the two. The new list should look like this −
![image](https://user-images.githubusercontent.com/47218880/52578975-e50de100-2dea-11e9-8c9d-04b7358aeaca.png)


Similar steps should be taken if the node is being inserted at the beginning of the list. 
While inserting it at the end, the second last node of the list should point to the new node and the new node will point to NULL.

## Deletion Operation
Deletion is also a more than one step process. We shall learn with pictorial representation. First, locate the target node to be removed, by using searching algorithms.

![image](https://user-images.githubusercontent.com/47218880/52579034-053da000-2deb-11e9-8942-f78a59440e36.png)

The left (previous) node of the target node now should point to the next node of the target node −
```
LeftNode.next −> TargetNode.next;
```
![image](https://user-images.githubusercontent.com/47218880/52579100-24d4c880-2deb-11e9-870d-4c586bee0421.png)

This will remove the link that was pointing to the target node. Now, using the following code, we will remove what the target node is pointing at.
```
TargetNode.next −> NULL;
```
![image](https://user-images.githubusercontent.com/47218880/52579167-48980e80-2deb-11e9-8c4c-e5edeae06804.png)

We need to use the deleted node. We can keep that in memory otherwise we can simply deallocate memory and wipe off the target node completely.

![image](https://user-images.githubusercontent.com/47218880/52579232-5ea5cf00-2deb-11e9-9dfd-16bb689eedc0.png)

## Reverse Operation
This operation is a thorough one. We need to make the last node to be pointed by the head node and reverse the whole linked list.


First, we traverse to the end of the list. It should be pointing to NULL. Now, we shall make it point to its previous node −


We have to make sure that the last node is not the lost node. So we'll have some temp node, which looks like the head node pointing to the last node. Now, we shall make all left side nodes point to their previous nodes one by one.


Except the node (first node) pointed by the head node, all nodes should point to their predecessor, making them their new successor. The first node will point to NULL.


We'll make the head node point to the new first node by using the temp node.


The linked list is now reversed. To see linked list implementation in C programming language,
