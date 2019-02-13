Bubble sort algorithm starts by comparing the first two elements of an array and swapping if necessary, i.e., 
if you want to sort the elements of array in ascending order and if the first element is greater than second then, 
you need to swap the elements but, if the first element is smaller than second, you mustn't swap the element. 
Then, again second and third elements are compared and swapped if it is necessary and this process go on until last and 
second last element is compared and swapped. This completes the first step of bubble sort.

If there are n elements to be sorted then, the process mentioned above should be repeated n-1 times to get required result. 
But, for better performance, in second step, last and second last elements are not compared becuase, 
the proper element is automatically placed at last after first step. 
Similarly, in third step, last and second last and second last and third last elements are not compared and so on.

A figure is worth a thousand words so, acknowledge this figure for better understanding of bubble sort.
![image](https://user-images.githubusercontent.com/47218880/52729449-d35d4280-2f7e-11e9-9bbc-bcfbca68af4f.png)
