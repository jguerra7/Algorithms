# Queue(Introduction and Array Implementation)
Like Stack, Queue is a linear structure which follows a particular order in which the operations are performed. 
The order is First In First Out (FIFO).  A good example of queue is any queue of consumers for a resource where the consumer 
that came first is served first.
The difference between stacks and queues is in removing. In a stack we remove the item the most recently added; 
in a queue, we remove the item the least recently added.

## Operations on Queue:
Mainly the following four basic operations are performed on queue:
```
Enqueue: Adds an item to the queue. If the queue is full, then it is said to be an Overflow condition.
Dequeue: Removes an item from the queue. The items are popped in the same order in which they are pushed. 
If the queue is empty, then it is said to be an Underflow condition.
Front: Get the front item from queue.
Rear: Get the last item from queue.
```
## Applications of Queue:
Queue is used when things don’t have to be processed immediatly, but have to be processed in First InFirst Out order 
like Breadth First Search. This property of Queue makes it also useful in following kind of scenarios.

1) When a resource is shared among multiple consumers. Examples include CPU scheduling, Disk Scheduling.
2) When data is transferred asynchronously (data not necessarily received at same rate as sent) between two processes.
Examples include IO Buffers, pipes, file IO, etc.

## Array implementation Of Queue
For implementing queue, we need to keep track of two indices, front and rear. 
We enqueue an item at the rear and dequeue an item from front. If we simply increment front and rear indices, 
then there may be problems, 
front may reach end of the array. 
The solution to this problem is to increase front and rear in circular manner 

## CODE EXAMPLE 
```C
// C program for array implementation of queue 
#include <stdio.h> 
#include <stdlib.h> 
#include <limits.h> 

// A structure to represent a queue 
struct Queue 
{ 
	int front, rear, size; 
	unsigned capacity; 
	int* array; 
}; 

// function to create a queue of given capacity. 
// It initializes size of queue as 0 
struct Queue* createQueue(unsigned capacity) 
{ 
	struct Queue* queue = (struct Queue*) malloc(sizeof(struct Queue)); 
	queue->capacity = capacity; 
	queue->front = queue->size = 0; 
	queue->rear = capacity - 1; // This is important, see the enqueue 
	queue->array = (int*) malloc(queue->capacity * sizeof(int)); 
	return queue; 
} 

// Queue is full when size becomes equal to the capacity 
int isFull(struct Queue* queue) 
{ return (queue->size == queue->capacity); } 

// Queue is empty when size is 0 
int isEmpty(struct Queue* queue) 
{ return (queue->size == 0); } 

// Function to add an item to the queue. 
// It changes rear and size 
void enqueue(struct Queue* queue, int item) 
{ 
	if (isFull(queue)) 
		return; 
	queue->rear = (queue->rear + 1)%queue->capacity; 
	queue->array[queue->rear] = item; 
	queue->size = queue->size + 1; 
	printf("%d enqueued to queue\n", item); 
} 

// Function to remove an item from queue. 
// It changes front and size 
int dequeue(struct Queue* queue) 
{ 
	if (isEmpty(queue)) 
		return INT_MIN; 
	int item = queue->array[queue->front]; 
	queue->front = (queue->front + 1)%queue->capacity; 
	queue->size = queue->size - 1; 
	return item; 
} 

// Function to get front of queue 
int front(struct Queue* queue) 
{ 
	if (isEmpty(queue)) 
		return INT_MIN; 
	return queue->array[queue->front]; 
} 

// Function to get rear of queue 
int rear(struct Queue* queue) 
{ 
	if (isEmpty(queue)) 
		return INT_MIN; 
	return queue->array[queue->rear]; 
} 

// Driver program to test above functions./ 
int main() 
{ 
	struct Queue* queue = createQueue(1000); 

	enqueue(queue, 10); 
	enqueue(queue, 20); 
	enqueue(queue, 30); 
	enqueue(queue, 40); 

	printf("%d dequeued from queue\n\n", dequeue(queue)); 

	printf("Front item is %d\n", front(queue)); 
	printf("Rear item is %d\n", rear(queue)); 

	return 0; 
} 
```
### output:
```
10 enqueued to queue
20 enqueued to queue
30 enqueued to queue
40 enqueued to queue
10 dequeued from queue
Front item is 20
Rear item is 40
```
## Time Complexity: 
Time complexity of all operations like enqueue(), dequeue(), isFull(), isEmpty(), front() and rear() is O(1).
There is no loop in any of the operations.
