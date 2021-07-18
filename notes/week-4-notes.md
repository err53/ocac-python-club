# Week 4 Notes

## Comments

```py
# Make a comment using a hashtag

'''
You could also use three quotation marks to make a multi-line string that acts like a comment
It's not pythonic, however, so you might choose to use hashtags instead.
'''

# You can also comment out a line of code with a hashtag
# print("This won't be run")
```

## Error Handling

You can use the `except` keyword to handle errors.

```py
try:
  num = int(input("Enter a number: "))
  print(num)
except:
  print("That's not a number!")
```

You can also pass a specific error type to handle.

```py
try:
  otherNum = 10 / 0
  num = int(input("Enter a number: "))
  print(num)
except ZeroDivisionError:
  print("You can't divide by zero!")
except ValueError:
  print("That's not a number!")
```

By excepting an error as a variable, you can print details about the error.

```py
try:
  otherNum = 10 / 0
except ZeroDivisionError as e:
  print(e)
```

## File I/O

Use the `open()` function to open a file.

You can use flags to specify how the file should be opened:

| flag | description    |
| ---- | -------------- |
| r    | read only      |
| w    | write only     |
| a    | append         |
| r+   | read and write |

```py
# Open a file
f = open("data.txt", "r")
```

Use the `close()` function to close a file.

```py
# Close a file
f.close()
```

### Reading Files

Use the `readable()` function to check if a file is readable.

```py
# Check if a file is readable
if f.readable():
  print("The file is readable")
```

Use the `read()` function to read a file.

```py
# Read a file
content = f.read()
print(content)
```

Use the `readline()` function to read a line from a file.

```py
# Read a line from a file
line = f.readline()
print(line)
```

Use the `readlines()` function to read all lines from a file and return them as a list.

```py
# Read all lines from a file
lines = f.readlines()
for line in lines:
  print(line)
```

### Writing Files

First, open a file for appending.

```py
# Open a file for appending
f = open("data.txt", "a")
```

Next, write a line to the file.

```py
# Write a line to a file
# Be sure to add a newline character at the end of the line
# Otherwise, the next line will be written on the same line
f.write("This is a line\n")
```

You can use the `w` flag to create a new file.

```py
# Create a new file
f = open("data2.txt", "w")
```

## Modules and PIP

Modules allow for more code reusability

```py
# Import a module
import math

# Call a function from a module
print(math.pi)
```

You can also import files you write as modules.

```py
# my_module.py
def my_function(x):
  return x + 1

# Import a file as a module
import my_module

print(my_module.my_function(5)) # Prints 6
```

If you want more modules, you can use the `pip` package manager.

```bash
# Install a module
pip install numpy
```

You can then use the module in your code.

```py
# Import a module
import numpy

# Call a function from a module
print(numpy.cos(math.pi))
```

Modules are installed in a `site-packages` folder by default.

You can uninstall modules using `pip` as well.

```bash
# Uninstall a module
pip uninstall numpy
```

## Classes and objects

Classes let you make your own data types.

```py
# student.py
class Student:
  def __init__(self, name, major, gpa, is_on_probation):
    self.name = name
    self.major = major
    self.gpa = gpa
    self.is_on_probation = is_on_probation
  # The `self` parameter is a reference to the current instance of the class, and is used to store data specific to that instance.
```

We can now create a new student object.

```py
# app.py
from student import Student

student1 = Student("John Doe", "CS", 3.5, False)
student2 = Student("Jane Doe", "Buisness", 3.8, True)

print(student1.name) # Prints "John Doe"
print(student2.major) # Prints "Buisness"
print(student2.gpa) # Prints 3.8
```

With classes and objects, we can make more complex data types and model representations of real-world objects.

## Object Functions

Lets update the student class to add an honour role calculation.

```py
# student.py
class Student:
  def __init__(self, name, major, gpa, is_on_probation):
    self.name = name
    self.major = major
    self.gpa = gpa
    self.is_on_probation = is_on_probation

  def on_honour_roll(self):
    if self.gpa >= 3.5:
      return True
    else:
      return False
```

Now we can update our code to use the new function.

```py
# app.py
from student import Student

student1 = Student("John Doe", "CS", 3.0, False)
student2 = Student("Jane Doe", "Buisness", 3.8, True)

student1.on_honour_roll() # Prints False
student2.on_honour_roll() # Prints True
```

## Inheritance

Inheritance allows us to create subclasses of existing classes.

```py
# chef.py
class Chef:
  def make_chicken(self):
    print("Chef makes a chicken")
  def make_salad(self):
    print("Chef makes a salad")
  def make_special_dish(self):
    print("Chef makes a special dish")
```

```py
# ItalianChef.py
class ItalianChef(Chef):
  def make_pasta(self):
    print("Chef makes pasta")
  def make_salad(self):
    print("Chef makes a Italian salad")
  def make_special_dish(self):
    print("Chef makes a meat-and-pasta")
```

```py
# ChineseChef.py
class ChineseChef(Chef):
  def make_rice(self):
    print("Chef makes rice")
  def make_salad(self):
    print("Chef makes a Chinese salad")
  def make_special_dish(self):
    print("Chef makes a chicken-and-rice")
```

```py
# app.py
from chef import Chef
from italian_chef import ItalianChef
from chinese_chef import ChineseChef

generic_chef = Chef()
generic_chef.make_chicken() # Prints "Chef makes a chicken"
generic_chef.make_salad() # Prints "Chef makes a salad"
generic_chef.make_special_dish() # Prints "Chef makes a special dish"

italian_chef = ItalianChef()
italian_chef.make_chicken() # Prints "Chef makes a chicken"
italian_chef.make_pasta() # Prints "Chef makes pasta"
italian_chef.make_salad() # Prints "Chef makes a Italian salad"
italian_chef.make_special_dish() # Prints "Chef makes a meat-and-pasta"

chinese_chef = ChineseChef()
chinese_chef.make_chicken() # Prints "Chef makes a chicken"
chinese_chef.make_rice() # Prints "Chef makes rice"
chinese_chef.make_salad() # Prints "Chef makes a Chinese salad"
chinese_chef.make_special_dish() # Prints "Chef makes a chicken-and-rice"
```

As demonstrated, the subclasses inherit methods from the parent class, and can override methods.
