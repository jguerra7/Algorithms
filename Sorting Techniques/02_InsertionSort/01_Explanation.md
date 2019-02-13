
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
## Another Example: 
> 12, 11, 13, 5, 6

Let us loop for i = 1 (second element of the array) to 5 (Size of input array)

i = 1. Since 11 is smaller than 12, move 12 and insert 11 before 12
> 11, 12, 13, 5, 6

i = 2. 13 will remain at its position as all elements in A[0..I-1] are smaller than 13
> 11, 12, 13, 5, 6

i = 3. 5 will move to the beginning and all other elements from 11 to 13 will move one position ahead of their current position.
> 5, 11, 12, 13, 6

i = 4. 6 will move to position after 5, and elements from 11 to 13 will move one position ahead of their current position.
> 5, 6, 11, 12, 13
