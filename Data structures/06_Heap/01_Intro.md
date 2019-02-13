
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


A binary heap is a complete binary tree which satisfies the heap ordering property. The ordering can be one of two types:

the min-heap property: the value of each node is greater than or equal to the value of its parent, with the minimum-value element at the root.
the max-heap property: the value of each node is less than or equal to the value of its parent, with the maximum-value element at the root.
Throughout this chapter the word "heap" will always refer to a min-heap.
![image](https://user-images.githubusercontent.com/47218880/52723788-c7b84e80-2f73-11e9-8826-6b746c7776ef.png)


## Applications:
A heap has many applications, including the most efficient implementation of priority queues, which are useful in many applications. In particular, heaps are crucial in several efficient graph algorithms.
