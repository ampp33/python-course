[[https://www.online-python.com/
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
](https://www.online-python.com/
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
- `print("asdf", end="")` - lets you print without adding a newline at the end (default `end` is `\n`)
## Convention
- `_` - underscore is a valid variable name, and means "we don't care about this value"
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
		- `text[::-1]` - reverses string[]()
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
- `enumerate` - takes an iterable, and gives us an index counter
	- `for i,char in enumerate("bro")`
- `while` loop exists
	- `while condition:`
	- Can have `else` blocks, and will only get executed if there isn't a `break` (aka it'll be ran at the end of the loop ONLY if we didn't break out of the loop.  Kinda a weird gotcha, but hey).  Ex:
```python
while i < 50:
	print('looping...')
else:
	print('done with the work') # printed once loop is done
```
- `break` - breaks out of a loop
- `continue` - ends current iteration but loop continues
- `pass` - not very useful, not seen very often in code, but it's a placeholder (ex: not sure what we want in the for loop, will put logic there in the future, but `pass` will put a placeholder there that will make the compiler happy)
## Functions
```python
def hello(name):
	print(f"hello, {name}!")
```
- must be defined in order, can't use a method before it's defined in a script
- *arguments* vs *parameters*
	- parameters - what's AVAILABLE to a function/class/etc's code
	- arguments - what/values you pass to the function WHEN you call it
### Functions vs. Methods
Function
```python
def some_function():
	pass
```
Method
```python
# uses dot (.) notation, and has to be OWNED by something, they're built into objects
"asdf".join(',')
```
## Docstrings
```python
def cool_thing():
	'''
	Documentation here <!- docstring
	'''
	print('hey')
```

Can call the method `help` on a function to have Python print out the docstring (woah), or a magic/dunder method:
```python
help(len)
print(len.__doc__)
# these methods both do the same thing
```
## Arguments and Keyword Arguments
```python
# args* - can accept any number of positional arguments
def super_func(*stuff):
	# stuff will be a `tuple`
	return sum(stuff)
	# ex: super_func(1,2,3) -> (1,2,3)

# kwargs** - keyword arguments
def do_stuff(**junk):
	# stuff will be a dictionary
	return sum(junk)
	# ex: do_stuff(hey="dude",stuff="herp") -> {'hey': 'dude', 'stuff': 'herp'}

# using both together
def wow(*args, **kwargs):
	print(args)
	print(kwargs)
	# ex: wow(1,2, thing="a", stuff="b") -> (1, 2) and {'thing': 'a', 'stuff': 'b'}
	# args was ONLY the non-named args, while kwargs was ONLY the named args
```

**Rule**: you must follow the order: `params`, `*args`, `default parameters`, `**kwargs`
Ex:
```python
def cool_thing(name, age, *args, is_cool=True, **kwargs):
```

```python
def highest_even(li):
	s = sorted(li, reverse=True)
	for num in s:
		if num % 2 == 0:
			return num
	# find the highest even number (get a list passed in)
```

## Walrus Operator
`:=` - assigns values to variables as part of a longer expression
Ex:
```python
while(text := read_from_stdio()):
	print(text) # saves us from having to call `get_item` twice
```
## Scope
- Python has *function* scope, new scopes are only created when you define functions

```python
# global scope
stuff = "asdf"

def some_func():
	total = 5

print(total) # won't work, total isn't available

if True:
	x = 10

print(x) # works
```

```python
a = 1

def confusion():
	a = 5
	return a

print(a) # prints 1
print(confusion()) # prints 5
```

```python
a = 1

def parent():
	a = 10 # python has closure!!
	def confusion():
		return a
	return confusion()

print(a) # prints 1
print(parent()) # prints 10
```

*Order of scope when evaluating values*:
1. local
2. parent local
3. global
4. built in python functions

### The `global` keyword
Lets you refer to global variables from within the scope of a function (that has its own universe)
Ex:
```python
total = 1

def do_stuff(a):
	global total
	total += 1
```
*This is not a good way of doing things :)*
### The `nonlocal` keyword
Does exactly what you'd expect, and is effectively the inverse of the `global` keyword, and works the same way

# Developer Environment
)
](https://www.online-python.com/
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
- `print("asdf", end="")` - lets you print without adding a newline at the end (default `end` is `\n`)
## Convention
- `_` - underscore is a valid variable name, and means "we don't care about this value"
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
		- `text[::-1]` - reverses string[]()
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
- `enumerate` - takes an iterable, and gives us an index counter
	- `for i,char in enumerate("bro")`
- `while` loop exists
	- `while condition:`
	- Can have `else` blocks, and will only get executed if there isn't a `break` (aka it'll be ran at the end of the loop ONLY if we didn't break out of the loop.  Kinda a weird gotcha, but hey).  Ex:
```python
while i < 50:
	print('looping...')
else:
	print('done with the work') # printed once loop is done
```
- `break` - breaks out of a loop
- `continue` - ends current iteration but loop continues
- `pass` - not very useful, not seen very often in code, but it's a placeholder (ex: not sure what we want in the for loop, will put logic there in the future, but `pass` will put a placeholder there that will make the compiler happy)
## Functions
```python
def hello(name):
	print(f"hello, {name}!")
```
- must be defined in order, can't use a method before it's defined in a script
- *arguments* vs *parameters*
	- parameters - what's AVAILABLE to a function/class/etc's code
	- arguments - what/values you pass to the function WHEN you call it
### Functions vs. Methods
Function
```python
def some_function():
	pass
```
Method
```python
# uses dot (.) notation, and has to be OWNED by something, they're built into objects
"asdf".join(',')
```
## Docstrings
```python
def cool_thing():
	'''
	Documentation here <!- docstring
	'''
	print('hey')
```

Can call the method `help` on a function to have Python print out the docstring (woah), or a magic/dunder method:
```python
help(len)
print(len.__doc__)
# these methods both do the same thing
```
## Arguments and Keyword Arguments
```python
# args* - can accept any number of positional arguments
def super_func(*stuff):
	# stuff will be a `tuple`
	return sum(stuff)
	# ex: super_func(1,2,3) -> (1,2,3)

# kwargs** - keyword arguments
def do_stuff(**junk):
	# stuff will be a dictionary
	return sum(junk)
	# ex: do_stuff(hey="dude",stuff="herp") -> {'hey': 'dude', 'stuff': 'herp'}

# using both together
def wow(*args, **kwargs):
	print(args)
	print(kwargs)
	# ex: wow(1,2, thing="a", stuff="b") -> (1, 2) and {'thing': 'a', 'stuff': 'b'}
	# args was ONLY the non-named args, while kwargs was ONLY the named args
```

**Rule**: you must follow the order: `params`, `*args`, `default parameters`, `**kwargs`
Ex:
```python
def cool_thing(name, age, *args, is_cool=True, **kwargs):
```

```python
def highest_even(li):
	s = sorted(li, reverse=True)
	for num in s:
		if num % 2 == 0:
			return num
	# find the highest even number (get a list passed in)
```

## Walrus Operator
`:=` - assigns values to variables as part of a longer expression
Ex:
```python
while(text := read_from_stdio()):
	print(text) # saves us from having to call `get_item` twice
```
## Scope
- Python has *function* scope, new scopes are only created when you define functions

```python
# global scope
stuff = "asdf"

def some_func():
	total = 5

print(total) # won't work, total isn't available

if True:
	x = 10

print(x) # works
```

```python
a = 1

def confusion():
	a = 5
	return a

print(a) # prints 1
print(confusion()) # prints 5
```

```python
a = 1

def parent():
	a = 10 # python has closure!!
	def confusion():
		return a
	return confusion()

print(a) # prints 1
print(parent()) # prints 10
```

*Order of scope when evaluating values*:
1. local
2. parent local
3. global
4. built in python functions

### The `global` keyword
Lets you refer to global variables from within the scope of a function (that has its own universe)
Ex:
```python
total = 1

def do_stuff(a):
	global total
	total += 1
```
*This is not a good way of doing things :)*
### The `nonlocal` keyword
Tells Python to use the non-global but non-local variable (parent variable)

# Developer Environment
- Linter - does spellcheck and syntax checks in your editor.  Didn't realize this wasn't handled by the compiler/interpeter
- PEP8 - Python standard formatting rules, can use `autopep8` extension in VSCode to install this formatter!
# OOP
- Paradigm
- Everything in Python is an object
	- Yes, even `None`, `bool`, `int`, etc

*Example Class:*
```python
class Character:
    # class object attribute (shouldn't change across class instances, is a constant)
    membership = True

    # constructor (dunder/magic method)
    def __init__(self, name):
        if(self.membership):
            pass
        if(Character.membership):
            pass
        self.name = name

    def run(self):
        print("run")

player = Character('bob')
```

)
