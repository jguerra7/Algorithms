# ONE DIMENSIONAL ARRAY IN C:
```
Syntax : data-type arr_name[array_size];
```
![onedimarray](https://user-images.githubusercontent.com/47218880/52574520-1cc45b00-2de2-11e9-8d8d-8a9278e4d697.png)

## EXAMPLE PROGRAM FOR ONE DIMENSIONAL ARRAY IN C:
```C
#include<stdio.h> 
 
int main() 
{ 
     int i; 
     int arr[5] = {10,20,30,40,50}; 
    
        // declaring and Initializing array in C 
        //To initialize all array elements to 0, use int arr[5]={0}; 
        /* Above array can be initialized as below also 
        arr[0] = 10; 
        arr[1] = 20; 
        arr[2] = 30; 
        arr[3] = 40;
        arr[4] = 50; */
 
     for (i=0;i<5;i++) 
     { 
         // Accessing each variable
         printf("value of arr[%d] is %d \n", i, arr[i]); 
      } 
 
} 
```
## OUTPUT:
```
value of arr[0] is 10
value of arr[1] is 20
value of arr[2] is 30
value of arr[3] is 40
value of arr[4] is 50
```
 ## TWO DIMENSIONAL ARRAY IN C:
 ```
Two dimensional array is nothing but array of array.
syntax : data_type array_name[num_of_rows][num_of_column];
```
![twodimarray](https://user-images.githubusercontent.com/47218880/52574828-b7249e80-2de2-11e9-853a-5970b6396320.png)

```C

#include<stdio.h>
 
int main()
{
   int i,j;
   // declaring and Initializing array
   int arr[2][2] = {10,20,30,40};
   /* Above array can be initialized as below also
      arr[0][0] = 10; // Initializing array
      arr[0][1] = 20;
      arr[1][0] = 30;
      arr[1][1] = 40; */
   for (i=0;i<2;i++)
   {
      for (j=0;j<2;j++)
      {
         // Accessing variables
         printf("value of arr[%d] [%d] : %d\n",i,j,arr[i][j]);
      }
   }
}
```
## OUTPUT:
```
value of arr[0] [0] is 10
value of arr[0] [1] is 20
value of arr[1] [0] is 30
value of arr[1] [1] is 40
```



