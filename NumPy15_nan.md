## nan

You can use [NaN](https://numpy.org/doc/stable/reference/constants.html#numpy.NAN) to represent missing or invalid values. NaN is a floating point constant that numpy reserves and treats specially.

For example, consider this array called bot which contains two missing values. 

```python
bot = np.ones(shape = (3, 4))
bot[[0, 2], [1, 2]] = np.nan

print(bot)
# [[ 1. nan  1.  1.]
#  [ 1.  1.  1.  1.]
#  [ 1.  1. nan  1.]]
```

If you want to identify which elements of bot are NaN, you might be inclined to try bot == np.nan but the result may surprise you.

```python
print(bot == np.nan)
# [[False False False False]
#  [False False False False]
#  [False False False False]]
```

NumPy designed NaN so that nan == nan returns False, but nan != nan returns True.
```python
np.nan == np.nan  # False
np.nan != np.nan  # True
```

This is because equivalence between missing or invalid values is not well-defined.

In order to see which elements of an array are NaN, you can use NumPy's [isnan()](https://numpy.org/doc/stable/reference/generated/numpy.isnan.html) function.
```python
np.isnan(bot)
# array([[False,  True, False, False],
#        [False, False, False, False],
#        [False, False,  True, False]])
```

> :warning: Caution<br>
NaN is a special floating point constant, so it can only exist inside an array of floats. If you try inserting NaN into an array of integers, booleans, or strings, you’ll get an error or unexpected behavior.

```python
foo = np.array([1,2,3], dtype = 'int64')
foo[1] = nan

--> error
```



