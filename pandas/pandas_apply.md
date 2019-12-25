# Ultimate Python Snippets
## Pandas
### `data.apply()`


<br>

-----


#### What is `data.apply()` for?

It allows the users to pass a function and apply it on every single value of the Pandas series.

**Syntax**

```python
Series.apply(func, axis=0, raw=False, result_type=None, args=(), **kwds)
```

<br>

| Parameter | Default | Explain |
|--|--|--|
| `func` |  | Function to apply to each column or row. |
| `axis` | `0` | Axis along which the function is applied: <br> - `0` or `‘index’`: apply function to each column. <br> - `1` or `‘columns’`: apply function to each row. |
| `raw` | `False` | - `False` : passes each row or column as a Series to the function. <br> - `True` : the passed function will receive ndarray objects instead. If you are just applying a NumPy reduction function this will achieve much better performance. |
| `result_type` | `None` | These only act when `axis=1` (columns): <br> - `‘expand’` : list-like results will be turned into columns. <br> - `‘reduce’` : returns a Series if possible rather than expanding list-like results. This is the opposite of ‘expand’. <br> - `‘broadcast’` : results will be broadcast to the original shape of the DataFrame, the original index and columns will be retained. <br>The default behaviour (`None`) depends on the return value of the applied function: list-like results will be returned as a Series of those. However if the apply function returns a Series these are expanded to columns. |
| `args` | `()` | Positional arguments to pass to `func` in addition to the array/series. |
| `**kdws` | | Additional keyword arguments to pass as keywords arguments to `func`. |

<br>


Let's look at our example data :


```python
import pandas as pd

matrix = [(222, 34, 23),
         (333, 31, 11),
         (444, 16, 21),
         (555, 32, 22),
         (666, 33, 27),
         (777, 35, 11)
         ]

data = pd.DataFrame(matrix, columns=list('abc'))
print(data)
```

**Output**

```
    a   b   c
0  222  34  23
1  333  31  11
2  444  16  21
3  555  32  22
4  666  33  27
5  777  35  11
```

<br>


We can apply defined function to our data with `.apply()`

```python
data1 = data.apply(lambda x: x // 2)
print(data1)
```

**Output**

```
    a   b   c
0  111  17  11
1  166  15   5
2  222   8  10
3  277  16  11
4  333  16  13
5  388  17   5
```


We can choose apply rows instead of columns with `axis` parameter.


We can apply defined function to our data with `.apply()`

```python
data2 = data.apply(lambda x: x // 2, axis=1)
print(data2)
```

**Output**

```
    a   b   c
0  111  17  11
1  166  15   5
2  222   8  10
3  277  16  11
4  333  16  13
5  388  17   5
```


<br>


We can also use a defined function to apply :

```python
def double(num):
    return num * num

data3 = data.apply(double)
print(data3)
```

**Output**

```
      a     b    c
0   49284  1156  529
1  110889   961  121
2  197136   256  441
3  308025  1024  484
4  443556  1089  729
5  603729  1225  121
```


<br>


We can give the function parameters as `.apply()` method parameter.


```python
def multi(num, mult):
    return num * mult

data4 = data.apply(multi, args=[4])
print(data4)
```

**Output**

```
      a    b    c
0   888  136   92
1  1332  124   44
2  1776   64   84
3  2220  128   88
4  2664  132  108
5  3108  140   44
```


<br>


We can use `apply()` function for a single column.


```python
def multi(num, mult):
    return num * mult

data["a"] = data["a"].apply(multi, args=[4])
print(data)
```

**Output**

```
      a   b   c
0   888  34  23
1  1332  31  11
2  1776  16  21
3  2220  32  22
4  2664  33  27
5  3108  35  11
```
