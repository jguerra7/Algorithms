# Tree Traversals (Inorder, Preorder and Postorder)
Unlike linear data structures (Array, Linked List, Queues, Stacks, etc) 
which have only one logical way to traverse them, trees can be traversed in different ways.
Following are the generally used ways for traversing trees.

![image](https://user-images.githubusercontent.com/47218880/52663845-2aa2da80-2ecd-11e9-9a59-917fe664741b.png)

Depth First Traversals:
(a) Inorder (Left, Root, Right) : 4 2 5 1 3
(b) Preorder (Root, Left, Right) : 1 2 4 5 3
(c) Postorder (Left, Right, Root) : 4 5 2 3 1

Breadth First or Level Order Traversal : 1 2 3 4 5

## Inorder Traversal:
```
Algorithm Inorder(tree)
   1. Traverse the left subtree, i.e., call Inorder(left-subtree)
   2. Visit the root.
   3. Traverse the right subtree, i.e., call Inorder(right-subtree)
```
### Uses of Inorder
In case of binary search trees (BST), Inorder traversal gives nodes in non-decreasing order. 
To get nodes of BST in non-increasing order, a variation of Inorder traversal where Inorder traversal s reversed can be used.
> Example: Inorder traversal for the above-given figure is 4 2 5 1 3.


## Preorder Traversal:
```
Algorithm Preorder(tree)
   1. Visit the root.
   2. Traverse the left subtree, i.e., call Preorder(left-subtree)
   3. Traverse the right subtree, i.e., call Preorder(right-subtree) 
   ```
### Uses of Preorder
Preorder traversal is used to create a copy of the tree. Preorder traversal is also used to get prefix expression on of an expression tree.
> Example: Preorder traversal for the above given figure is 1 2 4 5 3.

## Postorder Traversal:
```
Algorithm Postorder(tree)
   1. Traverse the left subtree, i.e., call Postorder(left-subtree)
   2. Traverse the right subtree, i.e., call Postorder(right-subtree)
   3. Visit the root.
   ```
### Uses of Postorder
Postorder traversal is used to delete the tree. Please see the question for deletion of tree for details. 
Postorder traversal is also useful to get the postfix expression of an expression tree. 

> Example: Postorder traversal for the above given figure is 4 5 2 3 1.

```C
// C program for different tree traversals 
#include <stdio.h> 
#include <stdlib.h> 

/* A binary tree node has data, pointer to left child 
and a pointer to right child */
struct node 
{ 
	int data; 
	struct node* left; 
	struct node* right; 
}; 

/* Helper function that allocates a new node with the 
given data and NULL left and right pointers. */
struct node* newNode(int data) 
{ 
	struct node* node = (struct node*) 
								malloc(sizeof(struct node)); 
	node->data = data; 
	node->left = NULL; 
	node->right = NULL; 

	return(node); 
} 

/* Given a binary tree, print its nodes according to the 
"bottom-up" postorder traversal. */
void printPostorder(struct node* node) 
{ 
	if (node == NULL) 
		return; 

	// first recur on left subtree 
	printPostorder(node->left); 

	// then recur on right subtree 
	printPostorder(node->right); 

	// now deal with the node 
	printf("%d ", node->data); 
} 

/* Given a binary tree, print its nodes in inorder*/
void printInorder(struct node* node) 
{ 
	if (node == NULL) 
		return; 

	/* first recur on left child */
	printInorder(node->left); 

	/* then print the data of node */
	printf("%d ", node->data); 

	/* now recur on right child */
	printInorder(node->right); 
} 

/* Given a binary tree, print its nodes in preorder*/
void printPreorder(struct node* node) 
{ 
	if (node == NULL) 
		return; 

	/* first print data of node */
	printf("%d ", node->data); 

	/* then recur on left sutree */
	printPreorder(node->left); 

	/* now recur on right subtree */
	printPreorder(node->right); 
}	 

/* Driver program to test above functions*/
int main() 
{ 
	struct node *root = newNode(1); 
	root->left			 = newNode(2); 
	root->right		 = newNode(3); 
	root->left->left	 = newNode(4); 
	root->left->right = newNode(5); 

	printf("\nPreorder traversal of binary tree is \n"); 
	printPreorder(root); 

	printf("\nInorder traversal of binary tree is \n"); 
	printInorder(root); 

	printf("\nPostorder traversal of binary tree is \n"); 
	printPostorder(root); 

	getchar(); 
	return 0; 
} 

```
