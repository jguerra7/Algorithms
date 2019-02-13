
# Quick sort Algorithm

Quick Sort is a sorting algorithm, which is commonly used in computer science. 
Quick Sort is a divide and conquer algorithm. 
It creates two empty arrays to hold elements less than the pivot value and elements greater than the pivot value, 
nd then recursively sort the sub arrays. There are two basic operations in the algorithm, 
swapping items in place and partitioning a section of the array.

## Quick Sort Algorithm: Steps on how it works:
```
1. Find a “pivot” item in the array. This item is the basis for comparison for a single round.
2. Start a pointer (the left pointer) at the first item in the array.
3. Start a pointer (the right pointer) at the last item in the array.
4. While the value at the left pointer in the array is less than the pivot value, 
move the left pointer to the right (add 1). Continue until the value at the left pointer 
is greater than or equal to the pivot value.
5. While the value at the right pointer in the array is greater than the pivot value,
move the right pointer to the left (subtract 1). Continue until the value at the right pointer is less than or equal to the pivot value.
6. If the left pointer is less than or equal to the right pointer, then swap the values at these locations in the array.
7. Move the left pointer to the right by one and the right pointer to the left by one.
8. If the left pointer and right pointer don’t meet, go to step 1.
```

## Quick sort Diagram:

![image](https://user-images.githubusercontent.com/47218880/52734389-b4fd4400-2f8a-11e9-9683-f929907f65d5.png)


## Quick Sort Pivot Algorithm ( another step by step explanation):
which is as follows.
```
Step 1 − Choose the highest index value has pivot
Step 2 − Take two variables to point left and right of the list excluding pivot
Step 3 − left points to the low index
Step 4 − right points to the high
Step 5 − while value at left is less than pivot move right
Step 6 − while value at right is greater than pivot move left
Step 7 − if both step 5 and step 6 does not match swap left and right
Step 8 − if left ≥ right, the point where they met is new pivot

```
