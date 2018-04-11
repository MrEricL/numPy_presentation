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

#### Operations

``` 
> a = np.array([1,  2,  3])
> b = np.array([4,  5,  6])
```

#### Shaping

**Random**: Same as before but with random values, based on the memory. The syntax is ``` np.empty([X,Y,Z])```.

```
> np.empty([3])
array([ -1.72723371e-77,  -1.72723371e-77,  -1.72723371e-77])
```

### Markdown

Markdown is a lightweight and easy-to-use syntax for styling your writing. It includes conventions for

```markdown
import np 
Syntax highlighted code block

# Header 1
## Header 2
### Header 3

- Bulleted
- List

1. Numbered
2. List

**Bold** and _Italic_ and `Code` text

[Link](url) and ![Image](src)
```

For more details see [GitHub Flavored Markdown](https://guides.github.com/features/mastering-markdown/).

### Usage

numPy is a staple in helping math/science research. Most machine learning done in Python relies on numPy, due to the mathematical complexity.

### Sample Code

```python
import numpy as np

```

### Credits

This website would not have been possible without the [NumPy User Guide](https://docs.scipy.org/doc/numpy-dev/user/). Everything on this website is covered more in depth in the documentation.


