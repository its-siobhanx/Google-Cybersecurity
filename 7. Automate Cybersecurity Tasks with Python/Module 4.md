# Open files

with open("update_log.txt", "r") as file:
This line consists of the with keyword, the open() function with its two parameters, and the as keyword followed by a variable name. You must place a colon (:) at the end of the line.

When you open a file using with open(), you must provide a variable that can store the file while you are within the with statement. You can do this through the keyword as followed by this variable name. The keyword as assigns a variable that references another object. The code with open("update_log.txt", "r") as file: assigns file to reference the output of the open() function within the indented code block that follows it.

The .read() method converts files into strings. This is necessary in order to use and display the contents of the file that was read.

## write files

To write to a file, you will need to open the file with "w" or "a" as the second argument of open(). 


You should use the "w" argument when you want to replace the contents of an existing file. When working with the existing file update_log.txt, the code with open("update_log.txt", "w") as file: opens it so that its contents can be replaced. 

Additionally, you can use the "w" argument to create a new file. For example, with open("update_log2.txt", "w") as file: creates and opens a new file called "update_log2.txt". 

You should use the "a" argument if you want to append new information to the end of an existing file rather than writing over it. The code with open("update_log.txt", "a") as file: opens "update_log.txt" so that new information can be appended to the end. Its existing information will not be deleted.

## Parsing
Parsing is the process of converting data into a more readable format. Data may need to become more readable in a couple of different ways. First, certain parts of your Python code may require modification into a specific format. By converting data into this format, you enable Python to process it in a specific way. Second, programmers need to read and interpret the results of their code, and parsing can also make the data more readable for them. Methods that can help you parse your data include .split() and .join().

### .split()
The .split() method converts a string into a list. It separates the string based on a specified character that's passed into .split() as an argument. If you do not pass an argument into .split(), it will separate the string every time it encounters a whitespace.#

The .split() method allows you to work with file content as a list after you've converted it to a string through the .read() method. This is useful in a variety of ways. For example, if you want to iterate through the file contents in a for loop, this can be easily done when it's converted into a list.

### .join()
If you need to convert a list into a string, there is also a method for that. The .join() method concatenates the elements of an iterable into a string. The syntax used with .join() is distinct from the syntax used with .split() and other methods that you've worked with, such as .index(). 

In methods like .split() or .index(), you append the method to the string or list that you're working with and then pass in other arguments. For example, the code usernames.index(2), appends the .index() method to the variable usernames, which contains a list. It passes in 2 as the argument to indicate which element to return.

However, with .join(), you must pass the list that you want to concatenate into a string in as an argument. You append .join() to a character that you want to separate each element with once they are joined into a string.

When working with files, it may also be necessary to convert its contents back into a string. For example, you may want to use the .write() method. The .write() method writes string data to a file. This means that if you have converted a file's contents into a list while working with it, you'll need to convert it back into a string before using .write(). You can use the .join() method for this.



