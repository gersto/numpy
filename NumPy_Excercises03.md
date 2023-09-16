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
12. What does it mean to import a module with an alias? Give an example.
13. What is the commonly used alias for `numpy`?
14. What is a Numpy array?
15. How do you create a Numpy array? Give an example.
16. What is the type of Numpy arrays?
17. How do you access the elements of a Numpy array?
18. How do you compute the dot product of two vectors using Numpy?
19. What happens if you try to compute the dot product of two vectors which have different sizes?
20. How do you compute the element-wise product of two Numpy arrays?
21. How do you compute the sum of all the elements in a Numpy array?
22. What are the benefits of using Numpy arrays over Python lists for operating on numerical data?
23. Why do Numpy array operations have better performance compared to Python functions and loops?
24. Illustrate the performance difference between Numpy array operations and Python loops using an example.
25. What are multi-dimensional Numpy arrays?
26. Illustrate the creation of Numpy arrays with 2, 3, and 4 dimensions.
27. How do you inspect the number of dimensions and the length along each dimension in a Numpy array?
28. Can the elements of a Numpy array have different data types?
29. How do you check the data type of the elements of a Numpy array?
30. What is the data type of a Numpy array?
31. What is the difference between a matrix and a 2D Numpy array?
32. How do you perform matrix multiplication using Numpy?
33. What is the `@` operator used for in Numpy?
34. What is the CSV file format?
35. How do you read data from a CSV file using Numpy?
36. How do you concatenate two Numpy arrays?
37. What is the purpose of the `axis` argument of `np.concatenate`?
38. When are two Numpy arrays compatible for concatenation?
39. Give an example of two Numpy arrays that can be concatenated.
40. Give an example of two Numpy arrays that cannot be concatenated.
41. What is the purpose of the `np.reshape` function?
42. What does it mean to “reshape” a Numpy array?
43. How do you write a numpy array into a CSV file?
44. Give some examples of Numpy functions for performing mathematical operations.
45. Give some examples of Numpy functions for performing array manipulation.
46. Give some examples of Numpy functions for performing linear algebra.
47. Give some examples of Numpy functions for performing statistical operations.
48. How do you find the right Numpy function for a specific operation or use case?
49. Where can you see a list of all the Numpy array functions and operations?
50. What are the arithmetic operators supported by Numpy arrays? Illustrate with examples.
51. What is array broadcasting? How is it useful? Illustrate with an example.
52. Give some examples of arrays that are compatible for broadcasting?
53. Give some examples of arrays that are not compatible for broadcasting?
54. What are the comparison operators supported by Numpy arrays? Illustrate with examples.
55. How do you access a specific subarray or slice from a Numpy array?
56. Illustrate array indexing and slicing in multi-dimensional Numpy arrays with some examples.
57. How do you create a Numpy array with a given shape containing all zeros?
58. How do you create a Numpy array with a given shape containing all ones?
59. How do you create an identity matrix of a given shape?
60. How do you create a random vector of a given length?
61. How do you create a Numpy array with a given shape with a fixed value for each element?
62. How do you create a Numpy array with a given shape containing randomly initialized elements?
63. What is the difference between `np.random.rand` and `np.random.randn`? Illustrate with examples.
64. What is the difference between `np.arange` and `np.linspace`? Illustrate with examples.
