# An Example of Heapsort:

Given an array of 6 elements: 15, 19, 10, 7, 17, 16, sort it in ascending order using heap sort.

Steps:

Consider the values of the elements as priorities and build the heap tree.
Start deleteMin operations, storing each deleted element at the end of the heap array.
After performing step 2, the order of the elements will be opposite to the order in the heap tree. 
Hence, if we want the elements to be sorted in ascending order, we need to build the heap tree 
in descending order - the greatest element will have the highest priority.

Note that we use only one array , treating its parts differently:

when building the heap tree, part of the array will be considered as the heap, 
and the rest part - the original array.
when sorting, part of the array will be the heap, and the rest part - the sorted array.

> Here is the array: 15, 19, 10, 7, 17, 16

![image](https://user-images.githubusercontent.com/47218880/52725984-d9035a00-2f77-11e9-83b7-13431de70c5e.png)



