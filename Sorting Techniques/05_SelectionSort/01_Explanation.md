
# Selection Sort

Selection sort is a simple sorting algorithm. This sorting algorithm is an in-place comparison-based algorithm in which the list is divided into two parts, the sorted part at the left end and the unsorted part at the right end. Initially, the sorted part is empty and the unsorted part is the entire list.

The smallest element is selected from the unsorted array and swapped with the leftmost element, and that element becomes a part of the sorted array. This process continues moving unsorted array boundary by one element to the right.

This algorithm is not suitable for large data sets as its average and worst case complexities are of Ο(n2), where n is the number of items.

![image](https://user-images.githubusercontent.com/47218880/52732246-57b2c400-2f85-11e9-8b18-778dbdb2b607.png)

Now, let us learn some programming aspects of selection sort.

## Algorithm
```
Step 1 − Set MIN to location 0
Step 2 − Search the minimum element in the list
Step 3 − Swap with value at location MIN
Step 4 − Increment MIN to point to next element
Step 5 − Repeat until list is sorted
```
Selection sort algorithm is easy to use but, there are other sorting algorithm which perform better than selection sort. Specially, selection sort shouldn't be used to sort large number of elements if the performance matters in that program.
