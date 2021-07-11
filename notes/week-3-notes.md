# Week 3 Notes

## Dictionaries

A structure that lets you store info in key-value pairs.
Efficient way to translate fixed inputs to outputs.
Similar in definition to Javascript's objects

### Declaration

```py
monthConversions = {
  "Jan": "January",
  "Feb": "February",
  "Mar": "March",
  "Apr": "April",
  ...
}
```

### Accessing Values

```py
print(monthConversions["Jan"])
```

or

```py
print(monthConversions.get("Jan", "Invalid Key Message"))
```

Prints `January`

## While Loops

Let's you loop through a block of code

### Usage

```py
i = 1
while i <= 10:
  print("I'm in a loop, on iteration " + str(i))
  i += 1

print("Done with loop")
```

## For Loops

A fancier while loop

### Usage

```py
for letter in "hello":
  print(letter)
```

Prints:

```
h
e
l
l
o
```

You can iterate through any iterable object (eg String, Array)

### range()

Lets you iterate through a range of numbers

```py
for i in range(5):
  print(i)
```

Prints:

```
0
1
2
3
4
```

## Exponent function

A faster way to do exponents

```py
2**3
# This equals 8
```

## 2D Lists

Lists inside of a list!

### Declaration

```py
number_grid = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9].
  [0]
]
```

### Accessing

```py
# This gets the number 6
number_grid[1][2]
```

## Nested loops

Loops inside of loops!

### Usage

```py
for row in number_grid:
  for col in row:
    print(number_grid[row][col])
```
