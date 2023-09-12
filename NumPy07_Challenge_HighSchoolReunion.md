## Setup

With your high school reunion fast approaching, you decide to get in shape and lose some weight. You record your weight every day for five weeks starting on a Monday.

```python
import numpy as np

dailywts = 185 - np.arange(5*7)/5

print(dailywts)
# [185.  184.8 184.6 184.4 184.2 184.  183.8 183.6 183.4 183.2 183.  182.8
#  182.6 182.4 182.2 182.  181.8 181.6 181.4 181.2 181.  180.8 180.6 180.4
#  180.2 180.  179.8 179.6 179.4 179.2 179.  178.8 178.6 178.4 178.2]
```
Given these daily weights, build an array with your average weight per weekend (A weekend includes Saturday and Sunday, but not Friday)

## Solution

These (strong) are the weekend values:
> [185.  184.8 184.6 184.4 184.2 **184.  183.8** 183.6 183.4 183.2 183.  182.8
> **182.6 182.4** 182.2 182.  181.8 181.6 181.4 **181.2 181.**  180.8 180.6 180.4
> 180.2 180.  **179.8 179.6** 179.4 179.2 179.  178.8 178.6 **178.4 178.2**]

```python
(dailywts[5::7] + dailywts[6::7])/2
# array([183.9, 182.5, 181.1, 179.7, 178.3])
```

### Explanation

We can use slicing to get the weights for every Saturday. (Keep in mind, index 0 represents a Monday, so the first Saturday occurs at index 5.)<br>
This is like telling NumPy give me every value from index 5 to the end of the array, stepping by 7
```python
dailywts[5::7]
# array([184. , 182.6, 181.2, 179.8, 178.4])
```

Similarly, we can use dailywts[6::7] to select the weights for every Sunday.
```python
dailywts[6::7]
# array([183.8, 182.4, 181. , 179.6, 178.2])
```

We can calculate the total weight per weekend by adding these same-sized arrays. Here, NumPy uses element-wise addition. 
```python
dailywts[5::7] + dailywts[6::7]
# array([367.8, 365. , 362.2, 359.4, 356.6])
```

Lastly, we can get the average weight per weekend by dividing by the previous array by 2. NumPy divides each element of the array by 2, thanks to broadcasting.
```python
(dailywts[5::7] + dailywts[6::7])/2
# array([183.9, 182.5, 181.1, 179.7, 178.3])
```
