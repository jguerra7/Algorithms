# Performance Labs With Solutions


## Create a C Program Linked List & Display the Elements in the List


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
OUTPUT: (Using the Linux Terminal)
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
