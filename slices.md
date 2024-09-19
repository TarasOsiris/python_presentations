## Slices work on sequences

A **sequence** is an ordered collection of items where each item has a unique index. Common sequence types:

- **Lists**: Mutable sequences of items. Example: `my_list = [1, 2, 3]`
- **Tuples**: Immutable sequences. Example: `my_tuple = (1, 2, 3)`
- **Strings**: Immutable sequences of characters. Example: `my_string = "Hello"`

---

## Syntax

```
sequence[start:stop:step]
```
- `start`: The index where the slice starts (inclusive).
- `stop`: The index where the slice ends (exclusive).
- `step`: The increment between each index (default is `1`).

---

## Example

```python
my_list = [0, 1, 2, 3, 4, 5]  
print(my_list[1:4]) # Output: [1, 2, 3]
```

---
## Positive indices
Positive indices start from `0` at the beginning of the sequence.

```python
my_string = "Python"

# Get characters from index 0 to 2 (excluding 3)
print(my_string[0:3])  # Output: "Pyt"

# Get the first three elements of a list
my_list = [10, 20, 30, 40, 50]
print(my_list[0:3])  # Output: [10, 20, 30]
```
---

## Negative indices
Negative indices start from `-1` at the end of the sequence.
```python
my_tuple = (1, 2, 3, 4, 5)

# Get the last two elements
print(my_tuple[-2:])  # Output: (4, 5)

# Get elements from the third-last to the second-last
print(my_tuple[-3:-1])  # Output: (3, 4)
```

---
## A bit of visuals
```
Index Positions (Positive and Negative):

   Positive Index:     0     1     2     3     4
                       |     |     |     |     |
Elements in `my_tuple`: 1     2     3     4     5
                       |     |     |     |     |
  Negative Index:     -5    -4    -3    -2    -1
```

---
## Example 1
```python
my_tuple[-2:] # Output: (4, 5)
```
```
   Indices (Negative):  -5    -4    -3    -2    -1
                         |     |     |     |     |
   Elements:             1     2     3     4     5
                         |     |     |     |     |
   Slice:                                [--------->
```
---
## Example 2
```python
my_tuple[-3:-1] # Output: (3, 5)
```
```
   Indices (Negative):  -5    -4    -3    -2    -1
                         |     |     |     |     |
   Elements:             1     2     3     4     5
                         |     |     |     |     |
   Slice:                           [-------------)
```

---
## Default values
When you omit `start`, `stop`, or `step`, Python uses default values.

- `start` defaults to `0` if `step` is positive and to the last index if `step` is negative.
- `stop` defaults to the length of the sequence if `step` is positive and to `-1` if `step` is negative.
- `step` defaults to `1`.
```python
my_list = [0, 1, 2, 3, 4, 5]
# Omitting start
print(my_list[:3])  # Output: [0, 1, 2]
# Omitting stop
print(my_list[3:])  # Output: [3, 4, 5]
# Omitting both start and stop
print(my_list[:])   # Output: [0, 1, 2, 3, 4, 5]
```
---
## The `step` parameter
```python
my_list = [0, 1, 2, 3, 4, 5]

# Step of 2
print(my_list[0:6:2])  # Output: [0, 2, 4]

# Step of 3
print(my_list[::3])    # Output: [0, 3]
```
---

## Negative `step`
A negative `step` reverses the direction of the slice.
```python
my_list = [0, 1, 2, 3, 4, 5]

# Reverse the list
print(my_list[::-1])  # Output: [5, 4, 3, 2, 1, 0]

# Get every second element in reverse
print(my_list[5:0:-2])  # Output: [5, 3, 1]

# Including the first element
print(my_list[5::-2])  # Output: [5, 3, 1]
```
---

Practical examples!
![[Pasted image 20240915200526.png]]
---
## Reverse a string
```python
my_string = "Hello, World!"
reversed_string = my_string[::-1]
print(reversed_string)  # Output: "!dlroW ,olleH"
```

---
## Copy a list
```python
my_list = [1, 2, 3]
copy_list = my_list[:]
print(copy_list)  # Output: [1, 2, 3]
```
---
## Skip elements
```python
numbers = list(range(10))
# Get even numbers
evens = numbers[::2]
print(evens)  # Output: [0, 2, 4, 6, 8]

# Get odd numbers
odds = numbers[1::2]
print(odds)  # Output: [1, 3, 5, 7, 9]
```
---
## Extract substrings
```python
date_str = "2024-09-15"
year = date_str[:4]
month = date_str[5:7]
day = date_str[8:10]
print(f"Year: {year}, Month: {month}, Day: {day}")
# Output: Year: 2024, Month: 09, Day: 15
```
---
## Remove elements
```python
my_list = [0, 1, 2, 3, 4, 5]
# Remove elements at even indices
del my_list[::2]
print(my_list)  # Output: [1, 3, 5]
```
---
## Edge cases
---
## Slicing Beyond the Sequence Bounds
If `start` or `stop` are beyond the sequence bounds, Python adjusts them to fit.
```python
my_list = [0, 1, 2, 3, 4, 5]
# Start index beyond length
print(my_list[10:])  # Output: []
# Stop index beyond length
print(my_list[:10])  # Output: [0, 1, 2, 3, 4, 5]
```
---
## Zero step error
A `step` of zero raises a `ValueError`.
```python
# Raises ValueError: slice step cannot be zero
print(my_list[::0])
```
---
## Empty slices
Slices can result in empty sequences.
```python
print(my_list[2:2])  # Output: []
print(my_list[5:2])  # Output: []
```
---
## You can assign to slices!
```python
my_list = [0, 1, 2, 3, 4, 5]

# Replace elements at index 2 to 4
my_list[2:5] = [20, 30]
print(my_list)  # Output: [0, 1, 20, 30, 5]
# Insert elements
my_list[2:2] = [100, 200]
print(my_list)  # Output: [0, 1, 100, 200, 20, 30, 5]
# Delete elements
my_list[2:4] = []
print(my_list)  # Output: [0, 1, 20, 30, 5]
```
