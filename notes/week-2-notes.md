# Week 2 Notes

## Lists

Store an ordered list of items.
If you have used other programming languages, you might know these data structures as arrays.

### Declaration

```py
operating_systems = ["Windows", "MacOS", "Linux"]
```

### Replacing by index

```py
operating_systems[2] = "Unix"
```

### Getting by index

```py
print(operating_systems[1])
```

## List functions

Various functions used to manipulate lists

### Joining lists

```py
items.extend(y)
```

### Adding an item to the end of a list

```py
items.append(item)
```

### Adding an item at an index

All other elements are pushed to the right

```py
items.insert(1, item)
```

### Removing a known element

```py
items.remove(item)
```

### Clearing the list

```py
items.clear()
```

### Remove the last element from the list

```py
items.pop()
```

### Get the index of an item in the list

```py
items.index(item)
```

### Sorting the list

```py
items.sort()
```

### Reversing the list

```py
items.reverse()
```

### Copying the list

```py
new_items = items.copy()
```

## Tuples

Same as a list, but is immutable (not modifiable).
Typically used for sets of items that are tightly bound.
Not often used.

### Declaration

```py
coords = (4, 5)
```

### Getting by index

```py
x_coord = (4, 5)
```

## Functions

Functions let you group code that you will use often.
They are a key part of programming and good software development practices.

Make sure you pay attention to indentation!

### Declaration and calling the function

```py
def new_function():
    print("Hello from the new function!")

new_function()
```

### Passing parameters to the function

```py
def say_new_function(text):
    print("The new function says: " + text)

new_function("How's it going?")
```

### Returning information

```py
def add_one(num):
    return num + 1

print(add_one(2))
```

## If Statements

Essential logic conditions used in most programs

### Declaration

```py
hungry = True
tired = False

if hungry and tired:
    print("I am hungry and tired")
elif hungry:
    print("I am hungry")
elif tired:
    print("I am tired")
else:
    print("I am fine")
```

### Boolean operations

You can get the inverse of a boolean variable by appending the keyword `not` to the variable

## Operations that produce booleans (comparisons)

| Operation                | Symbol |
| ------------------------ | ------ |
| Less than                | `<`    |
| Greater than             | `>`    |
| Less than or equal to    | `<=`   |
| Greater than or equal to | `>=`   |
| Equal to                 | `==`   |
| Not equal to             | `!=`   |

Note: We don't use a single equal sign `=` for the equal to comparison because that's used for variable assignments already.

## Extra info I (Jason) thought might be helpful

### Code Style

These recommendations are pulled from [PEP 8](https://pep8.org/), which can also be found under the Google Classroom's resources tab.

### Function and Variable Naming

Generally, Python recommends the use of snake case / underscore case for function and variable names

### Tabs or Spaces

Python will accept either tabs or spaces for indentation, as long as you are consistent. However, the creators recommend 4 spaces if you're not already using tabs.
