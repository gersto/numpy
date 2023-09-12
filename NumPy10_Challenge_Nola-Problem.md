## Setup

Make the following 4x7 array called nola that starts with 1 and steps by 2.
However, note that the first element in each row is always 4 more than the last element in the previous row.

```python
nola

[[ 1  3  5  7  9 11 13]
 [17 19 21 23 25 27 29]
 [33 35 37 39 41 43 45]
 [49 51 53 55 57 59 61]]
```

## Solution

```python
import numpy as np

nola = np.arange(start=1, stop=65, step=2).reshape(4,-1)
nola = nola[:, :-1]

print(nola)
# [[ 1  3  5  7  9 11 13]
#  [17 19 21 23 25 27 29]
#  [33 35 37 39 41 43 45]
#  [49 51 53 55 57 59 61]]
```

## Explanation

The trick here is to think of nola as the first 7 columns in this 4x8 array.
```python
[[ 1  3  5  7  9 11 13 15]
 [17 19 21 23 25 27 29 31]
 [33 35 37 39 41 43 45 47]
 [49 51 53 55 57 59 61 63]]
 ------ include ------
```

This array is simply the sequence 1, 3, 5, ... 61, 63 (without any weird gaps) arranged into a 4x8 shape.
So, if we can build this array, we can easily chop off the last column to make nola.

- Build the sequence array: 1, 3, 5, ... 61, 63.

  ```python
  [[ 1  3  5  7  9 11 13 15]
   [17 19 21 23 25 27 29 31]
   [33 35 37 39 41 43 45 47]
   [49 51 53 55 57 59 61 63]]
   ------ include ------
  ```
  Here we use np.arange(), passing in start=1, stop=65, and step=2. Note that stop is exclusive,
  so the sequence goes from 1 up to but not including 65.

- Reshape the 1-D array into a 2-D array.

  Specifically, we convert the array from shape (32,) to shape (4,8). There are a few ways we can do this..
  - np.reshape()
    ```python
    nola = np.reshape(np.arange(start=1, stop=65, step=2), (4,8))

    print(nola)
    # [[ 1,  3,  5,  7,  9, 11, 13, 15],
    #  [17, 19, 21, 23, 25, 27, 29, 31],
    #  [33, 35, 37, 39, 41, 43, 45, 47],
    #  [49, 51, 53, 55, 57, 59, 61, 63]]
    ```

  - ndarray.reshape()
    ```python
    nola = np.arange(start=1, stop=65, step=2).reshape(4,8)

    print(nola)
    # [[ 1,  3,  5,  7,  9, 11, 13, 15],
    #  [17, 19, 21, 23, 25, 27, 29, 31],
    #  [33, 35, 37, 39, 41, 43, 45, 47],
    #  [49, 51, 53, 55, 57, 59, 61, 63]]
    ```

  See [numpy.reshape()](https://numpy.org/doc/stable/reference/generated/numpy.reshape.html)

  Pro Tip:<br>
  In either of these methods, we can replace exactly one of the dimensions with -1 and NumPy will figure it out       for us. For example,
  ```python
  nola = np.arange(start=1, stop=65, step=2).reshape(4, -1)

  print(nola)
  # [[ 1,  3,  5,  7,  9, 11, 13, 15],
  #  [17, 19, 21, 23, 25, 27, 29, 31],
  #  [33, 35, 37, 39, 41, 43, 45, 47],
  #  [49, 51, 53, 55, 57, 59, 61, 63]]
  ```
  Here we're basically telling NumPy, "reshape the array into an array with 4 rows". Since the original array had     32 elements, NumPy knows the resulting array must have 8 columns.

- Select all columns but the last.
  ```python
  nola = nola[:, :-1]

  print(nola)
  # [[ 1  3  5  7  9 11 13]
  #  [17 19 21 23 25 27 29]
  #  [33 35 37 39 41 43 45]
  #  [49 51 53 55 57 59 61]]
  ```

  nola[:, :-1] can be interpreted as "Select every row, and select all columns from the start, up to but excluding    the last column". (-1 means "last" index. See **negative indexing**)
