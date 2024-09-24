## List comprehension

List comprehension is a powerful feature in Python that allows you to create lists in a concise and readable way. It combines loops and conditional statements into a single line, making your code more efficient and easier to understand.

---

## Traditional for loop

```python
squares = []
for x in range(10):
    squares.append(x**2)
print(squares)
# Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

---
## List comprehension

```python
squares = [x**2 for x in range(10)]
print(squares)
# Output: [0, 1, 4, 9, 16, 25, 36, 49, 64, 81]
```

---
## Syntax

```python
new_list = [expression for item in iterable]
```
- **`expression`**: The value to add to the list.
- **`item`**: The object or value in the iterable.
- **`iterable`**: A collection of objects like a list, tuple, or range.
---
## Example

```python
numbers = [1, 2, 3, 4, 5]
doubled = [n * 2 for n in numbers]
print(doubled)
# Output: [2, 4, 6, 8, 10]
```
---
## Conditionals
You can add an `if` statement to filter items.
```python
new_list = [expression for item in iterable if condition]
```
---
## Conditionals example
```python
even_numbers = [x for x in range(20) if x % 2 == 0]
print(even_numbers)
# Output: [0, 2, 4, 6, 8, 10, 12, 14, 16, 18]
```
---
## Using `if-else` in Expression

```python
new_list = [expression if condition else alternative for item in iterable]
```
---
## Conditionals example `if-else`
```python
numbers = [1, 2, 3, 4, 5]
result = ['Even' if n % 2 == 0 else 'Odd' for n in numbers]
print(result)
# Output: ['Odd', 'Even', 'Odd', 'Even', 'Odd']
```

---
## Nested loops!
You can include multiple `for` clauses to create combinations.

Syntax:

```python
new_list = [expression for item1 in iterable1 for item2 in iterable2]
```
---
## Example 1
```python
colors = ['red', 'green', 'blue']
objects = ['ball', 'cube']
combinations = [(color, obj) for color in colors for obj in objects]
print(combinations)
```
---
## We get all combinations!
```python
# Output: [('red', 'ball'), ('red', 'cube'), ('green', 'ball'), ('green', 'cube'), ('blue', 'ball'), ('blue', 'cube')]
```
---
## Example 2
```python
table = [(i, j, i * j) for i in range(1, 6) for j in range(1, 6)]
print(table)
```
---
## It's just a multiplication table!
```python
# Output: [(1, 1, 1), (1, 2, 2), ..., (5, 5, 25)]
```
---
## With functions
You can call functions within the expression.
```python
words = ['Hello', 'World', 'Python']
lengths = [len(word) for word in words]
print(lengths)
# Output: [5, 5, 6]
```
---
## Example
With custom function
```python
def square(n):
    return n * n

numbers = [1, 2, 3, 4]
squares = [square(n) for n in numbers]
print(squares)
# Output: [1, 4, 9, 16]
```

---
## What is dictionary and set?
