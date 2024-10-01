---
toc: False
comments: True
layout: post
title: 3.6 Conditionals
description: Student led teaching on Conditionals. Learn how conditionals control the flow of a program by executing specific blocks of code under certain conditions.
permalink: /csp/big-idea/3-6-solution
categories: ['CSP Big Ideas']
author: LEIA
menu: nav/csp_units/csp_unit3_p1_fundamentals.html
---

# Solution
This is the solution to the 3.6 Homework Hack.
This is just an example, your code may be slightly different and still be right.


```python
# Function to compare two numbers
def compare_two_numbers(num1, num2):
    # Check if the numbers are equal
    if num1 == num2:
        print("Both numbers are equal.")
    # Find the larger number if they are different
    elif num1 > num2:
        print(f"The larger number is {num1}.")
    else:
        print(f"The larger number is {num2}.")

# Get user input
num1 = float(input("Enter the first number: "))
num2 = float(input("Enter the second number: "))

# Call the function to compare the two numbers
compare_two_numbers(num1, num2)
```
