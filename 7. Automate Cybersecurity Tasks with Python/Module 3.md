# String Data

An index is a number assigned to every element in a sequence that indicates its position. With strings, this means each character in the string has its own index. Indices start at 0.

 For example, you might be working with this string containing a device ID: "h32rb17". The following table indicates the index for each character in this string:

| Index | Character |
|-------|-----------|
| 0     | h         |
| 1     | 3         |
| 2     | 2         |
| 3     | r         |
| 4     | b         |
| 5     | 1         |
| 6     | 7         |

Bracket notation refers to the indices placed in square brackets. You can use bracket notation to extract a part of a string. For example, the first character of the device ID might represent a certain characteristic of the device. If you want to extract it, you can use bracket notation for this:

"h32rb17"[0]

This device ID might also be stored within a variable called device_id. You can apply the same bracket notation to the variable:

device_id = "h32rb17"

device_id[0]

The str() and len() functions are useful for working with strings. You can also apply methods to strings, including the .upper(), .lower(), and .index() methods. A method is a function that belongs to a specific data type.

## List methods
List methods are functions that are specific to the list data type. These include the .insert() , .remove(), .append() and .index(). 

* The .insert() method adds an element in a specific position inside a list. It has two parameters. The first is the index where you will insert the new element, and the second is the element you want to insert.
* The .remove() method removes the first occurrence of a specific element in a list. It has only one parameter, the element you want to remove.
* The .append() method adds input to the end of a list. Its one parameter is the element you want to add to the end of the list.
* Similar to the .index() method used for strings, the .index() method used for lists finds the first occurrence of an element in a list and returns its index. It takes the element you're searching for as an input.

# Regular Expressions in Python

**Regular expressions (regex)** are patterns used to match character combinations in strings. They are powerful tools for text processing tasks like searching, replacing, or validating data (e.g., emails, phone numbers, etc.).

In Python, the `re` module provides functions to work with regular expressions.

## Key Concepts:
1. **Patterns**: Regular expressions are patterns composed of special characters (metacharacters) that define search criteria. For example, `\d` matches any digit, and `.` matches any character.

2. **Functions**: Common functions in the `re` module include:
   - **`re.match()`**: Checks if the pattern matches at the beginning of the string.
   - **`re.search()`**: Searches for the pattern anywhere in the string.
   - **`re.findall()`**: Returns a list of all matches.
   - **`re.sub()`**: Replaces occurrences of the pattern with a replacement string.

## Example:

```python
import re

# Example string
text = "My phone number is 555-1234."

# Search for a pattern (digits followed by a hyphen)
match = re.search(r"\d{3}-\d{4}", text)

if match:
    print("Phone number found:", match.group())  # Output: 555-1234

