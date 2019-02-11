#Linked List Practice Lab Solutions

## 1). Write a program in C to create and display Singly Linked List.
```C
#include <stdio.h>
#include <stdlib.h>

struct node 
{
    int num;                        //Data of the node
    struct node *nextptr;           //Address of the next node
}*stnode;

void createNodeList(int n); // function to create the list
void displayList();         // function to display the list

int main()
{
    int n;
		printf("\n\n Linked List : To create and display Singly Linked List :\n");
		printf("-------------------------------------------------------------\n");
		
    printf(" Input the number of nodes : ");
    scanf("%d", &n);
    createNodeList(n);
    printf("\n Data entered in the list : \n");
    displayList();
    return 0;
}
void createNodeList(int n)
{
    struct node *fnNode, *tmp;
    int num, i;
    stnode = (struct node *)malloc(sizeof(struct node));

    if(stnode == NULL) //check whether the fnnode is NULL and if so no memory allocation
    {
        printf(" Memory can not be allocated.");
    }
    else
    {
// reads data for the node through keyboard

        printf(" Input data for node 1 : ");
        scanf("%d", &num);
        stnode->num = num;      
        stnode->nextptr = NULL; // links the address field to NULL
        tmp = stnode;
// Creating n nodes and adding to linked list
        for(i=2; i<=n; i++)
        {
            fnNode = (struct node *)malloc(sizeof(struct node));
            if(fnNode == NULL)
            {
                printf(" Memory can not be allocated.");
                break;
            }
            else
            {
                printf(" Input data for node %d : ", i);
                scanf(" %d", &num);
 
                fnNode->num = num;      // links the num field of fnNode with num
                fnNode->nextptr = NULL; // links the address field of fnNode with NULL
 
                tmp->nextptr = fnNode; // links previous node i.e. tmp to the fnNode
                tmp = tmp->nextptr; 
            }
        }
    }
}
void displayList()
{
    struct node *tmp;
    if(stnode == NULL)
    {
        printf(" List is empty.");
    }
    else
    {
        tmp = stnode;
        while(tmp != NULL)
        {
            printf(" Data = %d\n", tmp->num);       // prints the data of current node
            tmp = tmp->nextptr;                     // advances the position of current node
        }
    }
} 
```

## FLOWCHART PROCESS
![image](https://user-images.githubusercontent.com/47218880/52583282-d75d5900-2df4-11e9-94f7-0f3eb2e535be.png)

## createNodeList():
![image](https://user-images.githubusercontent.com/47218880/52583326-f0fea080-2df4-11e9-98bf-a4cc269d94a1.png)

## displayList():
![image](https://user-images.githubusercontent.com/47218880/52583362-04aa0700-2df5-11e9-990d-3054f130b3dc.png)


## 2). Write a program in C to create a singly linked list of n nodes and count the number of nodes.

```C
#include <stdio.h>
#include <stdlib.h>


struct node 
{
    int num;                    //Data of the node
    struct node *nextptr;       //Address of the node
}*stnode;

void createNodeList(int n);     //function to create the list
int NodeCount();	            //function to count the nodes
void displayList();             //function to display the list

int main()
{
    int n,totalNode;
		printf("\n\n Linked List : Create a singly linked list and count the number of nodes :\n");
		printf("------------------------------------------------------------------------------\n");
    printf(" Input the number of nodes : ");
    scanf("%d", &n);
    createNodeList(n);
    printf("\n Data entered in the list are : \n");		
    displayList();
    totalNode = NodeCount();
    printf("\n Total number of nodes = %d\n", totalNode);
    return 0;
}
void createNodeList(int n)
{
    struct node *fnNode, *tmp;
    int num, i;
    stnode = (struct node *)malloc(sizeof(struct node));
    if(stnode == NULL) //check whether the stnode is NULL and if so no memory allocation
    {
        printf(" Memory can not be allocated.");
    }
    else
    {
// reads data for the node through keyboard
        printf(" Input data for node 1 : ");
        scanf("%d", &num);
        stnode-> num = num;      
        stnode-> nextptr = NULL; //Links the address field to NULL
        tmp = stnode;
//Creates n nodes and adds to linked list
        for(i=2; i<=n; i++)
        {
            fnNode = (struct node *)malloc(sizeof(struct node));
            if(fnNode == NULL) //check whether the fnnode is NULL and if so no memory allocation
            {
                printf(" Memory can not be allocated.");
                break;
            }
            else
            {
                printf(" Input data for node %d : ", i);
                scanf(" %d", &num);
                fnNode->num = num;      // links the num field of fnNode with num
                fnNode->nextptr = NULL; // links the address field of fnNode with NULL
                tmp->nextptr = fnNode; // links previous node i.e. tmp to the fnNode
                tmp = tmp->nextptr;
            }
        }
    }
} 

int NodeCount()
{
    int ctr = 0;
    struct node *tmp;
    tmp = stnode;
    while(tmp != NULL)
    {
        ctr++;
        tmp = tmp->nextptr;
    }
    return ctr;
}
void displayList()
{
    struct node *tmp;
    if(stnode == NULL)
    {
        printf(" No data found in the list.");
    }
    else
    {
        tmp = stnode;
        while(tmp != NULL)
        {
            printf(" Data = %d\n", tmp->num);   // prints the data of current node
            tmp = tmp->nextptr;                 // advances the position of current node
        }
    }
} 
```
## FLOWCHART

![image](https://user-images.githubusercontent.com/47218880/52583658-be08dc80-2df5-11e9-9e78-5ca6bf79d846.png)

createNodeList():

![image](https://user-images.githubusercontent.com/47218880/52583693-d4af3380-2df5-11e9-87f0-df0cec065e5a.png)

NodeCount():
![image](https://user-images.githubusercontent.com/47218880/52583746-fc060080-2df5-11e9-9339-e97c4bf95726.png)

displayList():

![image](https://user-images.githubusercontent.com/47218880/52583772-0e803a00-2df6-11e9-98dc-b1a4cfe72d1d.png)







