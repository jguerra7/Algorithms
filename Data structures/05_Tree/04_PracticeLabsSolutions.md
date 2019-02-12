# Practice Labs Solutions

## 1) Solution example code:
```C
#include <stdio.h>
#include <stdlib.h>
 
struct btnode
{ 
    int value; 
    struct btnode *left, *right; 
}; 
typedef struct btnode node;
 
/* function prototypes */
 
void insert(node *, node *);
void inorder(node *);
void largest(node *);
 
void main() 
{ 
    node *root = NULL, *new = NULL ; 
    int num = 1;
 
    printf("Enter the elements of the tree(enter 0 to exit)\n"); 
    while (1) 
    {     
        scanf("%d",  &num); 
        if (num == 0) 
            break; 
        new  =  malloc(sizeof(node)); 
        new->left  =  new->right  =  NULL; 
        new->value  =  num; 
        if (root  ==  NULL) 
            root = new; 
        else 
        { 
            insert(new, root); 
        } 
    }
    printf("elements in a tree in inorder are\n"); 
    inorder(root);
    largest(root);
}
 
/* displaying nodes of a tree using inorder */
 
void inorder(node *root)
{
    if (root != NULL)
    {
        inorder(root->left);
        printf("%d -> ", root->value);
        inorder(root->right);
    }
}
 
/* inserting nodes into the tree */
 
void insert(node * new , node *root) 
{ 
    if (new->value > root->value) 
    {     
        if (root->right  ==  NULL) 
            root->right  =  new; 
        else 
            insert (new, root->right); 
    } 
    if (new->value < root->value) 
    {     
        if (root->left  == NULL) 
            root->left = new; 
        else 
            insert(new, root->left); 
    }     
}
 
/* finding largest node in a tree */
void largest(node *root)
{
    if (root->right  == NULL) 
    {
        printf("largest element is %d", root->value);
    }
    while (root != NULL && root->right != NULL)
    {
        root = root->right;
    }
    printf("\nlargest value is %d\n", root->value);
}
```
### Output:
```
$ cc tree4.c
$ a.out
Enter the elements of the tree(enter 0 to exit)
40
20
60
10
30
80
90
0
elements in a tree in inorder are
10 -> 20 -> 30 -> 40 -> 60 -> 80 -> 90
largest value is 90
```
## 2)  Solution example code

```C
#include <stdio.h>
#include <stdlib.h>
 
struct btnode
{
    int value;
    struct btnode *l;
    struct btnode *r;
}*root = NULL, *temp = NULL;
 
typedef struct btnode N;
void insert();
N* bt(int arr[],int,int);
N* new(int);
void inorder(N *t);
void create();
void search(N *t);
void preorder(N *t);
void postorder(N *t);
 
void main()
{
    int ch, i, n;
    int arr[] = {10, 20, 30, 40, 60, 80, 90};
    n = sizeof(arr) / sizeof(arr[0]);
 
    printf("\n1- Inorder\n");
    printf("2 - postorder\n");
    printf("\nEnter choice : ");
    scanf("%d", &ch);
    switch (ch)
    {
    case 1:
        root = bt(arr, 0, n-1); 
        printf("Given inorder traversal as input\n");
        for (i = 0;i< = 6;i++)
            printf("%d->", arr[i]);
        printf("\npreorder traversal of tree\n");
        preorder(root);
        printf("\ninorder traversal of tree\n");
        inorder(root);
        printf("\npostorder traversal of tree\n");
        postorder(root);
        break;
    case 2:
        insert();
        printf("\npreorder traversal of tree\n");
        preorder(root);
        printf("\nInorder traversal of tree\n");
        inorder(root);
        printf("\npostorder traversal of tree\n");
        postorder(root);
        break;
        default:printf("enter correct choice");
    }
}
 
/* To create a new node */
N* new(int val)
{
    N* node = (N*)malloc(sizeof(N));
 
    node->value = val;
    node->l = NULL;
    node->r  =  NULL;
    return node;
}
 
/* To create a balanced binary search tree */
N* bt(int arr[], int first, int last)
{
    int mid;
 
    N* root = (N*)malloc(sizeof(N));
    if (first > last)
        return NULL;
    mid = (first + last) / 2;
    root = new(arr[mid]);
    root->l = bt(arr, first, mid - 1);
    root->r = bt(arr, mid + 1, last);
    return root;
}
 
/* Insert a node in the tree */
void insert()
{
    int arr1[] = {10, 30, 20, 90, 80, 60, 40}, i;
 
    printf("Given post order traversal array\n");
    for (i = 0;i <= 6;i++)
    {
        printf("%d->", arr1[i]);
     }
    for (i = 6;i >= 0;i--) 
    {
        create(arr1[i]);
        if (root =  = NULL)
            root = temp;
        else
            search(root);
    }
}
 
/*Create a node */
void create(int data)
{
    temp = (N *)malloc(1*sizeof(N));
 
    temp->value = data;
    temp->l = temp->r = NULL;
}
 
/* Search for the appropriate position to insert the new node */
void search(N *t)
{
    if ((temp->value>t->value)&&(t->r != NULL))
        search(t->r);
    else if ((temp->value>t->value)&&(t->r  == NULL))
        t->r = temp;
    else if ((temp->value<t->value)&&(t->l != NULL))
        search(t->l);
    else if ((temp->value<t->value)&&(t->l == NULL))
        t->l = temp;
}
 
/* to display inorder of tree */
void inorder(N *t)
{
    if (t->l != NULL)
        inorder(t->l);
    printf("%d->", t->value);
    if (t->r != NULL)
        inorder(t->r);
}
 
/* to display preorder traversal of tree */
void preorder(N *t) 
{
    printf("%d->", t->value);
    if (t->l != NULL)
        inorder(t->l);
    if (t->r != NULL)
        inorder(t->r);
}
 
/* to display postorder traversal of tree */
void postorder(N *t) 
{
    if (t->l != NULL)
        inorder(t->l);
    if (t->r != NULL)
        inorder(t->r);
    printf("%d->", t->value);
}
```
### Output:
```
$ cc trees.c
$ a.out
 
1- Inorder
2 - postorder
Enter choice : 1
Given inorder traversal as input
10->20->30->40->60->80->90
preorder traversal of tree
40->10->20->30->60->80->90
inorder traversal of tree
10->20->30->40->60->80->90
postorder traversal of tree
10->20->30->60->80->90->40
 
$ a.out
1 - Inorder
2 - postorder
Enter choice : 2
Given post order traversal array
10->30->20->90->80->60->40
preorder traversal of tree
40->10->20->30->60->80->90
Inorder traversal of tree
10->20->30->40->60->80->90
postorder traversal of tree
10->20->30->60->80->90->40
```
