# doc-python

# Python Reference for programming
This code reference is supposed to give an overview about the syntax and the elements of the Python programming language. 

# Table of Contents
- [Download and installation](#download-and-installation)
- [Data Types](#data-types)
  - [Sequence Types](#sequence-types)
  - [Mapping Types](#mapping-types)
  - [Set Types](#set-types)
- [Style](#style)
- [Method chaining](#method-chaining)
- [Documentation](#documentation)
- [Conditions](#conditions)
- [Loops](#loops)
- [Input and Output](#input-and-output)
- [Functions](#functions)
- [Classes](#classes)
- [Decorators](#decoratos)
- [Generators](#generators)
- [Exceptions](#exceptions)
- [Python typing](#python-typing)
- [Python dataclasses](#python-dataclasses)
- [Python packages](#python-packages)
- [Python virtual environments](#virtual-environments)
- [Pydantic](#pydantic)
- [Pytest](#pytest)
- [Singleton Patterns](#singleton-patterns)
- [Standard Library](#standard-library)
  - [Itertools](#itertools)
  - [Functools](#functools)
  - [Unittest](#unittest)
  - [Regular expressions](#regular-expressions)
  - [JSON](#json-package)
  - [Requests](#requests-package)
  - [Logging](#logging-1)
  - [Command line arguments](#command-line-arguments)
- [References](#references)


## Download and installation
We can download the build files for various operating systems on the official Python website [https://www.python.org/](https://www.python.org/).
## Data Types
### Check for Data Type
We can check for the data type of a variable as follows
```Python
isinstance(var_name, var_type)
```
Example
```Python
a = 2
if isinstance(a, int):
   print("Integer type")
else:
   print("No Integer type")
```
### None Type
The type None is used to represent a variable which is empty. In other words, the None type can be associated with a pointer which does not point to a specific address in memory.
```Python
var_none = None
```
Example
```Python
if isinstance(var_none, None):
   print("None type")
```
### Boolean Type
```Python
bool_true = True
bool_false = False
```
### Numeric Types
```Python
var_int = 1
var_float = 3.14159265359
```
### String Types
In Python strings are represented via quoted expressions
```Python
s_var1 = "This is a string"
s_var2 = "a, b, c"
```
Futhermore, there exist various methods to manipulate strings
```Python
len(s)		         # String length
list(s)		         # Create list of separate strings ['t', 'e', 'x', 't']

s1 + s2		         # Concatenate strings
(s + ' ') * 3	     # Repeat string with separator
s.upper()		     # Upper case
s.lower()		     # Lower case
s.capitalize()	     # Capitalize
s.title()		     # Capitalize each new word
s.split(sep = 'e')	 # Split string, Example: ['t', 'xt']
s.split(sep = ' ')	 # Split text into single words
s[::-1]		         # Reverse a string
s.strip('te')	     # Remove parts of a string, Example: 'xt'
s.replace('e', 'E')  # Replace parts of a string, Example: 'tExt'
s.replace('.', '')   # Remove punctuation in a string
''.join(['a', 'b'])  # Join list of characters into a string, Example: 'ab'
s.count('e')	     # Count characters in string, Example: 1
s.find('e')	         # Find sub string in given string, Example: 1
```

#### Case Conversion Methods

|Function      |Description                         |Syntax            |Example                     |Result         |
|--------------|------------------------------------|------------------|----------------------------|---------------|
|`upper()`     |Converts to uppercase               |`str.upper()`     |`"hello".upper()`           |`"HELLO"`      |
|`lower()`     |Converts to lowercase               |`str.lower()`     |`"HELLO".lower()`           |`"hello"`      |
|`capitalize()`|Capitalizes first letter            |`str.capitalize()`|`"hello world".capitalize()`|`"Hello world"`|
|`title()`     |Title case (each word capitalized)  |`str.title()`     |`"hello world".title()`     |`"Hello World"`|
|`swapcase()`  |Swaps case of all letters           |`str.swapcase()`  |`"Hello World".swapcase()`  |`"hELLO wORLD"`|
|`casefold()`  |Aggressive lowercase for comparisons|`str.casefold()`  |`"HELLO".casefold()`        |`"hello"`      |

#### Whitespace & Formatting Methods

|Function  |Description                        |Syntax                         |Example                  |Result        |
|----------|-----------------------------------|-------------------------------|-------------------------|--------------|
|`strip()` |Removes leading/trailing whitespace|`str.strip([chars])`           |`"  hello  ".strip()`    |`"hello"`     |
|`lstrip()`|Removes leading whitespace         |`str.lstrip([chars])`          |`"  hello  ".lstrip()`   |`"hello  "`   |
|`rstrip()`|Removes trailing whitespace        |`str.rstrip([chars])`          |`"  hello  ".rstrip()`   |`"  hello"`   |
|`center()`|Centers string in width            |`str.center(width, [fillchar])`|`"hello".center(10, '-')`|`"--hello---"`|
|`ljust()` |Left-justifies string              |`str.ljust(width, [fillchar])` |`"hello".ljust(10, '-')` |`"hello-----"`|
|`rjust()` |Right-justifies string             |`str.rjust(width, [fillchar])` |`"hello".rjust(10, '-')` |`"-----hello"`|
|`zfill()` |Pads with zeros on left            |`str.zfill(width)`             |`"42".zfill(5)`          |`"00042"`     |

#### Search & Find Methods

|Function  |Description                                    |Syntax                           |Example                        |Result|
|----------|-----------------------------------------------|---------------------------------|-------------------------------|------|
|`find()`  |Returns index of first occurrence              |`str.find(sub, [start], [end])`  |`"hello world".find("world")`  |`6`   |
|`rfind()` |Returns index of last occurrence               |`str.rfind(sub, [start], [end])` |`"hello hello".rfind("hello")` |`6`   |
|`index()` |Like find() but raises ValueError if not found |`str.index(sub, [start], [end])` |`"hello world".index("world")` |`6`   |
|`rindex()`|Like rfind() but raises ValueError if not found|`str.rindex(sub, [start], [end])`|`"hello hello".rindex("hello")`|`6`   |
|`count()` |Counts occurrences of substring                |`str.count(sub, [start], [end])` |`"hello hello".count("hello")` |`2`   |

#### Boolean Check Methods

|Function        |Description                                |Syntax                                  |Example                            |Result|
|----------------|-------------------------------------------|----------------------------------------|-----------------------------------|------|
|`startswith()`  |Checks if string starts with prefix        |`str.startswith(prefix, [start], [end])`|`"hello world".startswith("hello")`|`True`|
|`endswith()`    |Checks if string ends with suffix          |`str.endswith(suffix, [start], [end])`  |`"hello world".endswith("world")`  |`True`|
|`isalpha()`     |Checks if all characters are letters       |`str.isalpha()`                         |`"hello".isalpha()`                |`True`|
|`isdigit()`     |Checks if all characters are digits        |`str.isdigit()`                         |`"123".isdigit()`                  |`True`|
|`isalnum()`     |Checks if all characters are alphanumeric  |`str.isalnum()`                         |`"hello123".isalnum()`             |`True`|
|`isspace()`     |Checks if all characters are whitespace    |`str.isspace()`                         |`"   ".isspace()`                  |`True`|
|`islower()`     |Checks if all characters are lowercase     |`str.islower()`                         |`"hello".islower()`                |`True`|
|`isupper()`     |Checks if all characters are uppercase     |`str.isupper()`                         |`"HELLO".isupper()`                |`True`|
|`istitle()`     |Checks if string is title case             |`str.istitle()`                         |`"Hello World".istitle()`          |`True`|
|`isdecimal()`   |Checks if all characters are decimal       |`str.isdecimal()`                       |`"123".isdecimal()`                |`True`|
|`isnumeric()`   |Checks if all characters are numeric       |`str.isnumeric()`                       |`"123".isnumeric()`                |`True`|
|`isidentifier()`|Checks if string is valid Python identifier|`str.isidentifier()`                    |`"my_var".isidentifier()`          |`True`|
|`isprintable()` |Checks if all characters are printable     |`str.isprintable()`                     |`"hello world".isprintable()`      |`True`|

#### Split & Join Methods

|Function      |Description                            |Syntax                         |Example                      |Result              |
|--------------|---------------------------------------|-------------------------------|-----------------------------|--------------------|
|`split()`     |Splits string into list                |`str.split([sep], [maxsplit])` |`"a,b,c".split(",")`         |`['a', 'b', 'c']`   |
|`rsplit()`    |Splits from right                      |`str.rsplit([sep], [maxsplit])`|`"a.b.c".rsplit(".", 1)`     |`['a.b', 'c']`      |
|`splitlines()`|Splits on line breaks                  |`str.splitlines([keepends])`   |`"line1\nline2".splitlines()`|`['line1', 'line2']`|
|`partition()` |Splits into 3 parts at first separator |`str.partition(sep)`           |`"a-b-c".partition("-")`     |`('a', '-', 'b-c')` |
|`rpartition()`|Splits into 3 parts at last separator  |`str.rpartition(sep)`          |`"a-b-c".rpartition("-")`    |`('a-b', '-', 'c')` |
|`join()`      |Joins iterable with string as separator|`str.join(iterable)`           |`"-".join(['a', 'b', 'c'])`  |`"a-b-c"`           |

#### Replace & Translate Methods

|Function     |Description                       |Syntax                          |Example                                       |Result           |
|-------------|----------------------------------|--------------------------------|----------------------------------------------|-----------------|
|`replace()`  |Replaces occurrences of substring |`str.replace(old, new, [count])`|`"hello world".replace("world", "python")`    |`"hello python"` |
|`translate()`|Translates using translation table|`str.translate(table)`          |`"hello".translate(str.maketrans("el", "xy"))`|`"hyxxo"`        |
|`maketrans()`|Creates translation table         |`str.maketrans(x, [y], [z])`    |`str.maketrans("aeiou", "12345")`             |Translation table|

#### Encoding & Decoding Methods

|Function      |Description              |Syntax                            |Example                       |Result            |
|--------------|-------------------------|----------------------------------|------------------------------|------------------|
|`encode()`    |Encodes string to bytes  |`str.encode([encoding], [errors])`|`"hello".encode('utf-8')`     |`b'hello'`        |
|`expandtabs()`|Replaces tabs with spaces|`str.expandtabs([tabsize])`       |`"hello\tworld".expandtabs(4)`|`"hello    world"`|

#### Format Methods

|Function      |Description                  |Syntax                       |Example                                       |Result         |
|--------------|-----------------------------|-----------------------------|----------------------------------------------|---------------|
|`format()`    |Formats string with arguments|`str.format(*args, **kwargs)`|`"Hello {}".format("world")`                  |`"Hello world"`|
|`format_map()`|Formats using mapping        |`str.format_map(mapping)`    |`"Hello {name}".format_map({'name': 'world'})`|`"Hello world"`|

#### Common String Techniques & Patterns

#### 1. String Slicing

```python
text = "Hello World"
text[0:5]      # "Hello"
text[-5:]      # "World"
text[::-1]     # "dlroW olleH" (reverse)
text[::2]      # "HloWrd" (every 2nd char)
```

#### 2. Multiple Replacements

```python
text = "Hello World"
# Method 1: Chain replacements
result = text.replace("Hello", "Hi").replace("World", "Python")

# Method 2: Using translate
trans = str.maketrans("Helo", "Jxlp")
result = text.translate(trans)

# Method 3: Using format/f-strings
template = "{greeting} {subject}"
result = template.format(greeting="Hi", subject="Python")
```

#### 3. Case-Insensitive Operations

```python
text = "Hello World"
# Case-insensitive search
if "hello" in text.lower():
    print("Found!")

# Case-insensitive comparison
if text.lower() == "hello world":
    print("Match!")
```

#### 4. String Validation Patterns

```python
def validate_email(email):
    return "@" in email and "." in email.split("@")[1]

def is_valid_identifier(name):
    return name.isidentifier() and not name.iskeyword()
```

#### 5. Advanced Split Techniques

```python
text = "apple,banana;orange:grape"
# Split by multiple delimiters
import re
fruits = re.split('[,;:]', text)

# Split and keep delimiter
def split_keep_delimiter(text, delimiter):
    parts = text.split(delimiter)
    result = []
    for i, part in enumerate(parts[:-1]):
        result.extend([part, delimiter])
    result.append(parts[-1])
    return result
```

#### 6. String Padding & Alignment

```python
# Numeric padding
num = "42"
padded = num.zfill(5)  # "00042"

# Custom padding
text = "hello"
centered = f"{text:^10}"     # "  hello   "
left_aligned = f"{text:<10}" # "hello     "
right_aligned = f"{text:>10}" # "     hello"
```

#### 7. Working with Multiline Strings

```python
multiline = """Line 1
Line 2
Line 3"""

# Process each line
lines = multiline.splitlines()
processed = [line.strip().upper() for line in lines if line.strip()]

# Join back
result = '\n'.join(processed)
```

#### 8. String Interpolation Methods

```python
name = "World"
age = 25

# f-strings (Python 3.6+)
result = f"Hello {name}, you are {age} years old"

# format method
result = "Hello {}, you are {} years old".format(name, age)
result = "Hello {name}, you are {age} years old".format(name=name, age=age)

# % formatting (older style)
result = "Hello %s, you are %d years old" % (name, age)
```

#### 9. String Cleaning Utilities

```python
def clean_text(text):
    # Remove extra whitespace
    text = ' '.join(text.split())
    # Remove special characters (keep alphanumeric and spaces)
    text = ''.join(c for c in text if c.isalnum() or c.isspace())
    return text.strip()

def normalize_whitespace(text):
    return ' '.join(text.split())
```

#### 10. Performance Tips

```python
# Efficient string concatenation
# Bad: result = ""
# for item in items:
#     result += item

# Good: Use join for multiple concatenations
result = ''.join(items)

# Good: Use list comprehension with join
result = ''.join([process(item) for item in items])

# For few concatenations, f-strings are fine
result = f"{prefix}{middle}{suffix}"
```

### Binary Types
### Sequence Types
#### List
A list in Python is defined as a build-in mutable dynamic collection module container of objects. We characterize a list with square brackets
```Python
var_list = [1, 2, 3]
```
There are several methods defined for list creation and manipulation
```Python
append(x)        	    		# Add element x to end
extend(iterable) 	    		# Extend list 
insert(i, x)     	    		# Insert x at position i
remove(x)        	    		# Remove first element x
pop([i])         	    		# Remove and return item at i (last)
clear()                  		# Remove all items from list
index(x[, start[, end]]) 		# Return index in list of first item x
count(x) 		    		# Return number of times x appears
sort(*, key=None, reverse=False) 	# Sort (numerical) items in place
reverse()				# Reverse elements of list
copy()				# Return copy of the list
```
We give a few examples in the following
```Python 
my_list = [1, 2, 3]
sq_list = [x**2 for x in range(10)]
sq_list = list(map(lambda x: x**2, range(10)))
com_list = [(x, y) for x in [1,2,3] for y in [3,1,4] if x != y]
fil_list = [x for x in vec if x >= 0]
```
#### Tuple
```Python
my_tuple = (1, 5, -9)
```
#### Range
The range type represents an immutable sequence of numbers with syntax
```
class range(start, stop[, step])
```
It is commonly used for looping a specific number of times in for loops such as
We can define range iterators as follows
```Python
sum_iter = 0
for i in range(10):
    sum_iter += 1
```
We can also define lists by using range types
```Python
list(range(10))
# [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
```
### Mapping Types
#### Dictionary
In Python a dictionary represents a build-in mutable dynamic collection module container of objects (associative arrays). Dictionaries are collections of key-value pairs, with unique key-list. We can declare a dictionary via curly brackets
```Python
my_dict = {
    <key_1>: <value_1>,
    <key_2>: <value_2>,
    …
    <key_n>: <value_n>
}
```
The following methods are used to create or manipulate the data of a dictionary
```Python
clear()			                # Remove all elements
copy()			                # Return copy of given dictionary
fromkeys(keys[,value])	        # Create empty dictionary from keys iterable
get(keyname [,value])	        # Return dictionary value for given key
items()			                # Return view object to dictionary items
keys()			                # Return view object to dictionary keys [list(my_dict.keys())]
pop(keyname)		            # Remove key-value pair from dictionary and returns it
popitem()			            # Remove object that was last inserted (old: remove random object)
setdefault(keyname [,value])	# Return value of item with specific key (set if not exists) 
update(iterable)		        # Insert specified items to the dictionary
values()			            # Return view object to dictionary values [list(my_dict.values())]
```
We can iterate over the key value pairs of a dictionary in the following way
```Python
for key, value in my_dict.items():
    print(key, value)
```
Examples
```Python
var_dict = {"key_1": 1,
            "key_2": 2.53,
            "key_3": "text"}
my_dict = {'a': 1, 'b': 'text', 'c': 12.284}
my_dict_num = {x: x**2 for x in (2, 4, 6)} # Result: {2: 4, 4: 16, 6: 36}
```
### Set Types
#### Set
#### Frozenset


## Style

### Line breaks
Considering styling and readability of code we follog the PEP 8 style guide recommendations. The correct way to handle line breaks for different situations is given as follows
```Python
# Aligned with opening delimiter
foo = long_function_name(var_one, var_two,
                         var_three, var_four)

# Add 4 spaces (an extra level of indentation) to distinguish arguments from the rest.
def long_function_name(
      var_one, var_two, var_three,
      var_four):
   print(var_one)

# Hanging indents should add a level.
foo = long_function_name(
   var_one, var_two,
   var_three, var_four)
```
Considering line breaks for if statements we proceed as follows
```Python
# No extra indentation.
if (this_is_one_thing and
    that_is_another_thing):
    do_something()

# Add a comment, which will provide some distinction in editors
# supporting syntax highlighting.
if (this_is_one_thing and
    that_is_another_thing):
    # Since both conditions are true, we can frobnicate.
    do_something()

# Add some extra indentation on the conditional continuation line.
if (this_is_one_thing
      and that_is_another_thing):
   do_something()
```
### Method chaining
Concerning method chaining a single line with multiple chained method calls may suffer from good readability.

We can use backslashes allowing a line to continue beyond a line break
```Python
df_input = pd.read_csv("data/input/extract_test.csv", index_col=0) \
             .drop(columns="my_col") \
             .sort_values("index") \
             .head(1)
```
Furthermore, we may use parentheses () for which free line breaks are allowed
```Python
df_input = (
   pd.read_csv("data/input/extract_test.csv", index_col=0)
   .drop(columns="my_col")
   .sort_values("index")
   .head(1)
)
```
We can also use parentheses () for a standalone statement instead of assigning a value to a variable
```Python
(
   spark.createDataFrame(df).write
   .format("csv")
   .mode("overwrite")
   .save("/tmp/output/test_data")
)
```
## Documentation
We focus on the Google style format for Python in the following. The basic structure of the documentation docstring looks as follows
```Python
"""Fetches rows from a Smalltable.
    Args:
        parameter_one: The first parameter.
        parameter_two: The second parameter
          with a second line.

    Returns:
        A pandas DataFrame including the cleaned data

        {'data': ["a", "b", "c"],
         'value': [1, 2, 3]}

        If a key from the keys argument is missing from the dictionary, 
        then that row was not found in the DataFrame.

    Raises:
        IOError: An error occurred accessing the smalltable.
    """
```
A function is documented in the following way
```Python
# Example method
def fetch_smalltable_rows(
    table_handle: smalltable.Table,
    keys: Sequence[bytes | str],
    require_all_keys: bool = False,
) -> Mapping[bytes, tuple[str, ...]]:
    """Fetches rows from a Smalltable.

    Retrieves rows pertaining to the given keys from the Table instance
    represented by table_handle.  String keys will be UTF-8 encoded.

    Args:
        table_handle: An open smalltable.Table instance.
        keys: A sequence of strings representing the key of each table
          row to fetch.  String keys will be UTF-8 encoded.
        require_all_keys: If True only rows with values set for all keys will be
          returned.

    Returns:
        A dict mapping keys to the corresponding table row data
        fetched. Each row is represented as a tuple of strings. For
        example:

        {b'Serak': ('Rigel VII', 'Preparer'),
         b'Zim': ('Irk', 'Invader'),
         b'Lrrr': ('Omicron Persei 8', 'Emperor')}

        Returned keys are always bytes.  If a key from the keys argument is
        missing from the dictionary, then that row was not found in the
        table (and require_all_keys must have been False).

    Raises:
        IOError: An error occurred accessing the smalltable.
    """
```
A class is documented in the following way
```Python
class SampleClass:
    """Summary of class here.

    Longer class information...
    Longer class information...

    Attributes:
        likes_spam: A boolean indicating if we like SPAM or not.
        eggs: An integer count of the eggs we have laid.
    """

    def __init__(self, likes_spam: bool = False):
        """Initializes the instance based on spam preference.

        Args:
          likes_spam: Defines if instance exhibits this preference.
        """
        self.likes_spam = likes_spam
        self.eggs = 0

    def public_method(self):
        """Performs operation."""

```
## Conditions
In Python the conditional expressions are used as follows
```Python
if condition:
    pass
elif condition:
    pass
[...]
else:
    pass
```
Example
```Python
n = 10
if n < 10:
    print("n is smaller than 10")
elif n == 10:
    print("n is equal to 10")
else:
    print("n is larger than 10)"
```

## Loops
For-loop in Python
```Python
for i in range(10):
    print(i)
```
For-each loop in Python
```Python
my_list = [1, 2, 5]
for x in my_list:
    pass
```
While loop in Python
```Python
n = 10
while n > 0:
    n -= 1
```
## Input and Output
```Python
# Console input
inp = input('This is your input: ')
print('Your input: ' + inp)

# File object read methods, n: byte number
read(size=-1)      # read complete content
readline(size=-1)  # read a single line
readlines()        # read complete content and return list

# Read content of a given file [file_name='my_file.txt']
with open(file_name, 'r') as file_stream:
    file_content = file_stream.read()

# File object write methods [file_name='output.txt']
write(string)      # writes string to a file
writelines(seq)    # writes sequence to a file
with open(file_name, 'w') as file_stream:
    file_stream.write(my_data)
```


## Functions

### 1. Basic Method Syntax

### Function Definition

```python
def function_name(parameters):
    """Optional docstring"""
    # Function body
    return value  # Optional
```

### Method Definition (Inside Classes)

```python
class ClassName:
    def method_name(self, parameters):
        """Optional docstring"""
        # Method body
        return value  # Optional
```

### 2. Method Types in Classes

### Instance Methods

```python
class MyClass:
    def instance_method(self, param):
        """Operates on instance data"""
        self.attribute = param
        return self.attribute
```

### Class Methods

```python
class MyClass:
    class_var = 0
    
    @classmethod
    def class_method(cls, param):
        """Operates on class data"""
        cls.class_var = param
        return cls.class_var
```

### Static Methods

```python
class MyClass:
    @staticmethod
    def static_method(param):
        """Independent utility function"""
        return param * 2
```

### Property Methods

```python
class MyClass:
    def __init__(self):
        self._value = 0
    
    @property
    def value(self):
        """Getter"""
        return self._value
    
    @value.setter
    def value(self, val):
        """Setter"""
        self._value = val
    
    @value.deleter
    def value(self):
        """Deleter"""
        del self._value
```

### 3. Parameter Types and Arguments

### Positional Arguments

```python
def greet(name, age):
    return f"Hello {name}, you are {age} years old"

# Usage
greet("Alice", 25)
```

### Default Arguments

```python
def greet(name, age=18, city="Unknown"):
    return f"{name}, {age}, from {city}"

# Usage
greet("Bob")                    # Uses defaults
greet("Carol", 30)              # age=30, city="Unknown"
greet("Dave", city="NYC")       # age=18, city="NYC"
```

### Variable-Length Arguments (*args)

```python
def sum_all(*args):
    """Accepts any number of positional arguments"""
    return sum(args)

# Usage
sum_all(1, 2, 3, 4)      # Returns 10
sum_all()                # Returns 0
```

### Keyword Arguments (**kwargs)

```python
def process_data(**kwargs):
    """Accepts any number of keyword arguments"""
    for key, value in kwargs.items():
        print(f"{key}: {value}")

# Usage
process_data(name="Alice", age=25, city="NYC")
```

### Combined Arguments

```python
def complex_function(required, default="default", *args, **kwargs):
    print(f"Required: {required}")
    print(f"Default: {default}")
    print(f"Args: {args}")
    print(f"Kwargs: {kwargs}")

# Usage
complex_function("req", "custom", 1, 2, 3, key1="val1", key2="val2")
```

### Keyword-Only Arguments

```python
def function_with_kwonly(a, b, *, c, d="default"):
    """c must be passed as keyword argument"""
    return a + b + c

# Usage
function_with_kwonly(1, 2, c=3)        # Valid
# function_with_kwonly(1, 2, 3)        # Error!
```

### Positional-Only Arguments (Python 3.8+)

```python
def function_with_posonly(a, b, /, c, d):
    """a and b must be positional-only"""
    return a + b + c + d

# Usage
function_with_posonly(1, 2, 3, 4)      # Valid
function_with_posonly(1, 2, c=3, d=4)  # Valid
# function_with_posonly(a=1, b=2, c=3, d=4)  # Error!
```

### 4. Special Methods (Dunder Methods)

### Object Lifecycle

```python
class Example:
    def __init__(self, value):
        """Constructor"""
        self.value = value
    
    def __del__(self):
        """Destructor"""
        print("Object deleted")
    
    def __new__(cls, *args, **kwargs):
        """Object creation"""
        return super().__new__(cls)
```

### String Representation

```python
class Person:
    def __init__(self, name, age):
        self.name = name
        self.age = age
    
    def __str__(self):
        """Human-readable string"""
        return f"{self.name} ({self.age})"
    
    def __repr__(self):
        """Developer-friendly representation"""
        return f"Person('{self.name}', {self.age})"
```

### Arithmetic Operations

```python
class Number:
    def __init__(self, value):
        self.value = value
    
    def __add__(self, other):
        return Number(self.value + other.value)
    
    def __sub__(self, other):
        return Number(self.value - other.value)
    
    def __mul__(self, other):
        return Number(self.value * other.value)
```

### Comparison Operations

```python
class Student:
    def __init__(self, name, grade):
        self.name = name
        self.grade = grade
    
    def __eq__(self, other):
        return self.grade == other.grade
    
    def __lt__(self, other):
        return self.grade < other.grade
    
    def __le__(self, other):
        return self.grade <= other.grade
```

### 5. Reference Tables

### Common Special Methods

|Method                       |Purpose                 |Example Usage           |
|-----------------------------|------------------------|------------------------|
|`__init__(self, ...)`        |Constructor             |`obj = MyClass()`       |
|`__str__(self)`              |String representation   |`str(obj)`, `print(obj)`|
|`__repr__(self)`             |Developer representation|`repr(obj)`             |
|`__len__(self)`              |Length                  |`len(obj)`              |
|`__getitem__(self, key)`     |Item access             |`obj[key]`              |
|`__setitem__(self, key, val)`|Item assignment         |`obj[key] = val`        |
|`__contains__(self, item)`   |Membership test         |`item in obj`           |
|`__call__(self, ...)`        |Make callable           |`obj()`                 |
|`__iter__(self)`             |Make iterable           |`for x in obj:`         |
|`__next__(self)`             |Iterator protocol       |`next(obj)`             |

### Arithmetic Special Methods

|Method                     |Operation     |Example       |
|---------------------------|--------------|--------------|
|`__add__(self, other)`     |Addition      |`obj + other` |
|`__sub__(self, other)`     |Subtraction   |`obj - other` |
|`__mul__(self, other)`     |Multiplication|`obj * other` |
|`__truediv__(self, other)` |Division      |`obj / other` |
|`__floordiv__(self, other)`|Floor division|`obj // other`|
|`__mod__(self, other)`     |Modulo        |`obj % other` |
|`__pow__(self, other)`     |Power         |`obj ** other`|

### Comparison Special Methods

|Method               |Operation       |Example       |
|---------------------|----------------|--------------|
|`__eq__(self, other)`|Equal           |`obj == other`|
|`__ne__(self, other)`|Not equal       |`obj != other`|
|`__lt__(self, other)`|Less than       |`obj < other` |
|`__le__(self, other)`|Less or equal   |`obj <= other`|
|`__gt__(self, other)`|Greater than    |`obj > other` |
|`__ge__(self, other)`|Greater or equal|`obj >= other`|

### 6. Advanced Techniques

### Decorators

```python
def timing_decorator(func):
    """Decorator to time function execution"""
    import time
    def wrapper(*args, **kwargs):
        start = time.time()
        result = func(*args, **kwargs)
        end = time.time()
        print(f"{func.__name__} took {end - start:.4f} seconds")
        return result
    return wrapper

class MyClass:
    @timing_decorator
    def slow_method(self):
        import time
        time.sleep(1)
        return "Done"
```

### Method Chaining

```python
class FluentBuilder:
    def __init__(self):
        self.data = {}
    
    def set_name(self, name):
        self.data['name'] = name
        return self  # Enable chaining
    
    def set_age(self, age):
        self.data['age'] = age
        return self
    
    def build(self):
        return self.data

# Usage
result = FluentBuilder().set_name("Alice").set_age(25).build()
```

### Context Managers

```python
class FileManager:
    def __init__(self, filename, mode):
        self.filename = filename
        self.mode = mode
        self.file = None
    
    def __enter__(self):
        self.file = open(self.filename, self.mode)
        return self.file
    
    def __exit__(self, exc_type, exc_val, exc_tb):
        if self.file:
            self.file.close()

# Usage
with FileManager("test.txt", "w") as f:
    f.write("Hello, World!")
```

### Abstract Methods

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass
    
    @abstractmethod
    def move(self):
        pass

class Dog(Animal):
    def make_sound(self):
        return "Woof!"
    
    def move(self):
        return "Running"
```

### Cached Properties

```python
class ExpensiveComputation:
    def __init__(self, data):
        self.data = data
        self._result = None
    
    @property
    def result(self):
        if self._result is None:
            print("Computing expensive result...")
            self._result = sum(x**2 for x in self.data)
        return self._result
```

### 7. Best Practices

### Documentation

```python
class Calculator:
    """A simple calculator class.
    
    This class provides basic arithmetic operations
    and maintains a history of calculations.
    """
    
    def add(self, a: float, b: float) -> float:
        """Add two numbers.
        
        Args:
            a (float): First number
            b (float): Second number
            
        Returns:
            float: Sum of a and b
            
        Example:
            >>> calc = Calculator()
            >>> calc.add(2, 3)
            5.0
        """
        return a + b
```

### Type Hints

```python
from typing import List, Dict, Optional, Union

class DataProcessor:
    def process_list(self, data: List[int]) -> List[int]:
        """Process a list of integers"""
        return [x * 2 for x in data]
    
    def get_config(self) -> Dict[str, Union[str, int]]:
        """Return configuration dictionary"""
        return {"name": "processor", "version": 1}
    
    def find_item(self, items: List[str], target: str) -> Optional[str]:
        """Find item in list, return None if not found"""
        return target if target in items else None
```

### Error Handling

```python
class SafeCalculator:
    def divide(self, a: float, b: float) -> float:
        """Safely divide two numbers"""
        try:
            if b == 0:
                raise ValueError("Cannot divide by zero")
            return a / b
        except TypeError:
            raise TypeError("Arguments must be numbers")
        except Exception as e:
            print(f"Unexpected error: {e}")
            raise
```

### 8. Common Patterns

### Singleton Pattern

```python
class Singleton:
    _instance = None
    
    def __new__(cls):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance
```

### Factory Pattern

```python
class ShapeFactory:
    @staticmethod
    def create_shape(shape_type: str, **kwargs):
        """Factory method to create shapes"""
        if shape_type == "circle":
            return Circle(kwargs.get("radius", 1))
        elif shape_type == "rectangle":
            return Rectangle(kwargs.get("width", 1), kwargs.get("height", 1))
        else:
            raise ValueError(f"Unknown shape type: {shape_type}")
```

### Observer Pattern

```python
class Subject:
    def __init__(self):
        self._observers = []
    
    def attach(self, observer):
        """Add an observer"""
        self._observers.append(observer)
    
    def detach(self, observer):
        """Remove an observer"""
        self._observers.remove(observer)
    
    def notify(self, message):
        """Notify all observers"""
        for observer in self._observers:
            observer.update(message)
```

### 9. Quick Examples

#### Complete Class Example

```python
class BankAccount:
    """A simple bank account class demonstrating various method types"""
    
    # Class variable
    interest_rate = 0.02
    
    def __init__(self, account_number: str, initial_balance: float = 0):
        """Initialize account"""
        self.account_number = account_number
        self._balance = initial_balance
        self.transactions = []
    
    @property
    def balance(self) -> float:
        """Get current balance"""
        return self._balance
    
    def deposit(self, amount: float) -> None:
        """Deposit money"""
        if amount <= 0:
            raise ValueError("Amount must be positive")
        self._balance += amount
        self.transactions.append(f"Deposit: +${amount}")
    
    def withdraw(self, amount: float) -> None:
        """Withdraw money"""
        if amount <= 0:
            raise ValueError("Amount must be positive")
        if amount > self._balance:
            raise ValueError("Insufficient funds")
        self._balance -= amount
        self.transactions.append(f"Withdrawal: -${amount}")
    
    @classmethod
    def create_savings_account(cls, account_number: str, initial_deposit: float):
        """Factory method for savings accounts"""
        account = cls(account_number, initial_deposit)
        account.account_type = "Savings"
        return account
    
    @staticmethod
    def calculate_interest(principal: float, rate: float, time: float) -> float:
        """Calculate simple interest"""
        return principal * rate * time
    
    def __str__(self) -> str:
        return f"Account {self.account_number}: ${self._balance:.2f}"
    
    def __repr__(self) -> str:
        return f"BankAccount('{self.account_number}', {self._balance})"

# Usage example
account = BankAccount("ACC001", 1000)
account.deposit(500)
account.withdraw(200)
print(account)  # Account ACC001: $1300.00
```


## Classes
The basic syntax is given by

```Python
class ClassName:
    """
    Documentation of the class
    """
    def __init__(self, par, *args, **kwargs):
        self._par = par

    def update_par(self, par):
        self._par = par

    def read_par(self):
        return self._par
```

### Python OOP Reference Card

### 1. Basic Concepts

### Class Definition
```python
class ClassName:
    # Class body
    pass
```

### Constructor and Instance Methods
```python
class Person:
    def __init__(self, name, age):
        # Constructor (initializer)
        self.name = name  # Instance attribute
        self.age = age
    
    def introduce(self):
        # Instance method
        return f"Hi, I'm {self.name} and I'm {self.age} years old."
```

### Creating Instances
```python
person1 = Person("Alice", 30)
print(person1.introduce())
```

### 2. Inheritance

### Basic Inheritance
```python
class Animal:
    def __init__(self, name):
        self.name = name
    
    def speak(self):
        pass

class Dog(Animal):
    def speak(self):
        return f"{self.name} says Woof!"

class Cat(Animal):
    def speak(self):
        return f"{self.name} says Meow!"
```

### Multiple Inheritance
```python
class Parent1:
    def method1(self):
        print("Method from Parent1")

class Parent2:
    def method2(self):
        print("Method from Parent2")

class Child(Parent1, Parent2):
    def combined_method(self):
        self.method1()
        self.method2()
```

### 3. Advanced OOP Techniques

### Class Methods and Static Methods
```python
class MathOperations:
    @classmethod
    def create_from_string(cls, number_string):
        # Class method - operates on the class itself
        return cls(int(number_string))
    
    @staticmethod
    def add(x, y):
        # Static method - utility method not tied to instance or class state
        return x + y
```

### Property Decorators
```python
class Circle:
    def __init__(self, radius):
        self._radius = radius
    
    @property
    def radius(self):
        return self._radius
    
    @radius.setter
    def radius(self, value):
        if value < 0:
            raise ValueError("Radius cannot be negative")
        self._radius = value
    
    @property
    def area(self):
        return 3.14 * self._radius ** 2
```

### Abstract Base Classes
```python
from abc import ABC, abstractmethod

class Shape(ABC):
    @abstractmethod
    def area(self):
        pass
    
    @abstractmethod
    def perimeter(self):
        pass

class Rectangle(Shape):
    def __init__(self, width, height):
        self.width = width
        self.height = height
    
    def area(self):
        return self.width * self.height
    
    def perimeter(self):
        return 2 * (self.width + self.height)
```

### 4. Composition vs Inheritance

### Composition Example
```python
class Engine:
    def start(self):
        return "Engine started"

class Car:
    def __init__(self):
        self.engine = Engine()  # Composition
    
    def start_car(self):
        return self.engine.start()
```

### 5. Best Practices

### 1. SOLID Principles
- **S**ingle Responsibility Principle
- **O**pen/Closed Principle
- **L**iskov Substitution Principle
- **I**nterface Segregation Principle
- **D**ependency Inversion Principle

### 2. Coding Guidelines
- Use meaningful and descriptive class and method names
- Keep classes focused and modular
- Prefer composition over inheritance
- Use type hints for better code readability
- Implement `__repr__` and `__str__` methods
- Use property decorators for controlled attribute access

### 3. Example of Good Practice
```python
from typing import List

class Library:
    def __init__(self, name: str):
        self.name = name
        self._books: List[Book] = []
    
    def add_book(self, book: 'Book'):
        self._books.append(book)
    
    def __repr__(self) -> str:
        return f"Library(name='{self.name}', books={len(self._books)})"

class Book:
    def __init__(self, title: str, author: str):
        self.title = title
        self.author = author
    
    def __str__(self) -> str:
        return f"{self.title} by {self.author}"
```

### 6. Common Pitfalls to Avoid
- Overusing inheritance
- Creating deep inheritance hierarchies
- Modifying class attributes directly
- Ignoring type hints and documentation
- Not handling edge cases in methods

### 7. Performance Considerations
- Use `__slots__` for memory-efficient classes
- Prefer class methods for alternative constructors
- Be cautious with multiple inheritance
```python
class OptimizedClass:
    __slots__ = ['attribute1', 'attribute2']
    # Reduces memory overhead by preventing dynamic attribute creation
```

### 8. Design Patterns (Brief Overview)
- Singleton
- Factory
- Strategy
- Observer
- Decorator

## 9. Useful Built-in Methods
- `__init__()`: Constructor
- `__str__()`: String representation
- `__repr__()`: Detailed string representation
- `__eq__()`: Equality comparison
- `__lt__()`, `__gt__()`: Comparison methods


### Abstract (Base) Classes

#### What is ABC?
Abstract Base Classes (ABC) provide a way to define interfaces in Python. They allow you to:
- Define abstract methods that must be implemented by subclasses
- Register virtual subclasses
- Check if a class implements a particular interface

#### Key Components
- `abc` module - Contains tools for creating abstract base classes
- `ABC` class - Base class for creating abstract base classes
- `@abstractmethod` decorator - Marks methods that must be implemented by concrete subclasses
- `register()` method - Registers virtual subclasses

#### Basic Usage

#### Creating an Abstract Base Class

```python
from abc import ABC, abstractmethod

class MyAbstractClass(ABC):
    @abstractmethod
    def my_abstract_method(self):
        """This method must be implemented by subclasses."""
        pass
    
    def concrete_method(self):
        """This is a regular method that subclasses inherit as is."""
        return "This method is already implemented."
```

#### Implementing an Abstract Base Class

```python
class ConcreteClass(MyAbstractClass):
    def my_abstract_method(self):
        return "Implementation of the abstract method"
    
# This works
obj = ConcreteClass()
print(obj.my_abstract_method())  # Output: Implementation of the abstract method
print(obj.concrete_method())     # Output: This method is already implemented.

# This fails
# obj = MyAbstractClass()  # TypeError: Can't instantiate abstract class
```

#### Advanced Features

#### Additional Abstract Decorators

```python
from abc import ABC, abstractmethod, abstractproperty, abstractclassmethod, abstractstaticmethod

class AdvancedABC(ABC):
    @abstractmethod
    def abstract_method(self):
        pass
    
    @property
    @abstractmethod
    def abstract_property(self):
        pass
    
    @classmethod
    @abstractmethod
    def abstract_classmethod(cls):
        pass
    
    @staticmethod
    @abstractmethod
    def abstract_staticmethod():
        pass
```

#### Virtual Subclass Registration

```python
from abc import ABC, abstractmethod

class Animal(ABC):
    @abstractmethod
    def make_sound(self):
        pass

# A class that doesn't inherit from Animal
class Duck:
    def make_sound(self):
        return "Quack"

# Register Duck as a virtual subclass of Animal
Animal.register(Duck)

# Check subclass relationship
print(issubclass(Duck, Animal))  # True
print(isinstance(Duck(), Animal))  # True
```

#### Abstract Class Checking

```python
# Check if a class is an ABC
from abc import ABC
print(issubclass(MyAbstractClass, ABC))  # True

# Check if a method is abstract
from inspect import isabstract
print(isabstract(MyAbstractClass.my_abstract_method))  # True
```

#### Best Practices

#### Do's
- ✅ Use ABC for defining clear interfaces
- ✅ Provide docstrings for abstract methods
- ✅ Consider providing default implementations when appropriate
- ✅ Use `NotImplementedError` in abstract method bodies if you want to provide a more explicit error message
- ✅ Combine with `__subclasshook__` for more flexible interface checking

#### Don'ts
- ❌ Don't create deep hierarchies of abstract classes
- ❌ Don't overuse ABC for simple inheritance
- ❌ Don't make all methods abstract if defaults can be provided
- ❌ Don't use ABC when duck typing is sufficient

#### Real-World Examples

#### Creating a File Interface

```python
from abc import ABC, abstractmethod
import os

class FileInterface(ABC):
    @abstractmethod
    def read(self):
        """Read content from the file."""
        raise NotImplementedError
    
    @abstractmethod
    def write(self, data):
        """Write data to the file."""
        raise NotImplementedError
    
    @property
    @abstractmethod
    def is_open(self):
        """Check if the file is open."""
        raise NotImplementedError

class TextFile(FileInterface):
    def __init__(self, filename):
        self.filename = filename
        self._file = None
    
    def read(self):
        if not self._file:
            self._file = open(self.filename, 'r')
        return self._file.read()
    
    def write(self, data):
        if not self._file:
            self._file = open(self.filename, 'w')
        return self._file.write(data)
    
    @property
    def is_open(self):
        return self._file is not None and not self._file.closed
```

#### Using `__subclasshook__` for Duck Typing

```python
from abc import ABC, abstractmethod

class Walkable(ABC):
    @abstractmethod
    def walk(self):
        pass
    
    @classmethod
    def __subclasshook__(cls, subclass):
        if cls is Walkable:
            if any("walk" in B.__dict__ for B in subclass.__mro__):
                return True
        return NotImplemented

# This class doesn't inherit from Walkable but has a walk method
class Person:
    def walk(self):
        return "Walking..."

# Check if Person is a virtual subclass of Walkable
print(issubclass(Person, Walkable))  # True
print(isinstance(Person(), Walkable))  # True
```

#### Advanced Techniques

#### Abstract Base Classes with Metaclasses

```python
from abc import ABCMeta, abstractmethod

class MyInterface(metaclass=ABCMeta):
    @abstractmethod
    def method1(self):
        pass
    
    @abstractmethod
    def method2(self):
        pass
```

#### Combining ABC with Protocols (Python 3.8+)

```python
from abc import ABC, abstractmethod
from typing import Protocol, runtime_checkable

# Abstract base class
class Shape(ABC):
    @abstractmethod
    def area(self):
        pass

# Protocol
@runtime_checkable
class Drawable(Protocol):
    def draw(self) -> None:
        ...

class Circle(Shape):
    def __init__(self, radius):
        self.radius = radius
    
    def area(self):
        import math
        return math.pi * self.radius ** 2
    
    def draw(self):
        print(f"Drawing a circle with radius {self.radius}")

# Check both ABC and Protocol conformance
circle = Circle(5)
print(isinstance(circle, Shape))     # True
print(isinstance(circle, Drawable))  # True
```

#### Partial Implementations with Mix-ins

```python
from abc import ABC, abstractmethod

class BaseValidator(ABC):
    @abstractmethod
    def validate(self, data):
        pass

class EmailValidationMixin:
    def validate_email(self, email):
        import re
        pattern = r'^[\w\.-]+@[\w\.-]+\.\w+$'
        return bool(re.match(pattern, email))

class PasswordValidationMixin:
    def validate_password(self, password):
        return len(password) >= 8

class FormValidator(BaseValidator, EmailValidationMixin, PasswordValidationMixin):
    def validate(self, data):
        if 'email' in data and not self.validate_email(data['email']):
            return False
        if 'password' in data and not self.validate_password(data['password']):
            return False
        return True
```

#### Common Pitfalls and Solutions

#### Pitfall: Not Implementing All Abstract Methods

```python
# This will fail
class PartialImplementation(MyAbstractClass):
    pass  # Missing implementation of my_abstract_method

# Solution: Implement all abstract methods
class CorrectImplementation(MyAbstractClass):
    def my_abstract_method(self):
        return "Implemented abstract method"
```

#### Pitfall: Multiple Inheritance with Multiple ABCs

```python
from abc import ABC, abstractmethod

class Interface1(ABC):
    @abstractmethod
    def method(self):
        pass

class Interface2(ABC):
    @abstractmethod
    def method(self):
        pass

# This class needs to implement method only once
class Implementation(Interface1, Interface2):
    def method(self):
        return "Implemented method satisfies both interfaces"
```

#### Pitfall: Abstract Properties

```python
from abc import ABC, abstractmethod

class PropertyExample(ABC):
    # Python 3.3+ recommended way
    @property
    @abstractmethod
    def abstract_property(self):
        pass
    
    # Setting abstract property
    @abstract_property.setter
    @abstractmethod
    def abstract_property(self, value):
        pass
```

### Inheritance


## Decoratos

#### Basic Concepts

#### What Are Decorators?
- Decorators are a design pattern in Python that allows behavior to be added to an individual object, either statically or dynamically, without affecting the behavior of other objects from the same class
- Technically, decorators are functions that take another function as input and extend its behavior without explicitly modifying it
- Decorators use the `@` syntax as syntactic sugar (placed above function or class definitions)

#### Fundamental Structure
```python
def my_decorator(func):
    def wrapper(*args, **kwargs):
        # Code to execute before the function
        result = func(*args, **kwargs)
        # Code to execute after the function
        return result
    return wrapper

@my_decorator
def my_function():
    pass
```

#### Decorator Execution Flow
1. When Python encounters a decorated function, it compiles the function
2. The decorator is then executed with the compiled function as its argument
3. The original function is replaced with the return value of the decorator
4. The decorated function is executed when called

#### Basic Decorator Patterns

#### Timing Execution
```python
import time

def timer(func):
    def wrapper(*args, **kwargs):
        start_time = time.time()
        result = func(*args, **kwargs)
        end_time = time.time()
        print(f"{func.__name__} ran in {end_time - start_time:.6f} seconds")
        return result
    return wrapper

@timer
def slow_function():
    time.sleep(1)
    return "Function completed"
```

#### Logging
```python
def log_function_call(func):
    def wrapper(*args, **kwargs):
        print(f"Calling {func.__name__} with args: {args}, kwargs: {kwargs}")
        result = func(*args, **kwargs)
        print(f"{func.__name__} returned: {result}")
        return result
    return wrapper

@log_function_call
def add(a, b):
    return a + b
```

#### Memoization (Caching)
```python
def memoize(func):
    cache = {}
    def wrapper(*args):
        if args in cache:
            return cache[args]
        result = func(*args)
        cache[args] = result
        return result
    return wrapper

@memoize
def fibonacci(n):
    if n <= 1:
        return n
    return fibonacci(n-1) + fibonacci(n-2)
```

#### Advanced Decorator Techniques

#### Decorators with Arguments
```python
def repeat(num_times):
    def decorator(func):
        def wrapper(*args, **kwargs):
            results = []
            for _ in range(num_times):
                results.append(func(*args, **kwargs))
            return results
        return wrapper
    return decorator

@repeat(3)
def say_hello(name):
    return f"Hello, {name}!"
```

#### Class-based Decorators
```python
class CountCalls:
    def __init__(self, func):
        self.func = func
        self.count = 0
        
    def __call__(self, *args, **kwargs):
        self.count += 1
        print(f"{self.func.__name__} has been called {self.count} times")
        return self.func(*args, **kwargs)

@CountCalls
def say_hi():
    return "Hi!"
```

#### Stacking Decorators
```python
@decorator1
@decorator2
@decorator3
def function():
    pass

# Equivalent to:
# function = decorator1(decorator2(decorator3(function)))
# Execution order: decorator3, decorator2, decorator1
```

#### Preserving Metadata with functools.wraps
```python
from functools import wraps

def my_decorator(func):
    @wraps(func)  # Preserves original function's metadata
    def wrapper(*args, **kwargs):
        return func(*args, **kwargs)
    return wrapper

@my_decorator
def example():
    """This is a docstring."""
    pass

# Without @wraps, example.__name__ would be "wrapper"
# With @wraps, example.__name__ is "example"
# Also preserves docstrings and other metadata
```

#### Method Decorators
```python
def method_decorator(method):
    def wrapper(self, *args, **kwargs):
        print(f"Calling method {method.__name__} of {self.__class__.__name__}")
        return method(self, *args, **kwargs)
    return wrapper

class Example:
    @method_decorator
    def method(self, x):
        return x * 2
```

#### Class Decorators
```python
def add_greeting(cls):
    cls.greet = lambda self: f"Hello from {cls.__name__}"
    return cls

@add_greeting
class Person:
    def __init__(self, name):
        self.name = name

# Now Person instances have a greet method
p = Person("Alice")
p.greet()  # Returns "Hello from Person"
```

#### Real-World Examples

#### Authentication Decorator
```python
def require_auth(func):
    def wrapper(request, *args, **kwargs):
        if not request.user.is_authenticated:
            return redirect('login')
        return func(request, *args, **kwargs)
    return wrapper

@require_auth
def protected_view(request):
    return render(request, 'protected.html')
```

#### Rate Limiting
```python
import time
from functools import wraps

def rate_limit(max_calls, period=60):
    calls = []
    
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            now = time.time()
            # Remove calls older than the period
            while calls and calls[0] < now - period:
                calls.pop(0)
                
            if len(calls) >= max_calls:
                raise Exception(f"Rate limit exceeded. Max {max_calls} calls per {period}s")
                
            calls.append(now)
            return func(*args, **kwargs)
        return wrapper
    return decorator

@rate_limit(5, period=60)
def api_request():
    return "API response"
```

#### Retry Mechanism
```python
import time
from functools import wraps

def retry(max_attempts=3, delay=1):
    def decorator(func):
        @wraps(func)
        def wrapper(*args, **kwargs):
            attempts = 0
            while attempts < max_attempts:
                try:
                    return func(*args, **kwargs)
                except Exception as e:
                    attempts += 1
                    if attempts == max_attempts:
                        raise e
                    time.sleep(delay)
            return None
        return wrapper
    return decorator

@retry(max_attempts=5, delay=2)
def unstable_network_call():
    # Code that might fail due to network issues
    pass
```

#### Best Practices

#### DO:
- Use `functools.wraps` to preserve the original function's metadata
- Keep decorators simple and focused on a single responsibility
- Document the behavior added by your decorators
- Handle all possible exceptions within your decorator
- Make decorators reusable across different functions
- Use decorators for cross-cutting concerns (logging, timing, authentication)

#### DON'T:
- Create decorators that do too many things at once
- Modify function arguments or return values unless that's the explicit purpose
- Use decorators for complex logic that belongs in the function itself
- Forget to pass along `*args` and `**kwargs` in your wrapper function
- Nest too many decorators (hard to debug)
- Create decorators that significantly impact performance

#### Performance Considerations:
- Decorators add a function call overhead
- Complex decorators can impact performance
- Memoization decorators trade memory for speed
- Profile your code with and without decorators when performance is critical

#### Debugging Decorated Functions

#### Accessing the Original Function
```python
# Original function is available via __wrapped__ when using @wraps
@my_decorator
def function():
    pass

original_function = function.__wrapped__
```

#### Temporarily Disabling Decorators
```python
# Option 1: Comment out the decorator
# @decorator
def function():
    pass

# Option 2: Extract the decorator application
def function():
    pass
# Apply conditionally
if ENABLE_DECORATORS:
    function = decorator(function)
```

#### Standard Library Decorators

- `@classmethod`: Convert a method to a class method
- `@staticmethod`: Convert a method to a static method
- `@property`: Define a managed attribute
- `@functools.lru_cache`: Memoization with least recently used cache strategy
- `@functools.wraps`: Preserve function metadata in decorators
- `@contextlib.contextmanager`: Create context managers from generator functions
- `@abc.abstractmethod`: Define abstract methods in abstract base classes


## Generators



## Exceptions
The typical structure for catching or throwing exceptions is given by
```Python
try:
    # Some code
except SomeException:
    # Some code
```
A typical workflow for exception handling looks as follows
```Python
try:
    # Some code which may result in an exception case
except SomeException1 as e:
    # Consider check for exception one
except SomeException1 as e:
    # Consider check for exception two
except Exception as e:
    # Handle other exceptions at this point
```
We can also define a custom exception in Python
```Python
class CustomException(Exception):
    pass
```
This can be used as follows
```Python
try:
    if condition:
        raise CustomException("An error occured during the condition check.")
except CustomException as e:
    # Handle the custom exception
except Exception as e:
    # Handle other exceptions at this point
```
We can also define either an else or a finally section after the try/except blocks
```Python
try:
    # Some code which may result in an exception case
except SomeException1 as e:
    # Consider check for exception one
except SomeException1 as e:
    # Consider check for exception two
except Exception as e:
    # Handle other exceptions at this point
else:
    # Code which will be executed if there are no exceptions
```
Additionally, we give the finally section here
```Python
try:
    # Some code which may result in an exception case
except Exception as e:
    # Handle other exceptions at this point
else:
    # Code which will be executed if there are no exceptions
finally:
    # Code which will be always executed 
```
## Python Typing
The typing library is used as a tool to provide the developer hints and details about the data types of variables, primarily used in function or method definitions. Basically, the parameters and the return type of a method can receive a type hint as well as all variables which are initialized in the code. 
### Build-in types
The basic notation for internal build-in data types like int, str, float, bool, None works as follows
```Python
def add(x: int, y: int) -> int:
    return x + y
```
### Collections
In terms of collections we can use the following
```Python
from typing import List, Dict, Tuple

def get_names(ages: Dict[str, int]) -> List[str]:
    return list(ages.keys())

def process_coordinates(coords: Tuple[int, int, int]) -> str:
    return f"Coordinates: {coords}"
```
We may think of the generic types
* List[T]: A list containing elements of type T
* Dict[K, V]: A dictionary with keys of type K and values of type V
* Tuple[T1, T2, ...]: A tuple with specified types for each element

### Optional values
The optional type hint is used for variables or arguments that my be of type None
```Python
from typing import Optional

def greet(name: Optional[str] = None) -> str:
    return f"Hello, {name}" if name else "Hello, Stranger"

```

### Union
The Union type hint is used for variables that can have multiple types
```Python
from typing import Union

def parse_input(value: Union[int, str]) -> int:
    return int(value)
```

### Callable

The callable type hint is used to specify functions or callbacks within a specific signature
```Python
from typing import Callable

def operate(a: int, b: int, func: Callable[[int, int], int]) -> int:
    return func(a, b)
```

### Type aliases

We can also define custom aliases for more complex data types in the following way
```Python
from typing import List

Vector = List[float]

def scale(vector: Vector, factor: float) -> Vector:
    return [x * factor for x in vector]
```

### Generics
The TypeVar is used to create generic functions or classes
```Python
from typing import TypeVar, List

T = TypeVar('T')  # Can be any type

def get_first_element(items: List[T]) -> T:
    return items[0]
```

### Any type
The Any type hint allows any type and is used in the following way
```Python
from typing import Any

def handle_dynamic_input(data: Any) -> None:
    print(data)  # Accepts any type

```

### Final
The Final type hint is used for immutable variables in the following way
```Python
from typing import Final

PI: Final = 3.14159
```

### Literal
Using literal we can restrict variables to specific values 
```Python
from typing import Literal

def set_mode(mode: Literal['read', 'write']) -> None:
    pass

set_mode('read')  # Valid
set_mode('execute')  # Type error
```


## Python dataclasses

### Basic Syntax

#### Simple Dataclass

```python
from dataclasses import dataclass

@dataclass
class Person:
    name: str
    age: int
    email: str = "not provided"

# Usage
person = Person("Alice", 30)
print(person)  # Person(name='Alice', age=30, email='not provided')
```

### With Methods

```python
@dataclass
class Rectangle:
    width: float
    height: float
    
    def area(self) -> float:
        return self.width * self.height
    
    def perimeter(self) -> float:
        return 2 * (self.width + self.height)
```

-----

### Decorator Parameters

|Parameter     |Default|Description                                                       |Example                        |
|--------------|-------|------------------------------------------------------------------|-------------------------------|
|`init`        |`True` |Generate `__init__` method                                        |`@dataclass(init=False)`       |
|`repr`        |`True` |Generate `__repr__` method                                        |`@dataclass(repr=False)`       |
|`eq`          |`True` |Generate `__eq__` method                                          |`@dataclass(eq=False)`         |
|`order`       |`False`|Generate ordering methods (`__lt__`, `__le__`, `__gt__`, `__ge__`)|`@dataclass(order=True)`       |
|`unsafe_hash` |`False`|Force generation of `__hash__`                                    |`@dataclass(unsafe_hash=True)` |
|`frozen`      |`False`|Make instances immutable                                          |`@dataclass(frozen=True)`      |
|`match_args`  |`True` |Generate `__match_args__` for pattern matching                    |`@dataclass(match_args=False)` |
|`kw_only`     |`False`|All fields are keyword-only                                       |`@dataclass(kw_only=True)`     |
|`slots`       |`False`|Generate `__slots__`                                              |`@dataclass(slots=True)`       |
|`weakref_slot`|`False`|Add weak reference slot                                           |`@dataclass(weakref_slot=True)`|

### Examples

```python
# Immutable dataclass with ordering
@dataclass(frozen=True, order=True)
class Point:
    x: float
    y: float

p1 = Point(1, 2)
p2 = Point(3, 4)
print(p1 < p2)  # True (compares tuple of fields)

# Keyword-only fields
@dataclass(kw_only=True)
class Config:
    host: str
    port: int = 8080
    debug: bool = False

# Must use keywords
config = Config(host="localhost", debug=True)

# High-performance with slots
@dataclass(slots=True)
class FastPoint:
    x: float
    y: float
```

-----

### Field Function

### Basic Field Parameters

|Parameter        |Description                  |Example                      |
|-----------------|-----------------------------|-----------------------------|
|`default`        |Default value                |`field(default=42)`          |
|`default_factory`|Function to generate default |`field(default_factory=list)`|
|`init`           |Include in `__init__`        |`field(init=False)`          |
|`repr`           |Include in `__repr__`        |`field(repr=False)`          |
|`compare`        |Include in comparison methods|`field(compare=False)`       |
|`hash`           |Include in hash calculation  |`field(hash=False)`          |
|`kw_only`        |Keyword-only parameter       |`field(kw_only=True)`        |

### Field Examples

```python
from dataclasses import dataclass, field
from typing import List
import uuid
from datetime import datetime

@dataclass
class User:
    name: str
    # Mutable default using factory
    tags: List[str] = field(default_factory=list)
    
    # Auto-generated ID (not in init)
    id: str = field(default_factory=lambda: str(uuid.uuid4()), init=False)
    
    # Timestamp (not in repr for cleaner output)
    created_at: datetime = field(default_factory=datetime.now, repr=False)
    
    # Internal field (not compared)
    _cache: dict = field(default_factory=dict, compare=False, repr=False)
    
    # Keyword-only field
    admin: bool = field(default=False, kw_only=True)

# Usage
user = User("Alice", ["python", "data"], admin=True)
```

-----

### Generated Methods

### Automatic Method Generation

|Method                                |When Generated             |Customizable               |
|--------------------------------------|---------------------------|---------------------------|
|`__init__`                            |`init=True` (default)      |Via `init` parameter       |
|`__repr__`                            |`repr=True` (default)      |Via `repr` parameter       |
|`__eq__`                              |`eq=True` (default)        |Via `eq` parameter         |
|`__hash__`                            |Complex rules*             |Via `unsafe_hash` parameter|
|`__lt__`, `__le__`, `__gt__`, `__ge__`|`order=True`               |Via `order` parameter      |
|`__match_args__`                      |`match_args=True` (default)|Via `match_args` parameter |

*Hash generation rules:

- If `eq=False`: `__hash__` not generated
- If `eq=True` and `frozen=True`: `__hash__` generated
- If `eq=True` and `frozen=False`: `__hash__` set to `None`
- If `unsafe_hash=True`: `__hash__` always generated

### Custom Method Examples

```python
@dataclass
class BankAccount:
    account_number: str
    balance: float = 0.0
    
    def __post_init__(self):
        """Called after __init__"""
        if self.balance < 0:
            raise ValueError("Balance cannot be negative")
    
    def deposit(self, amount: float) -> None:
        if amount <= 0:
            raise ValueError("Deposit amount must be positive")
        self.balance += amount
    
    def __str__(self) -> str:
        """Custom string representation"""
        return f"Account {self.account_number}: ${self.balance:.2f}"
```

-----

### Type Hints & Validation

### Advanced Type Annotations

```python
from dataclasses import dataclass
from typing import Optional, List, Dict, Union, ClassVar
from enum import Enum

class Status(Enum):
    ACTIVE = "active"
    INACTIVE = "inactive"

@dataclass
class Product:
    # Class variable (not an instance field)
    tax_rate: ClassVar[float] = 0.08
    
    name: str
    price: float
    category: Optional[str] = None
    tags: List[str] = field(default_factory=list)
    metadata: Dict[str, Union[str, int]] = field(default_factory=dict)
    status: Status = Status.ACTIVE
    
    def __post_init__(self):
        # Validation
        if self.price < 0:
            raise ValueError("Price cannot be negative")
        if not self.name.strip():
            raise ValueError("Name cannot be empty")
```

### Generic Dataclasses

```python
from typing import TypeVar, Generic, List

T = TypeVar('T')

@dataclass
class Container(Generic[T]):
    items: List[T] = field(default_factory=list)
    
    def add(self, item: T) -> None:
        self.items.append(item)
    
    def get_first(self) -> Optional[T]:
        return self.items[0] if self.items else None

# Usage
int_container = Container[int]()
str_container = Container[str]()
```

-----

### Advanced Features

### Inheritance

```python
@dataclass
class Animal:
    name: str
    species: str

@dataclass
class Dog(Animal):
    breed: str
    species: str = "Canis lupus"  # Override default
    
    def bark(self) -> str:
        return f"{self.name} says woof!"

# Multiple inheritance with dataclasses
@dataclass
class Timestamp:
    created_at: datetime = field(default_factory=datetime.now)

@dataclass
class Pet(Animal, Timestamp):
    owner: str
```

### Post-Init Processing

```python
@dataclass
class Circle:
    radius: float
    area: float = field(init=False)
    circumference: float = field(init=False)
    
    def __post_init__(self):
        self.area = 3.14159 * self.radius ** 2
        self.circumference = 2 * 3.14159 * self.radius

# With InitVar for temporary values
from dataclasses import InitVar

@dataclass
class DatabaseConnection:
    host: str
    port: int
    username: str
    password: InitVar[str]  # Not stored as field
    connection: object = field(init=False)
    
    def __post_init__(self, password: str):
        # Use password to create connection, but don't store it
        self.connection = self._create_connection(self.host, self.port, 
                                                  self.username, password)
```

### Factory Functions

```python
def create_user(name: str, email: str, **kwargs) -> 'User':
    """Factory function for User creation with validation"""
    if '@' not in email:
        raise ValueError("Invalid email format")
    return User(name=name, email=email, **kwargs)

@dataclass
class User:
    name: str
    email: str
    active: bool = True
    
    @classmethod
    def from_dict(cls, data: dict) -> 'User':
        """Alternative constructor"""
        return cls(**data)
    
    @classmethod
    def create_admin(cls, name: str, email: str) -> 'User':
        """Factory method for admin users"""
        return cls(name=name, email=email, admin=True)
```

### Serialization

```python
import json
from dataclasses import dataclass, asdict, astuple

@dataclass
class Person:
    name: str
    age: int
    email: str
    
    def to_dict(self) -> dict:
        return asdict(self)
    
    def to_tuple(self) -> tuple:
        return astuple(self)
    
    def to_json(self) -> str:
        return json.dumps(self.to_dict())
    
    @classmethod
    def from_dict(cls, data: dict) -> 'Person':
        return cls(**data)
    
    @classmethod
    def from_json(cls, json_str: str) -> 'Person':
        return cls.from_dict(json.loads(json_str))

# Usage
person = Person("Alice", 30, "alice@example.com")
json_data = person.to_json()
restored_person = Person.from_json(json_data)
```

-----

### Utility Functions Reference

|Function                          |Purpose                     |Example                  |
|----------------------------------|----------------------------|-------------------------|
|`asdict(instance)`                |Convert to dictionary       |`asdict(person)`         |
|`astuple(instance)`               |Convert to tuple            |`astuple(person)`        |
|`fields(class_or_instance)`       |Get field information       |`fields(Person)`         |
|`is_dataclass(class_or_instance)` |Check if dataclass          |`is_dataclass(Person)`   |
|`make_dataclass(cls_name, fields)`|Create dataclass dynamically|See example below        |
|`replace(instance, **changes)`    |Create copy with changes    |`replace(person, age=31)`|

### Dynamic Dataclass Creation

```python
from dataclasses import make_dataclass, field

# Create dataclass dynamically
Point = make_dataclass('Point', [
    'x',
    'y', 
    ('z', float, field(default=0.0))
])

# Equivalent to:
# @dataclass
# class Point:
#     x: Any
#     y: Any
#     z: float = 0.0
```

### Field Introspection

```python
from dataclasses import fields

@dataclass
class Example:
    name: str
    age: int = 0
    tags: List[str] = field(default_factory=list)

# Examine fields
for f in fields(Example):
    print(f"Field: {f.name}, Type: {f.type}, Default: {f.default}")
    
# Check if class is a dataclass
print(is_dataclass(Example))  # True
print(is_dataclass(Example()))  # True
```

-----

### Best Practices

### 1. Use Type Hints Consistently

```python
# Good
@dataclass
class Good:
    name: str
    count: int
    rate: float

# Avoid
@dataclass
class Avoid:
    name  # No type hint
    count: int
    rate  # No type hint
```

### 2. Prefer `default_factory` for Mutable Defaults

```python
# Good
@dataclass
class Good:
    items: List[str] = field(default_factory=list)
    config: Dict[str, Any] = field(default_factory=dict)

# Dangerous - mutable default shared between instances
@dataclass
class Dangerous:
    items: List[str] = []  # DON'T DO THIS
```

### 3. Use `frozen=True` for Immutable Data

```python
@dataclass(frozen=True)
class ImmutablePoint:
    x: float
    y: float
    
# Can be used as dictionary keys
points = {ImmutablePoint(1, 2): "origin"}
```

### 4. Validation in `__post_init__`

```python
@dataclass
class ValidatedUser:
    name: str
    age: int
    email: str
    
    def __post_init__(self):
        if self.age < 0:
            raise ValueError("Age cannot be negative")
        if '@' not in self.email:
            raise ValueError("Invalid email format")
        if not self.name.strip():
            raise ValueError("Name cannot be empty")
```

### 5. Use Slots for Performance

```python
# For classes with many instances
@dataclass(slots=True)
class HighPerformance:
    x: float
    y: float
    z: float
    
# Reduces memory usage and improves attribute access speed
```

### 6. Combine with Properties

```python
@dataclass
class Temperature:
    _celsius: float = field(repr=False)
    
    @property
    def celsius(self) -> float:
        return self._celsius
    
    @celsius.setter
    def celsius(self, value: float) -> None:
        if value < -273.15:
            raise ValueError("Temperature below absolute zero")
        self._celsius = value
    
    @property
    def fahrenheit(self) -> float:
        return self._celsius * 9/5 + 32
    
    @property
    def kelvin(self) -> float:
        return self._celsius + 273.15
```

### 7. Pattern Matching (Python 3.10+)

```python
@dataclass
class Point:
    x: float
    y: float

def process_point(point: Point) -> str:
    match point:
        case Point(0, 0):
            return "Origin"
        case Point(x, 0):
            return f"On X-axis at {x}"
        case Point(0, y):
            return f"On Y-axis at {y}"
        case Point(x, y) if x == y:
            return f"On diagonal at ({x}, {y})"
        case Point(x, y):
            return f"Point at ({x}, {y})"
```

-----

### Common Patterns & Idioms

#### Builder Pattern with Dataclasses

```python
@dataclass
class HttpRequest:
    url: str
    method: str = "GET"
    headers: Dict[str, str] = field(default_factory=dict)
    params: Dict[str, str] = field(default_factory=dict)
    data: Optional[str] = None
    
    def add_header(self, key: str, value: str) -> 'HttpRequest':
        """Fluent interface for building requests"""
        new_headers = {**self.headers, key: value}
        return replace(self, headers=new_headers)
    
    def add_param(self, key: str, value: str) -> 'HttpRequest':
        new_params = {**self.params, key: value}
        return replace(self, params=new_params)

# Usage
request = (HttpRequest("https://api.example.com")
           .add_header("Authorization", "Bearer token")
           .add_param("limit", "10"))
```

#### Configuration Classes

```python
@dataclass(frozen=True)
class DatabaseConfig:
    host: str = "localhost"
    port: int = 5432
    database: str = "myapp"
    username: str = "user"
    password: str = field(repr=False, default="")  # Don't print password
    
    @property
    def connection_string(self) -> str:
        return f"postgresql://{self.username}:{self.password}@{self.host}:{self.port}/{self.database}"

@dataclass(frozen=True)
class AppConfig:
    database: DatabaseConfig = field(default_factory=DatabaseConfig)
    debug: bool = False
    log_level: str = "INFO"
```


## Python Packages
We can import python files as modules which is beneficial in terms of software development efforts including multiple source files structured within directories. We start with the following structure of code
```shell
package/
└── src/
    └── utils
        ├── __init__.py
        └── readwrite.py
    main.py
```
The readwrite module looks as follows
```Python
# src/utils/readwrite.py
def rw_function():
   pass
```
Within the main file, the readwrite module can be import as follows
```Python
# src/main.py
from utils.readwrite import rw_function
```
The __init__.py file indicates that the directory is considered as a Python package. The __init__.py file can contain the imports of modules, for instance
```Python
# src/utils/__init__.py
from .readwrite import rw_function
```
Then, within the main.py file we can simply import the module as follows
```Python
# src/main.py
from utils import readwrite
```



## Virtual Environments
There exist "venv" or "virtualenv" as virtual environment packages. The installation of "virtualenv" can be done via pip
```shell
python -m pip install virtualenv
```
### Venv
```shell
# UNIX/Linux
python -m venv myvenv         # Create
source myvenv/bin/activate    # Activate
deactivate                    # Deactivate

# Windows
python -m venv myvenv         # Create
.\myvenv\Scripts\activate     # Activate
deactivate                    # Deactivate
```
### Virtualenv
```shell
# UNIX/Linux
virtualenv myvenv             # Create
source myvenv/bin/activate    # Activate
deactivate                    # Deactivate

# Windows
python -m venv myvenv         # Create
.\myvenv\Scripts\activate     # Activate
deactivate                    # Deactivate
```


### Pydantic
The basic element of Pydantic is the model creation and validation
```Python
from pydantic import BaseModel
from typing import Optional, Literal

class User(BaseModel):
    id: int
    name: str
    age: int
    email: str
    employment_status: Literal['working', 'retired']
    is_active: bool = True
    information: Optional[str] = None

# Example Usage
user = User(id=1, name="Alice", age=25, email="alice@example.com", employment_status="working")

# Conversion to Python dictionary
user.dict()
```

#### Installation
```python
pip install pydantic
```

#### Simple Model
```python
from pydantic import BaseModel

class User(BaseModel):
    id: int
    name: str
    email: str
    active: bool = True  # Default value
```

#### Type Validation
```python
user = User(id=1, name="John Doe", email="john@example.com")  # Valid
user = User(id="1", name="John Doe", email="john@example.com")  # Coerces "1" to int(1)

try:
    User(id="not-an-int", name="John Doe", email="john@example.com")
except:
    print("Validation error: id must be an integer")
```

#### Model Methods
```python
# Dictionary conversion
user_dict = user.model_dump()  # In v2+, was .dict() in v1
user_json = user.model_dump_json()  # In v2+, was .json() in v1

# Copy and update
user2 = user.model_copy(update={"name": "Jane Doe"})  # In v2+, was .copy() in v1
```

#### Field Types and Validation

#### Common Types
```python
from datetime import datetime
from typing import List, Dict, Optional, Union
from uuid import UUID
from pydantic import BaseModel, EmailStr, HttpUrl, conint, confloat

class AdvancedUser(BaseModel):
    id: int
    name: str
    email: EmailStr  # Validates email format
    website: HttpUrl  # Validates URL format
    tags: List[str] = []
    metadata: Dict[str, str] = {}
    last_login: Optional[datetime] = None
    score: Union[int, float] = 0.0
    age: conint(ge=0, lt=120)  # Constrained integer
    rating: confloat(ge=0, le=5)  # Constrained float
    user_id: UUID  # UUID validation
```

#### Field Configuration
```python
from pydantic import BaseModel, Field

class Product(BaseModel):
    id: int
    name: str = Field(..., min_length=3, max_length=50)
    price: float = Field(gt=0, description="Price must be positive")
    description: Optional[str] = Field(
        None,
        title="Product description",
        max_length=1000,
        examples=["A great product"]
    )
    sku: str = Field(regex=r"^[A-Z]{3}-\d{4}$")
```

#### Advanced Validation

#### Validators
```python
from pydantic import BaseModel, field_validator, model_validator

class Order(BaseModel):
    id: int
    items: List[str]
    total: float
    
    # Field validator (single field)
    @field_validator('items')
    def check_items_not_empty(cls, v):
        if not v:
            raise ValueError('Order must have at least one item')
        return v
    
    # Model validator (multiple fields)
    @model_validator(mode='after')
    def check_total(self):
        if len(self.items) > 5 and self.total < 100:
            raise ValueError('Large orders should have higher total')
        return self
```

#### Custom Types
```python
from pydantic import BaseModel, GetCoreSchemaHandler
from pydantic.json_schema import JsonSchemaValue
from pydantic_core import CoreSchema, core_schema

class ISBN10:
    def __init__(self, value: str):
        if not self._is_valid(value):
            raise ValueError(f"Invalid ISBN-10: {value}")
        self.value = value
        
    @staticmethod
    def _is_valid(value: str) -> bool:
        # Simple validation for example
        return len(value) == 10
        
    def __repr__(self) -> str:
        return f"ISBN10({self.value!r})"
        
    @classmethod
    def __get_pydantic_core_schema__(
        cls, _source_type, _handler: GetCoreSchemaHandler
    ) -> CoreSchema:
        return core_schema.with_info_plain_validator_function(
            cls._validate,
            serialization=core_schema.str_serializer(),
            type=cls,
        )
    
    @classmethod
    def _validate(cls, value, info):
        if isinstance(value, cls):
            return value
        if isinstance(value, str):
            return cls(value)
        raise ValueError(f"Cannot convert {value} to {cls.__name__}")

class Book(BaseModel):
    title: str
    isbn: ISBN10
```

#### Nested Models

#### Model Composition
```python
from pydantic import BaseModel
from typing import List

class Address(BaseModel):
    street: str
    city: str
    country: str
    postal_code: str

class User(BaseModel):
    id: int
    name: str
    addresses: List[Address]

# Usage
user = User(
    id=1,
    name="John",
    addresses=[
        {"street": "123 Main St", "city": "New York", "country": "USA", "postal_code": "10001"},
        {"street": "456 Park Ave", "city": "Boston", "country": "USA", "postal_code": "02108"}
    ]
)
```

#### Recursive Models
```python
from pydantic import BaseModel
from typing import List, Optional

class Comment(BaseModel):
    id: int
    text: str
    replies: List['Comment'] = []

Comment.model_rebuild()  # Required for recursive models in v2
```

#### Config and Settings

#### Model Config
```python
from pydantic import BaseModel, ConfigDict
from datetime import datetime

class User(BaseModel):
    model_config = ConfigDict(
        extra='forbid',  # Raise error if extra fields provided
        str_strip_whitespace=True,  # Strip whitespace from strings
        validate_assignment=True,  # Validate attributes on assignment
        frozen=False,  # If True, models are immutable
        populate_by_name=True,  # Allow population by field name and alias
        json_schema_extra={
            'examples': [
                {
                    'id': 123,
                    'name': 'John Doe',
                    'signup_ts': '2020-01-01T00:00:00Z'
                }
            ]
        }
    )
    
    id: int
    name: str
    signup_ts: datetime
```

#### Settings Management
```python
from pydantic import BaseModel, Field
from pydantic_settings import BaseSettings
from typing import Optional

class DatabaseSettings(BaseModel):
    host: str
    port: int
    user: str
    password: str
    
class AppSettings(BaseSettings):
    app_name: str = "My App"
    debug: bool = False
    db: DatabaseSettings
    log_level: str = Field('INFO', env='LOG_LEVEL')
    
    model_config = {
        'env_nested_delimiter': '__',
        'env_file': '.env',
        'env_file_encoding': 'utf-8',
        'env_prefix': 'MYAPP_',
    }

# Usage
# Environment variables like:
# MYAPP_APP_NAME=MyApp
# MYAPP_DB__HOST=localhost
settings = AppSettings()
```

#### Serialization & Deserialization

#### JSON Schema Generation
```python
from pydantic import BaseModel
from typing import List

class Item(BaseModel):
    name: str
    price: float

class Order(BaseModel):
    id: int
    items: List[Item]

# Generate JSON schema
schema = Order.model_json_schema()
print(schema)
```

#### Custom Serialization
```python
from pydantic import BaseModel, field_serializer, field_validator
from datetime import datetime
import json

class LogEntry(BaseModel):
    timestamp: datetime
    level: str
    message: str

    @field_serializer('timestamp')
    def serialize_timestamp(self, value):
        return value.strftime("%Y-%m-%d %H:%M:%S")
        
    @field_serializer('level')
    def serialize_level(self, value):
        return value.upper()
```

#### Computed Fields
```python
from pydantic import BaseModel, computed_field
from typing import List

class Order(BaseModel):
    items: List[dict]
    tax_rate: float = 0.1
    
    @computed_field
    def subtotal(self) -> float:
        return sum(item.get('price', 0) for item in self.items)
        
    @computed_field
    def tax(self) -> float:
        return self.subtotal * self.tax_rate
        
    @computed_field
    def total(self) -> float:
        return self.subtotal + self.tax
```

#### Best Practices

#### Error Handling
```python
from pydantic import BaseModel, ValidationError

class User(BaseModel):
    id: int
    email: str

try:
    user = User(id="not-an-int", email="invalid-email")
except ValidationError as e:
    print(f"Validation errors: {e.errors()}")
    # Access specific errors
    for error in e.errors():
        print(f"Field: {error['loc'][0]}, Error: {error['msg']}")
```

#### Type Annotations
```python
# Prefer these imports for better type checking
from typing import Dict, List, Optional, Union, Any, Literal
from pydantic import BaseModel

# Use specific types when possible
class Config(BaseModel):
    mode: Literal["development", "testing", "production"]
    flags: Dict[str, bool]
    counts: Dict[str, int]
    # Avoid using Any when possible
    # metadata: Dict[str, Any]  # Less ideal
    metadata: Dict[str, Union[str, int, bool]]  # Better
```

#### Performance Tips
```python
from pydantic import BaseModel, Field, model_validator

# 1. Use validators sparingly - they impact performance
class EfficientModel(BaseModel):
    # 2. Use default values where appropriate
    count: int = 0
    
    # 3. Use Field constraints instead of validators when possible
    name: str = Field(..., min_length=2, max_length=50)
    
    # 4. For complex validation, use model_validator instead of multiple field validators
    @model_validator(mode='after')
    def validate_model(self):
        # Validate related fields together
        return self
```

#### Pydantic v2 Features

#### Schema Modes
```python
from pydantic import BaseModel

class User(BaseModel):
    model_config = {
        # Choose validation strictness mode
        'strict': False,  # Coerce types when possible (default)
        # 'strict': True,  # Strict type checking, no coercion
    }
    id: int
    name: str
```

#### RootModel
```python
from pydantic import RootModel
from typing import List, Dict

# For when your model is just a container for a single value
IntList = RootModel[List[int]]
numbers = IntList([1, 2, 3])
print(numbers.root)  # [1, 2, 3]
print(numbers.model_dump())  # [1, 2, 3]

# For mapping types
UserDict = RootModel[Dict[str, str]]
users = UserDict({"admin": "John", "user1": "Jane"})
```

#### Type Adapters
```python
from pydantic import TypeAdapter
from typing import List

# Validate without creating a model class
IntListValidator = TypeAdapter(List[int])
validated = IntListValidator.validate_python(["1", "2", "3"])  # [1, 2, 3]

# JSON parsing
json_data = '[1, 2, "3"]'
validated_json = IntListValidator.validate_json(json_data)
```

#### Testing with Pydantic

#### Schema Tests
```python
from pydantic import BaseModel, Field
import pytest

class Product(BaseModel):
    id: int
    name: str = Field(..., min_length=3)
    price: float = Field(..., gt=0)

def test_valid_product():
    product = Product(id=1, name="Test Product", price=19.99)
    assert product.id == 1
    assert product.name == "Test Product"
    assert product.price == 19.99

def test_invalid_product():
    with pytest.raises(ValueError):
        Product(id=1, name="TS", price=19.99)  # Name too short
    
    with pytest.raises(ValueError):
        Product(id=1, name="Test Product", price=-5)  # Negative price
```


### Pytest
Pytest is a robust testing framework for Python known for its  simple syntax, scalability, and powerful features like fixtures, parameterization, and plugins.

In order to install pytest we can just use the pip package manager and run the following command
```shell
pip install pytest
```

The execution of all pytest components can be done by running the following command
```shell
pytest
```
Alternatively, one specifiy test modules can be run
```shell
pytest test_file.py
```
Using the verbose flag we can give more output information
```shell
pytest -v
```

The basic concept for discovering the relevant test components is to identify the filenames that start with ```test_``` or end with ```_test.py```. 
The assert statement can be used to verify expressions in the pytest components.

A simple pytest defined in a test module with name ```test_component.py``` is given below
```python
import pytest

def test_component():
    assert 1 + 1 == 2
```

Tests can also be grouped within classes
```python
import pytest

class TestMathOperations:
    def test_addition(self):
        assert 1 + 2 == 2
    def test_subtraction(self):
        assert 2 - 1 == 1
```

Fixtures provide setup and teardown code for tests. They enhance test modularity and reusability.

```python
import pytest

@pytest.fixture
def sample_data():
    return {"key": "value"}
```

#### Installation & Setup

```bash
pip install pytest
pip install pytest-cov  # For coverage reports
```

#### Basic Test Structure

```python
# test_example.py
def test_simple_assertion():
    assert 1 + 1 == 2

def test_with_message():
    assert 1 == 2, "This will show when the test fails"
```

#### Running Tests

```bash
# Run all tests
pytest

# Run specific file
pytest test_example.py

# Run specific test
pytest test_example.py::test_simple_assertion

# Run tests containing specific substring in name
pytest -k "simple"

# Run tests matching specific markers
pytest -m "slow"

# Verbose output
pytest -v
```

#### Assertions

```python
# Equality
assert value == expected

# Greater than/less than
assert value > expected
assert value <= expected

# Boolean checks
assert is_valid
assert not is_empty

# String contains
assert "substring" in some_string

# List/dict contains
assert item in some_list
assert key in some_dict

# Exception check via context manager
with pytest.raises(ValueError):
    function_that_raises()

# Match exception message
with pytest.raises(ValueError, match="expected error message"):
    function_that_raises()

# Assert almost equal (for floats)
assert abs(0.1 + 0.2 - 0.3) < 0.0001
# Better alternative with pytest.approx
assert 0.1 + 0.2 == pytest.approx(0.3)
```

#### Fixtures

```python
import pytest

# Basic fixture
@pytest.fixture
def sample_data():
    return {"key": "value", "number": 42}

def test_using_fixture(sample_data):
    assert sample_data["number"] == 42

# Fixture with setup and teardown
@pytest.fixture
def db_connection():
    # Setup
    connection = create_connection()
    yield connection
    # Teardown
    connection.close()

# Fixture with scope
@pytest.fixture(scope="module")
def expensive_operation():
    # Runs once per module
    result = perform_expensive_setup()
    return result

# Parametrized fixture
@pytest.fixture(params=[1, 2, 3])
def test_data(request):
    return request.param

# Using built-in fixtures
def test_with_tmp_path(tmp_path):
    file_path = tmp_path / "test.txt"
    file_path.write_text("content")
    assert file_path.read_text() == "content"
```

#### Parameterized Tests

```python
@pytest.mark.parametrize("input,expected", [
    (1, 1),
    (2, 4),
    (3, 9),
    (4, 16),
])
def test_square(input, expected):
    assert input * input == expected

# Multiple parameters
@pytest.mark.parametrize("x", [1, 2])
@pytest.mark.parametrize("y", [3, 4])
def test_product(x, y):
    # Will test all combinations: (1,3), (1,4), (2,3), (2,4)
    pass
```

#### Markers

```python
# Skip test
@pytest.mark.skip(reason="Not implemented yet")
def test_future_feature():
    pass

# Skip based on condition
@pytest.mark.skipif(sys.version_info < (3, 8), reason="Requires Python 3.8+")
def test_new_feature():
    pass

# Mark test as expected to fail
@pytest.mark.xfail
def test_known_bug():
    assert False

# Custom markers (register in pytest.ini)
@pytest.mark.slow
def test_slow_operation():
    pass
```

#### Configuration (pytest.ini)

```ini
[pytest]
# Default command line options
addopts = -v --cov=myapp

# Register custom markers
markers =
    slow: marks tests as slow
    integration: marks tests as integration tests

# Directories to search for tests
testpaths = tests integration_tests

# Pattern for test modules
python_files = test_*.py *_test.py

# Pattern for test functions
python_functions = test_*

# Pattern for test classes
python_classes = Test*
```

#### Mocking

```python
# Using pytest-mock fixture
def test_with_mock(mocker):
    # Mock a function or method
    mock_function = mocker.patch('module.function')
    mock_function.return_value = 'mocked result'
    
    # Mock an attribute
    mocker.patch('module.Class.attribute', 'mocked value')
    
    # Mock with side effect (function or exception)
    mock_func = mocker.patch('module.function')
    mock_func.side_effect = ValueError("expected error")
    
    # Assert mock was called
    result = function_under_test()
    mock_function.assert_called_once()
    mock_function.assert_called_with(expected_arg)
```

#### Test Classes

```python
class TestCalculator:
    # Class-level fixture
    @pytest.fixture
    def calculator(self):
        return Calculator()
    
    def test_addition(self, calculator):
        assert calculator.add(1, 2) == 3
    
    def test_subtraction(self, calculator):
        assert calculator.subtract(5, 3) == 2
```

#### Pytest Hooks

```python
# In conftest.py
def pytest_addoption(parser):
    parser.addoption("--env", default="dev", help="Environment to run tests against")

def pytest_configure(config):
    # Add a custom marker
    config.addinivalue_line("markers", "env(name): mark test to run only on named environment")

def pytest_collection_modifyitems(config, items):
    # Skip tests based on custom logic
    env = config.getoption("--env")
    for item in items:
        if "prod_only" in item.keywords and env != "prod":
            item.add_marker(pytest.mark.skip(reason=f"Requires prod environment, current: {env}"))
```

#### Test Fixtures (conftest.py)

Shared fixtures can be placed in a `conftest.py` file:

```python
# conftest.py
import pytest

@pytest.fixture(scope="session")
def app():
    return create_app()

@pytest.fixture
def client(app):
    return app.test_client()
```

#### Best Practices

1. **Name tests descriptively**: Use long, descriptive names that explain the purpose and expected outcome
2. **One assertion per test**: Keep tests focused on a single behavior
3. **Use pytest.approx()** for floating-point comparisons
4. **Parametrize repetitive tests**: Use `@pytest.mark.parametrize` for data-driven tests
5. **Use fixtures for setup/teardown**: Keep tests clean by moving setup code to fixtures
6. **Keep tests independent**: Tests should not depend on each other
7. **Avoid mutable fixture state**: Be careful when fixtures have mutable state
8. **Use markers for categorization**: Group tests with custom markers for selective running
9. **Follow AAA pattern**: Arrange, Act, Assert structure for test clarity
10. **Minimize test duplication**: Reuse fixtures and helper functions

#### Advanced Patterns

#### Factory fixtures

```python
@pytest.fixture
def make_user():
    def _make_user(name="John", age=30):
        return {"name": name, "age": age}
    return _make_user

def test_user_factory(make_user):
    user1 = make_user(name="Alice")
    user2 = make_user(age=25)
    assert user1["name"] == "Alice"
    assert user2["age"] == 25
```

#### Monkeypatching

```python
def test_env_var(monkeypatch):
    monkeypatch.setenv("API_KEY", "test_key")
    assert os.environ["API_KEY"] == "test_key"

def test_patched_function(monkeypatch):
    def mock_read():
        return "mocked data"
    
    monkeypatch.setattr("module.read_file", mock_read)
    assert module.read_file() == "mocked data"
```

#### Autouse fixtures

```python
@pytest.fixture(autouse=True)
def setup_database():
    # Runs before every test
    db.setup()
    yield
    # Runs after every test
    db.teardown()
```

#### Coverage reporting

```bash
# Generate coverage report
pytest --cov=myapp

# Generate HTML report
pytest --cov=myapp --cov-report=html

# Enforce minimum coverage
pytest --cov=myapp --cov-fail-under=90
```

### Singleton patterns

#### Classic Implementation (Module-Level)
```python
class Singleton:
    _instance = None
    
    def __new__(cls, *args, **kwargs):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
        return cls._instance
```

#### Module-Level Singleton
```python
# In singleton.py
_config = None

def get_config():
    global _config
    if _config is None:
        _config = {}  # Or load from file, etc.
    return _config
```

#### Decorator Implementation
```python
def singleton(cls):
    instances = {}
    
    def get_instance(*args, **kwargs):
        if cls not in instances:
            instances[cls] = cls(*args, **kwargs)
        return instances[cls]
    
    return get_instance

@singleton
class Config:
    def __init__(self):
        self.data = {}
```

#### Metaclass Implementation
```python
class SingletonMeta(type):
    _instances = {}
    
    def __call__(cls, *args, **kwargs):
        if cls not in cls._instances:
            cls._instances[cls] = super().__call__(*args, **kwargs)
        return cls._instances[cls]

class Logger(metaclass=SingletonMeta):
    def __init__(self):
        self.logs = []
```

## Advanced Patterns

#### Thread-Safe Singleton
```python
import threading

class ThreadSafeSingleton:
    _instance = None
    _lock = threading.Lock()
    
    def __new__(cls, *args, **kwargs):
        with cls._lock:
            if cls._instance is None:
                cls._instance = super().__new__(cls)
        return cls._instance
```

#### Lazy Initialization
```python
class LazySingleton:
    __instance = None
    
    @classmethod
    def get_instance(cls):
        if cls.__instance is None:
            cls.__instance = cls()
        return cls.__instance
    
    def __init__(self):
        if self.__class__.__instance is not None:
            raise Exception("This class is a singleton!")
        self.__class__.__instance = self
```

#### Borg Pattern (Shared State)
```python
class Borg:
    _shared_state = {}
    
    def __init__(self):
        self.__dict__ = self._shared_state

class ConfigBorg(Borg):
    def __init__(self):
        Borg.__init__(self)
        if not hasattr(self, 'data'):
            self.data = {}
```

#### Multiton Pattern
```python
class Multiton:
    _instances = {}
    
    def __new__(cls, key, *args, **kwargs):
        if key not in cls._instances:
            cls._instances[key] = super().__new__(cls)
        return cls._instances[key]
    
    def __init__(self, key, *args, **kwargs):
        pass
```

#### Real-World Examples

#### Database Connection Pool
```python
class DatabaseConnection:
    _instance = None
    
    def __new__(cls, *args, **kwargs):
        if cls._instance is None:
            cls._instance = super().__new__(cls)
            cls._instance.pool = []
        return cls._instance
    
    def get_connection(self):
        if not self.pool:
            self.pool.append(self._create_connection())
        return self.pool.pop()
    
    def release_connection(self, conn):
        self.pool.append(conn)
    
    def _create_connection(self):
        # Implementation for creating actual database connection
        return "Connection"
```

#### Logger Implementation
```python
class Logger(metaclass=SingletonMeta):
    def __init__(self):
        self.log_level = "INFO"
        self.format = "%(asctime)s - %(name)s - %(levelname)s - %(message)s"
        self.handlers = []
    
    def log(self, message, level="INFO"):
        if self._should_log(level):
            print(f"[{level}] {message}")
    
    def _should_log(self, level):
        levels = {"DEBUG": 0, "INFO": 1, "WARNING": 2, "ERROR": 3, "CRITICAL": 4}
        return levels.get(level, 0) >= levels.get(self.log_level, 0)
```

#### Configuration Manager
```python
@singleton
class ConfigManager:
    def __init__(self, config_file=None):
        self.config = {}
        if config_file:
            self.load_config(config_file)
    
    def load_config(self, config_file):
        # Implementation for loading config from file
        self.config = {"key": "value"}  # Placeholder
    
    def get(self, key, default=None):
        return self.config.get(key, default)
    
    def set(self, key, value):
        self.config[key] = value
```

#### Best Practices

#### Do's:
- Use singletons sparingly for resources that genuinely need global access
- Consider dependency injection as an alternative
- Make singleton classes immutable when possible
- Document clearly that a class is a singleton
- Use thread-safe implementations in multi-threaded applications
- Consider using Python's built-in modules for singleton-like behavior

#### Don'ts:
- Don't use singletons for storing mutable state that changes frequently
- Avoid using singletons as a substitute for proper object-oriented design
- Don't create tight coupling between components through singletons
- Avoid making singleton classes with complex inheritance hierarchies
- Don't use singletons for objects that should be created on demand

#### Testing Considerations

#### Mocking Singletons
```python
import unittest
from unittest.mock import patch

# Original singleton
class Config(metaclass=SingletonMeta):
    def __init__(self):
        self.data = {"env": "production"}

# Test class
class TestWithSingleton(unittest.TestCase):
    @patch.object(Config, 'data', {"env": "testing"})
    def test_singleton(self):
        config = Config()
        self.assertEqual(config.data["env"], "testing")
```

#### Resetting Singletons for Tests
```python
def reset_singleton(SingletonClass):
    SingletonClass._instances = {}

# In test
def test_singleton_reset():
    config1 = Config()
    config1.data["test"] = "value"
    
    reset_singleton(SingletonMeta)
    
    config2 = Config()
    assert "test" not in config2.data
```

#### When to Use Singletons

#### Appropriate Use Cases:
- Configuration management
- Logging services
- Connection pools
- Cache management
- Device access (printers, etc.)
- Resource managers

#### Alternatives to Consider:
- Dependency injection
- Factory patterns
- Service locator pattern
- Module-level functions
- Global variables (in simple cases)



## Standard Library

### Itertools

The `itertools` module provides functions creating iterators for efficient looping. These are memory-efficient since they work with iterators and generators rather than creating entire sequences in memory.

#### Basic Infinite Iterators

| Function | Description | Example |
|----------|-------------|---------|
| `count(start, step)` | Count from `start` by `step` | `count(10, 2)` → 10, 12, 14, ... |
| `cycle(iterable)` | Cycle through elements repeatedly | `cycle('ABC')` → A, B, C, A, B, C, ... |
| `repeat(elem, n=None)` | Repeat `elem` `n` times or indefinitely | `repeat(10, 3)` → 10, 10, 10 |

#### Iterator Terminating Functions

| Function | Description | Example |
|----------|-------------|---------|
| `accumulate(iterable, func=add)` | Running totals (or other function) | `accumulate([1,2,3,4])` → 1, 3, 6, 10 |
| `chain(*iterables)` | Chain multiple iterables together | `chain('ABC', 'DEF')` → A, B, C, D, E, F |
| `chain.from_iterable(iterable)` | Chain from a single iterable of iterables | `chain.from_iterable(['ABC', 'DEF'])` → A, B, C, D, E, F |
| `compress(data, selectors)` | Filter elements where selector is true | `compress('ABCD', [1,0,1,0])` → A, C |
| `dropwhile(pred, seq)` | Drop items while predicate is true | `dropwhile(lambda x: x<5, [1,3,6,2])` → 6, 2 |
| `takewhile(pred, seq)` | Take items while predicate is true | `takewhile(lambda x: x<5, [1,3,6,2])` → 1, 3 |
| `filterfalse(pred, seq)` | Elements that don't satisfy predicate | `filterfalse(lambda x: x%2, range(5))` → 0, 2, 4 |
| `groupby(iterable, key=None)` | Group consecutive elements | `[(k,list(g)) for k,g in groupby('AAAABBBCCD')]` → ('A',['A','A','A','A']), ('B',['B','B','B']), ... |
| `islice(seq, start, stop, step)` | Slice an iterator | `islice('ABCDEF', 2, None)` → C, D, E, F |
| `starmap(func, seq)` | Map function accepting multiple args | `starmap(pow, [(2,5), (3,2)])` → 32, 9 |
| `tee(iterable, n=2)` | Create n independent iterators | `a, b = tee([1,2,3])` creates two iterators |
| `zip_longest(*iterables, fillvalue=None)` | Zip, using fillvalue for shorter iterables | `zip_longest('ABCD', 'xy', fillvalue='-')` → (A,x), (B,y), (C,-), (D,-) |

#### Combinatoric Iterators

| Function | Description | Example |
|----------|-------------|---------|
| `product(*iterables, repeat=1)` | Cartesian product | `product('AB', 'CD')` → (A,C), (A,D), (B,C), (B,D) |
| `permutations(iterable, r=None)` | All possible r-length permutations | `permutations('ABC', 2)` → (A,B), (A,C), (B,A), (B,C), (C,A), (C,B) |
| `combinations(iterable, r)` | All possible r-length combinations | `combinations('ABC', 2)` → (A,B), (A,C), (B,C) |
| `combinations_with_replacement(iterable, r)` | r-length combinations with replacement | `combinations_with_replacement('ABC', 2)` → (A,A), (A,B), (A,C), (B,B), (B,C), (C,C) |

#### Advanced itertools Techniques

#### Creating Custom Iterators

```python
def chunked(iterable, n):
    """Yield successive n-sized chunks from iterable."""
    it = iter(iterable)
    while True:
        chunk = tuple(islice(it, n))
        if not chunk:
            return
        yield chunk

# Example: chunked('ABCDEFG', 3) → (A,B,C), (D,E,F), (G,)
```

#### Flattening Nested Iterables

```python
def flatten(list_of_lists):
    """Flatten one level of nesting."""
    return chain.from_iterable(list_of_lists)

# Example: flatten([[1, 2], [3, 4]]) → 1, 2, 3, 4
```

#### Sliding Window

```python
def sliding_window(iterable, n):
    """Create a sliding window of size n over iterable."""
    it = iter(iterable)
    window = deque(islice(it, n), maxlen=n)
    if len(window) == n:
        yield tuple(window)
    for x in it:
        window.append(x)
        yield tuple(window)

# Example: sliding_window('ABCDE', 3) → (A,B,C), (B,C,D), (C,D,E)
```

#### Roundrobin

```python
def roundrobin(*iterables):
    """Take elements from each iterable in a cyclic fashion."""
    iterators = cycle(iter(it) for it in iterables)
    pending = len(iterables)
    while pending:
        try:
            for i in iterators:
                yield next(i)
        except StopIteration:
            pending -= 1
            iterators = cycle(islice(iterators, pending))

# Example: roundrobin('ABC', 'D', 'EF') → A, D, E, B, F, C
```


### Functools

The `functools` module provides higher-order functions and operations on callable objects.

#### Core Functions

| Function | Description | Example |
|----------|-------------|---------|
| `lru_cache(maxsize=128, typed=False)` | Least-recently-used cache decorator | `@lru_cache(maxsize=None)` |
| `cache(user_function)` | Simple unbounded cache decorator | `@cache` |
| `partial(func, *args, **kwargs)` | Freeze some arguments of a function | `partial(int, base=2)('10')` → 2 |
| `reduce(function, iterable, initializer=None)` | Apply function cumulatively to items | `reduce(lambda x, y: x+y, [1,2,3,4])` → 10 |
| `total_ordering` | Fill in missing comparison methods | `@total_ordering` class with `__eq__` and `__lt__` |
| `singledispatch` | Function dispatcher based on arg type | `@singledispatch` |
| `singledispatchmethod` | Method dispatcher based on arg type | `@singledispatchmethod` |
| `wraps(wrapped)` | Update wrapper function to look like wrapped | `@wraps(wrapped_function)` |

#### Advanced functools Techniques

#### Memoization with lru_cache

```python
from functools import lru_cache

@lru_cache(maxsize=None)
def fibonacci(n):
    if n < 2:
        return n
    return fibonacci(n-1) + fibonacci(n-2)

# Fast fibonacci calculation due to memoization
# fibonacci(100) is now efficient
```

#### Creating Partial Functions

```python
from functools import partial

# Create a base-2 int conversion function
binary_to_int = partial(int, base=2)
hex_to_int = partial(int, base=16)

binary_to_int('10010')  # 18
hex_to_int('12')        # 18
```

#### Single Dispatch for Type-Based Function Overloading

```python
from functools import singledispatch

@singledispatch
def process(obj):
    return f"Default: {obj}"

@process.register
def _(obj: list):
    return f"List with {len(obj)} items"

@process.register
def _(obj: str):
    return f"String with {len(obj)} characters"

process(10)        # "Default: 10"
process([1, 2, 3]) # "List with 3 items"
process("hello")   # "String with 5 characters"
```

#### Preserving Metadata in Decorators

```python
from functools import wraps

def my_decorator(func):
    @wraps(func)  # Preserves __name__, __doc__, etc.
    def wrapper(*args, **kwargs):
        """Wrapper doc"""
        print("Before function call")
        result = func(*args, **kwargs)
        print("After function call")
        return result
    return wrapper

@my_decorator
def example():
    """Example docstring"""
    print("Function called")

# example.__name__ will be "example" not "wrapper"
# example.__doc__ will be "Example docstring" not "Wrapper doc"
```

#### Best Practices

1. **Memory Efficiency**:
   - Use itertools functions instead of creating large lists in memory
   - Chain iterators instead of concatenating lists
   - Use generator expressions with itertools

2. **Performance Optimization**:
   - Apply `lru_cache` to recursive or expensive functions
   - Use `partial` to avoid repeating arguments in frequent calls
   - Prefer `islice` over slicing when working with large iterables

3. **Code Clarity**:
   - Use named functions with `partial` to document intent
   - Document the expected types when using `singledispatch`
   - Use `wraps` in all decorators to maintain function metadata

4. **Common Patterns**:
   - Filtering: `filter()` + `filterfalse()` is better than two separate filters
   - Grouping: Use `groupby()` with sorted data for complete grouping
   - Batching: Use `islice()` with chunking for memory-efficient batch processing

5. **Debugging Tips**:
   - Use `list()` to materialize iterators for debugging
   - Check `lru_cache.cache_info()` to verify cache effectiveness
   - Remember that `tee()` creates iterators that share tail, so avoid advancing one without the others



### Unittest

```bash
# unittest is part of the Python standard library - no installation needed!

# For mocking (pre-Python 3.3)
pip install mock  # Not needed for Python 3.3+, as unittest.mock is included
```

#### Basic Test Structure

```python
import unittest

class TestExample(unittest.TestCase):
    def test_simple_assertion(self):
        self.assertEqual(1 + 1, 2)
    
    def test_with_message(self):
        self.assertEqual(1, 1, "This message shows when the test fails")
```

#### Running Tests

```bash
# Run a test file
python -m unittest test_example.py

# Run a specific test class
python -m unittest test_example.TestExample

# Run a specific test method
python -m unittest test_example.TestExample.test_simple_assertion

# Run with discovery (finds all tests)
python -m unittest discover

# Run with discovery in a specific directory
python -m unittest discover -s tests

# Run with discovery following a specific pattern
python -m unittest discover -s tests -p "*_test.py"

# Run with verbose output
python -m unittest -v
```

#### Test Organization

```python
import unittest

# Setup and teardown
class TestWithSetup(unittest.TestCase):
    def setUp(self):
        # Runs before each test
        self.value = 10
    
    def tearDown(self):
        # Runs after each test
        pass
    
    @classmethod
    def setUpClass(cls):
        # Runs once before all tests in the class
        cls.shared_resource = open("test_file.txt", "w")
    
    @classmethod
    def tearDownClass(cls):
        # Runs once after all tests in the class
        cls.shared_resource.close()
        
    def test_value(self):
        self.assertEqual(self.value, 10)
```

#### Assertions

```python
def test_assertions(self):
    # Equality
    self.assertEqual(expected, actual)
    self.assertNotEqual(expected, actual)
    
    # Identity
    self.assertIs(expected, actual)  # Checks if objects are the same (is)
    self.assertIsNot(expected, actual)
    
    # Boolean checks
    self.assertTrue(expression)
    self.assertFalse(expression)
    
    # None checks
    self.assertIsNone(value)
    self.assertIsNotNone(value)
    
    # Type checks
    self.assertIsInstance(obj, cls)
    self.assertNotIsInstance(obj, cls)
    
    # Membership checks
    self.assertIn(member, container)
    self.assertNotIn(member, container)
    
    # String checks
    self.assertRegex(string, regex)
    self.assertNotRegex(string, regex)
    
    # Numeric comparisons
    self.assertAlmostEqual(first, second, places=7)  # For floating point
    self.assertNotAlmostEqual(first, second, places=7)
    self.assertGreater(a, b)
    self.assertGreaterEqual(a, b)
    self.assertLess(a, b)
    self.assertLessEqual(a, b)
    
    # Container comparisons
    self.assertCountEqual(first, second)  # Same elements, any order
    self.assertSequenceEqual(first, second)  # Same sequence, same order
    self.assertListEqual(first, second)
    self.assertTupleEqual(first, second)
    self.assertSetEqual(first, second)
    self.assertDictEqual(first, second)
    
    # Exception checks
    with self.assertRaises(SomeException):
        function_that_raises()
        
    # Context-specific checks
    with self.assertRaises(SomeException) as context:
        function_that_raises()
    self.assertEqual(str(context.exception), "Expected message")
    
    # Output checks
    with self.assertLogs(logger, level='INFO') as cm:
        logger.info("Test log message")
    self.assertEqual(len(cm.output), 1)
    
    # Warnings check
    with self.assertWarns(DeprecationWarning):
        function_with_warning()
```

#### Skipping Tests and Expected Failures

```python
class TestSkipping(unittest.TestCase):
    @unittest.skip("Skipping this test for now")
    def test_skipped(self):
        pass
        
    @unittest.skipIf(sys.version_info < (3, 8), "Requires Python 3.8+")
    def test_conditional_skip(self):
        pass
        
    @unittest.skipUnless(sys.platform == "win32", "Windows only test")
    def test_windows_only(self):
        pass
        
    @unittest.expectedFailure
    def test_known_bug(self):
        self.assertEqual(1, 2)  # This is expected to fail
```

#### Subtest - Running Variations Within a Test

```python
def test_with_subtests(self):
    test_cases = [
        (1, 1, 2),
        (2, 2, 4),
        (3, 3, 6)
    ]
    
    for a, b, expected in test_cases:
        with self.subTest(a=a, b=b):
            self.assertEqual(a + b, expected)
```

#### Testing Exceptions

```python
def test_exception(self):
    # Basic exception check
    with self.assertRaises(ValueError):
        int("not an integer")
    
    # Advanced exception check with context
    with self.assertRaises(ValueError) as context:
        int("not an integer")
    self.assertIn("invalid literal", str(context.exception))
```

#### Mock Objects

```python
import unittest
from unittest import mock
from unittest.mock import patch, MagicMock, Mock, call

class TestMocking(unittest.TestCase):
    def test_mock_function(self):
        # Creating a mock
        mock_func = Mock()
        mock_func.return_value = 42
        
        # Using the mock
        result = mock_func()
        
        # Assertions
        self.assertEqual(result, 42)
        mock_func.assert_called_once()
        
    def test_mock_with_side_effect(self):
        # Mock with side effects
        mock_func = Mock(side_effect=[1, 2, 3])
        
        # Each call returns the next item
        self.assertEqual(mock_func(), 1)
        self.assertEqual(mock_func(), 2)
        self.assertEqual(mock_func(), 3)
        
    def test_mock_raising_exception(self):
        # Mock that raises an exception
        mock_func = Mock(side_effect=ValueError("Invalid input"))
        
        with self.assertRaises(ValueError):
            mock_func()
    
    @patch('module_to_test.function_to_mock')
    def test_with_patch_decorator(self, mock_function):
        # Setup the mock
        mock_function.return_value = "mocked result"
        
        # Call the function that uses the now-mocked dependency
        from module_to_test import my_function
        result = my_function()
        
        # Assertions
        self.assertEqual(result, "mocked result")
        mock_function.assert_called_once()
    
    def test_with_patch_context_manager(self):
        with patch('module_to_test.function_to_mock') as mock_function:
            mock_function.return_value = "mocked result"
            
            from module_to_test import my_function
            result = my_function()
            
            self.assertEqual(result, "mocked result")
            
    def test_multiple_patches(self):
        with patch('module.func1') as mock1, \
             patch('module.func2') as mock2:
            # Both function calls are mocked
            pass
    
    def test_mock_class(self):
        with patch('module.MyClass') as MockClass:
            # Configure the instance returned when MyClass is instantiated
            instance = MockClass.return_value
            instance.method.return_value = "mocked method result"
            
            from module import code_that_uses_my_class
            result = code_that_uses_my_class()
            
            self.assertEqual(result, "mocked method result")
    
    def test_mock_object_attributes(self):
        mock_obj = Mock()
        mock_obj.attribute = "value"
        mock_obj.method.return_value = 42
        
        self.assertEqual(mock_obj.attribute, "value")
        self.assertEqual(mock_obj.method(), 42)
    
    def test_assert_mock_calls(self):
        mock_func = Mock()
        
        # Make some calls
        mock_func(1, 2)
        mock_func.method("a", b="b")
        
        # Check call count
        self.assertEqual(mock_func.call_count, 1)
        self.assertEqual(mock_func.method.call_count, 1)
        
        # Check call arguments
        mock_func.assert_called_with(1, 2)
        mock_func.method.assert_called_with("a", b="b")
        
        # Check call history
        expected_calls = [call(1, 2)]
        self.assertEqual(mock_func.mock_calls, expected_calls)
    
    def test_mock_spec(self):
        # Mock with specification (only allows existing attributes)
        class Person:
            def __init__(self, name):
                self.name = name
            
            def greet(self):
                return f"Hello, I'm {self.name}"
        
        # Create a mock with the spec
        mock_person = Mock(spec=Person)
        mock_person.name = "John"
        mock_person.greet.return_value = "Mocked greeting"
        
        # This works fine
        self.assertEqual(mock_person.name, "John")
        self.assertEqual(mock_person.greet(), "Mocked greeting")
        
        # This would raise AttributeError because 'dance' is not in the spec
        # mock_person.dance()
    
    def test_magic_mock(self):
        # MagicMock is like Mock but handles magic methods
        magic = MagicMock()
        magic.__len__.return_value = 42
        
        self.assertEqual(len(magic), 42)
```

#### Advanced Mocking Techniques

```python
class TestAdvancedMocking(unittest.TestCase):
    def test_mocking_context_manager(self):
        # Mock a context manager
        mock_context = MagicMock()
        mock_context.__enter__.return_value = "resource"
        
        with mock_context as resource:
            self.assertEqual(resource, "resource")
        
        mock_context.__enter__.assert_called_once()
        mock_context.__exit__.assert_called_once()
    
    def test_mock_with_autospec(self):
        # autospec creates a mock that validates attribute access
        # and method signatures based on the spec object
        def function(a, b, c):
            return a + b + c
        
        mock_func = mock.create_autospec(function)
        mock_func.return_value = 42
        
        result = mock_func(1, 2, 3)
        self.assertEqual(result, 42)
        
        # This would raise TypeError due to wrong number of arguments
        # mock_func(1, 2)
    
    def test_mock_property(self):
        class MyClass:
            @property
            def prop(self):
                return "value"
        
        # Mock the property
        with patch.object(MyClass, 'prop', new_callable=mock.PropertyMock) as mock_prop:
            mock_prop.return_value = "mocked value"
            
            obj = MyClass()
            self.assertEqual(obj.prop, "mocked value")
    
    def test_mock_builtin(self):
        # Mocking built-in functions
        with patch('builtins.open', mock.mock_open(read_data="mocked file content")) as mock_file:
            with open("file_path.txt", "r") as file:
                content = file.read()
            
            self.assertEqual(content, "mocked file content")
            mock_file.assert_called_once_with("file_path.txt", "r")
    
    def test_mock_chained_calls(self):
        # Mocking chained method calls
        mock_obj = Mock()
        mock_obj.method1.return_value.method2.return_value.method3.return_value = "result"
        
        result = mock_obj.method1().method2().method3()
        self.assertEqual(result, "result")
    
    def test_patch_dict(self):
        # Temporarily modify a dictionary
        original = {'key': 'original_value'}
        
        with patch.dict(original, {'key': 'new_value'}, clear=False):
            self.assertEqual(original['key'], 'new_value')
        
        # Original value is restored after the context manager
        self.assertEqual(original['key'], 'original_value')
```

#### Test Suites

```python
def create_test_suite():
    # Create a test suite manually
    suite = unittest.TestSuite()
    
    # Add test classes
    suite.addTest(unittest.makeSuite(TestExample))
    suite.addTest(unittest.makeSuite(TestMocking))
    
    # Add individual test methods
    suite.addTest(TestExample('test_simple_assertion'))
    
    return suite

if __name__ == '__main__':
    # Run the suite
    runner = unittest.TextTestRunner()
    runner.run(create_test_suite())
```

#### Test Runners

```python
import unittest

if __name__ == '__main__':
    # Basic test runner
    unittest.main()
    
    # Test runner with more options
    unittest.main(verbosity=2, failfast=True)
```

#### Load Tests from Multiple Modules

```python
import unittest

# Load all tests from specified modules
from test_module1 import *
from test_module2 import *

if __name__ == '__main__':
    unittest.main()
```

#### Best Practices

1. **Test method naming**: Begin with `test_` and use descriptive names that explain what is being tested
2. **Isolation**: Each test should be independent and not rely on other tests
3. **Arrange-Act-Assert**: Structure tests into setup, action, and verification phases
4. **Keep tests small**: Test one specific functionality per test method
5. **Use setUp and tearDown**: For common initialization and cleanup code
6. **Mock external dependencies**: Isolate your code from external systems
7. **Focus on behavior**: Test what methods do, not their implementation details
8. **Consistent assertions**: Use the most specific assertion for the condition
9. **Test edge cases**: Boundary conditions, empty inputs, error conditions
10. **Use subTest**: For variations of the same test with different inputs

#### Common Mocking Patterns

#### Mocking Database Access

```python
def test_database_access(self):
    # Create mock for database connection
    mock_conn = Mock()
    mock_cursor = Mock()
    mock_conn.cursor.return_value = mock_cursor
    
    # Configure cursor behavior
    mock_cursor.execute.return_value = None
    mock_cursor.fetchall.return_value = [{'id': 1, 'name': 'Test'}]
    
    # Use patch to replace actual database connection
    with patch('module.get_database_connection', return_value=mock_conn):
        # Call the function that uses database
        from module import get_user_data
        result = get_user_data(user_id=1)
        
        # Verify correct SQL was executed
        mock_cursor.execute.assert_called_with("SELECT * FROM users WHERE id = ?", (1,))
        self.assertEqual(result, [{'id': 1, 'name': 'Test'}])
```

#### Mocking HTTP Requests

```python
def test_api_client(self):
    # Mock the requests.get function
    mock_response = Mock()
    mock_response.status_code = 200
    mock_response.json.return_value = {'data': 'test_data'}
    
    with patch('requests.get', return_value=mock_response) as mock_get:
        # Call function that makes the request
        from api_client import get_data
        result = get_data('https://api.example.com/data')
        
        # Verify the request was made correctly
        mock_get.assert_called_once_with('https://api.example.com/data')
        self.assertEqual(result, {'data': 'test_data'})
```

#### Mocking File Operations

```python
def test_file_reading(self):
    # Use mock_open helper to mock file operations
    file_content = "line1\nline2\nline3"
    mock_open = mock.mock_open(read_data=file_content)
    
    with patch('builtins.open', mock_open):
        # Call function that reads file
        from file_utils import count_lines
        result = count_lines('dummy_file.txt')
        
        # Verify file was opened correctly
        mock_open.assert_called_once_with('dummy_file.txt', 'r')
        self.assertEqual(result, 3)
```

#### Mocking Time

```python
def test_time_dependent_function(self):
    # Mock the time.time function
    fixed_time = 1609459200  # 2021-01-01 00:00:00
    
    with patch('time.time', return_value=fixed_time):
        # Call function that depends on current time
        from time_utils import get_timestamp
        result = get_timestamp()
        
        self.assertEqual(result, fixed_time)
```

#### Partial Mocking

```python
def test_partial_mock(self):
    # Only mock specific method in a class
    class Calculator:
        def add(self, a, b):
            return a + b
            
        def multiply(self, a, b):
            return a * b
    
    calc = Calculator()
    
    # Only mock the multiply method
    with patch.object(calc, 'multiply', return_value=100):
        # Original method works normally
        self.assertEqual(calc.add(2, 3), 5)
        
        # Mocked method returns mock value
        self.assertEqual(calc.multiply(5, 5), 100)
```

### Regular expressions
The Python ```re``` package is used for working with regular expressions (regex). In particular, this allows to match, search, and manipulate
strings based on patterns

Overview of most frequently used functions
```python
match = re.match(pattern, string, flags=0)                          # re.match(r'hello', "hello world"), use match.group()
match = re.search(pattern, string, flags=0)                         # re.search(r'world', "hello world"), use match.group()
matches = re.findall(pattern, string, flags=0)                      # re.findall(r'\d+', "123 apples and 456 oranges"), gives ['123', '456']
matches = re.finditer(pattern, string, flags=0)                     # re.finditer(r'\d+', "123 apples and 456 oranges")
result = re.split(pattern, string, maxsplit=0, flags=0)             # re.split(r'[,\s]+', "apple, orange  banana")
result = re.sub(pattern, repl, string, count=0, flags=0)            # 
result, num_subs = re.subn(pattern, repl, string, count=0, flags=0) # re.subn(r'\d+', '###', "123 apples and 456 oranges")
match = re.fullmatch(pattern, string, flags=0)                      # re.fullmatch(r'\d+', "12345")
pattern = re.compile(pattern, flags=0)                              # re.compile(r'\d+'), use pattern.findall("my text")
```

#### Match 
The match function can be used as follows
```python
re.match(pattern, string, flags=0)
```

Example code
```python
import re

pattern = r'hello'
string = "hello World"

match = re.match(pattern, string)
if match:
    print("Match found: ", match.group())
else:
    print("No match found")
```

#### Basic Import and Usage

```python
import re

# Quick check if pattern exists in string
if re.search(r"pattern", "test string with pattern"):
    print("Found a match!")

# Find all occurrences
matches = re.findall(r"pattern", "multiple pattern matches pattern")
# Returns: ['pattern', 'pattern']

# Replace occurrences
new_string = re.sub(r"old", "new", "replace old with new")
# Returns: "replace new with new"
```

#### Primary Functions

```python
# search() - Find first match, return Match object or None
match = re.search(r"pattern", "string with pattern")
if match:
    print(f"Found at position {match.start()}-{match.end()}")

# match() - Check if pattern matches at START of string
start_match = re.match(r"Hello", "Hello World")  # Match
start_match = re.match(r"World", "Hello World")  # No match

# fullmatch() - Check if pattern matches ENTIRE string
full_match = re.fullmatch(r"Hello World", "Hello World")  # Match
full_match = re.fullmatch(r"Hello", "Hello World")  # No match

# findall() - Return all non-overlapping matches as list of strings
all_matches = re.findall(r"\d+", "Numbers: 123, 456, 789")
# Returns: ['123', '456', '789']

# finditer() - Return iterator of Match objects
for match in re.finditer(r"\d+", "Numbers: 123, 456, 789"):
    print(f"Found {match.group()} at {match.span()}")

# split() - Split string by pattern
parts = re.split(r",\s*", "apple, banana, cherry")
# Returns: ['apple', 'banana', 'cherry']

# sub() - Replace pattern with replacement
result = re.sub(r"(\d+)", r"Number: \1", "Cost: 45 dollars")
# Returns: "Cost: Number: 45 dollars"

# subn() - Like sub() but returns tuple (new_string, count)
result, count = re.subn(r"\d+", "NUM", "123 and 456")
# Returns: ("NUM and NUM", 2)
```

#### Compilation and Flags

```python
# Compile pattern for reuse (more efficient for multiple uses)
pattern = re.compile(r"\d+")
matches = pattern.findall("Numbers: 123, 456")
result = pattern.sub("NUM", "Replace 123 and 456")

# Common flags
pattern = re.compile(r"python", re.IGNORECASE)  # Case-insensitive matching

# Multiple flags with bitwise OR
pattern = re.compile(r"multi.*line", re.IGNORECASE | re.DOTALL)

"""
Available flags:
re.IGNORECASE (re.I) - Case-insensitive matching
re.MULTILINE (re.M) - ^ and $ match start/end of each line
re.DOTALL (re.S) - Dot matches any char including newline
re.VERBOSE (re.X) - Allow comments and whitespace in pattern
re.ASCII (re.A) - \w, \b, \s, \d match only ASCII characters
re.LOCALE (re.L) - Make \w, \b, \s, \d locale dependent (legacy)
re.UNICODE (re.U) - Make \w, \b, \s, \d match Unicode (default in Python 3)
"""

# Inline flags in pattern
pattern = re.compile(r"(?i)python")  # Same as re.IGNORECASE
```

#### Match Objects

```python
match = re.search(r"(\w+)@(\w+)\.(\w+)", "contact me at user@example.com")

if match:
    # Whole match
    match.group()  # 'user@example.com'
    match.group(0)  # Same as above
    
    # Accessing capturing groups
    match.group(1)  # 'user'
    match.group(2)  # 'example'
    match.group(3)  # 'com'
    
    # Multiple groups at once
    match.group(1, 3)  # ('user', 'com')
    
    # All groups as tuple
    match.groups()  # ('user', 'example', 'com')
    
    # Position information
    match.start()  # Start index of the match
    match.end()    # End index of the match
    match.span()   # (start, end) tuple
    
    # Named group
    named_match = re.search(r"(?P<name>\w+): (?P<value>\d+)", "Age: 30")
    named_match.group('name')   # 'Age'
    named_match.group('value')  # '30'
    named_match.groupdict()     # {'name': 'Age', 'value': '30'}
```

#### Character Classes and Special Sequences

```python
# Character classes
r"[abc]"      # Match a, b, or c
r"[a-z]"      # Match any lowercase letter
r"[A-Z]"      # Match any uppercase letter
r"[0-9]"      # Match any digit
r"[a-zA-Z0-9]"# Match any alphanumeric character
r"[^abc]"     # Match anything EXCEPT a, b, or c

# Predefined character classes
r"\d"         # Digit [0-9]
r"\D"         # Not a digit [^0-9]
r"\w"         # Word character [a-zA-Z0-9_]
r"\W"         # Not a word character [^a-zA-Z0-9_]
r"\s"         # Whitespace [ \t\n\r\f\v]
r"\S"         # Not whitespace [^ \t\n\r\f\v]

# Special characters
r"."          # Any character except newline
r"\."         # Literal period
r"^"          # Start of string (or line with re.MULTILINE)
r"$"          # End of string (or line with re.MULTILINE)
r"\b"         # Word boundary
r"\B"         # Not a word boundary
r"\A"         # Start of string (regardless of re.MULTILINE)
r"\Z"         # End of string (regardless of re.MULTILINE)
```

#### Quantifiers and Anchors

```python
# Quantifiers
r"a*"         # Match 0 or more 'a's (greedy)
r"a+"         # Match 1 or more 'a's (greedy)
r"a?"         # Match 0 or 1 'a's (greedy)
r"a{3}"       # Match exactly 3 'a's
r"a{3,5}"     # Match 3 to 5 'a's (greedy)
r"a{3,}"      # Match 3 or more 'a's (greedy)

# Non-greedy (minimal) quantifiers
r"a*?"        # Match 0 or more 'a's (non-greedy)
r"a+?"        # Match 1 or more 'a's (non-greedy)
r"a??"        # Match 0 or 1 'a's (non-greedy)
r"a{3,5}?"    # Match 3 to 5 'a's (non-greedy)
r"a{3,}?"     # Match 3 or more 'a's (non-greedy)

# Examples
re.findall(r"\d+", "Numbers: 123 456")      # ['123', '456']
re.findall(r"\d+?", "Numbers: 123 456")     # ['1', '2', '3', '4', '5', '6']
```

#### Grouping and Alternation

```python
# Grouping with ()
r"(ab)+"      # Match one or more "ab" sequences
r"(\d{2})-(\d{2})"  # Match "12-34" and group digits

# Non-capturing group
r"(?:abc)+"   # Match one or more "abc" but don't capture

# Named groups
r"(?P<year>\d{4})-(?P<month>\d{2})-(?P<day>\d{2})"  # Date with named groups

# Alternation with |
r"cat|dog"    # Match "cat" or "dog"
r"(cat|dog) food"  # Match "cat food" or "dog food"

# Backreferences
r"(\w+) \1"   # Match repeated word (e.g., "hello hello")
r"(?P<word>\w+) (?P=word)"  # Same as above with named group
```

#### Lookahead and Lookbehind Assertions

```python
# Positive lookahead: A(?=B) matches A only if followed by B
r"\w+(?=\s\d)"  # Match word followed by space and digit

# Negative lookahead: A(?!B) matches A only if not followed by B
r"\w+(?!\s\d)"  # Match word not followed by space and digit

# Positive lookbehind: (?<=B)A matches A only if preceded by B
r"(?<=\d\s)\w+"  # Match word preceded by digit and space

# Negative lookbehind: (?<!B)A matches A only if not preceded by B
r"(?<!\d\s)\w+"  # Match word not preceded by digit and space

# Examples
re.findall(r"\w+(?=ing)", "I am walking and running")  # ['walk', 'runn']
re.findall(r"(?<=\$)\d+", "Items: $50, $25")  # ['50', '25']
```

#### Common Patterns

```python
# Email validation (basic)
email_pattern = r"[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}"

# URL matching (basic)
url_pattern = r"https?://(?:www\.)?[a-zA-Z0-9-]+\.[a-zA-Z0-9.-]+(?:/[a-zA-Z0-9-._~:/?#[\]@!$&'()*+,;=]*)?"

# Phone number (US format)
phone_pattern = r"\(?\d{3}\)?[-.\s]?\d{3}[-.\s]?\d{4}"

# Date (YYYY-MM-DD)
date_pattern = r"\d{4}-\d{2}-\d{2}"

# IP address
ip_pattern = r"(?:\d{1,3}\.){3}\d{1,3}"

# Strong password (at least 8 chars, mixture of uppercase, lowercase, numbers, special chars)
password_pattern = r"^(?=.*[a-z])(?=.*[A-Z])(?=.*\d)(?=.*[@$!%*?&])[A-Za-z\d@$!%*?&]{8,}$"

# Credit card number (simplified)
cc_pattern = r"\d{4}[-\s]?\d{4}[-\s]?\d{4}[-\s]?\d{4}"
```

#### Handling Multiline Text

```python
text = """First line
Second line
Third line"""

# Find all lines containing "line"
re.findall(r"^.*line.*$", text, re.MULTILINE)
# Returns: ['First line', 'Second line', 'Third line']

# Find all lines starting with "S"
re.findall(r"^S.*$", text, re.MULTILINE)
# Returns: ['Second line']

# Match across multiple lines (including newlines)
re.search(r"First.*Third", text, re.DOTALL).group()
# Returns: "First line\nSecond line\nThird line"
```

#### Verbose Mode (Complex Patterns)

```python
# Regular expression for validating a hex color code
hex_color_re = re.compile(r"""
    \#              # Hash character
    (?:             # Non-capturing group for the hex digits
        [0-9A-Fa-f]{3}  # 3-digit format (#RGB)
        |           # OR
        [0-9A-Fa-f]{6}  # 6-digit format (#RRGGBB)
    )
    \b              # Word boundary
""", re.VERBOSE)

# Test the pattern
hex_color_re.match("#FFB6C1")  # Match (6-digit)
hex_color_re.match("#F00")     # Match (3-digit)
hex_color_re.match("#ZZZ")     # No match (invalid hex)
```

#### Performance Tips

```python
# 1. Compile patterns that are used multiple times
pattern = re.compile(r"\d+")

# 2. Use non-capturing groups (?:...) when capture isn't needed
re.findall(r"(?:\d+)-(?:\d+)", "123-456 789-012")  # ['123-456', '789-012']

# 3. Be specific with character classes
# Instead of:
re.findall(r".*", "hello")  # ['hello', '']
# Use:
re.findall(r"[a-z]+", "hello")  # ['hello']

# 4. Avoid unnecessary backtracking
# Instead of:
re.search(r"a.*b.*c", long_string)
# Use:
re.search(r"a[^c]*b[^c]*c", long_string)

# 5. Use atomic groups or possessive quantifiers when available
# 6. Be careful with nested quantifiers (a+)+ - can cause catastrophic backtracking
```

#### Common Mistakes and Solutions

```python
# Mistake: Not escaping special characters
re.search(r"1.2", "1.2")  # Matches "1" + any char + "2"
# Solution:
re.search(r"1\.2", "1.2")  # Matches literal "1.2"

# Mistake: Greedy vs. non-greedy quantifiers
re.search(r"<.*>", "<tag>value</tag>").group()  # '<tag>value</tag>'
# Solution:
re.search(r"<.*?>", "<tag>value</tag>").group()  # '<tag>'

# Mistake: Word boundaries
re.sub(r"cat", "dog", "cats and cat")  # "dogs and dog" (partial matches)
# Solution:
re.sub(r"\bcat\b", "dog", "cats and cat")  # "cats and dog" (whole word only)

# Mistake: Capture groups in findall
re.findall(r"(\d+)-(\d+)", "123-456")  # [('123', '456')] (tuples of groups)
# Solution (if you want full matches):
re.findall(r"\d+-\d+", "123-456")  # ['123-456']

# Mistake: Not handling None from search() or match()
match = re.search(r"pattern", string)
match.group()  # AttributeError if no match
# Solution:
if match:
    result = match.group()
```

#### Raw Strings vs. Regular Strings

```python
# Problem: Backslashes in regular strings
pattern = "\\d+"  # Need double backslash

# Solution: Use raw strings for regexes
pattern = r"\d+"  # Cleaner, less error-prone

# Compare:
print("\\\\")  # Prints: \\
print(r"\\")   # Prints: \\
```

#### Python-Specific Behaviors

```python
# Default is Unicode mode in Python 3
re.search(r"\w+", "Привет")  # Matches non-ASCII characters

# Using ASCII flag for legacy behavior
re.search(r"\w+", "Привет", re.ASCII)  # No match

# Escape sequences in string literals vs. regex patterns
print("\t")       # Prints a tab character
print(r"\t")      # Prints literal "\t"
re.search("\t", "a\tb")   # Matches a tab character
re.search(r"\t", "a\tb")  # Same as above
```

#### Debugging Regular Expressions

```python
import re

def debug_regex(pattern, string):
    """Helper function to debug regular expressions"""
    compiled = re.compile(pattern)
    
    print(f"Pattern: {pattern}")
    print(f"String: {string}")
    
    # Check if the pattern matches at the start
    match_result = compiled.match(string)
    print(f"match(): {'Success' if match_result else 'No match'}")
    if match_result:
        print(f"  span: {match_result.span()}")
        print(f"  groups: {match_result.groups()}")
    
    # Check if the pattern is found anywhere
    search_result = compiled.search(string)
    print(f"search(): {'Success' if search_result else 'No match'}")
    if search_result:
        print(f"  span: {search_result.span()}")
        print(f"  groups: {search_result.groups()}")
    
    # Find all occurrences
    findall_result = compiled.findall(string)
    print(f"findall(): {findall_result}")
    
    # Split by pattern
    split_result = compiled.split(string)
    print(f"split(): {split_result}")
    
    # Replace pattern
    sub_result = compiled.sub("REPLACED", string)
    print(f"sub(): {sub_result}")

# Example usage
debug_regex(r"(\d+)", "abc123def456")
```


### Web protocol and data handling
### JSON Package
```Python
# json.load()
# json.dump(obj, fp, *, …, indent=None, …, **kw)
# json.dumps(obj, *, …, **kw)

# Read JSON file [e.g. file_name = 'file.json']
with open(file_name, 'r') as file_reader:
    data = json.load(file_reader)

# Write JSON file [e.g. file_name = 'my_output.json']
with open(file_name, 'w') as file_writer:
    json.dump(output_data, file_writer, indent=4)
```
### Requests Package
```Python
# Install
python -m pip install requests

# Import
import requests

# Response object
response.status_code 		# Attribute: response status code
response.headers['Content-Type']	# Attribute: response headers
response.json()			# Method: receive json-object

api_url = 'https://apiurl.com/post'	# URL for the API

# GET request
response = requests.get(api_url) 
response_json = response.json() 	# Example: {'userID': 1, 'text': 'text_example'}

# POST request
response = requests.post(api_url, json={'id': 2, 'title': 'text'})
response = requests.post(api_url, json={'id': 2, 'title': 'text'}, headers={'Content-Type': 'application/json'})

# PUT request 
response = requests.post('https://apiurl.com/put', )
```

### Logging
The basic usage for logging message by using the default logging instance is given as follows
```Python
import logging

logging.info("This is an info message")
logging.debug('This message is for debugging purposes')
logging.warning("This is a warning message")
logging.error('This is an error message')
```
We list the different logging levels in the following
```Python
logging.DEBUG           # Detailed information, typically of interest only when diagnosing problems
logging.INFO            # Confirmation that things are working as expected
logging.WARNING         # An indication that something unexpected happened, or indicative of some problem in the near future
logging.ERROR           # Due to a more serious problem, the software has not been able to perform some function
logging.CRITICAL        # A serious error, indicating that the program itself may be unable to continue running
``` 
For logging to a specified logfile we can use
```Python
import logging

logging.basicConfig(filename='logfile-example.log', encoding='utf-8', level=logging.DEBUG)
```
By default all messages are appended to the specified logfile. In order to create a new logfile for each run we can use
```Python
logging.basicConfig(filename='logfile-example.log', filemode='w', level=logging.DEBUG)
```
For extended logging messages we can include a timestamp as follows
```Python
import logging

logging.basicConfig(filename="example2.log", 
                    format='%(asctime)s, %(levelname)s, %(message)s', 
                    datefmt='%m-%d-%Y-%H-%M-%S', 
                    level=logging.DEBUG, 
                    filemode="w")
```
### Command Line Arguments
We start with the basic setup of the argparse package
```Python
import argparse
# Create argparse object
parser = argparse.ArgumentParser()                  # Create argparse object
# Add arguments
parser.add_argument("path")                         # Add argument for parsing input parameters
parser.add_argument("file", help="file to read")    # Add help message for the given parameter
parser.add_argument("num", help"Number", type=int)  # Add argument with specified type (default: str)  
# Receive parameters      
args = parser.parse_args()                          # Parse arguments
# Evaluate parameters
print(args.path)
print(args.file)
```
This can be executed by using the command line (e.g. Bash)
```Shell
$ python main.py --help                 # Print information and usage message
```

#### Basic Components

#### Import & Setup
```python
import argparse

# Create parser
parser = argparse.ArgumentParser(description="Description of your program")

# Parse arguments
args = parser.parse_args()
```

#### Adding Arguments

#### Positional Arguments
```python
parser.add_argument("filename", help="Input file to process")
parser.add_argument("output", help="Output destination")
```

#### Optional Arguments
```python
parser.add_argument("-v", "--verbose", help="Increase output verbosity", action="store_true")
parser.add_argument("-n", "--number", help="A numeric value", type=int)
```

#### Default Values
```python
parser.add_argument("--batch-size", help="Batch size for processing", type=int, default=32)
```

#### Accessing Parsed Arguments
```python
args = parser.parse_args()
print(args.filename)  # Access positional argument
print(args.verbose)   # Access optional flag (True/False)
print(args.number)    # Access optional value
```

#### Advanced Components

#### Argument Types
```python
parser.add_argument("--count", type=int)                  # Integer
parser.add_argument("--price", type=float)                # Float
parser.add_argument("--enable", type=bool)                # Boolean
parser.add_argument("--names", type=str)                  # String
parser.add_argument("--path", type=argparse.FileType('r')) # File
```

#### Custom Types
```python
def positive_int(value):
    ivalue = int(value)
    if ivalue <= 0:
        raise argparse.ArgumentTypeError(f"{value} is not a positive integer")
    return ivalue

parser.add_argument("--quantity", type=positive_int)
```

#### Action Options
```python
parser.add_argument("--verbose", action="store_true")     # Flag (default: False)
parser.add_argument("--quiet", action="store_false")      # Flag (default: True)
parser.add_argument("-v", action="count", default=0)      # Count occurrences
parser.add_argument("--overwrite", action="store_const", const=True) # Store constant
parser.add_argument("--sum", dest="accumulate", action="store_const",
                    const=sum, default=max)               # Store function
parser.add_argument("--version", action="version", version="%(prog)s 1.0") # Show version
```

#### Multiple Values
```python
parser.add_argument("--files", nargs=2)                   # Exactly 2 arguments
parser.add_argument("--inputs", nargs="+")                # 1 or more arguments
parser.add_argument("--outputs", nargs="*")               # 0 or more arguments
parser.add_argument("--config", nargs="?", default="default.conf") # 0 or 1 argument
```

#### Choices
```python
parser.add_argument("--log-level", choices=["DEBUG", "INFO", "WARNING", "ERROR", "CRITICAL"])
parser.add_argument("--compression", choices=range(1, 10)) # Integers from 1-9
```

#### Required Optional Arguments
```python
parser.add_argument("--user", required=True)
```

#### Grouping Arguments
```python
group = parser.add_argument_group("authentication", "Authentication options")
group.add_argument("--user", help="Username")
group.add_argument("--password", help="Password")

exclusive_group = parser.add_mutually_exclusive_group()
exclusive_group.add_argument("--quiet", action="store_true")
exclusive_group.add_argument("--verbose", action="store_true")
```

#### Subcommands

```python
parser = argparse.ArgumentParser()
subparsers = parser.add_subparsers(dest="command", help="Commands")

# Create parser for "create" command
create_parser = subparsers.add_parser("create", help="Create a new resource")
create_parser.add_argument("name", help="Name of resource to create")
create_parser.add_argument("--type", default="basic", help="Resource type")

# Create parser for "delete" command
delete_parser = subparsers.add_parser("delete", help="Delete a resource")
delete_parser.add_argument("id", help="Resource ID to delete")
delete_parser.add_argument("--force", action="store_true", help="Force deletion")

# Parse and use
args = parser.parse_args()
if args.command == "create":
    print(f"Creating {args.name} of type {args.type}")
elif args.command == "delete":
    print(f"Deleting {args.id} with force={args.force}")
```

#### Complete Example

```python
import argparse

def main():
    # Create the top-level parser
    parser = argparse.ArgumentParser(
        description="Example CLI tool",
        epilog="Thank you for using this tool!",
        formatter_class=argparse.ArgumentDefaultsHelpFormatter
    )
    
    # Add global arguments
    parser.add_argument("-v", "--verbose", action="count", default=0,
                        help="Increase verbosity (can be used multiple times)")
    parser.add_argument("--config", default="config.ini",
                        help="Configuration file path")
    
    # Create subparsers for commands
    subparsers = parser.add_subparsers(dest="command", help="Commands")
    subparsers.required = True  # Require a command to be specified
    
    # Parser for the "process" command
    process_parser = subparsers.add_parser("process", help="Process files")
    process_parser.add_argument("files", nargs="+", help="Files to process")
    process_parser.add_argument("-o", "--output-dir", default="./output",
                               help="Output directory")
    process_parser.add_argument("--format", choices=["json", "csv", "xml"],
                               default="json", help="Output format")
    
    # Parser for the "config" command
    config_parser = subparsers.add_parser("config", help="Configure settings")
    config_parser.add_argument("--set", nargs=2, metavar=("KEY", "VALUE"),
                              action="append", help="Set a configuration value")
    config_parser.add_argument("--get", metavar="KEY",
                              help="Get a configuration value")
    
    # Parse arguments
    args = parser.parse_args()
    
    # Set verbosity level
    verbosity_levels = {
        0: "WARNING",
        1: "INFO",
        2: "DEBUG"
    }
    verbosity = verbosity_levels.get(args.verbose, "DEBUG")
    print(f"Verbosity set to {verbosity}")
    
    # Execute command
    if args.command == "process":
        for file in args.files:
            print(f"Processing {file}, output to {args.output_dir} in {args.format} format")
    elif args.command == "config":
        if args.set:
            for key, value in args.set:
                print(f"Setting {key}={value}")
        if args.get:
            print(f"Getting value for {args.get}")

if __name__ == "__main__":
    main()
```

#### Best Practices

1. **Use descriptive help texts**: Always provide clear, concise help texts for all arguments.
   ```python
   parser.add_argument("--timeout", type=int, help="Connection timeout in seconds")
   ```

2. **Group related arguments**: Use argument groups to organize related options.
   ```python
   network_group = parser.add_argument_group("Network Options")
   network_group.add_argument("--host", help="Server hostname")
   network_group.add_argument("--port", type=int, help="Server port")
   ```

3. **Use default formatter for better help output**:
   ```python
   parser = argparse.ArgumentParser(
       formatter_class=argparse.ArgumentDefaultsHelpFormatter
   )
   ```

4. **Provide meaningful error messages**:
   ```python
   try:
       args = parser.parse_args()
   except argparse.ArgumentError as e:
       parser.error(f"Error parsing arguments: {e}")
   ```

5. **Use environment variables as fallbacks**:
   ```python
   import os
   parser.add_argument("--api-key", default=os.environ.get("API_KEY"))
   ```

6. **Create reusable parent parsers for common options**:
   ```python
   parent_parser = argparse.ArgumentParser(add_help=False)
   parent_parser.add_argument("--verbose", action="store_true")
   
   parser = argparse.ArgumentParser(parents=[parent_parser])
   ```

7. **Use consistent naming**: Use kebab-case for argument names.
   ```python
   # Good
   parser.add_argument("--output-format", "--output-type")
   # Avoid
   parser.add_argument("--outputFormat", "--output_format")
   ```

8. **Validate arguments after parsing**:
   ```python
   args = parser.parse_args()
   if args.min_value > args.max_value:
       parser.error("min-value cannot be greater than max-value")
   ```

9. **Use custom actions for complex behaviors**:
   ```python
   class KeyValueAction(argparse.Action):
       def __call__(self, parser, namespace, values, option_string=None):
           key, value = values.split('=')
           if not hasattr(namespace, 'kv_pairs'):
               setattr(namespace, 'kv_pairs', {})
           getattr(namespace, 'kv_pairs')[key] = value
   
   parser.add_argument("--define", action=KeyValueAction, help="KEY=VALUE pair")
   ```

10. **Add metavar for clearer help display**:
    ```python
    parser.add_argument("--timeout", type=int, metavar="SECONDS")
    ```


### Database Connection


#### SQLite


### Graphical User Interfaces


#### Tkinter


## References
- Python Software Foundation: [https://www.python.org/](https://www.python.org/)
- Python Tutorial: [https://docs.python.org/3/tutorial/index.html](https://docs.python.org/3/tutorial/index.html)
- Python Standard Library: [https://docs.python.org/3/library/index.html](https://docs.python.org/3/library/index.html)

