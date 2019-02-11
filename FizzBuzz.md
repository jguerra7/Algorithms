For those of you that are new to programming and those of you coming from different programming bases,
such as Python, C, C++, or Java, this example should be quite helpful. In this section, we will discuss a simple solution for
implementing a typical algorithmic problem

## Fizz Buzz Test
The "Fizz-Buzz test" is an interview question designed to help filter out the 99.5% of programming job candidates who can't seem to program their way out of a wet paper bag. 
 text of the programming assignment is as follows:
"Write a program that prints the numbers from 1 to 100. 
But for multiples of three print “Fizz” instead of the number and for the multiples of five print “Buzz”. 
For numbers which are multiples of both three and five print “FizzBuzz”."

## Fizz Buzz Implementation
Fizz Buzz is a very simple programming task, asked in software developer job interviews and exams.

 A typical round of Fizz Buzz can be:
>Write a program that prints the numbers from 1 to 100 and for multiples of '3' print "Fizz" instead of the number and for the multiples of '5' print "Buzz".

Output:
```
1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, 
Fizz Buzz, 16, 17, Fizz, 19, Buzz, Fizz, 22, 23, Fizz, Buzz, 26, 
Fizz, 28, 29, Fizz Buzz, 31, 32, Fizz, 34, Buzz, Fizz, ...
```

## Why Fizz-Buzz is a "Challenge:"
We can't understand why so many people "fail" the Fizz-Buzz test unless we understand why it is "hard" (for them). Understanding that, 
we may be able to evaluate the usefulness of this tool, and others, as filtering tools for candidates.
I think Fizz-Buzz is "hard" for some programmers because (#1) it doesn't fit into any of the patterns that were given to them in school assignments, 
and (#2) it isn't possible to directly and simply represent the necessary tests, without duplication, in just about any commonly-used modern programming language.
On #1, that it doesn't match the patterns they memorized from lectures and class assignments: 
I think this makes it a good discriminator, 
because I wish to hire candidates who can think for themselves -- not those who are limited to copying solutions from others.

On #2, that it's hard to directly code it: Fizz-Buzz does not fall into the common pattern of
 > if 1 then A
  else if 2 then B
  else if 3 then C
  else/otherwise D
  
(Well it does, but not when you consider "1,2 & 3" to be atomic tests, like "is divisible by 3.")
Consider...
```
  if (theNumber is divisible by 3) then
	print "Fizz"
  else if (theNumber is divisible by 5) then
	print "Buzz"
  else /* theNumber is not divisible by 3 or 5 */
	print theNumber
  end if
  ```
Now where do you put "FizzBuzz" in this structure?
Like this...?
```
  if (theNumber is divisible by 3) then	--->
	if (theNumber is divisible by 5) then
	print "FizzBuzz"
	else			  <---
	print "Fizz"
  else if (theNumber is divisible by 5) then
	print "Buzz"
  else /* theNumber is not divisible by 3 or 5 */
	print theNumber
  end if
 ``` 
This is an example of an algorithm, which is a set of well-defined logical steps that
must be taken to perform a task.

## Example of the Fizzbuzz in C:
```C
#include <stdio.h> 
  
int main(void) 
{ 
    int i; 
    for (i=1; i<=100; i++) 
    { 
        // number divisible by 3 and 5 will 
        // always be divisible by 15, print  
        // 'FizzBuzz' in place of the number 
        if (i%15 == 0)         
            printf ("FizzBuzz\t");     
          
        // number divisible by 3? print 'Fizz' 
        // in place of the number 
        else if ((i%3) == 0)     
            printf("Fizz\t");                  
          
        // number divisible by 5, print 'Buzz'   
        // in place of the number 
        else if ((i%5) == 0)                        
            printf("Buzz\t");                  
      
        else // print the number             
            printf("%d\t", i);                  
  
    } 
  
    return 0; 
} 
```
  
A programmer breaks down the task that a program must perform in a similar way.
An algorithm is created, which lists all of the logical steps that must be taken. 
For example, suppose you have been asked to write a program to calculate and display the
gross pay for an hourly paid employee. Here are the steps that you would take:

>1. Get the number of hours worked.
2. Get the hourly pay rate.
3. Multiply the number of hours worked by the hourly pay rate.
4. Display the result of the calculation that was performed in Step 3.

Of course, this algorithm isn’t ready to be executed on the computer. The steps in this
list have to be translated into code. Programmers commonly use two tools to help them
accomplish this: pseudocode and flowcharts. Let’s look at each of these in more detail.
