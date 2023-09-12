## unique()

You can use the [unique()](https://numpy.org/doc/stable/reference/generated/numpy.unique.html) function to get the unique elements of an array.

Example
```python
gar = np.array(['b', 'b', 'a', 'a', 'c', 'c'])
np.unique(gar)
# array(['a', 'b', 'c'], dtype='<U1')
```

You may have noticed that 'b' appeared first in the input but 'a' appeared first in the output. That's because unique() returns the unique elements in sorted order.

### Get unique elements in order of first occurrence

You can use return_index=True to get index of first occurrence of each element in an array.
```python
gar = np.array(['b', 'b', 'a', 'a', 'c', 'c'])
np.unique(gar, return_index=True)
# (array(['a', 'b', 'c'], dtype='<U1'), array([2, 0, 4]))
```

With return_index=True, numpy returns a tuple containing 
- the unique elements array
- a corresponding array with the index at which each element first occurred in the original array

In the above example 'a' first occurred at index 2 in the original array, b first occurred at index 0, and so on.

If you want to reorder the unique elements in the same order they occurred in the original array, use argsort() the index array and use that to sort the unique elements array. 

```python
gar = np.array(['b', 'b', 'a', 'a', 'c', 'c'])
uniques, first_positions = np.unique(gar, return_index=True)
uniques[np.argsort(first_positions)]
# array(['b', 'a', 'c'], dtype='<U1')
```

### unique() with counts

You can use return_counts=True to additionally return the count of each element.

```python
np.unique(gar, return_counts=True)
# (array(['a', 'b', 'c'], dtype='<U1'), array([2, 2, 2]))
```
