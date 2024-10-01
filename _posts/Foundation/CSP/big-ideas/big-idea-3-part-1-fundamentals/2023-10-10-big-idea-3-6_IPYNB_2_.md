---
toc: False
comments: True
layout: post
title: 3.6 Conditionals
description: Student led teaching on Conditionals. Learn how conditionals control the flow of a program by executing specific blocks of code under certain conditions.
permalink: /csp/big-idea/3-6
categories: ['CSP Big Ideas']
author: LEIA
menu: nav/csp_units/csp_unit3_p1_fundamentals.html
---

## <mark>Conditionals</mark>

- Affect the sequential flow of control by executing different statements based on the value of a Boolean expression.
IF (condition)
{
	<block of statements>
}

The code in <block of statements> is executed if the Boolean expression condition evaluates to true; no action is taken if condition evaluates to false.

IF (condition)
{
	<block of statements>
}
ELSE
{
	<second block of statements>
}

The code in the first <block of statements> is executed if the Boolean expression condition evaluates to true; otherwise, the code in <second block of statements> is executed.
<b>Example:</b> Calculate the sum of 2 numbers. If the sum is greater than 10, display 10; otherwise, display the sum.
num1 = INPUT
num2 = INPUT
sum = num1 + num2
IF (sum > 10)
{
	DISPLAY (10)
}
ELSE
{
	DISPLAY (sum)
}
# Example

- Add a variable that represents an age.

- Add an 'if' and 'print' function that says "You are an adult" if your age is greater than or equal to 18.

- Make a function that prints "You are a minor" with the else function.


```python

age = input("age: ")
if int(age) >= 18:
    print("Adult")
else:
    print("Minor")
```

## JavaScript
This is the JS equivalent of the code


```python
let age = prompt("Enter your age:");
if (parseInt(age) >= 18) {
    console.log("Adult");
} else {
    console.log("Minor");
}
```

# Example

- Make a variable called 'is_raining' and set it to 'True".

- Make an if statement that prints "Bring an umbrella!" if it is true

- Make an else statement that says "The weather is clear".


```python

is_raining = False
if is_raining:
    print("Bring a umbrella")
else:
    print("The weather is clear")
```

## JavaScript
This is the JS equivalent of the code


```python
let isRaining = false;
if (isRaining) {
    console.log("Bring an umbrella");
} else {
    console.log("The weather is clear");
}
```

# Example

- Make a function to randomize numbers between 0 and 100 to be assigned to variables a and b using random.randint

- Print the values of the variables

- Print the relationship of the variables; a is more than, same as, or less than b


```python

import random


a = random.randint(0,100)
b = random.randint(0,100)
print(a, b)

if a > b:
    print( str(a) + " > " + str(b) )
elif a < b: 
    print( str(a) + " < " + str(b) )
else:
    print( str(a) + " = " + str(b) )


```

## JavaScript
This is the JS equivalent of the code


```python
let a = Math.floor(Math.random() * 101); // Random number between 0 and 100
let b = Math.floor(Math.random() * 101);

console.log(a, b);

if (a > b) {
    console.log(a + " > " + b);
} else if (a < b) {
    console.log(a + " < " + b);
} else {
    console.log(a + " = " + b);
}
```

## Hacks

Create a 5 question quiz following the comments in the `#HOMEWOR` code cell below.

1. Provided is `question_with_response` function and some introductory samples.
2. A key to the homeworks is to research and come up with each question type.
3. A key to the program is to evaluate input from user and calculate a result


```python
# Import necessary modules
import sys  # Module to access system-related information

# Function to ask a theoretical question and get a response
def question_with_response(prompt):
    answer = input(prompt)
    return answer

# Define the number of questions and initialize the correct answers counter
questions = 5
correct = 0

# Personalized greeting message
user_name = question_with_response("Enter your name: ")
print('Hello, ' + user_name + " you are running " + sys.executable)
ready = question_with_response("Are you ready to take a test on conditionals? (yes/no): ")

# Question 1: Basic Conditional Theory
q1 = question_with_response("1. What keyword is used in Python to check a condition? (a) for (b) if (c) while: ")
if q1.lower() == "b":
    print("Correct!")
    correct += 1
else:
    print("Incorrect. The correct answer is (b) if.")

# Question 2: `else` Statement
q2 = question_with_response("2. What happens if an `if` condition is false and there is an `else` block? (a) The program does nothing (b) The `else` block runs (c) An error occurs: ")
if q2.lower() == "b":
    print("Correct!")
    correct += 1
else:
    print("Incorrect. The correct answer is (b) The `else` block runs.")

# Question 3: `elif` Statement
q3 = question_with_response("3. What is the purpose of the `elif` keyword in Python? (a) It checks another condition if the previous one was false (b) It ends the program (c) It only runs if the `if` block runs: ")
if q3.lower() == "a":
    print("Correct!")
    correct += 1
else:
    print("Incorrect. The correct answer is (a) It checks another condition if the previous one was false.")

# Question 4: Boolean Expressions
q4 = question_with_response("4. Which of the following is a correct Boolean expression in an `if` statement? (a) if 5 > 3 (b) if 'text' (c) if == 10: ")
if q4.lower() == "a":
    print("Correct!")
    correct += 1
else:
    print("Incorrect. The correct answer is (a) if 5 > 3.")

# Question 5: Nested Conditionals
q5 = question_with_response("5. 3.7 Preview! What is a nested conditional? (a) An `if` statement inside another `if` statement (b) An `else` block that runs without conditions (c) A loop inside a conditional: ")
if q5.lower() == "a":
    print("Correct!")
    correct += 1
else:
    print("Incorrect. The correct answer is (a) An `if` statement inside another `if` statement.")

# Display the final score
print(user_name + ", you scored " + str(correct) + "/" + str(questions))
```

# Homework Hack
Write a Python program that takes two numbers as input from the user. The program should:

- Determine if the numbers are equal.
- If the numbers are different, print which number is larger.

## Answer:
<a href="{{site.baseurl}}/csp/big-idea/3-6-solution">See an example solution</a>
