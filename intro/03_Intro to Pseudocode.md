# PseudoCode

We all know each programming language has strict rules( at least we "should"), known as syntax,
that the programmer must follow when writing a program. If the programmer writes code
that violates these rules, a syntax error will result and the program cannot be compiled or
executed. 

When this happens, the programmer has to locate the error and correct it.
Because small mistakes like misspelled words and forgotten punctuation characters
can cause syntax errors, programmers have to be mindful of such small details when
writing code. For this reason, programmers find it helpful to write their programs in
pseudocode (pronounced “sue doe code”) before they write it in the actual code of a
programming language.

The word pseudo means fake, so pseudocode is fake code. It is an informal language
that has no syntax rules, and is not meant to be compiled or executed. Instead, programmers
use pseudocode to create models, or “mock-ups” of programs. Because programmers
don’t have to worry about syntax errors while writing pseudocode, they can focus
all of their attention on the program’s design. Once a satisfactory design has been created
with pseudocode, the pseudocode can be translated directly to actual code.


## Here is an example of how you might write pseudocode for the pay calculating
## program that we discussed earlier:
```
Display "Enter the number of hours the employee worked."
Input hours
Display "Enter the employee's hourly pay rate."
Input payRate
Set grossPay = hours * payRate
Display "The employee's gross pay is $", grossPay
```
Each statement in the pseudocode represents an operation that can be performed in
any high-level language. For example, all languages provide a way to display messages
on the screen, read input that is typed on the keyboard, and perform mathematical calculations.
For now, don’t worry about the details of this particular pseudocode program.

>NOTE: As you read the examples in this section, keep in mind that pseudocode is
not an actual programming language. It is a generic way to write the statements of
an algorithm, without worrying about syntax rules. If you mistakenly write
pseudocode into an editor for an actual programming language, such as Python or
C, Java, or Visual Basic, errors will result.

## PseudoCode Practice Labs:

## 1 Calculating Cell Phone Overage Fees
Suppose your cell phone calling plan allows you to use 700 minutes per month. If you
use more than this limit in a month, you are charged an overage fee of 35 cents for each
excess minute. Your phone shows you the number of excess minutes that you have
used in the current month, but it does not show you how much your overage fee currently
is. Until now, you’ve been doing the math the old-fashioned way (with pencil
and paper, or with a calculator), but you would like to design a program that will simplify
the task. You would like to be able to enter the number of excess minutes, and
have the program perform the calculation for you.
First, you want to make sure that you understand the steps that the program must perform.
It will be helpful if you closely look at the way you’ve been solving this problem,
using only paper and pencil, or calculator.

## 2 Calculating a Percentage
Determining percentages is a common calculation in computer programming. In
mathematics, the % symbol is used to indicate a percentage, but most programming
languages don’t use the % symbol for this purpose. In a program, you usually have to
convert a percentage to a decimal number. 
For example, 50 percent would be written as 0.5 and 2 percent would be written as 0.02.

Let’s step through the process of writing a program that calculates a percentage. Suppose
a retail business is planning to have a storewide sale where the prices of all items
will be 20 percent off. We have been asked to write a program to calculate the sale
price of an item after the discount is subtracted.

## 3 Calculating an Average

Determining the average of a group of values is a simple calculation: You add all of the
values and then divide the sum by the number of values. Although this is a straightforward
calculation, it is easy to make a mistake when writing a program that calculates an
average. For example, let’s assume that the variables a, b, and c each hold a value and
we want to calculate the average of those values. If we are careless, we might write a
statement such as the following to perform the calculation:

Set average = a + b + c / 3

Can you see the error in this statement? When it executes, the division will take place
first. The value in c will be divided by 3, and then the result will be added to a + b.
That is not the correct way to calculate an average. To correct this error we need to put
parentheses around a + b + c, as shown here:

Set average = (a + b + c) / 3

Let’s step through the process of writing a program that calculates an average. Suppose
you have taken three tests in your computer science class, and you want to write a program
that will display the average of the test scores.

## 4 Converting a Math Formula to a programming Statement

Suppose you want to deposit a certain amount of money into a savings account, and
then leave it alone to draw interest for the next 10 years. At the end of 10 years you
would like to have $10,000 in the account. How much do you need to deposit today to
make that happen? You can use the following formula to find out:

	P= F/(1+r)squared n

The terms in the formula are as follows:
● P is the present value, or the amount that you need to deposit today.
● F is the future value that you want in the account. (In this case, F is $10,000.)
● r is the annual interest rate.
● n is the number of years that you plan to let the money sit in the account.
It would be nice to write a computer program to perform the calculation, because
then we can experiment with different values for the terms.
