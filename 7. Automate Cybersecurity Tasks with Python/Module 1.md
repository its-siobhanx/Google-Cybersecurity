# Python

### Comments in Python
Useful for explaining what a section of code does and helping to make code more readable etc
* Use hashtag for a comment #

### Print function
Useful for displaying information to the screen
* Use print("")

### Data types
* **String:** Characters in a string may include letters, numbers, symbols, and spaces. These characters must be placed within quotation marks. Can use either double or single quoatation marks but ensure to keep consistency whatever you choose.
* **List:** Lists elements can be of any data type, such as strings, integers, Booleans, or even other lists. The elements of a list are placed within square brackets, and each element is separated by a comma.
* **Integer:** integer data is data consisting of a number that does not include a decimal point.
* **Float:** Float data is data consisting of a number with a decimal point.
* **Boolean:** Boolean data is data that can only be one of two values: either True or False.
* **Tuple:** Tuple data is a data structure that consists of a collection of data that cannot be changed. Like lists, tuples can contain elements of varying data types. A difference between tuple data and list data is that it is possible to change the elements in a list, but it is not possible to change the elements in a tuple
* **Dictionary:** Dictionary data is data that consists of one or more key-value pairs. Each key is mapped to a value. A colon (:) is placed between the key and value. Commas separate key-value pairs from other key-value pairs, and the dictionary is placed within curly brackets ({}).

You can use type() to get the variable type.

## Variables 
In a programming language, a variable is a container that stores data. It's a named storage location in a computer's memory that can hold a value. It stores the data in a particular data type, such as integer, string, or Boolean. The value that is stored in a variable can change. 

* **EXAMPLE** username = "Siobhan"
* Give the variable a name and use the = sign to give a value.
* Can reassign a variable value later on in the code
* Can assign one variable to another variable
* Use only letters, numbers, and underscores in variable names. Valid examples: date_3, username, interval2
* Remember that variable names in Python are case-sensitive.
* Don't use Python’s built-in keywords or functions for variable names. 

## Conditionals

| Operator | Description              |
|----------|--------------------------|
| `>`      | greater than             |
| `<`      | less than                |
| `>=`     | greater than or equal to |
| `<=`     | less than or equal to    |
| `==`     | equal to                 |
| `!=`     | not equal to             |

### if statements
The keyword if starts a conditional statement. It’s a necessary component of any conditional statement.

* The first line of this code is the header. In the header of an if statement, the keyword if is followed by the condition. The condition can be placed in brackets:
* You must always place a colon (:) at the end of the header. Without this syntax, the code will produce an error.
* After the header of an if statement comes the body of the if statement. This tells Python what action or actions to perform when the condition evaluates to True.
* Must have the body idented
* The keyword else precedes a code section that only evaluates when all conditions that precede it within the conditional statement evaluate to False. Requires : too
* In some cases, you might have multiple alternative actions that depend on new conditions. In that case, you can use elif. The elif keyword precedes a condition that is only evaluated when previous conditions evaluate to False. Unlike with else, there can be multiple elif statements following if.
* Can use logical operators along with if statements: and, or not
* And must have both conditions evaluate to true
* Or requires only one of the conditions on either side of the operator to evaluate to True.
* Not negates a given condition so that it evaluates to False if the condition is True and to True if it is False.

## Loops
An iterative statement is code that repeatedly executes a set of instructions. Depending on the criteria, iterative statements execute zero or more times. 

### for loops
If you need to iterate through a specified sequence, you should use a for loop. 

* The first line of this code is the loop header. In the loop header, the keyword for signals the beginning of a for loop.
* Directly after for, the loop variable appears. The loop variable is a variable that is used to control the iterations of a loop. In for loops, the loop variable is part of the header. Typically i is used.
* can use in operator with it
* In the body, you indicate what the loop should do with each iteration.
* The start point is inclusive, meaning that 0 will be included in the sequence of numbers, but the stop point is exclusive, meaning that 5 will be excluded from the sequence. It will conclude one integer before the stopping point.
* for i in range(5):  # Iterates from 0 to 4
    print(i)

 ### while loops
 If you want a loop to iterate based on a condition, you should use a while loop. As long as the condition is True, the loop continues, but when it evaluates to False, the while loop exits. 

 * In this while loop, the loop header is the line while i < 5:
 * Unlike with for loops, the value of a loop variable used to control the iterations is not assigned within the loop header in a while loop. Instead, it is assigned outside of the loop. In this example, i is assigned a starting value of 1 in a line preceding the loop.
 * The keyword while signals the beginning of a while loop. After this, the loop header indicates the condition that determines when the loop terminates. This condition uses the same comparison operators as conditional statements. Like in a for loop, the header of a while loop must end with a colon (:).
 * The body of a while loop indicates the actions to take with each iteration.
 * Conditions in while loops can also depend on other data types, including comparisons of Boolean data. In Boolean data comparisons, your loop condition can check whether a loop variable equals a value like True or False. The loop iterates an indeterminate number of times until the Boolean condition is no longer True.

### Managing loops
You can use the break and continue keywords to further control your loop iterations. Both are incorporated into a conditional statement within the body of the loop. They can be inserted to execute when the condition in an if statement is True. The break keyword is used to break out of a loop. The continue keyword is used to skip an iteration and continue with the next one. 


