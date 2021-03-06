## In this section, methods to insert a new node in linked list are discussed. A node can be added in three ways
```
1) At the front of the linked list
2) After a given node.
3) At the end of the linked list.
```
## Add a node at the front: (A 4 steps process)
The new node is always added before the head of the given Linked List. And newly added node becomes the new head of the Linked List. 
For example if the given Linked List is 10->15->20->25 and we add an item 5 at the front, 
then the Linked List becomes 5->10->15->20->25. Let us call the function that adds at the front of the list is push(). 
The push() must receive a pointer to the head pointer, because push must change the head pointer to point to the new node.

![image](https://user-images.githubusercontent.com/47218880/52581403-43898e00-2df0-11e9-8580-145e3c916a0a.png)

## Following are the 4 steps to add node at the front.
```C
/* Given a reference (pointer to pointer) to the head of a list 
and an int, inserts a new node on the front of the list. */
void push(struct Node** head_ref, int new_data) 
{ 
	/* 1. allocate node */
	struct Node* new_node = (struct Node*) malloc(sizeof(struct Node)); 

	/* 2. put in the data */
	new_node->data = new_data; 

	/* 3. Make next of new node as head */
	new_node->next = (*head_ref); 

	/* 4. move the head to point to the new node */
	(*head_ref) = new_node; 
} 
```
Time complexity of push() is O(1) as it does constant amount of work.

## Add a node after a given node: (5 steps process)

We are given pointer to a node, and the new node is inserted after the given node.
![image](https://user-images.githubusercontent.com/47218880/52581463-70d63c00-2df0-11e9-93c6-67f8969d1013.png)

```C
/* Given a node prev_node, insert a new node after the given 
prev_node */
void insertAfter(struct Node* prev_node, int new_data) 
{ 
	/*1. check if the given prev_node is NULL */
	if (prev_node == NULL) 
	{ 
	printf("the given previous node cannot be NULL");	 
	return; 
	} 
		
	/* 2. allocate new node */
	struct Node* new_node =(struct Node*) malloc(sizeof(struct Node)); 

	/* 3. put in the data */
	new_node->data = new_data; 

	/* 4. Make next of new node as next of prev_node */
	new_node->next = prev_node->next; 

	/* 5. move the next of prev_node as new_node */
	prev_node->next = new_node; 
} 
```
Time complexity of insertAfter() is O(1) as it does constant amount of work.

## Add a node at the end: (6 steps process)
The new node is always added after the last node of the given Linked List. 
For example if the given Linked List is 5->10->15->20->25 and we add an item 30 at the end, 
then the Linked List becomes 5->10->15->20->25->30.
Since a Linked List is typically represented by the head of it,
we have to traverse the list till end and then change the next of last node to new node.

![image](https://user-images.githubusercontent.com/47218880/52581498-83e90c00-2df0-11e9-91fc-2d3d76276dfe.png)


Following are the 6 steps to add node at the end.
```C
/* Given a reference (pointer to pointer) to the head 
of a list and an int, appends a new node at the end */
void append(struct Node** head_ref, int new_data) 
{ 
	/* 1. allocate node */
	struct Node* new_node = (struct Node*) malloc(sizeof(struct Node)); 

	struct Node *last = *head_ref; /* used in step 5*/

	/* 2. put in the data */
	new_node->data = new_data; 

	/* 3. This new node is going to be the last node, so make next 
		of it as NULL*/
	new_node->next = NULL; 

	/* 4. If the Linked List is empty, then make the new node as head */
	if (*head_ref == NULL) 
	{ 
	*head_ref = new_node; 
	return; 
	} 
	
	/* 5. Else traverse till the last node */
	while (last->next != NULL) 
		last = last->next; 

	/* 6. Change the next of last node */
	last->next = new_node; 
	return;	 
} 
```
Time complexity of append is O(n) where n is the number of nodes in linked list.
Since there is a loop from head to end, the function does O(n) work.
This method can also be optimized to work in O(1) by keeping an extra pointer to tail of linked list/

## Following is a complete program that uses all of the above methods to create a linked list.

```C
// A complete working C program to demonstrate all insertion methods 
// on Linked List 
#include <stdio.h> 
#include <stdlib.h> 

// A linked list node 
struct Node 
{ 
int data; 
struct Node *next; 
}; 

/* Given a reference (pointer to pointer) to the head of a list and 
an int, inserts a new node on the front of the list. */
void push(struct Node** head_ref, int new_data) 
{ 
	/* 1. allocate node */
	struct Node* new_node = (struct Node*) malloc(sizeof(struct Node)); 

	/* 2. put in the data */
	new_node->data = new_data; 

	/* 3. Make next of new node as head */
	new_node->next = (*head_ref); 

	/* 4. move the head to point to the new node */
	(*head_ref) = new_node; 
} 

/* Given a node prev_node, insert a new node after the given 
prev_node */
void insertAfter(struct Node* prev_node, int new_data) 
{ 
	/*1. check if the given prev_node is NULL */
	if (prev_node == NULL) 
	{ 
	printf("the given previous node cannot be NULL"); 
	return; 
	} 

	/* 2. allocate new node */
	struct Node* new_node =(struct Node*) malloc(sizeof(struct Node)); 

	/* 3. put in the data */
	new_node->data = new_data; 

	/* 4. Make next of new node as next of prev_node */
	new_node->next = prev_node->next; 

	/* 5. move the next of prev_node as new_node */
	prev_node->next = new_node; 
} 

/* Given a reference (pointer to pointer) to the head 
of a list and an int, appends a new node at the end */
void append(struct Node** head_ref, int new_data) 
{ 
	/* 1. allocate node */
	struct Node* new_node = (struct Node*) malloc(sizeof(struct Node)); 

	struct Node *last = *head_ref; /* used in step 5*/

	/* 2. put in the data */
	new_node->data = new_data; 

	/* 3. This new node is going to be the last node, so make next of 
		it as NULL*/
	new_node->next = NULL; 

	/* 4. If the Linked List is empty, then make the new node as head */
	if (*head_ref == NULL) 
	{ 
	*head_ref = new_node; 
	return; 
	} 

	/* 5. Else traverse till the last node */
	while (last->next != NULL) 
		last = last->next; 

	/* 6. Change the next of last node */
	last->next = new_node; 
	return; 
} 

// This function prints contents of linked list starting from head 
void printList(struct Node *node) 
{ 
while (node != NULL) 
{ 
	printf(" %d ", node->data); 
	node = node->next; 
} 
} 

/* Driver program to test above functions*/
int main() 
{ 
/* Start with the empty list */
struct Node* head = NULL; 

// Insert 6. So linked list becomes 6->NULL 
append(&head, 6); 

// Insert 7 at the beginning. So linked list becomes 7->6->NULL 
push(&head, 7); 

// Insert 1 at the beginning. So linked list becomes 1->7->6->NULL 
push(&head, 1); 

// Insert 4 at the end. So linked list becomes 1->7->6->4->NULL 
append(&head, 4); 

// Insert 8, after 7. So linked list becomes 1->7->8->6->4->NULL 
insertAfter(head->next, 8); 

printf("\n Created Linked list is: "); 
printList(head); 

return 0; 
} 
```
## Output:
```
 Created Linked list is:  1  7  8  6  4
```



