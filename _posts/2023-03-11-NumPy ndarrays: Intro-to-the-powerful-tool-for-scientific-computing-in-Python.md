NumPy which is short for Numerical Python is the one of the most foundational tools for scientific computing with Python today. It is so important that many other tools like pandas utilise NumPy array objects as their basis. The most important tool in NumPy is the ndarray  which is usually a fixed-size multidimensional container of items of the same type and size. Other useful tools in NumPy are the mathematical functions that support fast operations on the ndarrays without using loops as required in pure Python, and even a C API that connects NumPy with libraries written in C, C ++ or FORTRAN. 

In this short piece, I attempt to highlight some important NumPy features that may be useful to individuals interested in scientific computing. 

First before using NumPy, it is important to install it first, after installing Python of course. This can be done using conda or pip. The specific codes can be found in the documentation and is dependent on the individual's setup eg windows, linux, Mac etc. After installation, NumPy can be imported in the following way before it can be used:

```py
import numpy as np
```
There are other ways of importing NumPy but the syntax above is the most widely accepted and it is advisable as it can foster collaboration. 
To check the package version, the following can be used:
```py
print('numpy:', np.__version__)
```
Unto the NumPy array object, the basis of NumPy

N-dimensional array object, or ndarray, is a fast, flexible container for large datasets in Python. Arrays enable performance of mathematical operations on whole blocks of data using similar syntax to the equivalent operations between scalar elements. It enables one to perform computations on indivudual elements of an ndarray without the need for a loop or list comprehension as may be required while trying to perform a similar computation using lets say a list in pure python. 
In addition, computations in NumPy are significantly faster than those in pure Python eg:

```py
# Comparing speed with pure Python

my_arr = np.arange(1_000_000)

my_list = list(range(1_000_000))

```
An ndarray and a list of the same size are declared and the below, I time a similar computation on the array and the list. 


```py
%timeit my_arr2 = my_arr * 2


%timeit my_list2 = [x * 2 for x in my_list]
```

The result below shows that the  computation on the array is many times faster than same on the list and this is due to the power of NumPy. 
```
1.28 ms ± 16.9 µs per loop (mean ± std. dev. of 7 runs, 1,000 loops each)
64.4 ms ± 1.14 ms per loop (mean ± std. dev. of 7 runs, 10 loops each)
```
Continuing the discussion on the ndarray, it contains elements of the same data type. In addition, every array has a shape which is a tuple that gives the dimensions of the array (ie size of each dimension) , and also a dtype (data type, since the array has the same data type). 

### Creating ndarrays
ndarrays can be created by using the array function and they can be initiated from lists or other data structures as shown below

```py
# from lists
data = [1,2,3,4,5,6]
arr1 = np.array(data)

```

This creates an array object that contains the elements in the data list. We can also input the elements directly as a list as follows:

```py
arr2 = np.array([1,2,3,4,5,6])

```
Same array object will be created as arr1 above. 

The functions and methods available in NumPy can be accessed by the following code:
```py
dir(np)  # assuming numpy is imported as np
```
Using the dir function is a handy way of finding the methods and functions associated with a package or even an object. 

### Data types for ndarrays
It has been established that elements in an ndarray are usually of the same data type. As such, the data type of an array can be declared while creating the array as follows:

```py
arr = np.array([4,3,5,6,7], dtype = np.float64)
```
Also, conversion of data types can also be done:

```py
int_arr = arr.astype(np.int64)
```
The following is a list of NumPy data types:
1. int
2. float
3. bool
4. complex
5. object
6. string
7. unicode
We can also specify the number of bits for some of them e.g. int8, int32, float64, complex64 etc. 

### Mathematical Calculations in NumPy
NumPy has two features on ndarrays that reflect the powerful nature of the library, vectorization and broadcasting. These are not available on traditional data structures like Python lists. 
Vectorization to refers to element-wise calculations done on entire arrays by using simple syntax same as will be used for scalar calculations:
```py
arr = np.array([[1., 2., 3.], [4., 5., 6.]])
arr
out: 
array([[1., 2., 3.],
       [4., 5., 6.]])

arr * arr 
out:
array([[ 1.,  4.,  9.],
       [16., 25., 36.]])

```

Arithmetic with scalars propagates the scalar to each element in the array:
```py
1 / arr

out:
array([[1.    , 0.5   , 0.3333],
       [0.25  , 0.2   , 0.1667]])
```
In the above, 1 is divided by each of the elements in arr to return a new array of the same size as arr. This is the beauty of NumPy. 

Apart from regular calculations, NumPy also supports ufuncs (universal functions) that allow element-wise computations on ndarrays.
Examples include numpy.sqrt and numpy.exp. Ufuncs can be unary (acts on elements of a single array) eg numpy.sqrt or binary (takes two arrays as arguments) eg numpy.multiply, numpy.mod etc. Ufuncs are powerful and I have seen them used in a simple implementation of logistic regression. 

### Indexing ndarrays

There are a variety of ways to index NumPy arrays but in the basic form, indexing  one dimensional arrays is very similar to indexing lists in pure Python. However, since the dimensions of an ndarray can be multidimensional, it becomes more complex with increase in dimension. In addition, numpy allows for boolean indexing (using a conditional) and fancy indexing (using integer arrays). Both are not available in pure Python. An important first distinction from Python's built-in lists is that array slices are views on the original array. This means that the data is not copied, and any modifications to the view will be reflected in the source array. 



In conclusion, NumPy provides powerful tools that can be harnessed for scientific computing and this is an attempt to provide a brief intro. 
As I begin my data science journey, I try to document my learnings and this is one of such attempts at documentation. This is a very skeletal view of the potential possibilities with NumPy. I have barely begun to scratch the surface. I recommend checking the NumPy documentation and also practicing the concepts as we learn. 
