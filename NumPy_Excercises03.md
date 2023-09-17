1. What is a vector?
   ```python
   np.array(['a', 'b', 'c'])
   ```
2. How do you represent vectors using a Python list? Give an example.
   ```python
   # 3 dimensional vectors
   v2 = [x1,x2,x3]
   v3 = [2,3,4]
   ```
3. What is a dot product of two vectors?
   ```python
   x = (x1,x2,x3)
   y = (y1,y2,y3)
   z = x dot y = x1*y1 + x2*y2 + x3*y3
   x = (1,2,3)
   y = (4,5,6)
   z = 1*2 + 2*5 + 3*6 = 30
   ```
4. Write a function to compute the dot product of two vectors.
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
5. What is Numpy?
   
   The **Numpy library** provides **specialized data structures**, **functions**, and other tools for **numerical computing** in Python
   
6. How do you import the `numpy` module?
   ```python
   import numpy as np
   a=np.array([1,2,3])
   ```
   ```python
   import numpy
   b=numpy.array([4,5,6])
   ```
7. What does it mean to import a module with an alias? Give an example.
   ```python
   import numpy as np
   a=np.array([1,2,3])
   ```
8. What is the commonly used alias for `numpy`?
    
    **np**
9. What is a Numpy array?
    
    Numpy arrays are a spezial list of equal value-types from type **ndarray**
10. How do you create a Numpy array? Give an example.
    ```python
    import numpy as np
    a=np.array([1,2,3])
    ```
11. What is the type of Numpy arrays?

    **ndarray**
12. How do you access the elements of a Numpy array?
    ```python
    # Numpy-Arrays support indexing
    import numpy as np
    a=np.array([1,2,3])
    # to print the third element
    print(a[2])
    ```
13. How do you compute the dot product of two vectors using Numpy?
    ```python
    # using the dot-Function
    import numpy as np
    a=np.array([1,2,3])
    b=np.array([4,5,6])
    print(np.dot(a,b))
    ```
14. What happens if you try to compute the dot product of two vectors which have different sizes?
    
    You got an **ValueError**
15. How do you compute the element-wise product of two Numpy arrays?
    ```python
    # using the * Operator
    import numpy as np
    a=np.array([1,2,3])
    b=np.array([4,5,6])
    print(a*b)
    ```
16. How do you compute the sum of all the elements in a Numpy array?
    ```python
    # using the sum-Funktion
    import numpy as np
    a=np.array([1,2,3])
    print(sum(a))
    # using the sum-Method
    print(a.sum())
    ```
17. What are the benefits of using Numpy arrays over Python lists for operating on numerical data?
    - They're **easy to use**: You can write small, concise, and intuitive mathematical expressions like (kanto * weights).sum() rather than using loops
    - **Performance**: Numpy operations and functions are implemented internally in C++, which makes them much faster than using Python statements and loops that are interpreted at runtime
18. Why do Numpy array operations have better performance compared to Python functions and loops?

    Because Numpy operations and functions are implemented internally in C++
19. Illustrate the performance difference between Numpy array operations and Python loops using an example.
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
20. What are multi-dimensional Numpy arrays?
    
    Numpy arrays can have any number of dimensions and different lengths along each dimension. We can inspect the length along each dimension using the .shape property of an array.
21. Illustrate the creation of Numpy arrays with 2, 3, and 4 dimensions.
    ```python
    a1 = np.array([1,2,3])
    a1.shape
    a2 = np.array([[1,2,3],[4,5,6]])
    a2.shape
    a3 = np.array([[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]]])
    a3.shape
    a4 = np.array([[[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]]],[[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]],[[1,2,3],[4,5,6]]]])
    a4.shape
    ```
22. How do you inspect the number of dimensions and the length along each dimension in a Numpy array?

    We can inspect the length along each dimension using the **.shape** property of an array
23. Can the elements of a Numpy array have different data types?

    All the elements in a numpy array have the **same data type**
24. How do you check the data type of the elements of a Numpy array?

    You can check the data type of an array using the **.dtype property**
25. What is the data type of a Numpy array?
    ```python
    import numpy as np
    a=np.array([1,2,3])
    print(type(a))
    # <class 'numpy.ndarray'>
    ```  
26. What is the difference between a matrix and a 2D Numpy array?

    Numpy matrices are strictly 2-dimensional, while numpy arrays (ndarrays) are N-dimensional.
27. How do you perform matrix multiplication using Numpy?

    We can use the np.matmul function or the @ operator to perform matrix multiplication
    ```python
    np.matmul(a1,a2)
    a1 @ a2
    ```  
28. What is the `@` operator used for in Numpy?

    for **matrix multiplication**
29. What is the CSV file format?

    A comma-separated values (CSV) file is a delimited text file that uses a comma to separate values
30. How do you read data from a CSV file using Numpy?

    To read this file into a numpy array, we can use the **genfromtxt** function
    ```python
    climate_data = np.genfromtxt('climate.txt', delimiter=',', skip_header=1)
    climate_data
    climate_data.shape
    ```  
31. How do you concatenate two Numpy arrays?

    using the **np.concatenate** function
32. What is the purpose of the `axis` argument of `np.concatenate`?

    The axis argument specifies the dimension for concatenation
33. When are two Numpy arrays compatible for concatenation?

    The arrays should have the same number of dimensions, and the same length along each except the dimension used for concatenation
34. Give an example of two Numpy arrays that can be concatenated.
    ```python
    a = np.array([[0,1,3],[5,7,9]])
    b = np.array([[0,2,4],[6,8,10]])
    print(np.concatenate((a,b)))
    #[[ 0  1  3]
    # [ 5  7  9]
    # [ 0  2  4]
    # [ 6  8 10]]
    print(np.concatenate((a,b), axis=1))
    #[[ 0  1  3  0  2  4]
    # [ 5  7  9  6  8 10]]
    ```  
35. Give an example of two Numpy arrays that cannot be concatenated.
    ```python
    a = np.array([[0,1,3],[5,7,9]])
    b = np.array([[0,2],[6,8]])
    print(np.concatenate((a,b)))
    # ValueError
    print(np.concatenate((a,b), axis=1))
    #[[ 0  1  3  0  2]
    # [ 5  7  9  6  8]]
    ```      
36. What is the purpose of the `np.reshape` function?

    We use the **np.reshape** function to change the shape of an array
37. What does it mean to “reshape” a Numpy array?

    It means me change the shape of an array
38. How do you write a numpy array into a CSV file?

    With the **np.savetxt** function
    ```python
    np.savetxt('climate_results.txt', 
           climate_results, 
           fmt='%.2f', 
           delimiter=',',
           header='temperature,rainfall,humidity,yeild_apples', 
           comments='')
    ```
39. Give some examples of Numpy functions for performing mathematical operations.

    Mathematics: np.sum, np.exp, np.round, arithmetic operators
40. Give some examples of Numpy functions for performing array manipulation.

    Array manipulation: np.reshape, np.stack, np.concatenate, np.split
41. Give some examples of Numpy functions for performing linear algebra.

    Linear Algebra: np.matmul, np.dot, np.transpose, np.eigvals
42. Give some examples of Numpy functions for performing statistical operations.

    Statistics: np.mean, np.median, np.std, np.max
43. How do you find the right Numpy function for a specific operation or use case?

    The easiest way to find the right function for a specific operation or use-case is to do a web search. For instance, searching for "How to join numpy arrays" leads to [this tutorial on array concatenation](https://cmdlinetips.com/2018/04/how-to-concatenate-arrays-in-numpy/).

44. Where can you see a list of all the Numpy array functions and operations?

    You can find a full list of array functions [here](https://numpy.org/doc/stable/reference/routines.html)
45. What are the arithmetic operators supported by Numpy arrays? Illustrate with examples.
    ```python
    arr2 = np.array([[1, 2, 3, 4], 
                 [5, 6, 7, 8], 
                 [9, 1, 2, 3]])
                 
    arr3 = np.array([[11, 12, 13, 14], 
                 [15, 16, 17, 18], 
                 [19, 11, 12, 13]])
                 
    # Adding a scalar
    arr2 + 3

    # array([[ 4,  5,  6,  7],
    #        [ 8,  9, 10, 11],
    #        [12,  4,  5,  6]])

    # Element-wise subtraction
    arr3 - arr2

    # array([[10, 10, 10, 10],
    #        [10, 10, 10, 10],
    #        [10, 10, 10, 10]])

    # Division by scalar
    arr2 / 2

    # array([[0.5, 1. , 1.5, 2. ],
    #        [2.5, 3. , 3.5, 4. ],
    #        [4.5, 0.5, 1. , 1.5]])

    # Element-wise multiplication
    arr2 * arr3

    # array([[ 11,  24,  39,  56],
    #        [ 75,  96, 119, 144],
    #        [171,  11,  24,  39]])

    # Modulus with scalar
    arr2 % 4

    # array([[1, 2, 3, 0],
    #        [1, 2, 3, 0],
    #        [1, 1, 2, 3]])
    ```
46. What is array broadcasting? How is it useful? Illustrate with an example.

    Numpy arrays also support broadcasting, allowing arithmetic operations between two arrays with different numbers of dimensions but compatible shapes
47. Give some examples of arrays that are compatible for broadcasting?
    ```python
    arr2 = np.array([[1, 2, 3, 4], 
                 [5, 6, 7, 8], 
                 [9, 1, 2, 3]])               
    arr2.shape
    # (3, 4)

    arr4 = np.array([4, 5, 6, 7])
    arr4.shape
    # (4,)

    arr2 + arr4
    # array([[ 5,  7,  9, 11],
    #        [ 9, 11, 13, 15],
    #        [13,  6,  8, 10]])
    ```
    
48. Give some examples of arrays that are not compatible for broadcasting?
    ```python
    arr2 = np.array([[1, 2, 3, 4], 
                 [5, 6, 7, 8], 
                 [9, 1, 2, 3]])               
    arr2.shape

    arr5 = np.array([7,8])
    arr5.shape
    # (2,0)

    arr2 + arr5
    # ValueError: operands could not be broadcast together with shapes (3,4) (2,)
    ```
49. What are the comparison operators supported by Numpy arrays? Illustrate with examples.

    Numpy arrays also support comparison operations like ==, !=, > and so on. The result is an array of booleans.
    ```python
    arr1 = np.array([[1, 2, 3], [3, 4, 5]])
    arr2 = np.array([[2, 2, 3], [1, 2, 5]])

    arr1 == arr2
    # array([[False,  True,  True],
    #        [False, False,  True]])

    arr1 != arr2
    # array([[ True, False, False],
    #        [ True,  True, False]])

    arr1 >= arr2
    # array([[False,  True,  True],
    #        [ True,  True,  True]])

    arr1 < arr2
    # array([[ True, False, False],
    #        [False, False, False]])
    ```
50. How do you access a specific subarray or slice from a Numpy array?
    Numpy extends Python's list indexing notation using [] to multiple dimensions in an intuitive fashion. You can provide a comma-separated list of indices or ranges to select a specific element or a subarray (also called a slice) from a Numpy array.
51. Illustrate array indexing and slicing in multi-dimensional Numpy arrays with some examples.
    ```python
    arr3 = np.array([
        [[11, 12, 13, 14], 
         [13, 14, 15, 19]], 
    
        [[15, 16, 17, 21], 
         [63, 92, 36, 18]], 
    
        [[98, 32, 81, 23],      
         [17, 18, 19.5, 43]]])
     
    arr3.shape
    # (3, 2, 4)

    # Single element
    arr3[1, 1, 2]

    # 36.0

    # Subarray using ranges
    arr3[1:, 0:1, :2]

    # array([[[15., 16.]],
    # 
    #        [[98., 32.]]])

    # Mixing indices and ranges
    arr3[1:, 1, 3]

    # array([18., 43.])

    arr3[1:, 1, :3]
    # array([[63. , 92. , 36. ],
    #        [17. , 18. , 19.5]])

    # Using fewer indices
    arr3[1]

    # array([[15., 16., 17., 21.],
    #        [63., 92., 36., 18.]])

    arr3[:2, 1]
    # array([[13., 14., 15., 19.],
    #        [63., 92., 36., 18.]])
    ```   
52. How do you create a Numpy array with a given shape containing all zeros?
    ```python
    # All zeros
    np.zeros((3, 2))

    # array([[0., 0.],
    #        [0., 0.],
    #        [0., 0.]])
    ```     
52. How do you create a Numpy array with a given shape containing all ones?
    ```python
    # All ones
    np.ones([2, 2, 3])

    # array([[[1., 1., 1.],
    #         [1., 1., 1.]],
    #
    #        [[1., 1., 1.],
    #         [1., 1., 1.]]])
    ```     
53. How do you create an identity matrix of a given shape?
    ```python
    # Identity matrix
    np.eye(3)

    # array([[1., 0., 0.],
    #        [0., 1., 0.],
    #        [0., 0., 1.]])
    ```     
54. How do you create a random vector of a given length?
    ```python
    # Random vector
    np.random.rand(5)

    # array([0.92929562, 0.11301864, 0.64213555, 0.8600434 , 0.53738656])

    # Random matrix
    np.random.randn(2, 3) # rand vs. randn - what's the difference?

    # array([[ 0.09906435, -1.64668094,  0.08073528],
    #        [ 0.1437016 ,  0.80715712,  1.27285476]])
    ```     
55. How do you create a Numpy array with a given shape with a fixed value for each element?
    ```python
    # Fixed value
    np.full([2, 3], 42)

    # array([[42, 42, 42],
    #        [42, 42, 42]])
    ```     
56. How do you create a Numpy array with a given shape containing randomly initialized elements?
    ```python
    # Random matrix
    np.random.randn(2, 3) # rand vs. randn - what's the difference?

    # array([[ 0.09906435, -1.64668094,  0.08073528],
    #        [ 0.1437016 ,  0.80715712,  1.27285476]])
    ```     
57. What is the difference between `np.random.rand` and `np.random.randn`? Illustrate with examples.
    - **np.random.rand** is for Uniform distribution (in the half-open interval [0.0, 1.0))
    - **np.random.randn** is for Standard Normal (aka. Gaussian) distribution (mean 0 and variance 1)
58. What is the difference between `np.arange` and `np.linspace`? Illustrate with examples.
    ```python
    # Range with start, end and step
    np.arange(10, 90, 3)

    # array([10, 13, 16, 19, 22, 25, 28, 31, 34, 37, 40, 43, 46, 49, 52, 55, 58,
    #        61, 64, 67, 70, 73, 76, 79, 82, 85, 88])

    # Equally spaced numbers in a range
    np.linspace(3, 27, 9)

    # array([ 3.,  6.,  9., 12., 15., 18., 21., 24., 27.])
    ```     
