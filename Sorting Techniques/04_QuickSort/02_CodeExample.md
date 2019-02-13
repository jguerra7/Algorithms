# Quick Sort example 

## Quick Sort Pivot Pseudocode (easier to take in the process):

### The pseudocode for the above algorithm can be derived as −
```
function partitionFunc(left, right, pivot)
   leftPointer = left
   rightPointer = right - 1

   while True do
      while A[++leftPointer] < pivot do
         //do-nothing            
      end while
		
      while rightPointer > 0 && A[--rightPointer] > pivot do
         //do-nothing         
      end while
		
      if leftPointer >= rightPointer
         break
      else                
         swap leftPointer,rightPointer
      end if
		
   end while 
	
   swap leftPointer,right
   return leftPointer
	
end function
```

### Example C code for Quick sort:

Example output:
![image](https://user-images.githubusercontent.com/47218880/52735369-1cb48e80-2f8d-11e9-8002-aa7a1d9bb865.png)


### C code for example output:
```C
  
#include <stdio.h>
#include <conio.h>
void qsort();
int n;
void main()
{
	int a[100],i,l,r;
	clrscr();
	printf("\nENTER THE SIZE OF THE ARRAY: ");
	scanf("%d",&n);
	for(i=0;i<n;i++)
	{
		printf("\nENTER NUMBER-%d: ",i+1);
		scanf("%d",&a[i]);
	}
	printf("\nTHE ARRAY ELEMENTS BEFORE SORTING: \n");
	for(i=0;i<n;i++)
	{
		printf("%5d",a[i]);
	}
	l=0;
	r=n-1;
	qsort(a,l,r);
	printf("\nTHE ARRAY ELEMENTS AFTER SORTING: \n");
	for(i=0;i<n;i++)
		printf("%5d",a[i]);
	getch();
}
void qsort(int b[],int left,int right)
{
	int i,j,p,tmp,finished,k;
	if(right>left)
	{
		i=left;
		j=right;
		p=b[left];
		finished=0;
		while (!finished)
		{
			do
			{
				++i;
			}
			while ((b[i]<=p) && (i<=right));
			while ((b[j]>=p) && (j>left))
			{
				--j;
			}
			if(j<i)
				finished=1;
			else
			{
				tmp=b[i];
				b[i]=b[j];
				b[j]=tmp;
			}
		}
		tmp=b[left];
		b[left]=b[j];
		b[j]=tmp;
		qsort(b,left,j-1);
		qsort(b,i,right);
	}
	return;
}

```
