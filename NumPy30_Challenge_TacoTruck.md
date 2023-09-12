## Taco Truck

### Setup

You own a taco truck that’s open 24/7 and manage five employees who run it. Employees work solo, eight-hour shifts. You decide the best way to set their schedule for the upcoming week is to create a bunch of random schedules and select one that looks best.

You build a 1000x21 array of random employee ids where element (i,j) gives the employee id working shift j for schedule i.

```python
import numpy as np

generator = np.random.default_rng(999)
schedules = generator.integers(low=0, high=5, size=(1000, 21))

print(schedules)
# [[4 3 0 ... 2 0 0]
#  [2 4 3 ... 3 3 2]
#  [1 0 1 ... 1 2 1]
#  ...
#  [2 2 1 ... 3 1 4]
#  [1 0 3 ... 2 3 2]
#  [1 1 4 ... 2 4 2]]
```

A Schedule is valid as long as no employee works two consecutive shifts. Get the row indices of all valid schedules.

### Solution

```python
is_valid = np.all(schedules[:, :-1] != schedules[:, 1:], axis=1)
np.nonzero(is_valid)[0]
```

### Explanation

```python
is_valid = np.all(schedules[:, :-1] != schedules[:, 1:], axis=1)
np.nonzero(is_valid)[0]
```

