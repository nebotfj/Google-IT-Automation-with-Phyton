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

````Python
# Want to try this out? Let's give it a go!
# Fill in the gaps of the sum_squares function, so that it returns the sum of all the squares of numbers between 0 and x (not included). Remember that you can use the range(x) function to generate a sequence of numbers from 0 to x (not included).
def square(n):
    return n*n

def sum_squares(x):
    sum = 0
    for n in range(x):
        sum += int(square(n))
    return sum

print(sum_squares(10)) # Should be 285
````

#### For Loops Recap
For loops allow you to iterate over a sequence of values. Let's take the example from the beginning of the video:

for x in range(5):

  print(x)

Similar to if statements and while loops, for loops begin with the keyword **for** with a colon at the end of the line. Just like in function definitions, while loops and if statements, the body of the for loop begins on the next line and is indented to the right. But what about the stuff in between the for keyword and the colon? In our example, we’re using the range() function to create a sequence of numbers that our for loop can iterate over. In this case, our variable **x** points to the current element in the sequence as the for loop iterates over the sequence of numbers. Keep in mind that in Python and many programming languages, a range of numbers will start at 0, and the list of numbers generated will be one less than the provided value. So range(5) will generate a sequence of numbers from 0 to 4, for a total of 5 numbers.

Bringing this all together, the range(5) function will create a sequence of numbers from 0 to 4. Our for loop will iterate over this sequence of numbers, one at a time, making the numbers accessible via the variable x and the code within our loop body will execute for each iteration through the sequence. So for the first loop, x will contain 0, the next loop, 1, and so on until it reaches 4. Once the end of the sequence comes up, the loop will exit and the code will continue.

The power of for loops comes from the fact that it can iterate over a sequence of any kind of data, not just a range of numbers. You can use for loops to iterate over a list of strings, such as usernames or lines in a file.

Not sure whether to use a for loop or a while loop? Remember that a while loop is great for performing an action over and over until a condition has changed. A for loop works well when you want to iterate over a sequence of elements.  

The range function, range():
1. A range of numbers will start with the value 0 by default.
2. The list of numbers generated will be one less than the given value
3. The range function takes two parameters to the function instead of one to specify the first element of the list to generate
4. The range function takes a third parameter to change the size of each step (increments)

#### A Closer Look at the Range() Function
Previously we had used the range() function by passing it a single parameter, and it generated a sequence of numbers from 0 to one less than we specified. But the range() function can do much more than that. We can pass in two parameters: the first specifying our starting point, the second specifying the end point. Don't forget that the sequence generated won't contain the last element; it will stop one before the parameter specified.

The range() function can take a third parameter, too. This third parameter lets you  alter the size of each step. So instead of creating a sequence of numbers incremented by 1, you can generate a sequence of numbers that are incremented by 5.

To quickly recap the range() function when passing one, two, or three parameters:
- One parameter will create a sequence, one-by-one, from zero to one less than the parameter.
- Two parameters will create a sequence, one-by-one, from the first parameter to one less than the second parameter.
- Three parameters will create a sequence starting with the first parameter and stopping before the second parameter, but this time increasing each step by the third parameter.


### Nested for Loops
**Nested for loops** are two for loops, one inside the other.

However, use caution when using nested for loops since the longer the list your code needs to iterate through, the longer it takes computer to complete the task. 

````Python
teams = [ 'Dragons', 'Wolves', 'Pandas', 'Unicorns']
for home_team in teams:
    for away_team in teams:
````
    
What should the next line be to avoid both variables being printed with the same value?
- while home_team != away_team:
- for home_team == away_team:
- away_team = home_team
- if home_team != away_team: [CORRECT]

### Common Errors
The interpreter will refuse to iterate over a single element. This can be mitigated by:
1. Using range()
2. Make the loop iterate over a list with the single element

Since strings are iterable, above solution may be needed. 

for loops are best when you want to iterate over a known sequence of elements but when you want to operate while a certain condition is true, while loops are the best choice.

### Loops Cheat Sheet
#### Loops Cheat Sheet
Check out below for a run down of the syntax for while loops and for loops.
#### While Loops
A while loop executes the body of the loop while the condition remains True.

Syntax:
````Python
while condition:
    body
````
Things to watch out for!
- Failure to initialize variables. Make sure all the variables used in the loop’s condition  are initialized before the loop.
- Unintended infinite loops. Make sure that the body of the loop modifies the variables used in the condition, so that the loop will eventually end for all possible values of the variables.

 Typical use:
While loops are mostly used when there’s an unknown number of operations to be performed, and a condition needs to be checked at each iteration.

#### For Loops
A for loop iterates over a sequence of elements, executing the body of the loop for each element in the sequence.

Syntax:
````Python
for variable in sequence:
    body
````
The range() function:
range() generates a sequence of integer numbers. It can take one, two, or three parameters:
- range(n): 0, 1, 2, ... n-1
- range(x,y): x, x+1, x+2, ... y-1
- range(p,q,r): p, p+r, p+2r, p+3r, ... q-1 (if it's a valid increment)

#### Common pitfalls:
- Forgetting that the upper limit of a range() isn’t included.
- Iterating over non-sequences. Integer numbers aren’t iterable. Strings are iterable letter by letter, but that might not be what you want.

Typical use:
For loops are mostly used when there's a pre-defined sequence or range of numbers to iterate.

#### Break & Continue
You can interrupt both while and for loops using the break keyword. We normally do this to interrupt a cycle due to a separate condition.

You can use the continue keyword to skip the current iteration and continue with the next one. This is typically used to jump ahead when some of the elements of the sequence aren’t relevant.

If you want to learn more, check out this [wiki page on for loops](https://wiki.python.org/moin/ForLoop).

## Recursion
### What is recursion?
**Recursion** is the repeated application of the same procedure to a smaller problem. It tackles complex problems by reducing the problem to a simpler one by a function call itself until it reaches the **base case**.

In Python, a recursive function can be called up to 1,000 times.

---


## Credit
* [Coursera - Python Crash Course Week 3](https://www.coursera.org/learn/python-crash-course/home/week/3)
