In this module you'll dive into more advanced ways to manipulate strings using indexing, slicing, and advanced formatting. You'll also explore the more advanced data types: lists, tuples, and dictionaries. You'll learn to store, reference, and manipulate data in these structures, as well as combine them to store complex data structures.
----
Objetivos de aprendizaje
- Manipulate strings using indexing, slicing, and formatting
- Use lists and tuples to store, reference, and manipulate data
- Leverage dictionaries to store more complex data, reference data by keys, and manipulate data stored
- Combine these data types to construct complex data structures


STRINGS

## BASIC STRUCTURES INTRODUCTION

Welcome back and congratulations on getting this far. I sure I'm glad we didn't lose you and all those loops we covered in the last module. You're doing great and making tons of progress. In earlier videos, we covered the basic elements of Python syntax. We talked about how to define functions, how to make your computer act differently based on conditionals, and how to make it perform operations repeatedly using while, and for loops, and recursion. Now that we have the basics of syntax out of the way, we can start growing our Python knowledge which will let us do more and more interesting operations. Remember, one of our main goals in this course is to help you learn to write short Python scripts that automate actions, you've made big steps towards getting there. In the upcoming videos, we're going to learn a bunch of new super useful skills to add to your programming toolbox. We'll check out some datatypes provided by the Python language to help us solve common problems with our scripts. In particular, will do a deep dive into strings, lists, and dictionaries. Heads-up, while we've used strings in our scripts already, we barely scratched the surface of all the things we can do with them in Python. We also ran into a few lists in some examples but there's a lot more of them we haven't seen yet. Dictionaries are a whole new datatype for us to dig our teeth into. These are all data types or data structures that are super flexible. We're going to use them to write all kinds of scripts in Python. So it's a good idea to spend some time getting to know them, and learning when to use them, and how to make the most out of them. We've got a lot of new and exciting concepts to discover. So let's get right to it.
        
   ## WHAT IS A STRING?

   By now, we've used strings in a lot of examples, but we haven't spent time looking at them in detail yet. Before we dive into the nitty-gritty though, let's go over what we've seen so far and add a few more points. First, a quick refresher. A string is a data type in Python that's used to represent a piece of text. It's written between quotes, either double quotes or single quotes, your choice. It doesn't matter which type of quotes you use as long as they match. If we mix up double and single quotes, Python won't be too happy, and it'll return a syntax error, telling us it couldn't find the end of the string. A string can be as short as zero characters, usually called an empty string or really long. We also learned that we can use strings to build longer strings using the plus sign and action called concatenating. A less common operation is to multiply the string by a number, which multiplies the content of the string that many times like this. If we want to know how long a string is, we can use the len function which we saw in earlier videos. The len function tells us the number of characters contained in the string. We can use strings to represent a lot of different things. They can hold a username, the name of a machine, an email address, the name of a file, and any other text. A lot of the data that we'll interact with will be stored in strings, so it's important to know how to use them. There are tons of things we could do with strings in our scripts. For example, we can check if files are named a certain way by looking at the filename and seeing if they match our criteria, or we can create a list of emails by checking out the users of our system and concatenating our domain. I recently wrote a script that worked with a bunch of files and took different actions according to the name of each file. So the file ended in a certain extension say, .TXT , then my script would print it. If the file had a certain string and the name, say, test, then my script would ignore it and move on to the next thing and so on. The contents of a text file are also strings. A few months ago, I had to change the default values for a bunch of configuration options from true to false. So I wrote a function that would find the string true in a file and replace it with false. You can probably think of more examples where your code needs to handle strings, but to use strings effectively, we need to know what options are available to us in Python. In the next few videos, we'll cover some of the operations we can perform over strings, including how to access parts of them and modify them.
````Python
Modify the double_word function so that it returns the same word repeated twice, followed by the length of the new doubled word. 
For example, double_word("hello") should return hellohello10.

EXERCISE
def double_word(word):
    return

print(double_word("hello")) # Should return hellohello10
print(double_word("abc"))   # Should return abcabc6
print(double_word(""))      # Should return 0



SOLUTION

def double_word(word):
    word = word *2
    return word + str(len(word))

print(double_word("hello")) # Should return hellohello10
print(double_word("abc"))   # Should return abcabc6
print(double_word(""))      # Should return 0
````

## THE PARTS OF A STRING
0:00
When we first came across the for loop, we called out that we can iterate over a string character by character. But what if we want to access just a specific character or characters? We might want to do this, for example, if we have a text that's too long to display and we want to show just a portion of it. Or if we want to make an acronym by taking the first letter of each word in a phrase. We can do that through an operation called string indexing. This operation lets us access the character in a given position or index using square brackets and the number of the position we want. Like this. This might seem confusing at first, like Python is acting up. We're asking for the first character, and it's giving us the second. What gives Python? Well, what's happening here is that Python starts counting indexes from 0 not 1. Just like it does with the range function. So if we want the first character, we need to access the one at index 0. Knowing that indexes start at 0, which one do you think will be the last index in the string? It'll always be one less than the length of the string. In this case, our string has six characters, so the last index will be 5. Let's try it out.
1:28
We see that the character in position five is the last character of the string. And if we try to access index six, we get an index error telling us that it's out of range. We can only go up to length minus 1. What if you want to print the last character of a string but you don't know how long it is? You can do that using negative indexes. Let's see that in a different example.
2:02
In this example, we don't know the length of the string, but it doesn't matter. Using negative indexes lets us access the positions in the string starting from the last. Nice, right?
2:14
On top of accessing individual characters, we can also access a slice of a string. A slice is the portion of a string that can contain more than one character, also sometimes called a substring. We do that by creating a range using a colon as a separator. Let's see an example of this.
2:38
The range we use when accessing a slice of a string works just like the one created by the range function. It includes the first number, but goes up to one less than the last number. In this case, we start with indexed one, the second letter of the string, and go up to index three, the fourth letter of the string. Another option for the range is to include only one of the two indexes. In that case, it's assumed that the other index is either 0 for the first value or the length of the string for the second value. Check this out.
3:24
Accessing the slice from nothing to 4 takes the first four characters of the string, indexes 0 to 3. Accessing the slice from 4 to nothing takes everything from index four onward. All of this indexing might seem confusing at first. Don't worry, we all took time to wrap our heads around it. Just like all the challenges we've come across so far, the key is to keep practicing until you master it. And there are a bunch of exercises ahead to help you with that. Now that we know how to select, slice, and access the parts of the string we want, we're going to learn how to modify them. That's coming up next.

````Python
EXERCISE
Want to give it a go yourself? Be my guest! Modify the first_and_last function so that it returns True if the first letter of the string is the same as the last letter of the string, False if they’re different. Remember that you can access characters using message[0] or message[-1].
Be careful how you handle the empty string, which should return True since nothing is equal to nothing.

def first_and_last(message):
        return False

print(first_and_last("else"))
print(first_and_last("tree"))
print(first_and_last(""))

SOLUTION 
def first_and_last(message):
    if not message:
        return True
    return message[0] == message[-1]

        #As noted in the comments this can be pushed a bit more into a single line:
def first_and_last(message):
    return not message or message[0] == message[-1]

        #Another type of solution
def first_and_last(message):
    if not message:
       return True
    elif (message[0] == message[-1]):
        return True
    elif (message[0] != message[-1]):
          return False
````

## STRING INDEXING AND SLICING
String indexing allows you to access individual characters in a string. You can do this by using square brackets and the location, or index, of the character you want to access. It's important to remember that Python starts indexes at 0. So to access the first character in a string, you would use the index [0]. If you try to access an index that’s larger than the length of your string, you’ll get an IndexError. This is because you’re trying to access something that doesn't exist! You can also access indexes from the end of the string going towards the start of the string by using negative values. The index [-1] would access the last character of the string, and the index [-2] would access the second-to-last character.

You can also access a portion of a string, called a slice or a substring. This allows you to access multiple characters of a string. You can do this by creating a range, using a colon as a separator between the start and end of the range, like [2:5]. 

This range is similar to the range() function we saw previously. It includes the first number, but goes to one less than the last number. For example:

>>> fruit = "Mangosteen"
>>> fruit[1:4]
'ang'

The slice includes the character at index 1, and excludes the character at index 4. You can also easily reference a substring at the start or end of the string by only specifying one end of the range. For example, only giving the end of the range:

>>> fruit[:5]
'Mango'

This gave us the characters from the start of the string through index 4, excluding index 5. On the other hand this example gives is the characters including index 5, through the end of the string:

>>> fruit[5:]
'steen'

You might have noticed that if you put both of those results together, you get the original string back!

>>> fruit[:5] + fruit[5:]
'Mangosteen'

Cool!


## BASIC STRING METHODS
In Python, strings are immutable. This means that they can't be modified. So if we wanted to fix a typo in a string, we can't simply modify the wrong character. We would have to create a new string with the typo corrected. We can also assign a new value to the variable holding our string.

If we aren't sure what the index of our typo is, we can use the string method index to locate it and return the index. Let's imagine we have the string "lions tigers and bears" in the variable animals. We can locate the index that contains the letter g using animals.index("g"), which will return the index; in this case 8. We can also use substrings to locate the index where the substring begins. animals.index("bears") would return 17, since that’s the start of the substring. If there’s more than one match for a substring, the index method will return the first match. If we try to locate a substring that doesn't exist in the string, we’ll receive a ValueError explaining that the substring was not found.

We can avoid a ValueError by first checking if the substring exists in the string. This can be done using the in keyword. We saw this keyword earlier when we covered for loops. In this case, it's a conditional that will be either True or False. If the substring is found in the string, it will be True. If the substring is not found in the string, it will be False. Using our previous variable animals, we can do "horses" in animals to check if the substring "horses" is found in our variable. In this case, it would evaluate to False, since horses aren’t included in our example string. If we did "tigers" in animals, we'd get True, since this substring is contained in our string.


## ADVANCE STRING METHODS

We've covered a bunch of String class methods already, so let's keep building on those and run down some more advanced methods.

The string method **lower** will return the string with all characters changed to lowercase. The inverse of this is the **upper** method, which will return the string all in uppercase. Just like with previous methods, we call these on a string using dot notation, like **"this is a string".upper().** This would return the string **"THIS IS A STRING"**. This can be super handy when checking user input, since someone might type in all lowercase, all uppercase, or even a mixture of cases.

You can use the **strip** method to remove surrounding whitespace from a string. Whitespace includes spaces, tabs, and newline characters. You can also use the methods  **lstrip** and **rstrip** to remove whitespace only from the left or the right side of the string, respectively.

The method **count** can be used to return the number of times a substring appears in a string. This can be handy for finding out how many characters appear in a string, or counting the number of times a certain word appears in a sentence or paragraph.

If you wanted to check if a string ends with a given substring, you can use the method **endswith.** This will return True if the substring is found at the end of the string, and False if not.

The **isnumeric** method can check if a string is composed of only numbers. If the string contains only numbers, this method will return True. We can use this to check if a string contains numbers before passing the string to the **int()** function to convert it to an integer, avoiding an error. Useful!

We took a look at string concatenation using the plus sign, earlier. We can also use the **join** method to concatenate strings. This method is called on a string that will be used to join a list of strings. The method takes a list of strings to be joined as a parameter, and returns a new string composed of each of the strings from our list joined using the initial string. For example, **" ".join(["This","is","a","sentence"])** would return the string **"This is a sentence".**

The inverse of the join method is the **split** method. This allows us to split a string into a list of strings. By default, it splits by any whitespace characters. You can also split by any other characters by passing a parameter.

````Python
the phrase received, in upper case. For example: "Universal Serial Bus" should return "USB"; "local area network" should return "LAN”.
def initials(phrase):
    words = phrase.split()
    result = ""
    for word in words:
        result += word[0].upper()
    return result

print(initials("Universal Serial Bus")) # Should be: USB
print(initials("local area network")) # Should be: LAN
print(initials("Operating system")) # Should be: OS
````

## FORMATTING STRINGS

You can use the format method on strings to concatenate and format strings in all kinds of powerful ways. To do this, create a string containing curly brackets, {}, as a placeholder, to be replaced. Then call the format method on the string using .format() and pass variables as parameters. The variables passed to the method will then be used to replace the curly bracket placeholders. This method automatically handles any conversion between data types for us. 

If the curly brackets are empty, they’ll be populated with the variables passed in the order in which they're passed. However, you can put certain expressions inside the curly brackets to do even more powerful string formatting operations. You can put the name of a variable into the curly brackets, then use the names in the parameters. This allows for more easily readable code, and for more flexibility with the order of variables.

You can also put a formatting expression inside the curly brackets, which lets you alter the way the string is formatted. For example, the formatting expression {:.2f} means that you’d format this as a float number, with two digits after the decimal dot. The colon acts as a separator from the field name, if you had specified one. You can also specify text alignment using the greater than operator: >. For example, the expression {:>3.2f} would align the text three spaces to the right, as well as specify a float number with two decimal places. String formatting can be very handy for outputting easy-to-read textual output.

## String Reference Guide

In Python, there are a lot of things you can do with strings. In this guide, you’ll find the most common string operations and string methods.

String operations
len(string) - Returns the length of the string

for character in string - Iterates over each character in the string

if substring in string - Checks whether the substring is part of the string

string[i] - Accesses the character at index i of the string, starting at zero

string[i:j] - Accesses the substring starting at index i, ending at index j minus 1. If i is omitted, its value defaults to 0. If j is omitted, the value will default to len(string).

String methods
string.lower() - Returns a copy of the string with all lowercase characters
string.upper() - Returns a copy of the string with all uppercase characters
string.lstrip() - Returns a copy of the string with the left-side whitespace removed
string.rstrip() - Returns a copy of the string with the right-side whitespace removed
string.strip() - Returns a copy of the string with both the left and right-side whitespace removed
string.count(substring) - Returns the number of times substring is present in the string
string.isnumeric() - Returns True if there are only numeric characters in the string. If not, returns False.
string.isalpha() - Returns True if there are only alphabetic characters in the string. If not, returns False.
string.split() - Returns a list of substrings that were separated by whitespace (whitespace can be a space, tab, or new line)
string.split(delimiter) - Returns a list of substrings that were separated by whitespace or a delimiter
string.replace(old, new) - Returns a new string where all occurrences of old have been replaced by new.
delimiter.join(list of strings) - Returns a new string with all the strings joined by the delimiter

[Check out the official documentation for  all available String methods](https://docs.python.org/3/library/stdtypes.html#string-methods)

.  
