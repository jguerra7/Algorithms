# Performance Labs With Solutions


## 1) Create a C Program Linked List & Display the Elements in the List


This C Program create a linked list & display the elements in the list. 
Linked list is an ordered set of data elements, each containing a link to its successor. 
This program is to create a linked list and display all the elements present in the created list.
Here is source code of the C program to create a linked list & display the elements in the list. 
The C program is successfully compiled and run on a Linux system. 
The program output is also shown below.

```C
/*
 * C program to create a linked list and display the elements in the list
 */
#include <stdio.h>
#include <malloc.h>
#include <stdlib.h>
 
void main()
{
    struct node
    {
        int num;
        struct node *ptr;
    };
    typedef struct node NODE;
 
    NODE *head, *first, *temp = 0;
    int count = 0;
    int choice = 1;
    first = 0;
 
    while (choice)
    {
        head  = (NODE *)malloc(sizeof(NODE));
        printf("Enter the data item\n");
        scanf("%d", &head-> num);
        if (first != 0)
        {
            temp->ptr = head;
            temp = head;
        }
        else
        {
            first = temp = head;
        }
        fflush(stdin);
        printf("Do you want to continue(Type 0 or 1)?\n");
        scanf("%d", &choice);
 
    }
    temp->ptr = 0;
    /*  reset temp to the beginning */
    temp = first;
    printf("\n status of the linked list is\n");
    while (temp != 0)
    {
        printf("%d=>", temp->num);
        count++;
        temp = temp -> ptr;
    }
    printf("NULL\n");
    printf("No. of nodes in the list = %d\n", count);
}
```
## OUTPUT: (Using the Linux Terminal)
```
$ cc pgm98.c
$ a.out
Enter the data item
5
Do you want to continue(Type 0 or 1)?
0
 
status of the linked list is
5=>NULL
No. of nodes in the list = 1
 
$ a.out
Enter the data item
5
Do you want to continue(Type 0 or 1)?
1
Enter the data item
9
Do you want to continue(Type 0 or 1)?
1
Enter the data item
3
Do you want to continue(Type 0 or 1)?
0
 
status of the linked list is
5=>9=>3=>NULL
No. of nodes in the list = 3
```
## 2) C Program Find the Length of the Linked List without using Recursion
This C Program, using iteration, counts the number of nodes in a linked list. 
A linked list is an ordered set of data elements, each containing a link to its successor.
Here is the source code of the C program to count the number of nodes in a linked list. 
The C Program is successfully compiled and run on a Linux system. 
The program output is also shown below.
```C
/*
 * C Program find the Length of the Linked List without using Recursion
 */
#include <stdio.h>
#include <stdlib.h>
 
struct node
{
    int a;
    struct node *next;
};
 
 
void generate(struct node **);
int length(struct node*);
void delete(struct node **);
 
int main()
{
    struct node *head = NULL;
    int count;
 
    generate(&head);
    count = length(head);
    printf("The number of nodes are: %d\n", count);
    delete(&head);
 
    return 0;
}
 
void generate(struct node **head)
{
    /* for unknown number of nodes use num = rand() % 20; */
    int num = 10, i;
    struct node *temp;
 
    for (i = 0; i < num; i++)
    {
        temp = (struct node *)malloc(sizeof(struct node));
        temp->a = i;
        if (*head == NULL)
        {
            *head = temp;
            (*head)->next = NULL;
        }
        else
        {
            temp->next = *head;
            *head = temp;
        }
    }
}
 
int length(struct node *head)
{
    int num = 0;
    while (head != NULL)
    {
        num += 1;
        head = head->next;
    }
    return num;
}
 
void delete(struct node **head)
{
    struct node *temp;
    while (*head != NULL)
    {
        temp = *head;
        *head = (*head)->next;
        free(temp);
    }
}
```
## OUTPUT: (Using the Linux Terminal)
```
$ gcc numbernode.c -o numbernode
$ a.out
The number of nodes are: 10
```
