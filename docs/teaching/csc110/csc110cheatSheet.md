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

## Look-Ahead Cheat sheet

The following are SUPER SHORT looks at subjects we'll see  throughout the course

Subjects:

  * [Variables](#variables)
  * [Expressions](#expressions)
  * [Strings](#strings)
  * [Conditionals](#conditionals)
  * [File IO](#file-io)
  * [Loops](#loops)
  * [Lists](#lists)

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
st = "three word phrase" 
st2 = st.capitalize() # st2 contains "Three word phrase"
num_hr = st.count("hr") # num_hr has a 2 (times "hr" is in "three word phrase")
# Below, ind has a 6, the index where substring "wo" is in the string
ind = st.find("wo")
# ... and many more
```

#### Slicing strings

One can slice a string by indicating a sliced access with the notation:

`<string name>[<start> : <stop> : <step>]`

With:

  * `<stop>` is the ending value but it is excluded! (not counting that value)
  * `<start>` and `<step` are optional. 


```python
st = "three word phrase" # this is an empty string
st2 = st[0:8]
print(st2) # prints "three wo"
```
Note the slice excludes the end index!

If you specify a different `<start>`, it will begin in the indicated spot:
```python
st = "three word phrase" # this is an empty string
st2 = st[2:8]
print(st2) # prints "ree wo"
```

If you indicate a `<step>` it will skip that many characters until it reaches (but does not include) the `<stop>` index:
```python
st = "three word phrase" # this is an empty string
st2 = st[4:15:3]
print(st2) # prints "eo r"
```
Note this starts at index `4`, then goes to `7` (skip of `3`), then `10`, then `13`, and since `16` is after `15`, it stops at index `13`.


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

#### The with notation

instead of opening a file, working with it, and closing it later, one can encapsulate the work done on a file (or a set of files) inside a with block. The benefit is that it is nice and localized, and that it closes the file(s) for you at the end.

The notation is:

```python
# using with statement
with open('myfile.txt', 'w') as file:
    file.write('hello world !')
```

The example shown above opens the file `myfile.txt` for writing, writes `hello world !` into it, and then automatically closes it for you.

You can do multiple things inside a with block but it is recommended to keep it short and precise. 

### Loops

A loop is a block of inside of which one can add code that will be run over and over again.

The two basic types are the `while` loop and the `for` loop.

#### while

The `while` is a loop that has content that is run until a condition resolves to False. These are good for repeated execution "until" something happens or something stops happening. 

An excellent example is a menu:

```python
do_it_again = True # the condition is initialized
iteration = 0
# the while loop statement
while do_it_again:
  print("loop count: ",iteration+=1)
  reply = input("continue menu (y/n)?")
  if (reply == "n"):
    print("ending loop")
    do_it_again = False
  else:
    print("continuing loop")

```
The output of this when replying first `y`, then `y`, and then `n` is:

```
loop count:  1
continue menu (y/n)?y
continuing loop
loop count:  2
continue menu (y/n)?y
continuing loop
loop count:  3
continue menu (y/n)?n
ending loop
```

#### range

Before we discuss the `for` loop I'd like to discuss the `range` function. this function returns a sequence of numbers. These can be used to define the number of iterations in a loop.

The notation is `range(<start>, <stop>, <step>)` where 

  * `<stop>` is the ending value but it is excluded! (not counting that value)
  * `<start>` and `<step` are optional. 

We'll see an example use below.


#### for

The `for` loop is a loop that has content that is run for a set sequence of iterations. The iterations can be defined in many ways (some discussed above). These are good for repeated execution for each element in a set or for a known number of iterations. 


An excellent example is the scan of all the characters in a String:

```python
my_str = "abcdefg"
for i in range(4):
  print(my_str[i])

```

Here, the variable `i` will take the following sequence of values: `0,1,2,3`, one each time the body of the loop is executed. If not specified, the start value is always 0.

The result of running this block of code is:

```
a
b
c
d

```
If we were to change the range, this would affect the loop:
```python
my_str = "abcdefg"
for i in range(6):
  print(my_str[i])

```

produces:

```
a
b
c
d
e
f

```
Note that, since the last valid index of `my_str` is `7`, the variable `i` should not take any value after `7`.

Specifying the start allows a start different than 0:
```python
my_str = "abcdefg"
for i in range(2,6):
  print(my_str[i])

```

produces:

```
c
d
e
f

```

The step indicates by how much to change (increase/decrease) each number in the sequence. For example, 
```python
my_str = "abcdefg"
for i in range(1,7,2):
  print(my_str[i])

```

produces:

```
b
d
f

```
because the rane sequence will be `1,3,5` (remember, the `<stop>` vallue is excluded); That means the indices printed are: `my_str[1]` or `b`, `my_str[3]` or `d`, and `my_str[5]` or `f`.

#### for each member of a container

One can use a `for` loop for each element in a set, list, string, and other containers.

Example:

```python
my_str = "abcdefg"
for c in my_str:
  print(c)

```

Note the slightly different notation!

This produces:

```
a
b
c
d
e
f
g

```


### Lists

A list is a group of elements stored inside a container. This list can have repeated elements (of different types), order matters, it is mutable (you can modify it in place), and it has member methods.

The notation to construct it in one go is:

```python
my_list = [3, 5, 7, 9]
```
One can combine elements of different types!
```python
my_list = [3, "hi", True, 2.4142]
```

You can even put lists inside lists!
```python
my_list = ["element 1", [3, "hi", True, 2.4142], "element 3"]
```
The example above has three elements in the top-level list, and it has four elements in the nested list that is the second element of the top-level list.


One can access list elements in the same way we accessed characters in a string, using their index:


```python
my_list = [3, 5, 7, 9]
elem2 = my_list[2]
print(elem2) # prints a 7
```

if we access a list element inside another list, one can access elements inside the nested list with a second index specification, for example:

```python
my_list = ["element 1", [3, "hi", True, 2.4142], "element 3"]
elem1 = my_list[1]
print(elem1) # prints [3, "hi", True, 2.4142]
elem1_3 = elem1[3]
print(elem1_3) # prints 2.4142
# you can access the inner element directly:
elem1_3 = my_list[1][3]
print(elem1_3) # prints 2.4142
```

check it out [here](https://pythontutor.com/visualize.html#code=my_list%20%3D%20%5B%22element%201%22,%20%5B3,%20%22hi%22,%20True,%202.4142%5D,%20%22element%203%22%5D%0Aelem1%20%3D%20my_list%5B1%5D%0Aprint%28elem1%29%20%23%20prints%20%5B3,%20%22hi%22,%20True,%202.4142%5D%0Aelem1_3%20%3D%20elem1%5B3%5D%0Aprint%28elem1_3%29%20%23%20prints%202.4142%0A%23%20you%20can%20access%20the%20inner%20element%20directly%3A%0Aelem1_3%20%3D%20my_list%5B1%5D%5B3%5D%0Aprint%28elem1_3%29%20%23%20prints%202.4142&cumulative=false&heapPrimitives=nevernest&mode=edit&origin=opt-frontend.js&py=3&rawInputLstJSON=%5B%5D&textReferences=false)

#### Slicing lists

One can slice a list to make copies of sub-parts of a list. For example:

```python
my_list = [10,11,12,13,14,15,16]
list_b = my_list[0:3]
print(list_b) # prints [10, 11, 12]
```

You can choose not to specify the start or add a step, same as with string slicing.

#### List methods

##### TODO