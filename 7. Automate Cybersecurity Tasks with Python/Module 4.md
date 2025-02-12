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
