# Linked List Examples

A linked list is represented by a pointer to the first node of the linked list. The first node is called head. If the linked list is empty, then value of head is NULL.
Each node in a list consists of at least two parts:
```
1) data
2) Pointer (Or Reference) to the next node
```
In C, we can represent a node using structures. Below is an example of a linked list node with an integer data.

Example of linked list node
```C
// A linked list node 
struct Node 
{ 
  int data; 
  struct Node *next; 
}; 
```
## First Simple Linked List in C Let us create a simple linked list with 3 nodes

```C
// A simple C program to introduce 
// a linked list 
#include<stdio.h> 
#include<stdlib.h> 
  
struct Node  
{ 
  int data; 
  struct Node *next; 
}; 
  
// Program to create a simple linked  
// list with 3 nodes 
int main() 
{ 
  struct Node* head = NULL; 
  struct Node* second = NULL; 
  struct Node* third = NULL; 
    
  // allocate 3 nodes in the heap   
  head = (struct Node*)malloc(sizeof(struct Node));  
  second = (struct Node*)malloc(sizeof(struct Node)); 
  third = (struct Node*)malloc(sizeof(struct Node)); 
  
  /* Three blocks have been allocated  dynamically.  
     We have pointers to these three blocks as first, 
     second and third      
       head           second           third 
        |                |               | 
        |                |               | 
    +---+-----+     +----+----+     +----+----+ 
    | #  | #  |     | #  | #  |     |  # |  # | 
    +---+-----+     +----+----+     +----+----+ 
     
   # represents any random value. 
   Data is random because we haven’t assigned  
   anything yet  */
    
  head->data = 1; //assign data in first node 
  head->next = second; // Link first node with  
                       // the second node 
    
  /* data has been assigned to data part of first 
     block (block pointed by head).  And next 
     pointer of first block points to second.   
     So they both are linked. 
  
       head          second         third 
        |              |              | 
        |              |              | 
    +---+---+     +----+----+     +-----+----+ 
    | 1  | o----->| #  | #  |     |  #  | #  | 
    +---+---+     +----+----+     +-----+----+     
  */  
    
  // assign data to second node  
  second->data = 2;  
  
  // Link second node with the third node 
  second->next = third; 
    
  /* data has been assigned to data part of second 
     block (block pointed by second). And next 
     pointer of the second block points to third  
     block. So all three blocks are linked. 
    
       head         second         third 
        |             |             | 
        |             |             | 
    +---+---+     +---+---+     +----+----+ 
    | 1  | o----->| 2 | o-----> |  # |  # | 
    +---+---+     +---+---+     +----+----+      */    
    
  third->data = 3; //assign data to third node 
  third->next = NULL; 
    
  /* data has been assigned to data part of third 
    block (block pointed by third). And next pointer 
    of the third block is made NULL to indicate 
    that the linked list is terminated here. 
  
     We have the linked list ready.   
  
           head     
             | 
             |  
        +---+---+     +---+---+       +----+------+ 
        | 1  | o----->|  2  | o-----> |  3 | NULL | 
        +---+---+     +---+---+       +----+------+        
     
      
    Note that only head is sufficient to represent  
    the whole list.  We can traverse the complete  
    list by following next pointers.    */      
  
  return 0; 
} 
```
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
