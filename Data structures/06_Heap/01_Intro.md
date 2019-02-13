
# Heap 
is a special case of balanced binary tree data structure where the root-node key 
is compared with its children and arranged accordingly. If α has child node β then −
```
key(α) ≥ key(β)
```
As the value of parent is greater than that of child, this property generates Max Heap.
Based on this criteria, a heap can be of two types −

> For Input → 35 33 42 10 14 19 27 44 26 31

Min-Heap − Where the value of the root node is less than or equal to either of its children.

![image](https://user-images.githubusercontent.com/47218880/52723263-cd616480-2f72-11e9-8850-886d2cde6be5.png)


Max-Heap − Where the value of the root node is greater than or equal to either of its children.

![image](https://user-images.githubusercontent.com/47218880/52723379-04d01100-2f73-11e9-8022-b2c806bb7a0e.png)

Both trees are constructed using the same input and order of arrival.

## Max Heap Construction Algorithm
We shall use the same example to demonstrate how a Max Heap is created. The procedure to create Min Heap is similar but we go for min values instead of max values.

We are going to derive an algorithm for max heap by inserting one element at a time. At any point of time, heap must maintain its property. While insertion, we also assume that we are inserting a node in an already heapified tree.
```
Step 1 − Create a new node at the end of heap.
Step 2 − Assign new value to the node.
Step 3 − Compare the value of this child node with its parent.
Step 4 − If value of parent is less than child, then swap them.
Step 5 − Repeat step 3 & 4 until Heap property holds.
```
Note − In Min Heap construction algorithm, we expect the value of the parent node to be less than that of the child node.

A binary heap is a complete binary tree which satisfies the heap ordering property. The ordering can be one of two types:

the min-heap property: the value of each node is greater than or equal to the value of its parent, with the minimum-value element at the root.
the max-heap property: the value of each node is less than or equal to the value of its parent, with the maximum-value element at the root.
Throughout this chapter the word "heap" will always refer to a min-heap.
![image](https://user-images.githubusercontent.com/47218880/52723788-c7b84e80-2f73-11e9-8826-6b746c7776ef.png)


## Applications:
A heap has many applications, including the most efficient implementation of priority queues, which are useful in many applications. In particular, heaps are crucial in several efficient graph algorithms.
