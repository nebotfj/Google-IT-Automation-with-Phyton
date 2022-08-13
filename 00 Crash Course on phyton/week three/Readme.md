# Crash Course of Python - Week 3
In this module you'll explore the intricacies of loops in Python! You'll learn how to use while loops to continuously execute code, as well as how to identify infinite loop errors and how to fix them. You'll also learn to use for loops to iterate over data, and how to use the range() function with for loops. You'll also explore common errors when using for loops and how to fix them.
## Learning Objectives
- Implement while loops to continuously execute code
- Identify and fix infinite loops when using while loops
- Utilize for loops to iterate over sets of data
- Use the range() function to control for loops
- Identify and correct common errors when using loops

---

## While Loops
### What is a while loop?
While Loops instruct computer to continuously execute the code based on the value of a condition. The difference between if statements and while loop is that the body of the block can be executed multiple times instead of just once.

#### Anatomy of a While Loop
A while loop will continuously execute code depending on the value of a condition. It begins with the keyword while, followed by a comparison to be evaluated, then a colon. On the next line is the code block to be executed, indented to the right. Similar to an if statement, the code in the body will only be executed if the comparison is evaluated to be true. What sets a while loop apart, however, is that this code block will keep executing as long as the evaluation statement is true. Once the statement is no longer true, the loop exits and the next line of code will be executed.  
````Python
def attempts(n):
    x = 1
    while x <= n:
        print("Attempt " + str(x))
        x += 1
    print("Done")
    
attempts(5)
# Attempt 1
# Attempt 2
# Attempt 3
# Attempt 4
# Attempt 5
# Done
````

### Why initializing variables matters
**Initialization** is to give an initial value to a variable.
When we forget to initialize the variable two different things can happen:
1. A name error when we forget to initialize a variable 
2. When we forget to initialize variables with the right value
````Python
# In this code, there's an initialization problem that's causing our function to behave incorrectly. Can you find the problem and fix it?
def count_down(start_number):
  while (start_number > 0):
    print(start_number)
    start_number -= 1
  print("Zero!")
count_down(3)
# Here is your output: 3 2 1 Zero!
````
#### Common Pitfalls With Variable Initialization
You'll want to watch out for a common mistake: forgetting to initialize variables. If you try to use a variable without first initializing it, you'll run into a NameError. This is the Python interpreter catching the mistake and telling you that you’re using an undefined variable. The fix is pretty simple: initialize the variable by assigning the variable a value before you use it.

Another common mistake to watch out for that can be a little trickier to spot is forgetting to initialize variables with the correct value. If you use a variable earlier in your code and then reuse it later in a loop without first setting the value to something you want, your code may wind up doing something you didn't expect. Don't forget to initialize your variables before using them!

### Infinite loops and how to break them
An **infinite loop**, a loop that keeps executing and never stops.
While loops:
* Use the condition to check when to exit
* The body of the while loop needs to make sure that the condition being checked will change

**Break** keyword can stop infinite loops but also to stop a loop early if the code has already achieved what's needed.

````Python
#The following code causes an infinite loop. Can you figure out what’s missing and how to fix it?
def print_range(start, end):
	# Loop through the numbers from start to end
	n = start
	while n <= end:
		print(n)
		n = n+1
print_range(1, 5)  # Should print 1 2 3 4 5 (each number on its own line) 
# Here is your output: 1 2 3 4 5 
# Great work! You've managed to fix the error in the code that was causing an infinite loop!
````
#### Infinite loops and Code Blocks
Another easy mistake that can happen when using loops is introducing an infinite loop. An infinite loop means the code block in the loop will continue to execute and never stop. This can happen when the condition being evaluated in a while loop doesn't change. Pay close attention to your variables and what possible values they can take. Think about unexpected values, like zero.

In the Coursera code blocks, you may see an error message that reads "Evaluation took more than 5 seconds to complete." This means that the code encountered an infinite loop, and it timed out after 5 seconds. You should take a closer look at the code and variables to spot where the infinite loop is.
---

## for Loops
### What is for loop?
For loops iterate over a sequence of values. The for loop can iterate over a sequence of values of any type, not just a range of numbers.

The range function, range():
1. A range of numbers will start with the value 0 by default.
2. The list of numbers generated will be one less than the given value
3. The range function takes two parameters to the function instead of one to specify the first element of the list to generate
4. The range function takes a third parameter to change the size of each step (increments)

### Nested for Loops
**Nested for loops** are two for loops, one inside the other.

However, use caution when using nested for loops since the longer the list your code needs to iterate through, the longer it takes computer to complete the task. 

### Common Errors
The interpreter will refuse to iterate over a single element. This can be mitigated by:
1. Using range()
2. Make the loop iterate over a list with the single element

Since strings are iterable, above solution may be needed. 

for loops are best when you want to iterate over a known sequence of elements but when you want to operate while a certain condition is true, while loops are the best choice.

---

## Recursion
### What is recursion?
**Recursion** is the repeated application of the same procedure to a smaller problem. It tackles complex problems by reducing the problem to a simpler one by a function call itself until it reaches the **base case**.

In Python, a recursive function can be called up to 1,000 times.

---


## Credit
* [Coursera - Python Crash Course Week 3](https://www.coursera.org/learn/python-crash-course/home/week/3)
