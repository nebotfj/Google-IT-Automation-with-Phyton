# Crash Course of Python - Week 2
In this module you’ll learn about different data types in Python, how to identify them, and how to convert between them. You’ll also learn how to use variables to assign data and to reference variables. You’ll deep dive into functions: 
- how to define them, 
- pass them parameters, 
- and have them return information. 
You’ll explore the concepts of code reuse, code style, and refactoring complex code, along with effectively using code comments. Finally, you’ll learn about comparing data using equality and logical operators, and leveraging these to build complex branching scripts using if statements.

## Learning Objectives
- Objetivos de aprendizaje
- Differentiate and convert between different data types utilizing variables
- Define and call functions utilizing parameters and return data
- Refactor code and write comments to reduce complexity and enhance code readability and code reuse
- Compare values using equality operators and logical operators
- Build complex branching scripts utilizing if, else and elif statements

---

## Expression and Variables
### Data Types
There are different data tpyes in Python. Some of the examples include:
* String 
   - which represents text wrapped in quotation marks to be manipulated by a script
   - text in between quotes -- either single or double quotes --
* Integer which represents whole numbers without a fraction (ex. 1)
* Float 
   - which represents real numbers like a number with a fractional part (ex. 2.5)
   - An integer is a whole number, without a fraction, while a float is a real number that can contain a fractional part. For example, 1, 7, 342 are all integers, while 5.3, 3.14159 and 6.0 are all floats.

Generally, computer doesn't know how to mix different data types - it results "TypeError" (When attempting to mix incompatible data types).

If you're ever not 100 percent sure what data types a certain value is, Python gives you a handy way to find out. You can use the type() function, to have the computer tell you the type

### Variables
* **Variables** are names that we give to certain values in our programs - variables are like containers for data.
    * Values can be of any data type; numbers, strings or even the results of operations.
    * Variables are important in programming because they let you perform operations on data that may change
* **Assignment** is the process of storing a value inside a variable.
    * A value is assigned to a variable by using the equal sign in the form of variable equals value
* An **expression** is a combination of numbers, symbols or other variables that produce a result when evaluated.

````Python
Question
Fill in the blanks to calculate the area of a triangle of base 5, height 3 and output the result.  Reminder:  the area of a triangle is (base*height)/2.

base = 5
height = 3
area = (base * height)/2

print(area)
````

Below are some **restrictions** when naming variables in Python
1. Key words or functions that Python reserves for its own cannot be used as variable names
2. Variable names can't have any spaces and they must start with either a letter or an underscore
3. Variable names can only be made up of letters, numbers and underscores
4. Python variables are case sensitive

### Expressions, Numbers, and Type Conversion
* **Implicit conversion** takes plance when the interpreter automatically converts one data type into another.
   - Implicit conversion is where the interpreter helps us out and automatically converts one data type into another, without having to explicitly tell it to do so.
* **Explicit conversion** takes place when a function is called to convert one data type into antother
   - explicit conversion is where we manually convert from one data type to another by calling the relevant function for the data type we want to convert to.
````Python
Question
In this scenario, we have a directory with 5 files in it. Each file has a different size: 2048, 4357, 97658, 125, and 8. Fill in the blanks to calculate the average file size by having Python add all the values for you, and then set the files variable to the number of files. Finally, output a message saying "The average size is: " followed by the resulting number. Remember to use the str() function to convert the number into a string. 

total = 2048 + 4357 + 97658 + 125 + 8
files = 5
average = total / files
print("The average size is: " + str(average))
````
---

## Functions
### Defining Functions
To define a function in Python,
1. Use the **def** keyword to define a function. The name of the function is what comes after the keyword. 
2. The parameters of the function are written between parentheses after the name.
3. The body of the function must be to the right of the definition.
Example:
    ```Python
    def greeting(name):
        print("Welcome, " + name)
    
    greeting("Kay") # Will print Welcome, Kay
    ```
````Python
    Flesh out the body of the print_seconds function so that it prints the total amount of seconds given the hours, minutes, and seconds function parameters. Remember that there are 3600 seconds in an hour and 60 seconds in a minute.

def print_seconds(hours, minutes, seconds):
    print(3600*hours+60*minutes+seconds)

print_seconds(1,2,3) #Output 3723
````   
#### Defining Functions Recap
We looked at a few examples of built-in functions in Python, but being able to define your own functions is incredibly powerful. We start a function definition with the def keyword, followed by the name we want to give our function. After the name, we have the parameters, also called arguments, for the function enclosed in parentheses. A function can have no parameters, or it can have multiple parameters. Parameters allow us to call a function and pass it data, with the data being available inside the function as variables with the same name as the parameters. Lastly, we put a colon at the end of the line.

After the colon, the function body starts. It’s important to note that in Python the function body is delimited by indentation. This means that all code indented to the right following a function definition is part of the function body. The first line that’s no longer indented is the boundary of the function body. It’s up to you how many spaces you use when indenting -- just make sure to be consistent. So if you choose to indent with four spaces, you need to use four spaces everywhere in your code.

### Returning Values
The return statement allows us to:
* Combine calls to functions
* Perform more complex operations
* Makes the code more reusable
* **In Python, it can return more than one value**
 
* **Double slash operator (//)** is called **floor division**. A floor division divides a number and takes the integer part of the division as the result.
* **None** is a very special data type in Python used to indicate that things are empty or that they return nothing.

````Python
Use the get_seconds function to work out the amount of seconds in 2 hours and 30 minutes, then add this number to the amount of seconds in 45 minutes and 15 seconds. Then print the result.

def get_seconds(hours, minutes, seconds):
  return 3600*hours + 60*minutes + seconds

amount_a = get_seconds(2,30,0)
amount_b = get_seconds(0,45,15)
result = amount_a + amount_b
print(result) #Output 11715 
````
#### Returning Values Using Functions
Sometimes we don't want a function to simply run and finish. We may want a function to manipulate data we passed it and then return the result to us. This is where the concept of return values comes in handy. We use the return keyword in a function, which tells the function to pass data back. When we call the function, we can store the returned value in a variable. Return values allow our functions to be more flexible and powerful, so they can be reused and called multiple times.

Functions can even return multiple values. Just don't forget to store all returned values in variables! You could also have a function return nothing, in which case the function simply exits.

### The Principles of Code Reuse
A lesson about how to clean code

````Phyton
In this code, identify the repeated pattern and replace it with a function called month_days, that receives the name of the month and the number of days in that month as parameters. Adapt the rest of the code so that the result is the same. Confirm your results by making a function call with the correct parameters for both months listed.

# REPLACE THIS STARTER CODE WITH YOUR FUNCTION
june_days = 30
print("June has " + str(june_days) + " days.")
july_days = 31
print("July has " + str(july_days) + " days.")


# REPLACE THIS STARTER CODE WITH YOUR FUNCTION
def month_days(month,days):
    print(month +" has " + str(days) +" days. ")
month_days("June","30")
month_days("July","31")

````

### Code Style
A few principles in mind to create good well styled code are:
1. Code to be self-documenting as possible: Refactoring
    * Self-documenting code is written in a way that's readable and doesn't conceal its intent. 
2. Leave a comment to add a bit of explanatory texts to the code
    * In Python, comments are indicated by the hash character (#)
````Python
# This id how to write a comment in Python
````
````Python
This function to calculate the area of a rectangle is not very readable. Can you refactor it, and then call the function to calculate the area with base of 5 and height of 6?
Tip: a function that calculates the area of a rectangle should probably be called rectangle_area, and if it's receiving base and height, that's what the parameters should be called.

def rectangle_area(base, height):
	z = base*height  # the area is base*height
	print("The area is " + str(z))
rectangle_area(5,6)
# Refactoring consists in clarifying the name of the variables to remove doubts about their interpretation.
# Here is your output: The area is 30
````

---

## Conditionals
### Compare Things
**Boolean**: One of two possible states: true or false

Equality operators allows us to take the result of the expressions and use them to make decisions
* a == b: a is equal to b
* a != b: a is different than b # Not equals operatos
* a < b: a is smaller than b
* a <= b: a is smaller or equal to b
* a > b: a is bigger than b
* a >= b: a is bigger or equal to b

````Python
# Figure out what's the relationship between the strings "cat" and "Cat" by replacing the plus sign with comparison operators.
print("cat" > "Cat")
# "cat" is larger than "Cat"
````
**In Python uppercase letters are alphabetically sorted before lowercase letters**

Logical operators allow connecting multiple statements together and perform more complex comparisons: AND, OR, NOT:
* a and b: True if both a and b are True. False otherwise.
* a or b: True if either a or b or both are True. False if both are False.
* not a: True if a is False, False if a is True.

#### Comparasion Operators Recap
In Python, we can use comparison operators to compare values. When a comparison is made, Python returns a boolean result, or simply a True or False. 
- To check if two values are the same, we can use the equality operator: **==**
- To check if two values are not the same, we can use the not equals operator: **!=**

We can also check if values are greater than or lesser than each other using **>** and **<**. If you try to compare data types that aren’t compatible, like checking if a string is greater than an integer, Python will throw a **TypeError.** 

We can make very complex comparisons by joining statements together using logical operators with our comparison operators. These logical operators are **and**, **or**, and **not.** 
- Using the **and** operator, both sides of the statement being evaluated must be true for the whole statement to be true. 
- Using the **or** operator, if either side of the comparison is true, then the whole statement is true. 
- Using the **not** operator simply inverts the value of the statement immediately following it. So if a statement evaluates to True, and we put the not operator in front of it, it would become False.

### Branching with if Statements
**Branching** is the ability of a program to alter its execution sequence  depending on the values of variables.

if block vs. defined function
| Similarities | Differences |
|:-|:-|
| * The keyword, either def or if, indicates the start of a special block
* Colon is used at the end of the first line
* The body of the function or the if block is indented to the right | * The body of the if block will only execute when the condition evaluates to true; otherwise, it skipped |

We can use an if statement to evaluate a comparison.
- We start with the if keyword, followed by our comparison. 
- We end the line with a colon. 
- The body of the if statement is then indented to the right. 
	- If the comparison is True, the code inside the if body is executed. 
	- If the comparison evaluates to False, then the code block is skipped and will not be run.

### else Statements
We just covered the if statement, which executes code if an evaluation is true and skips the code if it’s false. But what if we wanted the code to do something different if the evaluation is false? We can do this using the else statement. The else statement follows an if block, and is composed of the keyword else followed by a colon. The body of the else statement is indented to the right, and will be executed if the above if statement doesn’t execute.

* The **modulo operator** is represented by the percentage sign (%) and __returns the remainder of the integer division between two numbers__. 
* **The integer division is an operation between integers that yields two results which are both integers, the quotient and the remainder.*
* When a return statement is executed, the function exits so that the code that follows doesn't get executed.

This operator performs integer division, but only returns the remainder of this division operation. If we’re dividing 5 by 2, the quotient is 2, and the remainder is 1. Two 2s can go into 5, leaving 1 left over. So 5%2 would return 1. Dividing 10 by 5 would give us a quotient of 2 with no remainder, since 5 can go into 10 twice with nothing left over. In this case, 10%2 would return 0, as there is no remainder.

````Python
The is_positive function should return True if the number received is positive and False if it isn't. Can you fill in the gaps to make that happen?
def is_positive(number):
  if number > 0:
    return True
  else:
    return False
    ````

### elif Statements (else if)
The main difference between elif and if statements is that an elif block can be only written as as a companion to an if block.

Building off of the if and else blocks, which allow us to branch our code depending on the evaluation of one statement, the elif statement allows us even more comparisons to perform more complex branching. 
Very similar to the if statements, an elif statement starts with the elif keyword, followed by a comparison to be evaluated. This is followed by a colon, and then the code block on the next line, indented to the right. 
An elif statement must follow an if statement, and will only be evaluated if the if statement was evaluated as false. You can include multiple elif statements to build complex branching in your code to do all kinds of powerful things!

````Python
The number_group function should return "Positive" if the number received is positive, "Negative" if it's negative, and "Zero" if it's 0. Can you fill in the gaps to make that happen?
def number_group(number): 
  if number > 0:
    return "Positive"
  elif number == 0:
    return "Zero"
  else:
    return "Negative"

print(number_group(10)) #Should be Positive
print(number_group(0)) #Should be Zero
print(number_group(-5)) #Should be Negative
````

### Conditionals Cheat Sheet
In earlier videos, we took a look at some of the built-in Python operators that allow us to compare values, and some logical operators we can use to combine values. We also learned how to use operators in if-else-elif blocks. 

It’s a lot to learn but, with practice, it gets easier to remember it all. In the meantime, this handy cheat sheet gives you all the information you need at a glance. 

#### Comparison operators
- a == b: a is equal to b
- a != b: a is different than b
- a < b: a is smaller than b
- a <= b: a is smaller or equal to b
- a > b: a is bigger than b
- a >= b: a is bigger or equal to b

#### Logical operators
- a and b: True if both a and b are True. False otherwise.
- a or b: True if either a or b or both are True. False if both are False.
- not a: True if a is False, False if a is True.

#### Branching blocks
In Python, we branch our code using if, else and elif. This is the branching syntax:
````Python
if condition1:
	if-block
elif condition2:
	elif-block
else:
	else-block
````
Remember: The if-block will be executed if condition1 is True. The elif-block will be executed if condition1 is False and condition2 is True. The else block will be executed when all the specified conditions are false.
---

## Credit
* [Coursera - Python Crash Course Week 2](https://www.coursera.org/learn/python-crash-course/home/week/2)
