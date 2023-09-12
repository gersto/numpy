## Math Functions

### sum()

Consider this 2-d array, foo.
```python
foo = np.array(
    [[5.0, 2.0, 9.0],
     [1.0, 0.0, 2.0],
     [1.0, 7.0, 8.0]]
)
```

There are numerous ways to take its sum with the [sum()](https://numpy.org/doc/stable/reference/generated/numpy.sum.html) function.

Sum all the values of foo
```python
np.sum(foo)  # 35.0
```

Sum across axis 0 (column sums)
```python
np.sum(foo, axis=0)
# array([ 7.,  9., 19.])
```

Sum across axis 1 (row sums)
```python
np.sum(foo, axis=1)
# array([16.,  3., 16.])
```

To keep the dimension of the array
```python
np.sum(foo, axis=0, keepdima=True)
# array([[ 7.,  9., 19.]])
```

If foo contains NaNs, sum() returns NaN
```python
foo[0, 0] = np.nan
np.sum(foo)  # nan
```

There are numerous ways to exclude NaNs or treat them as 0s.

- where parameter
  ```python
  np.sum(foo, where = ~np.isnan(foo))  # 30.0
  ```
  Here we use the where parameter, telling the sum() function to only include elements where ~np.isnan(foo) evaluates to True;
- nan_to_num()
  ```python
  np.sum(np.nan_to_num(foo))  # 30.0
  ```
  Here we use the [nan_to_num()](https://numpy.org/doc/stable/reference/generated/numpy.nan_to_num.html) function, which converts NaNs to 0 (by default).
- nan_sum()
  ```python
  np.nansum(foo)  # 30.0
  ```
  Here we use the [nansum()](https://numpy.org/doc/stable/reference/generated/numpy.nansum.html) function which treats NaNs as 0s.

### Other Math Functions

Unsurprisingly, there are numerous math functions in NumPy including minimum(), maximum(), mean(), exp(), log(), floor(), and ceil() among others.
