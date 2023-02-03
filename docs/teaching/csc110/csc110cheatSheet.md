---
layout: default
title: CSC110cheatSheet
parent: CSC110
grand_parent: Teaching
nav_order: 4
#permalink: /docs/teaching/csc110/
---


# Cheat Sheet Info


## Links

  * [https://www.pythoncheatsheet.org/](https://www.pythoncheatsheet.org/)
  * [https://quickref.me/python](https://quickref.me/python)
  * [https://perso.limsi.fr/pointal/_media/python:cours:mementopython3-english.pdf](https://perso.limsi.fr/pointal/_media/python:cours:mementopython3-english.pdf)
  * [Python Expressions](https://www.scaler.com/topics/expression-in-python/)

## Look-Ahead Cheatsheet

The following are SUPER SHORT looks at subjects we'll see  throughout the course

Subjects:

  * Variables
  * Expressions
  * Strings
  * Consitionals
  * File I/O
  * Loops
  * Lists

The code snippets are not complete programs so assume the code is correct (necessary declarations were made)

### Variables

Values can be saved for future use using valid identifiers. A valid identifier has the following rules:

  * it is NOT a [reserved word](https://docs.python.org/3/reference/lexical_analysis.html#keywords)
  * starts with a letter or underscore
  * is composed of only letters,numbers and underscores
     * it cannot contain spaces

Examples of using variables:
```python
num = 5 # type is integer
num2 = 3.1416 # type is a float
is_on = True # type is boolean
is_on = False # type is boolean
st = "this is a string" # type is String
```

Variables can be reused and overwritten by reassigning a value.

### Expressions

An expression is a combination ov values, variables and operators that can be resolved to a value.

Example: Arithmetic expressions (results in a number)
```python
x = 2 # type is integer
y = 8 # another integer
z = x + y # the expression 'x+y' is resolved to a 10 and assigned to z
z = z*3 # z is resolved to 10 and multiplied by 3 to reassign a 30 to z
r = z/6 # z is divided by 6, resulting in float 5.0, and assigned to r
```

Example: Logic expressions (results in a boolean)
```python
is_on = True or False # type is boolean and result is True
is_on = True and False # type is boolean and result is False
is_on = not False # type is boolean and result is True
is_on = not is_on # type is boolean and result is False
is_on = 2 < 8 # (smaller than) type is boolean and result is True
is_on = 2 <= 8 # (smaller or equal than) type is boolean and result is True
is_on = 2 == 8 # (equals) type is boolean and result is False
is_on = 2 != 8 # (different) type is boolean and result is True
is_on = 2 >= 8 # (greater or equal than) type is boolean and result is False
is_on = 2 > 8 # (greater) type is boolean and result is False
is_on = "og" in "frog" # (contained) type is boolean and result is True
```

Example: Fancy operators
```python
x = 2**3 # (power operator) x has 2 to the 3 or 8; type is integer
x = 10//4 # (integer division) x has a 2 (2.5 round down); type is integer
x = 10//4.0 # (integer division) x has a 2.0 (2.5 round down); type is float
x = 10.0//4 # (integer division) x has a 2.0 (2.5 round down); type is float
x = 10.0//4.0 # (integer division) x has a 2.0 (2.5 round down); type is float
# Below: (modulo operator) y has a 4, leftover of 8 fitting 2 times in 20
#   type is integer
y = 20%8 
# Below: y has a 0; there is nothing leftover
#   after fitting 5 exactly 4 times in 20
y = 20%5 
```


### Strings

Strings are groupings of characters. They are complex objects with immutable values plus methods.

You can declare (inside single or double quotes) and overwrite strings:
```python
st = "" # this is an empty string
st = "contents"
st = "overwritte contents"
```

You can concatenate strings wit the \+ operator (concatenate if surrounded by strings)
```python
st = "" # this is an empty string
st = st + "hi" # st now contains "hi"
st2 = " there"
st = st + st2 # st now contains "hi there"
```

Each string object has access to [string methods](https://www.w3schools.com/python/python_ref_string.asp). 

To use a method one employs the **dot operator for objects**: 

The dot operator means "look inside this object and employ the next thing I mention"

Examples:

```python
st = "three word phrase" # this is an empty string
st2 = st.capitalize() # st2 contains "Three word phrase"
num_hr = st.count("hr") # num_hr has a 2 (times "hr" is in "three word phrase")
# Below, ind has a 6, the index where substring "wo" is in the string
ind = st.find("wo")
# ... and many more
```


### Conditionals

A conditional is a structure that allows execution flow to take different paths depending on the truth value (`True` or `False`) of a condition.

A condition is any *python expression* whose answer is not a number but a truth value (`True` or `False`).

The following are examples of expressions:
```python
# below, out will contain a value of True if 
#   the value in x is smaller than the value of y
out = x < y 
# below, out will contain a value of True if 
#   the value in st is a substring of "blah blah"
out = st in "blah blah" 
# below, out will contain a value of True if 
#   the value in i is equal to 0
out = i == 0 
```

A conditional structure uses a condition to direct execution flow

#### If: The lone conditional

The `if` statement can indicate code that can be skipped

The following example will print `output 1` if the condition is `True` and skip the body of the if statement (the indented code under the `if`) if `False`
```python
if x < y:
  print("output 1")
```

#### If..If: Sequence of conditionals

Multiple possible skips in a sequence

The following example will print `output 1` if the condition `x<y` is `True` and skip the body of the **first** if statement if `False`; Then, independently, it will print `output 2` if the condition `i == 0` is `True` and skip the body of the **second** if statement if `False`
```python
if x < y:
  print("output 1")
if i == 10:
  print("output 2")  
```

#### If-Else: Alternative paths

Only one of two alternative paths can be executed:

In the following example, `output 1` will be printed if the condition `x<y` is `True` and `output 2` if the condition is `False`
```python
if x < y:
  print("output 1")
else:
  print("output 2")  
```
Note that the `else` has no condition.

#### If-Elif... and If-Elif...Else: Alternative paths (more than 2)

Only one of many alternative paths can be executed:

In the following example, `output 1` will be printed if the condition `x == 1` is `True`; If previous conditions are `False` and condition `x == 2` is `True`, `output 2` is printed;  If previous conditions are `False` and condition `x == 3` is `True`, `output 3` is printed;
```python
if x == 1:
  print("output 1")
elif x == 2:
  print("output 2")
elif x == 3:
  print("output 3")   
```
This structure can be combined with an `else` to force one of the paths to be executed:
```python
if x == 1:
  print("output 1")
elif x == 2:
  print("output 2")
elif x == 3:
  print("output 3")
else:
  print("output 4") 
```
Above, one of the four printouts MUST be printed. Also note that the `else` has no condition!

### File IO

In addition to the memory used by a program during its execution, we can use long term memory by reading and writing in files. This is different than printing to console and exact, character-by-character writing and reading is necessary. 

First, one must open a file and use a file pointer to "hold a reference to it".
One must indicate the **mode** in which we wish to open the file. this is indicated using a string of flags in the indicated location:


```python
f = open("filename.txt", "<flags go here>")
```

| Flags | What they do                                                                                                                                                                                                                               |
|-------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| r     | Opens a file for reading only. The file pointer is placed at the beginning of the file. This is the default mode.                                                                                                                          |
| rb    | Opens a file for reading only in binary format. The file pointer is placed at the beginning of the file. This is the default mode.                                                                                                         |
| r+    | Opens a file for both reading and writing. The file pointer placed at the beginning of the file.                                                                                                                                           |
| rb+   | Opens a file for both reading and writing in binary format. The file pointer placed at the beginning of the file.                                                                                                                          |
| w     | Opens a file for writing only. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.                                                                                                         |
| wb    | Opens a file for writing only in binary format. Overwrites the file if the file exists. If the file does not exist, creates a new file for writing.                                                                                        |
| w+    | Opens a file for both writing and reading. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.                                                                        |
| wb+   | Opens a file for both writing and reading in binary format. Overwrites the existing file if the file exists. If the file does not exist, creates a new file for reading and writing.                                                       |
| a     | Opens a file for appending. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.                                         |
| ab    | Opens a file for appending in binary format. The file pointer is at the end of the file if the file exists. That is, the file is in the append mode. If the file does not exist, it creates a new file for writing.                        |
| a+    | Opens a file for both appending and reading. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing.                  |
| ab+   | Opens a file for both appending and reading in binary format. The file pointer is at the end of the file if the file exists. The file opens in the append mode. If the file does not exist, it creates a new file for reading and writing. |

[This](https://www.tutorialspoint.com/python/python_files_io.htm) has a succinct explanation.

#### Reading from the file

We can read from the file pointer. We can do this character by character or line by line:

Example 1 (all at once)

```python
f = open("filename.txt", "r")
st = f.read() 
# st now contains all of the ASCII characters inside 
# the file called filename.txt
```

Imagine our file has the following inside:

```text
line 1
line 2
line 3

```
Technically, this can be represented by a single series of characters:
`line 1\nline 2\nline 3\n`

Although, when visualizing them, the new lines (`\n`) are not visible, instead, the display just continues showing the text in a new line.

Example 1 (one line at a time)

```python
f = open("filename.txt", "r")
st = f.readline() # st now contains "line1\n"
st = f.readline() # st now contains "line2\n"
```

### To Be Continued