## Loops in python

`for`, `while` and other friends

---

## The `for` loop

```python
for variable in sequence: 
	# Code block to execute
```

The `for` loop in Python is used to iterate over the elements of a sequence (such as a list, tuple, string, or other iterable objects).

---

## Example?

```python
fruits = ['apple', 'banana', 'cherry'] 
for fruit in fruits:
	print(fruit)
```

```
apple
banana
cherry
```

---

## String is also iterable
You just go through letters
```python
word = 'Python'
for letter in word:
    print(letter)
```

```
P
y
t
h
o
n
```

---

## `range()` function basic syntax

```python
range(stop)
range(start, stop[, step])
```

- **`start`**: The starting number of the sequence (inclusive). Defaults to `0` if not provided.
- **`stop`**: The ending number of the sequence (exclusive). This parameter is required.
- **`step`**: The difference between each number in the sequence. Defaults to `1` if not provided.

---

## Single Argument (`stop`)

The `range()` function generates a sequence of numbers, which is particularly useful for looping a specific number of times.

```python
for i in range(5):
    print(i)
```
```
0
1
2
3
4
```

---

## Two Arguments (`start`, `stop`)

```python
for i in range(2, 7):
    print(i)
```
```
2
3
4
5
6
```

---

## Three Arguments (`start`, `stop`, `step`)
```python
for i in range(1, 10, 2): print(i)
```
```
1
3
5
7
9
```

---
## And you can even go back
```python
for i in range(10, 0, -2):
    print(i)
```
```
10
8
6
4
2
```
---
