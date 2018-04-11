By Eric Li and Masha Zorin

## Background
[numPy](http://www.numpy.org) is a package for Python often used in scientific and mathematical projects. It's is useful for computation-intesensive projects. numPy is flexible as it works with other programming languages such as C,C++, and Fortran.

numPy was created by Travis Oliphant from an older math package called numeric, and is now mantained by a community.

### Getting Started
To install with pip enter into your terminal:
```
python -m pip install --user numpy
```

numPy works with a host of other packages. For a full list, try:
```
python -m pip install --user numpy scipy matplotlib ipython jupyter pandas sympy nose
```
These other packages covers other functinalities required for mathematical and scientific usage such as graphing. 


To start using it in python, make sure to import it by including ``` import numpy as np```.

### Overview

The main object in numPy is called a multi dimensional array. Many people will think this means that a multi dimensional array is the same thing as a matrix, but the two are distinct. A matrix is a *subclass* of the multi dimensional array since it's only 2D.

For this site, we will refer to multi dimensional array as just arrays. 

Let's use this sample array:
``` 
> a = np.array([1.5,  2])
> a
array([1.5, 2])
```
**Remember**
- Use brackets! Know the syntax otherwise run into an error.
```np.array([1.5,2])```
NOT
```np.array(1.5,2)```

- All elements in array is the same type
``` 
> a.dtype
dtype('float64')
```
The 1.5 forces the overall array type to be considered as a float. 


### Basic functions

Here is a sample of basic functions for new users.

#### Generating Basic Arrays 
**Zero**: To generate an array of zeros, use the syntax ``` np.zeros([X,Y,Z])``` where X and Y refers to the dimensions of the array. The Y and Z can be left out and be assumed as 1.
```
> np.zeros([2,  3])
array([[ 0.,  0.,  0.],
       [ 0.,  0.,  0.]])
```

**Unit**: The same as the zero, but with 1s instead, with the syntax ``` np.ones([X,Y,Z])```.
```
> np.ones([2, 2,  3])
array([[[ 1.,  1.,  1.],
        [ 1.,  1.,  1.]],

       [[ 1.,  1.,  1.],
        [ 1.,  1.,  1.]]])
```
**Random**: Same as before but with random values, based on the memory. The syntax is ``` np.empty([X,Y,Z])```.

```
> np.empty([3])
array([ -1.72723371e-77,  -1.72723371e-77,  -1.72723371e-77])
```
#### Operations

Let's use the following arrays as an example.
``` 
> a = np.array([1,  2,  3])
> b = np.array([4,  5,  6])
```

**Addition and Subtraction**: You can just add/subtract arrays, and the values at the corresponding indicies will be added/subtracted.

Addition
```
> c = a + b
> c
array([5, 7, 9])
```

Subtraction
```
> c = a - b
> c
array([-3, -3, -3])
```

**Functions**: You can apply a function to an array, and each index will be applied to.
```
> np.sin(c)
array([-0.95892427,  0.6569866 ,  0.41211849])
```

**Multiplication**
Scalar: You multiply every index by some value. 
```
> a
array([1, 2, 3])
> a * 5
array([5, 10, 15])
```
Multiplication by Index: This is the same as addition and subtraction where respective indicies are multiplied.
```
> a * b
array([ 4, 10, 18])
```
Dot Product: This is when you want the dot product. Use syntax ```<array0>.dot(<array1>)```.
```
> a.dot(b)
32
> m = np.array([(1, 2),(3, 4)])
> m = np.array([(5, 6),(7, 8)])
> m.dot(n)
array([[44, 55, 66],
       [60, 75, 90]])
```

#### Shaping

The arrays in numPy are very flexible, allowing changes to the structure of the array.

**Ravel**: This flattens the array, using the syntax ```<array>.ravel()```.

```
> a = np.array([[1,  2,  3],[1,  2,  3]])
> a.ravel()
array([1, 2, 3, 1, 2, 3])
```

**Reshape**: This allows you to reshape the array, although the total size must be the same. You can not reshape an array with one element in a 1x1 structure into an array with ten elements in a 2x5. Use the syntax ```<array>.reshape()```.

```
> a = np.array([1,  2,  3])
> a.reshape(3,1)
array([[1],
       [2],
       [3]])
```

#### Aggregate Operations

Aggregate Operations produce a scalar using all the elements (eg. sum, max, min). You can specify axis (in a 2D array, this would mean row or column), and get an array.

**Sum**: Finds the sum of all the elements in the array.

```
> a  =  array([[ 0,  1,  2,  3],   [ 4,  5,  6,  7],  [ 8,  9, 10, 11]])
> a.sum()
66
> a.sum(axis=0)   # sum of each column
array([12, 15, 18, 21])
```

**Max/Min**: Finds the maximum (or minimum) value in the array.

```
> a  =  array([[ 0,  1,  2,  3],   [ 4,  5,  6,  7],  [ 8,  9, 10, 11]])
> a.min()
0
> a.max()
11
```

#### Copying

By default, no copying is done:

```
> a = np.arange(12)
> b = a            # no new object is created
> b is a
True
```

To make a copy of an array, you do:

```
> d = a.copy()        # a new array object with new data is created
> d is a
False
```

#### Slicing

Each axis can be sliced to form a sub matrix by giving the start and end index of each axis (rows, columns).

```
> b = array([[1, 2, 3], 
  [4, 5, 6], 
  [7, 8, 9]]
> b [ 0 : 3, 1 : 2]        	#rows 0 (inclusive) to 3 (exclusive), cols 1-2
[[2],[5],[8]]
> b [ : , 1]        	       #gives same result as above
[[2],[5],[8]]
```

#### Iterating

Iterating over multidimensional arrays is done with respect to the first axis.

```
> for row in b:
...    print(row)
```

Can also iterate over all elements using attribute flat:

```
> for element in b.flat:
...     print(element)
```

#### Other

```
> np.polyval([1,2,3], 4)  #1 * 4^2 + 2 * 4^1 + 3 * 4^0 = 27
27
> n, p = 10, .5
> s = np.random.binomial(n, p, 1)   # result of flipping coin ten times, tested 1 time
> s
array([7, 8, 8, 3, 5, 7, 4, 2, 5, 5])
```

### Usage

numPy is a staple in helping math/science research. Most machine learning done in Python relies on numPy, due to the mathematical complexity.


### Credits

This website would not have been possible without the [NumPy User Guide](https://docs.scipy.org/doc/numpy-dev/user/). Everything on this website is covered more in depth in the documentation.


