# Practice Lab Solutions

## 1). Write a program in C to store elements in an array and print it.

```C
#include <stdio.h>  
  
void  main()  
{  
    int arr[10]; 
    int i;  
       printf("\n\nRead and Print elements of an array:\n");
       printf("-----------------------------------------\n");	
  
    printf("Input 10 elements in the array :\n");  
    for(i=0; i<10; i++)  
    {  
	    printf("element - %d : ",i);
        scanf("%d", &arr[i]);  
    }  
  
    printf("\nElements in array are: ");  
    for(i=0; i<10; i++)  
    {  
        printf("%d  ", arr[i]);  
    } 
    printf("\n");	
}
```
![example1array](https://user-images.githubusercontent.com/47218880/52576672-31a2ed80-2de6-11e9-8431-3c05a0f24761.png)

## 2). Write a program in C for a 2D array of size 3x3 and print the matrix.

```C
#include <stdio.h>

void main()
{
  int arr1[3][3],i,j;
  
       printf("\n\nRead a 2D array of size 3x3 and print the matrix :\n");
       printf("------------------------------------------------------\n");  
  
 
    /* Stored values into the array*/
       printf("Input elements in the matrix :\n");
  for(i=0;i<3;i++)
  {
      for(j=0;j<3;j++)
      {
	      printf("element - [%d],[%d] : ",i,j);
	      scanf("%d",&arr1[i][j]);
      }
  }  
 
 printf("\nThe matrix is : \n");
  for(i=0;i<3;i++)
  {
      printf("\n");
      for(j=0;j<3;j++)
           printf("%d\t",arr1[i][j]);
  }
 printf("\n\n");
}
```
![twodarray](https://user-images.githubusercontent.com/47218880/52576871-965e4800-2de6-11e9-962a-ae54ae780211.png)
