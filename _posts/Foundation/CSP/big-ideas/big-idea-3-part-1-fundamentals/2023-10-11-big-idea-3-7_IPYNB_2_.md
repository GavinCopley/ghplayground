---
toc: False
comments: True
layout: post
title: 3.7 Nested Conditionals
description: A supplemental blog on nested conditionals. Learn how nested conditionals allow for more complex decision-making by enabling multiple levels of conditions than regular conditionals.
permalink: /csp/big-idea/3-7
author: Isabel Marilla
menu: nav/csp_units/csp_unit3_p1_fundamentals.html
---

## Nested Conditionals



## Introduction

**Nested conditionalsare a fundamental concept in programming where one conditional statement is placed inside another. This allows for more complex decision-making processes and enables programs to handle a wider range of scenarios.

## Objectives

By the end of this lesson, students will be able to:
1. **Understand what nested conditionals are.**
2. **Write pseudocode using nested conditionals.**
3. **Apply nested conditionals to solve problems.**

## Key Concepts

1. `Conditional Statements`: Used to perform different actions based on different conditions.
2. `Nested Conditionals`: A conditional statement inside another conditional statement.

## Example Syntax (College Board Pseudocode)

College Board pseudocode uses the following structure for conditional statements:

```plaintext
IF condition1
{
    // Code block for condition1
    IF condition2
    {
        // Code block for condition2
    }
    ELSE
    {
        // Code block if condition2 is false
    }
}
ELSE
{
    // Code block if condition1 is false
}


`Example 1: Checking Grade Categories`

## Pseudocode
Let's write a pseudocode to determine the grade category based on a score:


```python
IF score >= 90
{
    DISPLAY "A"
}
ELSE
{
    IF score >= 80
    {
        DISPLAY "B"
    }
    ELSE
    {
        IF score >= 70
        {
            DISPLAY "C"
        }
        ELSE
        {
            IF score >= 60
            {
                DISPLAY "D"
            }
            ELSE
            {
                DISPLAY "F"
            }
        }
    }
}

```

## Python
Here is the equivalent Python code:


```python
score = 85

if score >= 90:
    print("A")
else:
    if score >= 80:
        print("B")
    else:
        if score >= 70:
            print("C")
        else:
            if score >= 60:
                print("D")
            else:
                print("F")

```

    B


# Javascript

Here is the equivalent Javascript code example: 


```python
let score = 85;

if (score >= 90) {
    console.log("A");
} else if (score >= 80) {
    console.log("B");
} else if (score >= 70) {
    console.log("C");
} else if (score >= 60) {
    console.log("D");
} else {
    console.log("F");
}

```

`Example 2: Determining Eligibility for a Loan`


## Pseudocode
Let's consider a scenario where we determine if a person is eligible for a loan based on their credit score and income:


```python
IF credit_score >= 700
{
    IF income >= 50000
    {
        DISPLAY "Eligible for loan"
    }
    ELSE
    {
        DISPLAY "Not eligible for loan due to low income"
    }
}
ELSE
{
    DISPLAY "Not eligible for loan due to low credit score"
}

```

## Python
Here is the equivalent Python code:




```python
credit_score = 750
income = 60000

if credit_score >= 700:
    if income >= 50000:
        print("Eligible for loan")
    else:
        print("Not eligible for loan due to low income")
else:
    print("Not eligible for loan due to low credit score")

```

    Eligible for loan


# Javascript

Here is the equivalent Javascript code: 


```python
// Input values
let credit_score = 750;
let income = 60000;

// Nested conditionals to check loan eligibility
if (credit_score >= 700) {
    if (income >= 50000) {
        console.log("Eligible for loan");
    } else {
        console.log("Not eligible for loan due to low income");
    }
} else {
    console.log("Not eligible for loan due to low credit score");
}
```

`Example 3`
Write pseudocode to determine if a person qualifies for a discount based on their membership status and purchase amount:

If the person is a member:
  - If the purchase amount is greater than $100, they get a 20% discount.
  - Otherwise, they get a 10% discount.
If the person is not a member:
   - If the purchase amount is greater than $100, they get a 5% discount.
    - Otherwise, they get no discount.



```python
IF is_member = TRUE
{
    IF purchase_amount > 100
    {
        DISPLAY "20% discount"
    }
    ELSE
    {
        DISPLAY "10% discount"
    }
}
ELSE
{
    IF purchase_amount > 100
    {
        DISPLAY "5% discount"
    }
    ELSE
    {
        DISPLAY "No discount"
    }
}

```

## Hacks
Review each of the sections above and produce ...

- Write pseudocode to determine if a student passes a class based on their exam scores and attendance using nested conditionals.
- Write a python segment  to decide the shipping cost based on the weight of a package and the delivery speed chosen (standard or express) using nested conditionals. 




```python
# Pseudocode 

IF exam_score >= 60
{
    IF attendance >= 75
    {
        DISPLAY "Pass"
    }
    ELSE
    {
        DISPLAY "Fail due to low attendance"
    }
}
ELSE
{
    DISPLAY "Fail due to low exam score"
}
```


```python

## Python Segment

# Ask the user for input values
weight = float(input("Enter the weight of the package in pounds: "))
delivery_days = int(input("Enter the delivery speed (number of delivery days): "))

# Determine if the delivery is under 3 days or not
is_express = delivery_days < 3

# Nested conditionals to calculate shipping cost
if is_express:  # More expensive if under 3 days
    if weight <= 5:
        print("Shipping cost is $15")
    else:
        print("Shipping cost is $25")
else:  # Less expensive if 3 days or more
    if weight <= 5:
        print("Shipping cost is $5")
    else:
        print("Shipping cost is $10")

```

    Shipping cost is $10



```python
## Another Example 

# Ask the user for input values
age = int(input("Enter your age: "))
is_student = input("Are you a student? (yes or no): ")

# Determine if the user is a student
student_discount = (is_student == 'yes' or is_student == 'Yes' or is_student == 'YES')

# Nested conditionals to calculate ticket price
if age < 12:  # Child ticket
    ticket_price = 8  # Base price for children
elif age >= 12 and age <= 64:  # Adult ticket
    ticket_price = 12  # Base price for adults
else:  # Senior ticket
    ticket_price = 10  # Base price for seniors

# Apply student discount if applicable
if student_discount:
    ticket_price *= 0.8  # 20% discount

print(f"The ticket price is: ${ticket_price:.2f}")


```

    The ticket price is: $9.60


* The program uses nested conditionals to determine the ticket price based on the user's age:
    * If the user is under 12, they receive a child ticket priced at $8.
    * If the user is between 12 and 64, they receive an adult ticket priced at $12.
    * If the user is 65 or older, they receive a senior ticket priced at $10.

* Discount Application:
    * If the student_discount is True, indicating that the user qualifies for a discount, the ticket price is multiplied by 0.8, applying a 20% discount.

* Calculate and display a result (in this case, the price of a movie ticket) based on multiple criteria (age and student status).
