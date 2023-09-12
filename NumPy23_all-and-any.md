## all() and any()

### all()

You can use the [all()](https://numpy.org/doc/stable/reference/generated/numpy.all.html#numpy.all) function to check if all the values in an array meet some condition.

```python
foo = np.array([
    [np.nan,    4.4],
    [   1.0,    3.2],
    [np.nan, np.nan],
    [   0.1, np.nan]
])
```

```python
np.isnan(foo)

array([[ True, False],
       [False, False],
       [ True,  True],
       [False,  True]])
```

Check if all the values are NaN
```python
np.all(np.isnan(foo)) 
# False
```

Check if all the values in each row are NaN
```python
np.all(np.isnan(foo), axis=1)
# array([False, False,  True, False])
```

Check if all the values in each column are NaN
```python
np.all(np.isnan(foo), axis=0)
# array([False, False])
```

### any()

You can use the [any()](https://numpy.org/doc/stable/reference/generated/numpy.any.html#numpy.any) function to check if any of the values in an array meet some condition.
```python
foo = np.array([
    [np.nan,    4.4],
    [   1.0,    3.2],
    [np.nan, np.nan],
    [   0.1, np.nan]
])
```

Check if any value is NaN
```python
np.any(np.isnan(foo)) 
# True
```

Check if any value in each row is NaN
```python
np.any(np.isnan(foo), axis=1)
array([ True, False,  True,  True])
```

Check if any value in each column is NaN
```python
np.any(np.isnan(foo), axis=0)
array([ True,  True])
```

You can use it to mask some values
```python
mask = np.any(np.isnan(foo), axis=1)
foo[mask]

array([[nan, 4.4],
       [nan, nan],
       [0.1, nan]])
```

