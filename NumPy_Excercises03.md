1. What is a vector?
   ```python
   np.array(['a', 'b', 'c'])
   ```
3. How do you represent vectors using a Python list? Give an example.
   ```python
   # 3 dimensional vectors
   v2 = [x1,x2,x3]
   v3 = [2,3,4]
   ```
5. What is a dot product of two vectors?
   ```python
   x = (x1,x2,x3)
   y = (y1,y2,y3)
   z = x dot y = x1*y1 + x2*y2 + x3*y3
   x = (1,2,3)
   y = (4,5,6)
   z = 1*2 + 2*5 + 3*6 = 30
   ```
7. Write a function to compute the dot product of two vectors.
   ```python
   x1 = [1,2,3]
   x2 = [4,5,6]

   def dot1(l1,l2):
     i=0
     s=0
     while (i < len(l1)):
        s = s + l1[i]*l2[i]
        i=i+1
     return s
    
   print(dot1(x1,x2))
   ```
9. What is Numpy?
   
   The **Numpy library** provides **specialized data structures**, **functions**, and other tools for **numerical computing** in Python
   
11. How do you import the `numpy` module?
   ```python
   import numpy as np
   a=np.array([1,2,3])
   ```
   ```python
   import numpy
   b=numpy.array([4,5,6])
   ```
13. What does it mean to import a module with an alias? Give an example.
   ```python
   import numpy as np
   a=np.array([1,2,3])
   ```
15. What is the commonly used alias for `numpy`?
    
    **np**
17. What is a Numpy array?
    
    Numpy arrays are a spezial list of equal value-types from type **ndarray**
19. How do you create a Numpy array? Give an example.
   ```python
   import numpy as np
   a=np.array([1,2,3])
   ```
21. What is the type of Numpy arrays?

    **ndarray**
23. How do you access the elements of a Numpy array?
   ```python
   # Numpy-Arrays support indexing
   import numpy as np
   a=np.array([1,2,3])
   # to print the third element
   print(a[2])
   ```
25. How do you compute the dot product of two vectors using Numpy?
   ```python
   # using the dot-Function
   import numpy as np
   a=np.array([1,2,3])
   b=np.array([4,5,6])
   print(np.dot(a,b))
   ```
27. What happens if you try to compute the dot product of two vectors which have different sizes?
    
    You got an **ValueError**
29. How do you compute the element-wise product of two Numpy arrays?
   ```python
   # using the * Operator
   import numpy as np
   a=np.array([1,2,3])
   b=np.array([4,5,6])
   print(a*b)
   ```
31. How do you compute the sum of all the elements in a Numpy array?
   ```python
   # using the sum-Funktion
   import numpy as np
   a=np.array([1,2,3])
   print(sum(a))
   # using the sum-Method
   print(a.sum())
   ```
33. What are the benefits of using Numpy arrays over Python lists for operating on numerical data?
34. Why do Numpy array operations have better performance compared to Python functions and loops?
35. Illustrate the performance difference between Numpy array operations and Python loops using an example.
36. What are multi-dimensional Numpy arrays?
37. Illustrate the creation of Numpy arrays with 2, 3, and 4 dimensions.
38. How do you inspect the number of dimensions and the length along each dimension in a Numpy array?
39. Can the elements of a Numpy array have different data types?
40. How do you check the data type of the elements of a Numpy array?
41. What is the data type of a Numpy array?
42. What is the difference between a matrix and a 2D Numpy array?
43. How do you perform matrix multiplication using Numpy?
44. What is the `@` operator used for in Numpy?
45. What is the CSV file format?
46. How do you read data from a CSV file using Numpy?
47. How do you concatenate two Numpy arrays?
48. What is the purpose of the `axis` argument of `np.concatenate`?
49. When are two Numpy arrays compatible for concatenation?
50. Give an example of two Numpy arrays that can be concatenated.
51. Give an example of two Numpy arrays that cannot be concatenated.
52. What is the purpose of the `np.reshape` function?
53. What does it mean to “reshape” a Numpy array?
54. How do you write a numpy array into a CSV file?
55. Give some examples of Numpy functions for performing mathematical operations.
56. Give some examples of Numpy functions for performing array manipulation.
57. Give some examples of Numpy functions for performing linear algebra.
58. Give some examples of Numpy functions for performing statistical operations.
59. How do you find the right Numpy function for a specific operation or use case?
60. Where can you see a list of all the Numpy array functions and operations?
61. What are the arithmetic operators supported by Numpy arrays? Illustrate with examples.
62. What is array broadcasting? How is it useful? Illustrate with an example.
63. Give some examples of arrays that are compatible for broadcasting?
64. Give some examples of arrays that are not compatible for broadcasting?
65. What are the comparison operators supported by Numpy arrays? Illustrate with examples.
66. How do you access a specific subarray or slice from a Numpy array?
67. Illustrate array indexing and slicing in multi-dimensional Numpy arrays with some examples.
68. How do you create a Numpy array with a given shape containing all zeros?
69. How do you create a Numpy array with a given shape containing all ones?
70. How do you create an identity matrix of a given shape?
71. How do you create a random vector of a given length?
72. How do you create a Numpy array with a given shape with a fixed value for each element?
73. How do you create a Numpy array with a given shape containing randomly initialized elements?
74. What is the difference between `np.random.rand` and `np.random.randn`? Illustrate with examples.
75. What is the difference between `np.arange` and `np.linspace`? Illustrate with examples.
