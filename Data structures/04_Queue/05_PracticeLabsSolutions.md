# Solutions to Queue Practice Labs

## 1) Solution example

```C
/*
 * C Program to Implement a Queue using an Array
 */
#include <stdio.h>
 
#define MAX 50
int queue_array[MAX];
int rear = - 1;
int front = - 1;
main()
{
    int choice;
    while (1)
    {
        printf("1.Insert element to queue \n");
        printf("2.Delete element from queue \n");
        printf("3.Display all elements of queue \n");
        printf("4.Quit \n");
        printf("Enter your choice : ");
        scanf("%d", &choice);
        switch (choice)
        {
            case 1:
            insert();
            break;
            case 2:
            delete();
            break;
            case 3:
            display();
            break;
            case 4:
            exit(1);
            default:
            printf("Wrong choice \n");
        } /*End of switch*/
    } /*End of while*/
} /*End of main()*/
insert()
{
    int add_item;
    if (rear == MAX - 1)
    printf("Queue Overflow \n");
    else
    {
        if (front == - 1)
        /*If queue is initially empty */
        front = 0;
        printf("Inset the element in queue : ");
        scanf("%d", &add_item);
        rear = rear + 1;
        queue_array[rear] = add_item;
    }
} /*End of insert()*/
 
delete()
{
    if (front == - 1 || front > rear)
    {
        printf("Queue Underflow \n");
        return ;
    }
    else
    {
        printf("Element deleted from queue is : %d\n", queue_array[front]);
        front = front + 1;
    }
} /*End of delete() */
display()
{
    int i;
    if (front == - 1)
        printf("Queue is empty \n");
    else
    {
        printf("Queue is : \n");
        for (i = front; i <= rear; i++)
            printf("%d ", queue_array[i]);
        printf("\n");
    }
} /*End of display() */
```
## Program Explanation
1. Ask the user for the operation like insert, delete, display and exit.
2. According to the option entered, access its respective function using switch statement. 
Use the variables front and rear to represent the first and last element of the queue.
3. In the function insert(), firstly check if the queue is full. If it is, 
then print the output as “Queue Overflow”. Otherwise take the number to be inserted as input and store it in the variable add_item. 
Copy the variable add_item to the array queue_array[] and increment the variable rear by 1.
4. In the function delete(), firstly check if the queue is empty. If it is, 
then print the output as “Queue Underflow”. Otherwise print the first element of the array queue_array[] 
and decrement the variable front by 1.
5. In the function display(), using for loop print all the elements of the array starting from front to rear.
6. Exit.

## 2) Solution Code Example:
```C
#include <stdio.h>
#include <string.h>
#include <stdlib.h>
#include <stdbool.h>

#define MAX 6

int intArray[MAX];
int front = 0;
int rear = -1;
int itemCount = 0;

int peek() {
   return intArray[front];
}

bool isEmpty() {
   return itemCount == 0;
}

bool isFull() {
   return itemCount == MAX;
}

int size() {
   return itemCount;
}  

void insert(int data) {

   if(!isFull()) {
	
      if(rear == MAX-1) {
         rear = -1;            
      }       

      intArray[++rear] = data;
      itemCount++;
   }
}

int removeData() {
   int data = intArray[front++];
	
   if(front == MAX) {
      front = 0;
   }
	
   itemCount--;
   return data;  
}

int main() {
   /* insert 5 items */
   insert(3);
   insert(5);
   insert(9);
   insert(1);
   insert(12);

   // front : 0
   // rear  : 4
   // ------------------
   // index : 0 1 2 3 4 
   // ------------------
   // queue : 3 5 9 1 12
   insert(15);

   // front : 0
   // rear  : 5
   // ---------------------
   // index : 0 1 2 3 4  5 
   // ---------------------
   // queue : 3 5 9 1 12 15
	
   if(isFull()) {
      printf("Queue is full!\n");   
   }

   // remove one item 
   int num = removeData();
	
   printf("Element removed: %d\n",num);
   // front : 1
   // rear  : 5
   // -------------------
   // index : 1 2 3 4  5
   // -------------------
   // queue : 5 9 1 12 15

   // insert more items
   insert(16);

   // front : 1
   // rear  : -1
   // ----------------------
   // index : 0  1 2 3 4  5
   // ----------------------
   // queue : 16 5 9 1 12 15

   // As queue is full, elements will not be inserted. 
   insert(17);
   insert(18);

   // ----------------------
   // index : 0  1 2 3 4  5
   // ----------------------
   // queue : 16 5 9 1 12 15
   printf("Element at front: %d\n",peek());

   printf("----------------------\n");
   printf("index : 5 4 3 2  1  0\n");
   printf("----------------------\n");
   printf("Queue:  ");
	
   while(!isEmpty()) {
      int n = removeData();           
      printf("%d ",n);
   }   
}
```
