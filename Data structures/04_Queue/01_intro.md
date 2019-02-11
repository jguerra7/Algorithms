
# Queue Data Structure

A Queue is a linear structure which follows a particular order in which the operations are performed. 
The order is First In First Out (FIFO). 
A good example of a queue is any queue of consumers for a resource where the consumer that came first is served first. 
The difference between stacks and queues is in removing.
In a stack we remove the item the most recently added; in a queue, we remove the item the least recently added.

A real-world example of queue can be a single-lane one-way road, where the vehicle enters first, exits first. 
More real-world examples can be seen as queues at the ticket windows and bus-stops.
![image](https://user-images.githubusercontent.com/47218880/52595531-b5270380-2e13-11e9-94d4-76e1d1a682e5.png)

## Queue Representation
As we now understand that in queue, we access both ends for different reasons. 
The following diagram given below tries to explain queue representation as data structure −

![image](https://user-images.githubusercontent.com/47218880/52595629-e99abf80-2e13-11e9-8720-62275bbfd9d0.png)

As in stacks, a queue can also be implemented using Arrays, Linked-lists, Pointers and Structures. 
For the sake of simplicity, we shall implement queues using one-dimensional array.

## Basic Operations
Queue operations may involve initializing or defining the queue, utilizing it, and then completely erasing it from the memory. 
Here we shall try to understand the basic operations associated with queues −

> enqueue() − add (store) an item to the queue.

> dequeue() − remove (access) an item from the queue.

![image](https://user-images.githubusercontent.com/47218880/52595704-18189a80-2e14-11e9-92cd-e1ddeb0f98bd.png)
