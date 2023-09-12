## Infinity

Like NaN, numpy reserves floating point constants for [infinity](https://numpy.org/devdocs/reference/constants.html#numpy.Infinity) and [negative infinity](https://numpy.org/devdocs/reference/constants.html#numpy.Infinity) that behave specially.

If you want to insert these values directly, you can use np.inf and np.NINF

```python
np.array([np.inf, np.NINF])
# array([ inf, -inf])
```

More commonly, these values occur when you divide by 0. 

```python
np.array([-1, 1])/0
# array([-inf,  inf])
```

Spezial behaviour:
- Multiplying a positiv constant to inf gives inf
  ```python
  np.inf * 22
  inf
  ```
- Adding Infinity to Infinity gives inf
  ```python
  np.inf + np.inf
  inf
  ```
- Substracting Infinity from Infinity has undefined behaviour
  ```python
  np.inf - np.inf
  nan
  ```
- Dividing Infinity from Infinity has undefined behaviour
  ```python
  np.inf / np.inf
  nan
  ```
- Comparing Infinity to Infinity is True
  ```python
  np.inf == np.inf
  True
  ```
- Comparing Negative Infinity to Negative Infinity is True
  ```python
  np.NINF == np.NINF
  True
  ```
- Comparing array with inf
  ```python
  foo = np.array([4.4, np.inf, 1.0, np.NINF, 3.1, np.inf])
  foo == np.inf
  array([False, True, False, False, False, True])
  ```
- Comparing array with NINF
  ```python
  foo = np.array([4.4, np.inf, 1.0, np.NINF, 3.1, np.inf])
  foo == np.NINF
  array([False, False, False, True, False, False])
  ```
- Use of inf-Funktions
  ```python
  foo = np.array([4.4, np.inf, 1.0, np.NINF, 3.1, np.inf])

  np.isposinf(foo)
  array([False, True, False, False, False, True])

  np.isneginf(foo)
  array([False, False, False, True, False, False])

  np.isinf(foo)
  array([False, True, False, True, False, True])
  ```
