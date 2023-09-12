## Setup

You decide to invest in a series of billboards along interstate 10 to advertise your stylish new chicken restaurant, Chic-fil-A
- You buy three billboards evenly spaced starting from mile marker 17 and ending on mile marker 28.
- You buy another three billboards starting on mile marker 32 and ending on mile marker 36.
- In order, from mile marker 17 to 36, your billboards display these ads: A, B, C, C, B, A.

Determine how far each C ad is from your restaurant which is located at mile marker 30.

```python
# ads / restaurant*:   A     B     C   *   C  B  A
# billboards:        --|-----|-----|---|---|--|--|--
# mile markers:       17          28  30  32    36
```

## Solution

```python
import numpy as np

dists = np.abs(np.linspace([17,32],[28,36], num = 3, axis=1) - 30)
dists[[0, 1],[2, 0]]

array([2., 2.])
```

### Explanation

First thinking about the first 3 ads (A,B,C) evently spaced between marker 17 and 28.<br>
Numpy has a function of evently spaced numbers (search google "numpy array of evently spaced numbers").<br>
You will find a function called [linspace](https://numpy.org/doc/stable/reference/generated/numpy.linspace.html)
```python
# A five element array from 0 to 10
np.linspace(start=0, stop=10, num=5)

array([0., 2.5, 5., 7.5, 10.])
```

Start and stop could be an array-value. You will get back an 2-dimensional array.
```python
np.linspace(start=[0,5], stop=[10,15], num=5)

array([[0., 5.],
       [2.5, 7.5],
       [5., 10.],
       [7.5, 12.5],
       [10., 15.]])
```
The first column is a sequence from 0 to 10 and the second column is a sequence from 5 to 15.

With the axis paramater you can control the orientation of the arrays
```python
np.linspace(start=[0,5], stop=[10,15], num=5, axis=1)

array([[0., 2.5, 5., 7.5, 10.],
       [5., 7.5, 10., 12.5, 15.]])
```

With the mile markers
```python
np.linspace(start=[17,32], stop=[28,36], num=3, axis=1)

array([[17., 22.5, 28.],
       [32., 34., 36.]])
```
These array represents the ads ABC and CBA abd where they located.

To build the distance from the restaurant we substract 30
```python
np.linspace(start=[17,32], stop=[28,36], num=3, axis=1) - 30

array([[-13., -7.5, -2.],
       [2., 4., 6.]])
```

There are no negativ distances possible, therefore we need an absolute funktion ([absolute](https://numpy.org/doc/stable/reference/generated/numpy.absolute.html))
```python
np.abs(np.linspace(start=[17,32], stop=[28,36], num=3, axis=1) - 30)

array([[13., 7.5, 2.],
       [2., 4., 6.]])
```

To determine how far is the C Ad from the restaurant.<br>
The C Ad is located on 0,2 (2.) and 1,0 (2.) and therfore we have to pick up the indexes (a list of row indexes and a list of column indexes) for this
```python
np.abs(np.linspace(start=[17,32], stop=[28,36], num=3, axis=1) - 30)[[0, 1],[2, 0]]

array([2., 2.])
```

2.0 and 2.0 is the desired solution !!!
