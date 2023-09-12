## Setup

After binge watching the discovery channel, you ditch your job as a trial lawyer to become a gold miner.
You decide to prospect five locations underneath a 7x7 grid of land. How much gold do you uncover at each location?

```python
import numpy as np

np.random.seed(5555)
gold = np.random.randint(low=0, high=10, size=(7,7))

print(gold)
# [[2 3 0 5 2 0 3]
#  [8 8 0 7 1 5 3]
#  [0 1 6 2 1 4 5]
#  [4 0 8 9 9 8 7]
#  [4 2 7 0 7 2 1]
#  [9 8 9 2 5 0 8]
#  [1 9 8 2 6 4 3]]

locs = np.array([
    [0,4],
    [2,2],
    [2,3],
    [5,1],
    [6,3]
])

print(locs)

[[0 4]
 [2 2]
 [2 3]
 [5 1]
 [6 3]]
```

Notes:
- **gold** states how much gold is under each location in the 7x7 grid of land
- **locs** states the coordinates of the five locations where you dig


## Solution

```python
gold[locs[:, 0], locs[:, 1]]

array([2, 6, 2, 8, 2])
```

### Explanation

```python
gold[locs[:, 0], locs[:, 1]]

array([2, 6, 2, 8, 2])
```

How do we get the value of gold manualy:
```python
gold[0, 4]

2
gold[2, 2]

6
```

How we can do this in one action. We can pass a list of row indexes and a list of column indexes.
```python
gold[[0, 2], [4, 2]]

array([2, 6])
```

How we can do this dynamically instead of manually. The first list corresponds to the first column of locs, and the second list corresponds to the second column of locs. The question is how you get back a column as an array?
```python
locs[:, 0]

array([0, 2, 2, 5, 6])

locs[:, 1]

array([4, 2, 3, 1, 3])
```

This makes the desired solution
```python
gold[locs[:, 0], locs[:, 1]]

array([2, 6, 2, 8, 2])
```
