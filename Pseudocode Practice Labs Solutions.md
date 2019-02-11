PseudoCode Practice Labs Solutions:

## 1 Calculating Phone Overage fees Algorithm (Using pencil and paper, or calculator)

1. You get the number of excess minutes that you have used.
2. You multiply the number of excess minutes by 0.35.
3. The result of the calculation is your current overage fee.

Ask yourself the following questions about this algorithm:

Question: What input do I need to perform this algorithm?
Answer: I need the number of excess minutes.

Question: What must I do with the input?
Answer: I must multiply the input (the number of excess minutes) by
0.35. The result of that calculation is the overage fee.

Question: What output must I produce?
Answer: The overage fee.

Now that you have identified the input, the process that must be performed, and the
output, you can write the general steps of the program’s algorithm:

Computer Algorithm

1. Get the number of excess minutes as input.
2. Calculate the overage fee by multiplying the number of excess minutes by 0.35.
3. Display the overage fee.

In Step 1 of the computer algorithm, the program gets the number of excess minutes
from the user. Any time a program needs the user to enter a piece of data, it does two
things: (1) it displays a message prompting the user for the piece of data, and (2) it
reads the data that the user enters on the keyboard, and stores that data in a variable.

In pseudocode, Step 1 of the algorithm will look like this:

Display "Enter the number of excess minutes."
Input excessMinutes
Notice that the Input statement stores the value entered by the user in a variable
named excessMinutes.

In Step 2 of the computer algorithm, the program calculates the overage fee by multiplying
the number of excess minutes by 0.35. The following pseudocode statement performs
this calculation, and stores the result in a variable named overageFee:

Set overageFee = excessMinutes * 0.35

In Step 3 of the computer algorithm, the program displays the overage fee. Because the
overage fee is stored in the overageFee variable, the program will display a message
that shows the value of the overageFee variable. 
In pseudocode we will use the following statement:

Display "Your current overage fee is $", overageFee

The Following shows the entire pseudocode program, with example output.

Program:

1 Display "Enter the number of excess minutes."
2 Input excessMinutes
3 Set overageFee = excessMinutes * 0.35
4 Display "Your current overage fee is $", overageFee

Program Output (with Input Shown in Bold)

Enter the number of excess minutes.
100 [Enter]
Your current overage fee is $35


#2 Here is the algorithm for Calculating a Percentage:

1. Get the original price of the item.
2. Calculate 20 percent of the original price. This is the amount of the discount.
3. Subtract the discount from the original price. This is the sale price.
4. Display the sale price.

In Step 1 we get the original price of the item. We will prompt the user to enter this
data on the keyboard. Recall from the previous section that prompting the user is a
two-step process: (1) display a message telling the user to enter the desired data, and
(2) reading that data from the keyboard. We will use the following pseudocode statements
to do this. Notice that the value entered by the user will be stored in a variable
named originalPrice.

Display "Enter the item's original price."
Input originalPrice

In Step 2, we calculate the amount of the discount. To do this we multiply the original
price by 20 percent. The following statement performs this calculation and stores the
result in the discount variable.

Set discount = originalPrice * 0.2

In Step 3, we subtract the discount from the original price. The following statement
does this calculation and stores the result in the salePrice variable.

Set salePrice = originalPrice – discount

Last, in Step 4, we will use the following statement to display the sale price:

Display "The sale price is $", salePrice

The following shows the entire pseudocode program, with example output. 

1 Display "Enter the item's original price."
2 Input originalPrice
3 Set discount = originalPrice * 0.2
4 Set salePrice = originalPrice – discount
5 Display "The sale price is $", salePrice

#3 Calculating an Average
Here is the algorithm:

1. Get the first test score.
2. Get the second test score.
3. Get the third test score.
4. Calculate the average by adding the three test scores and dividing the sum by 3.
5. Display the average.

In Steps 1, 2, and 3 we will prompt the user to enter the three test scores. We will store
those test scores in the variables test1, test 2, and test 3. In Step 4 we will calculate
the average of the three test scores. We will use the following statement to perform the
calculation and store the result in the average variable:

Set average = (test1 + test2 + test3) / 3

Last, in Step 5, we display the average.
This shows the pseudocode program for this lab:

1 Display "Enter the first test score."
2 Input test1
3 Display "Enter the second test score."
4 Input test2
5 Display "Enter the third test score."
6 Input test3
7 Set average = (test1 + test2 + test3) / 3
8 Display "The average score is ", average

Program Output (with Input Shown in Bold)

Enter the first test score.
90 [Enter]
Enter the second test score.
80 [Enter]
Enter the third test score.
100 [Enter]
The average score is 90

#4 Converting a Math Formula to a Programming Statement
Here is the Algorithm:

1. Get the desired future value.
2. Get the annual interest rate.
3. Get the number of years that the money will sit in the account.
4. Calculate the amount that will have to be deposited.
5. Display the result of the calculation in Step 4.

In Steps 1 through 3, we will prompt the user to enter the specified values. We will
store the desired future value in a variable named futureValue, the annual interest
rate in a variable named rate, and the number of years in a variable named years.

In Step 4, we calculate the present value, which is the amount of money that we will
have to deposit. We will convert the formula previously shown to the following
pseudocode statement. The statement stores the result of the calculation in the presentValue
variable.

Set presentValue = futureValue / (1 + rate)^years

In Step 5, we display the value in the presentValue variable. The Following shows the
pseudocode for this program.

1 Display "Enter the desired future value."
2 Input futureValue
3 Display "Enter the annual interest rate."
4 Input rate
5 Display "How many years will you let the money grow?"
6 Input years
7 Set presentValue = futureValue / (1 + rate)^years
8 Display "You will need to deposit $", presentValue

Program Output (with Input Shown in Bold)

Enter the desired future value.
10000 [Enter]
Enter the annual interest rate.
0.05 [Enter]
How many years will you let the money grow?
10 [Enter]
You need to deposit $6139



