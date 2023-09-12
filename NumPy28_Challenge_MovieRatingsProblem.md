## Movie Ratings Problem

### Setup

You’re given a 10x2 array of floats where each row represents a movie. The first column represents the movie’s rating and the second column represents the director’s rating.

```python
import numpy as np

generator = np.random.default_rng(123)
ratings = np.round(generator.uniform(low=0.0, high=10.0, size=(10, 2)))
ratings[[1,2,7,9], [0,0,0,0]] = np.nan

print(ratings)
# [[ 7.  1.]
#  [nan  2.]
#  [nan  8.]
#  [ 9.  3.]
#  [ 8.  9.]
#  [ 5.  2.]
#  [ 8.  2.]
#  [nan  6.]
#  [ 9.  2.]
#  [nan  5.]]
```

Your goal is to create a third column that represents the overall rating. The overall rating is equal to the movie rating if it exists, otherwise the director’s rating.

### Solution

#### Solution 1

```python
x = np.where(np.isnan(ratings[:, 0]), ratings[:, 1], ratings[:,0])
result = np.insert(arr = ratings, values = x, axis = 1, obj = 2)

print(result)
```

#### Solution 2

```python
x = np.where(np.isnan(ratings[:, 0]), ratings[:, 1], ratings[:,0])
result = np.hstack((ratings, x[:, None]))

print(result)
```

### Explanation

#### Explanation 1

Do determine the values of the third column
```python
x = np.where(np.isnan(ratings[:, 0]), ratings[:, 1], ratings[:,0])

print(x)
```

The challenge is to put these values in the array. We use the [insert()](https://numpy.org/doc/stable/reference/generated/numpy.insert.html) function.

We assign these to an extra array(result) and we don't modify the ratings array
```python
x = np.where(np.isnan(ratings[:, 0]), ratings[:, 1], ratings[:,0])
result = np.insert(arr = ratings, values = x, axis = 1, obj = 2)

print(result)
```

#### Explanation 2

It starts like the first solution
```python
x = np.where(np.isnan(ratings[:, 0]), ratings[:, 1], ratings[:,0])

print(x)
```

The trick is to make x a 2-dimensional array
```python
x[:, None]

array([[7.],
       [2.],
       [8.],
       [9.],
       [8.],
       [5.],
       [8.],
       [6.],
       [9.],
       [5.]])
```

Now you can use the hstack function to combine these 2 arrays
```python
x = np.where(np.isnan(ratings[:, 0]), ratings[:, 1], ratings[:,0])
result = np.hstack((ratings, x[:, None]))

print(result)
```



