## Creating NumPy Arrays

### How to make a 1-d array from a list

```python
np.array(['a', 'b', 'c'])
```

### How to make a 2-d array from a list of lists

```python
np.array([
    ['a', 'b'],
    ['c', 'd'],
    ['e', 'f']
])
```

### How to make a 3-d array from a list of lists of lists

```python
np.array([
    [
        ['a', 'b'],
        ['c', 'd'],
        ['e', 'f']
    ],
    [
        ['g', 'h'],
        ['i', 'j'],
        ['k', 'l']
    ]
])
```

> :memo: Info<br>
You can make follow this pattern to create higher dimensional arrays.
 
### How to make an array of zeros

A [quick google](https://www.google.com/search?q=how+to+make+a+numpy+array+of+zeros) search will lead you to the numpy documentation for [numpy.zeros](https://numpy.org/doc/stable/reference/generated/numpy.zeros.html).

**Make a (3,) array of 0s**

```python
np.zeros(shape=3)
# array([0., 0., 0.])
```

**Make a (3,5) array of 0s**

```python
np.zeros(shape=(3,5))
# array([[0., 0., 0., 0., 0.],
#        [0., 0., 0., 0., 0.],
#        [0., 0., 0., 0., 0.]])
```

### How to make an array filled with any value

See [numpy.full](https://numpy.org/doc/stable/reference/generated/numpy.zeros.html).

```python
np.full(shape = (3,5), fill_value = 'cat')
# array([['cat', 'cat', 'cat', 'cat', 'cat'],
#        ['cat', 'cat', 'cat', 'cat', 'cat'],
#        ['cat', 'cat', 'cat', 'cat', 'cat']], dtype='<U3')
```

### How to make a sequence array 1, 2, ... N

```python
np.arange(start=1, stop=5, step=1)
# array([1, 2, 3, 4])
```


> :memo: Note<br>
Note that start is inclusive while stop is exclusive.

**Alternatively:**

```python
np.arange(4)
# array([0, 1, 2, 3])
```

**Random Values**

```python
np.random.randint(low = 1, high = 7, size = (2,3))
# array([[5, 6, 5],
         [4, 3, 4]])
```

