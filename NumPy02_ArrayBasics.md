## Why use NumPy Arrays?

NumPy arrays are a lot like Python lists, but

1. arrays are faster than lists (for accessing data)
2. lists can store mixed types (e.g. ints and floats). The data in an array must be of the same type (e.g. ints or floats but not both).

Because arrays contain a homogeneous data type, you can do things like sum() an array of floats without worry that one of those elements might be a string.

## Basic Array Operations
### Make a 1-d array

<!-- You can make a 1-d array from a list. -->
Man kann aus einem 1-d array eine Liste erzeugen

```python
arr = np.array([10, 20, 30, 40, 50])
```

**Print the array**

```python
print(arr)  
# [10 20 30 40 50]
```

**Check its dimensionality**

```python
print(arr.ndim)
# 1
```

**Check its shape**

```python
print(arr.shape)
# (5,)
```

**Check how many elements are in the array**

```python
len(arr)
# 5
```

### Make a 2-d array¶

You can make a 2-d array from a list of lists.

```python
arr_2d = np.array([
    [10, 20, 30, 40, 50],
    [100, 200, 300, 400, 500]
])

print(arr_2d)
# [[ 10  20  30  40  50]
#  [100 200 300 400 500]]
```

**Check its dimensionality**

```python
print(arr_2d.ndim)
# 2
```

**Check its shape**

```python
print(arr_2d.shape)
# (2, 5)
```

**Check its length**

```python
print(len(arr_2d))
# 2
```

> :memo: You might be surprised to see arr_2d has length 2, not 10. That's because arr_2d can be interpreted as an array that contains 2 arrays inside it. If you want to get the total number of nested elements in the array, you can use the array size attribute.

**Check how many elements are in the array**

```python
print(arr_2d.size)
# 10
```

**Check the object's type**

```python
type(arr_2d)
# <class 'numpy.ndarray'>
```

Check what type of data the array contains

```python
arr_2d.dtype
# int64
```

## Rules For Every NumPy Array

There are two basic rules for every numpy array..

1. Every element in the array must be of the same type and size.
2. If an array's elements are also arrays, those inner arrays must have the same type and number of elements as each other. In other words, multidimensional arrays must be rectangular, not jagged.

Good:

```python
np.array([1, 2, 3])
```

Bad:

```python
np.array([1, 'hello', 3])
#  array(['1', 'hello', '3'], dtype='<U21')
```

> :warning: Attention<br>
If you try to make an array from a list that contains a mix of integers and strings, numpy doesn't error. But, it casts the integers to strings in order to satisfy the property that every element is the same type.

Bad:

```python
np.array([
    [1, 2, 3, 4],
    [5, 6]
])
# array([list([1, 2, 3, 4]), list([5, 6])], dtype=object)
```

> :warning: Attention<br>
If you try to make an array from jagged lists like this, numpy doesn't error but it creates an array of objects. This means the array is essentially a Python list and lacks the performance benefits of using an array.

