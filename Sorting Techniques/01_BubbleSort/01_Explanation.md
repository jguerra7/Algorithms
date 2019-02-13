
# The Bubble Sort
The bubble sort makes multiple passes through a list. 
It compares adjacent items and exchanges those that are out of order. 
Each pass through the list places the next largest value in its proper place. In essence, each item “bubbles” up to the location 
where it belongs.

Figure below the first pass of a bubble sort. 
The shaded items are being compared to see if they are out of order. 
If there are n items in the list, then there are n−1 pairs of items that need to be compared on the first pass. 
It is important to note that once the largest value in the list is part of a pair, 
it will continually be moved along until the pass is complete.

![image](https://user-images.githubusercontent.com/47218880/52727772-8deb4600-2f7b-11e9-988d-c3912012a869.png)

We observe in algorithm that Bubble Sort compares each pair of array element unless 
the whole array is completely sorted in an ascending order.
This may cause a few complexity issues like what if the array needs no more swapping as all the elements are already ascending.
