## Question 1: 
The problem size is the number of people in the room.

## Question 2: 
Assume there are N people in the room. 
In algorithm 1 you always ask 1 question. In algorithm 2, the worst case is if no one has your birthday. 
Here you have to ask every person to figure this out. This is N questions. 

In algorithm 3, the worst case is the same as algorithm 2. 
he number of questions is 1 + 2 + 3 + ... + N-1 + N. We showed before that this sum is N(N+1)/2.

## Question 3: 
Given the number of questions you can see that algorithm 1 is constant time, 
algorithm 2 is linear time, and algorithm 3 is quadratic time in the problem size.
