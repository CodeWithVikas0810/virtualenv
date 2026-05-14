# Popular List Operations and Methods in Python — 

---

# 1. Introduction

Lists are one of the most important data structures in Python.

They are used to:

* store collections of data
* maintain ordered sequences
* process grouped information
* implement stacks, queues, and more

Python lists are:

* ordered
* mutable
* dynamic

---

# 2. What is a List?

A list is:

> An ordered, mutable collection of elements.

Example:

```python id="2mndcm"
numbers = [1, 2, 3, 4]
```

A list can store:

* integers
* strings
* objects
* mixed data types

Example:

```python id="a5l9im"
data = [1, "hello", 3.5, True]
```

---

# 3. Characteristics of Python Lists

| Feature           | Description               |
| ----------------- | ------------------------- |
| Ordered           | Maintains insertion order |
| Mutable           | Can modify elements       |
| Dynamic           | Size can grow/shrink      |
| Indexed           | Supports indexing         |
| Allows duplicates | Duplicate values allowed  |

---

# 4. Creating Lists

## Empty List

```python id="rb1a6v"
items = []
```

---

## Using `list()`

```python id="5ol1qj"
items = list()
```

---

# 5. List Indexing

Lists use zero-based indexing.

Example:

```python id="2tcrh9"
fruits = ["apple", "banana", "mango"]

print(fruits[0])
```

Output:

```text id="bbfsl5"
apple
```

---

## Negative Indexing

```python id="a3o1lq"
print(fruits[-1])
```

Output:

```text id="zqz5yv"
mango
```

---

# 6. List Slicing

Syntax:

```python id="2m7db4"
list[start:end:step]
```

---

## Example

```python id="9m8z7v"
numbers = [1, 2, 3, 4, 5]

print(numbers[1:4])
```

Output:

```text id="l0nlpq"
[2, 3, 4]
```

---

## Reverse List

```python id="r7e2mz"
print(numbers[::-1])
```

Output:

```text id="vdu9mc"
[5, 4, 3, 2, 1]
```

---

# 7. Common List Operations

---

# Concatenation

```python id="2g8b7r"
a = [1, 2]
b = [3, 4]

print(a + b)
```

Output:

```text id="sn95gt"
[1, 2, 3, 4]
```

---

# Length

```python id="d79npx"
len(fruits)
```

---

# 8. Popular List Methods

---

# `append()`

Adds one element at end.

```python id="mxjlwm"
numbers = [1, 2]

numbers.append(3)

print(numbers)
```

Output:

```text id="jv0q9q"
[1, 2, 3]
```

---

# `extend()`

Adds multiple elements.

```python id="4hm5lu"
numbers = [1, 2]

numbers.extend([3, 4])

print(numbers)
```

Output:

```text id="5spjlwm"
[1, 2, 3, 4]
```

---

# `insert()`

Insert at specific index.

```python id="gm7tq9"
numbers = [1, 3]

numbers.insert(1, 2)

print(numbers)
```

Output:

```text id="szhzj7"
[1, 2, 3]
```

---

# `remove()`

Removes first matching value.

```python id="o9k5ul"
numbers = [1, 2, 3]

numbers.remove(2)

print(numbers)
```

Output:

```text id="5x7ggl"
[1, 3]
```

---

# `pop()`

Removes and returns element.

```python id="e3mbul"
numbers = [1, 2, 3]

value = numbers.pop()

print(value)
print(numbers)
```

Output:

```text id="4yyh67"
3
[1, 2]
```

---

# `clear()`

Removes all elements.

```python id="b6z87n"
numbers.clear()
```

---

# `index()`

Returns index of value.

```python id="j8hlsm"
fruits = ["apple", "banana"]

print(fruits.index("banana"))
```

Output:

```text id="vjlwm3"
1
```

---

# `count()`

Counts occurrences.

```python id="j5b6y8"
numbers = [1, 1, 2]

print(numbers.count(1))
```

Output:

```text id="q6k6h8"
2
```

---

# `sort()`

Sorts original list.

```python id="0h0kv5"
numbers = [3, 1, 2]

numbers.sort()

print(numbers)
```

Output:

```text id="djlwm9"
[1, 2, 3]
```

---

# Descending Sort

```python id="0lk4im"
numbers.sort(reverse=True)
```

---

# `reverse()`

Reverses original list.

```python id="bgmfg0"
numbers.reverse()
```

---

# `copy()`

Creates shallow copy.

```python id="n4j8y4"
new_list = numbers.copy()
```

---

# 9. Mutable vs Immutable Behavior

Lists are mutable.

Example:

```python id="m8p6br"
numbers = [1, 2, 3]

numbers[0] = 100

print(numbers)
```

Output:

```text id="9l7vko"
[100, 2, 3]
```

Unlike strings:

```python id="8n4gr4"
name = "hello"

# name[0] = "H"
```

This causes error because strings are immutable.

---

# 10. Nested Lists

Lists inside lists.

```python id="u7prmn"
matrix = [
    [1, 2],
    [3, 4]
]
```

Access:

```python id="n1yzr5"
print(matrix[1][0])
```

Output:

```text id="2dlzbb"
3
```

---

# 11. Iterating Through Lists

---

# Using `for`

```python id="t14gzd"
fruits = ["apple", "banana"]

for fruit in fruits:
    print(fruit)
```

---

# Using `range()`

```python id="e53qg6"
for i in range(len(fruits)):
    print(fruits[i])
```

---

# Using `enumerate()`

```python id="z5v1g9"
for index, value in enumerate(fruits):
    print(index, value)
```

---

# 12. List Comprehensions

Compact way to create lists.

Syntax:

```python id="xtvtjlwm"
[expression for item in iterable]
```

---

## Example

```python id="n7k9b0"
squares = [x * x for x in range(5)]

print(squares)
```

Output:

```text id="gkq63o"
[0, 1, 4, 9, 16]
```

---

## With Condition

```python id="5fyz1r"
evens = [x for x in range(10) if x % 2 == 0]
```

---

# 13. Copying Lists

---

# Assignment Problem

```python id="cw0c50"
a = [1, 2]
b = a
```

Both point to same memory.

---

# Shallow Copy

```python id="qzcb7y"
b = a.copy()
```

or

```python id="wzxg3l"
b = a[:]
```

---

# Deep Copy

For nested lists:

```python id="m9p1dw"
import copy

b = copy.deepcopy(a)
```

---

# 14. Sorting Lists

---

# `sorted()`

Returns new sorted list.

```python id="3ppl3o"
numbers = [3, 1, 2]

new_numbers = sorted(numbers)

print(new_numbers)
```

Original list unchanged.

---

# Custom Sorting

```python id="fjlwmn"
words = ["apple", "kiwi", "banana"]

words.sort(key=len)
```

---

# 15. Searching in Lists

---

# Using `in`

```python id="5r4r9t"
print(2 in [1, 2, 3])
```

---

# Linear Search

```python id="e2pjm8"
numbers = [1, 2, 3]

target = 2

for num in numbers:
    if num == target:
        print("Found")
```

---

# 16. Built-in Functions for Lists

---

# `len()`

```python id="30mn0x"
len(numbers)
```

---

# `max()`

```python id="c0n7ml"
max(numbers)
```

---

# `min()`

```python id="jlwmv6"
min(numbers)
```

---

# `sum()`

```python id="pk1p9d"
sum(numbers)
```

---

# `any()`

```python id="e8j2gf"
any([False, True])
```

---

# `all()`

```python id="rx6dgh"
all([True, True])
```

---

# 17. Time Complexity of List Operations

| Operation           | Complexity |
| ------------------- | ---------- |
| Access by index     | O(1)       |
| Append              | O(1)       |
| Insert at beginning | O(n)       |
| Remove              | O(n)       |
| Search              | O(n)       |
| Sort                | O(n log n) |

---

# 18. Common Mistakes

---

# Modifying While Iterating

Bad:

```python id="ib9e44"
for item in numbers:
    numbers.remove(item)
```

Can skip elements.

---

# Confusing `append()` vs `extend()`

```python id="1srmbl"
a.append([3, 4])
```

Produces:

```text id="cnkh8w"
[1, 2, [3, 4]]
```

Whereas:

```python id="s8yqjh"
a.extend([3, 4])
```

Produces:

```text id="kshv63"
[1, 2, 3, 4]
```

---

# 19. Best Practices

---

# Prefer List Comprehensions

Cleaner and faster.

---

# Use Meaningful Variable Names

Good:

```python id="93jjlwm"
student_names = []
```

Bad:

```python id="vjiv8x"
x = []
```

---

# Avoid Excessive Nested Lists

Can reduce readability.

---

# 20. Real-World Examples

---

# Stack Using List

```python id="nxb2tx"
stack = []

stack.append(1)
stack.append(2)

stack.pop()
```

---

# Queue Simulation

```python id="jlwm7u"
queue = []

queue.append(1)
queue.append(2)

queue.pop(0)
```

---

# Store User Data

```python id="3mjlwm"
users = ["vikas", "rahul", "aman"]
```

---
