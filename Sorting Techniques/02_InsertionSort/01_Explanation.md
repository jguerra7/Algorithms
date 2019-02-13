
# Insertion Sort

This is an in-place comparison-based sorting algorithm. Here, a sub-list is maintained which is always sorted.
For example, the lower part of an array is maintained to be sorted. An element which is to be 'insert'ed in this sorted sub-list, 
has to find its appropriate place and then it has to be inserted there. Hence the name, insertion sort.

The array is searched sequentially and unsorted items are moved and inserted into the sorted sub-list (in the same array).
This algorithm is not suitable for large data sets as its average and worst case complexity are of Ο(n2), where n is the number of items.

##  How insertion sort Algorithm works?

![image](https://user-images.githubusercontent.com/47218880/52731013-5338dc00-2f82-11e9-9df4-5d7034dd5559.png)

## Algorithm
Now that we have a bigger picture of how this sorting technique works,  we can derive simple steps by which we can achieve insertion sort.
```
Step 1 − If it is the first element, it is already sorted. return 1;
Step 2 − Pick next element
Step 3 − Compare with all elements in the sorted sub-list
Step 4 − Shift all the elements in the sorted sub-list that is greater than the 
         value to be sorted
Step 5 − Insert the value
Step 6 − Repeat until list is sorted
```
