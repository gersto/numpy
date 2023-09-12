## Professor Prick

### Setup

You’re a vindictive professor and one of your pet peeves is when students rush through their exams. To teach them a lesson, you decide to give zeros to the first three students who score less than sixty, in the order they turned in their exams.

Given a 1-d array of integers, identify the first three values less than sixty and replace them with zero.

```python
import numpy as np

generator = np.random.default_rng(80085)
scores = np.round(generator.uniform(low=30, high=100, size=15))

print(scores)
# [68. 36. 76. 57. 56. 54. 63. 64. 36. 88. 80. 82. 84. 76. 42.]
```

### Solution

```python
scores[(scores < 60).nonzero()[0][:3]] = 0
print(scores)

[68.  0. 76.  0.  0. 54. 63. 64. 36. 88. 80. 82. 84. 76. 42.]
```

### Explanation

To get an boolean array of persons with score < 60
```python
scores < 60

array([False,  True, False,  True,  True,  True, False, False,  True, False, False, False, False, False,  True])
```

To get the index of an array with values >0 use the [nonzero-Function](https://numpy.org/doc/stable/reference/generated/numpy.nonzero.html)

```python
np.array([0,1,2,0]).nonzero()

(array([1, 2], dtype=int64),)
```

We can use nonzero() on boolean values to get indexes in True values
```python
(scores < 60).nonzero()

(array([ 1,  3,  4,  5,  8, 14], dtype=int64),)
```

We can pick out the first array with index 0
```python
(scores < 60).nonzero()[0]

array([ 1,  3,  4,  5,  8, 14], dtype=int64)
```

To get the first 3 elements - now we have the indexes of the people
```python
(scores < 60).nonzero()[0][:3]

array([1, 3, 4], dtype=int64)
```

To give these peoples a 0 value
```python
scores[(scores < 60).nonzero()[0][:3]] = 0
print(scores)

[68.  0. 76.  0.  0. 54. 63. 64. 36. 88. 80. 82. 84. 76. 42.]
```
