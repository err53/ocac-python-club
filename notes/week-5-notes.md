# Week 5 Notes

Parts:
3, 8, 14, 19, 24, 25, 26, 27, 28, 29

## 3: Multiple Assignment

```py
# var_1 = 1
# var_2 = 2
# var_3 = 3

var_1, var_2, var_3 = 1, 2, 3
```

## 8: String Slicing

```py
string = "Hello World"

sliced_string = string[0:5]
# => "Hello"
```

## 14: Break, Continue, Pass

break = terminates current loop

```py
while True:
  var = input("Enter some input: ")
  if input != "":
    break
```

continue = skips current iteration of loop

```py
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in nums:
  if num % 2 == 0:
    continue
  print(num)
# => 1, 3, 5, 7, 9
```

pass = does nothing

```py
nums = [1, 2, 3, 4, 5, 6, 7, 8, 9, 10]
for num in nums:
  if num % 2 == 0:
    pass
  print(num)
# => 1, 2, 3, 4, 5, 6, 7, 8, 9, 10
```

## 19: Dictionaries

```py
# Create a dictionary
dictionary = {
  "key_1": "value_1",
  "key_2": "value_2",
  "key_3": "value_3"
}

# Get a value from a dictionary
print(dictionary["key_1"])
# => value_1

# Get a list of keys
print(dictionary.keys())
# => dict_keys(['key_1', 'key_2', 'key_3'])

# Get a list of values
print(dictionary.values())
# => dict_values(['value_1', 'value_2', 'value_3'])

# These are view objects, which are updated when the dictionary is changed
```

# 24: Nested Function Calls

Functions can be nested within other functions

```py
# Instead of writing the following code:
num = input("Enter a number: ")
num = float(num)
num = abs(num)
num = round(num)
print(num)

# We can combine the functions into a single line of code:
print(abs(round(float(input("Enter a number: ")))))
```

# 25: Variable Scope

The scope of a variable in Python is the area where they can be accessed and modified.

Variables declared at the top level of a program are accessible throughout the program,
but variables declared inside a function are only accessible within that function.

```py
# Global variables
num = 1

# Private variables within a function
def func():
  num = 2
  print(num)

# The global variable is not overwritten outside of the function
func()
# => 2
print(num)
# => 1
```

# 26: \*args

When calling Python functions, `*args` will be a tuple of all arguments passed to the function.

```py
def add(*args):
  total = 0
  for num in args:
    total += num
  return total

add(1, 2, 3, 4, 5)
# => 15
```

It can be named anything, but it is convention to use `*args`.

# 27: \*\*kwargs

Instead of packing arguments into a tuple, we can use `**kwargs` to pass a dictionary of arguments to a function.

```py
def say_hello(**kwargs):
  if "name" in kwargs:
    print("Hello, " + kwargs["name"])
  else:
    print("Hello, world!")

say_hello(name="John")
# => Hello, John
```

# 28: String Formatting

Using `.format()` we can format strings.

```py
print("Hello, {name}!".format(name="John"))
# => Hello, John!
```

# 29: Random Numbers

Use the `random` module to generate random numbers.

```py
import random

print(random.randint(1, 10)) # generates a random integer between 1 and 10

coolList = ["Python", "Java", "C++", "Ruby", "PHP"]
print(random.choice(coolList)) # chooses a random item from coolList
```
