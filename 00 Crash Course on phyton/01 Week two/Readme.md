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

### Reutrning Values
The return statement allows us to:
* Combine calls to functions
* Perform more complex operations
* Makes the code more reusable
* **In Python, it can return more than one value**
 
* **Double slash operator (//)** is called **floor division**. A floor division divides a number and takes the integer part of the division as the result.
* **None** is a very special data type in Python used to indicate that things are empty or that they return nothing.

### Code Style
A few principles in mind to create good well styled code are:
1. Code to be self-documenting as possible
    * Self-documenting code is written in a way that's readable and doesn't conceal its intent. 
2. Leave a comment to add a bit of explanatory texts to the code
    * In Python, comments are indicated by the hash character

---

## Conditionals
### Compare Things
Equality operators allows us to take the result of the expressions and use them to make decisions
* a == b: a is equal to b
* a != b: a is different than b
* a < b: a is smaller than b
* a <= b: a is smaller or equal to b
* a > b: a is bigger than b
* a >= b: a is bigger or equal to b

Logical operators allow connecting multiple statements together and perform more complex comparisons
* a and b: True if both a and b are True. False otherwise.
* a or b: True if either a or b or both are True. False if both are False.
* not a: True if a is False, False if a is True.

**In Python uppercase letters are alphabetically sorted before lowercase letters**

### Branching with if Statements
**Branching** is the ability of a program to alter its execution sequence.

if block vs. defined function
| Similarities | Differences |
|:-|:-|
| * The keyword, either def or if, indicates the start of a special block
* Colon is used at the end of the first line
* The body of the function or the if block is indented to the right | * The body of the if block will only execute when the condition evaluates to true; otherwise, it skipped |

### else Statements
* The **modulo operator** is represented by the percentage sign (%) and __returns the remainder of the integer division between two numbers__. 
* **The integer division is an operation between integers that yields two results which are both integers, the quotient and the remainder.*
* When a return statement is executed, the function exits so that the code that follows doesn't get executed.

### elif Statements
The main difference between elif and if statements is that an elif block can be only written as as a companion to an if block.

---

## Credit
* [Coursera - Python Crash Course Week 2](https://www.coursera.org/learn/python-crash-course/home/week/2)
