# Ultimate Python Snippets
## NumPy
### `array`


<br>

-----


#### What is NumPy array ?

A homogeneous container of numerical elements. Each element in the array occupies a fixed amount of memory (hence homogeneous), and can be a numerical element of a single type (such as float, int or complex) or a combination (such as (float, int, float)).

NumPy arrays are a bit like Python lists, but still very much different at the same time. For those of you who are new to the topic, let’s clarify what it exactly is and what it’s good for.

As the name kind of gives away, a NumPy array is a central data structure of the numpy library. The library’s name is actually short for "Numeric Python" or "Numerical Python".


```python
import numpy as np

x = np.array([1,2,3])
y = np.array([[1,2,3], [4,5,6]])

print(x)
print(y)
print(type(x))

```

**Output**

```
[1 2 3]

[[1 2 3]
 [4 5 6]]

<class 'numpy.ndarray'>
```

<br>

--------

<br>


#### Creating a NumPy Array

Simplest way to create an array in Numpy is to use Python List


```python
myPythonArray = [1,9,8,3]
```


To convert python list to a `numpy` array by using the object `np.array`.

```python
import numpy as np

myPythonArray = [1,9,8,3]
myArray = np.array(myPythonArray)

print(myArray)
print(type(myArray))
```

**Output**

```
[1 9 8 3]
<class 'numpy.ndarray'>
```

<br>

--------

<br>

### Mathematical Operations on an Array

You could perform mathematical operations like additions, subtraction, division and multiplication on an array.


```python
import numpy as np

myPythonArray = [1,9,8,3]
myArray = np.array(myPythonArray)

print(myArray + 10)
print(myArray - 10)
print(myArray * 10)
print(myArray / 10)
print(myArray % 10)
print(myArray ** 2)
```

**Output**

```
[11 19 18 13]
[-9 -1 -2 -7]
[10 90 80 30]
[0.1 0.9 0.8 0.3]
[1 9 8 3]
[ 1 81 64  9]
```


---
