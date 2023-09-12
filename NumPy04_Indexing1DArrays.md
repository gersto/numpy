## Indexing 1-D Arrays

Start by making a 1d array called foo with five elements.

```python
foo = np.array([10, 20, 30, 40, 50])

print(foo)
# [10 20 30 40 50]
```

### Access the ith element of an array

We can access the ith element just like a python list using square bracket notation where the first element starts at index zero.

```python
print(foo)
# [10 20 30 40 50]

foo[0]  # 10, 1st element
foo[1]  # 20, 2nd element
```

### Modify the ith element

Set the 2nd element to 99

```python
print(foo) 
# [10 20 30 40 50]

foo[1] = 99

print(foo)
# [10 99 30 40 50]
```

### Access the last element
**Okay**
```python
print(foo)
# [10 20 30 40 50]

print(foo[4])
# 50
```

**Better**
```python
print(foo)
# [10 20 30 40 50]

print(foo[len(foo) - 1])
# 50
```

**Best**
```python
print(foo)
# [10 20 30 40 50]

print(foo[-1])
# 50
```

### Negative Indexing

Just like python lists, we can use negative indexing..

```python
print(foo)
# [10 20 30 40 50]

print(foo[-1])  # 50, last element
print(foo[-2])  # 40, 2nd-to-last element
print(foo[-3])  # 30, 3rd-to-last element
```

### Out of bounds error

If we try to access an element outside the bounds of the array, we’ll get an “out of bounds” error.

```python
print(foo)
# [10 20 30 40 50]

print(foo[999])
# IndexError:
```


### Accessing multiple elements

We can access multiple elements using a list or numpy array of indices.

Example

```python
print(foo)
# [10 20 30 40 50]

print(foo[[0, 1, 4]])
# [ 10, 20,  50]
```

Indices can be repeated..

```python
print(foo)
# [10 20 30 40 50]

print(foo[[0, 1, 0]])
# [ 10, 20,  10]
```

Indices can be another numpy array

```python
print(foo)
# [10 20 30 40 50]

print(foo[np.zeros(shape=3, dtype='int64')]) 
# array([10, 10, 10])
```

**Array Slicing**

We can use slicing just like python lists. The signature is essentially

```python
foo[ start index : end index : step size ]
```

>:memo: Note<br>
Note that start index is inclusive while end index is exclusive.

Get every element from the beginning of the array to index 2 exclusive

```python
print(foo)
# [10 20 30 40 50]

print(foo[:2])
# [ 10, 20]
```

Get every element from index 2 inclusive to the end of the array

```python
print(foo)
# [10 20 30 40 50]

print(foo[2:])
# [30, 40, 50]
```

Get every other element from the beginning of the array to the end

```python
print(foo)
# [10 20 30 40 50]

print(foo[::2])
# [10, 30, 50]
```

### Modifying multiple elements

If you want to modify multiple elements of a 1-d array, you can use a list of indices and a list of assignment values. The list of assignment values should be the same length as the list of indices.

```python
print(foo)
# [10 20 30 40 50]

foo[[0, 1, 4]] = [100, 200, 400]

print(foo)
# [100 200  30  40 400]
```

..or you can assign everything to a scalar.

```python
print(foo)
# [10 20 30 40 50]

foo[[0, 1, 4]] = 99

print(foo)
# [99 99 30 40 99]
```

