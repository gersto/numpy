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
    - They're **easy to use**: You can write small, concise, and intuitive mathematical expressions like (kanto * weights).sum() rather than using loops
    - **Performance**: Numpy operations and functions are implemented internally in C++, which makes them much faster than using Python statements and loops that are interpreted at runtime
35. Why do Numpy array operations have better performance compared to Python functions and loops?

    Because Numpy operations and functions are implemented internally in C++
37. Illustrate the performance difference between Numpy array operations and Python loops using an example.
   ```python
   import math
   import timeit

   start_time = timeit.default_timer()
   for i in range(1, 1000000):
       math.sqrt(i)
   end_time = timeit.default_timer()

   print(f"Execution time: {end_time - start_time} seconds")
   ```
   ```python
   import numpy as np
   import timeit

   start_time = timeit.default_timer()
   np.sqrt(np.arange(1, 1000000))
   end_time = timeit.default_timer()

   print(f"Execution time: {end_time - start_time} seconds")
   ```
   ```python
   # Python lists
   arr1 = list(range(1000000))
   arr2 = list(range(1000000, 2000000))

   # Numpy arrays
   arr1_np = np.array(arr1)
   arr2_np = np.array(arr2)

   %%time
   result = 0
   for x1, x2 in zip(arr1, arr2):
       result += x1*x2
   result

   # CPU times: user 300 ms, sys: 3.26 ms, total: 303 ms
   # Wall time: 302 ms
   # 833332333333500000

   %%time
   np.dot(arr1_np, arr2_np)

   # CPU times: user 2.11 ms, sys: 951 µs, total: 3.07 ms
   # Wall time: 1.58 ms
   # 833332333333500000
   ```
39. What are multi-dimensional Numpy arrays?
    
    Numpy arrays can have any number of dimensions and different lengths along each dimension. We can inspect the length along each dimension using the .shape property of an array.
41. Illustrate the creation of Numpy arrays with 2, 3, and 4 dimensions.
42. How do you inspect the number of dimensions and the length along each dimension in a Numpy array?
43. Can the elements of a Numpy array have different data types?
44. How do you check the data type of the elements of a Numpy array?
45. What is the data type of a Numpy array?
46. What is the difference between a matrix and a 2D Numpy array?
47. How do you perform matrix multiplication using Numpy?
48. What is the `@` operator used for in Numpy?
49. What is the CSV file format?
50. How do you read data from a CSV file using Numpy?
51. How do you concatenate two Numpy arrays?
52. What is the purpose of the `axis` argument of `np.concatenate`?
53. When are two Numpy arrays compatible for concatenation?
54. Give an example of two Numpy arrays that can be concatenated.
55. Give an example of two Numpy arrays that cannot be concatenated.
56. What is the purpose of the `np.reshape` function?
57. What does it mean to “reshape” a Numpy array?
58. How do you write a numpy array into a CSV file?
59. Give some examples of Numpy functions for performing mathematical operations.
60. Give some examples of Numpy functions for performing array manipulation.
61. Give some examples of Numpy functions for performing linear algebra.
62. Give some examples of Numpy functions for performing statistical operations.
63. How do you find the right Numpy function for a specific operation or use case?
64. Where can you see a list of all the Numpy array functions and operations?
65. What are the arithmetic operators supported by Numpy arrays? Illustrate with examples.
66. What is array broadcasting? How is it useful? Illustrate with an example.
67. Give some examples of arrays that are compatible for broadcasting?
68. Give some examples of arrays that are not compatible for broadcasting?
69. What are the comparison operators supported by Numpy arrays? Illustrate with examples.
70. How do you access a specific subarray or slice from a Numpy array?
71. Illustrate array indexing and slicing in multi-dimensional Numpy arrays with some examples.
72. How do you create a Numpy array with a given shape containing all zeros?
73. How do you create a Numpy array with a given shape containing all ones?
74. How do you create an identity matrix of a given shape?
75. How do you create a random vector of a given length?
76. How do you create a Numpy array with a given shape with a fixed value for each element?
77. How do you create a Numpy array with a given shape containing randomly initialized elements?
78. What is the difference between `np.random.rand` and `np.random.randn`? Illustrate with examples.
79. What is the difference between `np.arange` and `np.linspace`? Illustrate with examples.
