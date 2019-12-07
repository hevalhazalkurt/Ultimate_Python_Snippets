# Ultimate Python Snippets
## NumPy
### `ndarray.shape`


<br>

-----


#### What is `ndarray.shape` ?

The `shape` of an array is a tuple of integers giving the size of the array along each dimension. It returns the dimension of numpy array as tuple.


```python
ndarray.shape
```

<br>

--------

<br>


#### Getting the 1-Dimension of a Numpy array


```python
x = np.array([1, 2, 3, 4])
print(x.shape)
```

**Output**

```
(4,)
```

<br>

--------

<br>

#### Getting the 2-Dimension of a Numpy array


```python
arr = np.array([[11 ,12,13,11], [21, 22, 23, 24], [31,32,33,34]])
print(arr.shape)
```

**Output**

```
(3, 4)
```

<br>

--------

<br>

#### Getting the 3-Dimension of a Numpy array


```python
arr = np.array([[[111,112], [121,122]],
 								[[211,212], [221,222]],
								[[311,312], [321,322]]])
print(arr.shape)
```

**Output**

```
(3, 2, 2)
```

<br>

--------


<br>

#### Getting Number of Rows and Columns


```python
arr = np.array([[11 ,12,13,11], [21, 22, 23, 24], [31,32,33,34]])
print("Number os Rows:", arr.shape[0])
print("Number os Columns:", arr.shape[1])
```

**Output**

```
Number os Rows: 3
Number os Columns: 4
```

<br>

--------

<br>

#### Getting Total Number of Elements


```python
arr = np.array([[11 ,12,13,11], [21, 22, 23, 24], [31,32,33,34]])
print("Total number of elements:", (arr.shape[0] * arr.shape[1]))
```

**Output**

```
Total number of elements: 12
```

<br>

--------
