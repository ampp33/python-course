https://www.online-python.com/
# Interpreter
Most common interpreter is `cpython`, though ones like `jython` exist (converts python code to be ran on the JVM) or `pypy` (python interpreter written in python).

Python code gets compiled into bytecode (`.pyc` inside `__pycache__`) and ran against the PVM, which is part of the `cpython` interpreter, the PVM interprets the bytecode line by line and calls compiled C functions to do the actual work.

## Python2 vs Python3
Very similar, but a few *minor* syntactical changes.  Our Python3 knowledge mostly applies to Python2 as well

# Basics
- Expression: `user_age / 5`
- Statement: `div_by_5 = user_age / 5` (entire line of code that performs an action)
- "Augmented Assignment Operator" - `user_age += 5`
- Python doesn't care about how you've indented, just that you've indented (1 space, 2 spaces, 4 spaces, tab, etc)
## Datatypes
- int - `3`
- float - `2.4323`
	- Stores `2` in one location and `4323` in another
- bool - `true`
- str - `"hello"`
	- *Immutable*
	- Can use single or double quotes, doesn't matter
	- `"""` - triple quotes can be used for long multi-line strings
	- `'a' + 'b' -> 'ab'` - concat strings
	- `len(str)` - length of string
	- Substrings
		- `text[0]` - first char in string
		- `text[start:end:step]` - string "slicing"
			- `step` - 1 is default
			- `a = "0123"; text[0:4:2] gets us '02'`
		- `text[2:]` - 3rd char until the end
		- `text[:2]` - beginning to the 3rd character
		- `text[-1]` - gets last character
		- `text[:-1]` - all but last char
		- `text[::-1]` - reverses string
	- Escape special characters with `\` backslashes
	- `\t` - tab
	- `\n` - newline
	- Formatting - `f"my name is {name}"`, creates string and uses `name` variable
- list - `[1,2,3]`
	- Can mix datatypes in a list, but personally that's bad news
	- *Mutable*
	- `list[:]` - returns a shallow copy of the list
	- Matrix - multi-dimensional list
	- `list.append(1)` - add an item to the end of the list
	- `list.extend([1,2,3,4])` - add items from another list onto the end of `list`
	- `list.insert(3, 'abc')` - inserts `abc` at index `3`
	- `list.pop(index)` - remove last item from the end of list by default and returns it, though you can also give it an index and that just pops the item off from that index
	- `list.remove(value_to_remove)` - removes a specific value
	- Unpacking
		- `a,b,c = [1,2,3]`, `a = 1, b = 2, c = 3`
		- `a,*other = [1,2,3]`, `a=1, other = [2,3]`
		- `a,*other,b = [1,2,3,4]`, `a=1, other = [2,3], b=4`
- tuple - `(1,2)`
	- Like lists, but we can't modify them
	- Think of them like immutable lists
	- `tuple_obj[1]` - get 2nd item from a tuple 'list'
	- `'stuff' in tuple_obj` - check for item in tuple
	- Tuples tell people that you don't want to change these objects
	- Slightly more performant than lists
- set - `set(1,2,3)`
	- `{1,2,3}`
	- Can use all the same operations as lists (splitting, etc) except addressing things at indexes because a set is unordered/map/dict
	- Has methods like `intersection, difference, etc` that let you compare sets and see how they're the same and different (think Venn diagrams)
- dict - `{"a":1}`
	- Keys need to be immutable, can't be thinks like lists or complex objects
	- `dict(name = 'bob')` - initiates dict with the supplied tuple(s), not very common
	- `.get(key, default)`
	- `'name' in dict_obj` - checks if a key exists in a dict
	- `dict_obj.update({'age': 55})` - updates the 'age' key to value '55'
- `complex` - allows real and imaginary parts

Type conversion - most of the types above can be "called" to convert a value to their data type, like so: `int('123')`, `str(5)`
## Nothing
- `None`
## Useful Methods
- `type()` - tells us what datatype something is
- `bin()` - returns the binary representation
- `range`
	- `range(1,100)` - creates a `range` object, not too useful, but can change to `list(range(1,100))` and it'll give you an actual list
- `'abc'.join(elements)` - joins all the elements into a single string, separated by `abc`
## Math Functions
- `**` - to the power of
- `//` - does a divide and returns an integer, rounded down
- `%` - modulus (remainder)
- `round(num, digits)` - round to a certain number of digits
- `abs()` - absolute value
- Check the docs, there are a lot of these functions, these are just a few
## Variables
- Use `snake_case`
- Constants are usually in `ALL_CAPS`, but this doesn't actually make it unchangable
- `__` (double underscores) - *dunder*, means *these are meant to be left alone*
## Conditional Logic
- `if word == "hello":`
	- Can use things like `and`, `or`, `not`, `==`, `!\=`
	- `if 5:` is the same as `if bool(5):`, because the interpreter does the type conversion for us
		- `True`
			- non-empty
			- not "false"
			- non-zero
			- basically everything except what's listed under `False`
		- `False`
			- 0
			- 0.0
			- False
			- ''
			- None
			- {}
			- []
- `else:`
- `elif expression:`
- Ternary / Conditional Expressions
	- `condition_if_true if condition else condition_if_else`
- Handles *short circuiting*
- `==` vs `is`
	- `==` checks for equality in value (casting as necessary)
	- `is` checks if the location in memory is the same
## Loops
- `for item in 'Cool Text':` (loops thru every variable in the string)
	- `Cool Text` here, and for any `in`loop, is an iterable
	- `item` is still in scope outside the loop, because python doesn't require you to define variables ahead of time, so the variable is just available in memory now
	- Dictionaries
		- `item` would be each key if iterating over a dictionary
		- `dict.items()` - returns a list of items: each `item` will be a tuple of `(key, value)`
			- `for key, value in dict.items()` - shorthand way of getting key and value in a loop from an array
		- `dict.keys()` returns a list of keys, the default behavior
		- `dict.values()` returns a list of values
- Iterables
	- Collection that can be iterated over, or going one by one thru its elements
- 
