# Using Real World Situations:
Big O notation is used to describe or calculate time complexity (worst-case performance)of an algorithm. 
This section will show concrete examples of Big O notation.

Many “operations” in real life can help us with finding what the order is. When analyzing algorithms/operations, 
we often consider the worst-case scenario. 
What’s the worst that can happen to our algorithm and when does our algorithm need the most instructions to complete the execution? 
Big O notation will always assume the upper limit where the algorithm will perform the maximum number of iterations.

Let’s assume I am standing in the front of a class of students and one of them has my bag.
Here are few scenarios and ways in which I can find my bag and their corresponding order of notation.

## O(n) — Linear Time:
```
Scenario: Only one student in my class who hid my bag knows about it.

Approach: I will have to ask each student individually in the class if they have my bag.
If they don’t, I move on to ask the next student.

Worst-Case Scenario: In the worst case scenario, I will have to ask n questions.
```
```python
def search_for_bag(data):
    found = False
    for i,name in enumerate(data):
        # Have to go through each student to find who has my bag
            if data[name] is True:
                found = True
                return name

data = {
    'Jane' : False,
    'James' : False,
    'Jon' : False,
    'Joe': True
    } 
print(search_for_bag(data)) #Joe has my bag.
```

> o/p: The bag is with Joe

## Explanation:

Here, given an input of size n, the number of steps required is directly related to the amount of data it is processing.
Single for loops, linear search are examples of linear time
In above example, an array size/input size increases, time to find desired value also increases.

## O(1) — Constant Time
```
Scenario: Student who hid my bag name is known to me.

Approach : Since I know Joe has my bag, I’ll directly ask him to give it to me.

```
```python
#If I know the persons name, I have to take only one step to check
def get_bag(name):
    return data[name]
data = {
    'Jane' : False,
    'James' : False,
    'Jon' : False,
    'Joe': True
    }
print("Is bag with Joe ? " +str(get_bag('Joe')))
```
> o/p: Is bag with Joe ? True

## Explanation:

Here, given an input of size n, it only takes a one step for the algorithm to accomplish the task.
An algorithm takes same time(constant time) to execute irrespective of the amount of data.
This algorithm is not affected by the array size either


## O(n²) — Quadratic Time:
```
Scenario: In the entire class, only one student knows on which student desk my bag is hidden.

Approach: I will start questioning each student individually and ask him about all the others students too. 
If I don’t get the answer from the first student, I will move on to the next one.

Worst-Case Scenario: In the worst case scenario, 
I will have to ask n2 questions, questioning each student about other students as well.

```
```python

def search_bag(data):
    n = len(data)
    for x in range(n):
       answer = input("Do you have my bag, "+data[x] + "?")
       # each student individually if they have my bag
       if answer == 'yes':
         return "Ha! Found it "+ data[x] + "had my bag"
       else:
        # If they don't have it, ask about all other students.
         for y in range(x+1, n):
            new_answer = input("You think my bag is with " +data[y])
            if new_answer == 'yes':
                return 'Your bag is with '+data[y]
data=  ['Jane','James','Jon', 'Joe']  # Here Joe has the bag
print(search_bag(data))
```
## Explanation:

Here, given an input of size n, the number of steps it takes to accomplish a task is square of n.
Each pass to outer loop O(n) requires going through entire list through the inner-loop.
Nested for-loops are example of quadratic time as we run a linear operation within other linear operation

## O(log n) — Logarithmic time:
```
Scenario: Here, all the students know who has my bag but will only tell me if I guessed the right name.

Approach: I will divide the class in half, then ask: “Is my bag on the left side, or the right side of the class?” 
Then I take that group and divide it into two and ask again, and so on.

Worst Case Scenario: In the worst case, I will have to ask log n questions.
```
```python
def binary_bag_search(data, target, low = 0, high = None):
    if high is None:
        high = len(data)-1
    if low > high :
        return False
    else:
        mid = (low + high)// 2
        if data[mid] == target:
            return True
        elif data[mid] > target:
           return binary_search(data, target, low, mid-1)
        else:
            return binary_search(data,target, mid+1, high)
data=  ['Jane','James','Jon', 'Joe']  # Here Joe has the bag
found = binary_bag_search(data, 'Joe')
print("Bag Found ?" + found)
```
## Explanation:

Here, given an input of size n, the number of steps it takes to accomplish the task are decreased by 
roughly 50% each time through the algorithm.
O (log N) algorithms are very efficient because increasing amount of data has little effect at some point 
on because the amount of data is halved on each run through.
Binary search is a perfect example of this.(Which we will dive into later)
