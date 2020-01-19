# Ultimate Python Snippets
## Pandas
### `data.iloc[]`


<br>

-----


#### What is `data.iloc[]` for?

It selects data by row index from a DataFrame.

**Syntax**

```python
DataFrame.iloc[row selection]
DataFrame.iloc[[row selection], [column selection]]
```

Allowed inputs are :

| Allowed inputs | Example |
|--|--|
| An integer | `data.iloc[3]` |
| A list of integers | `data.iloc[3, 5, 2]` |
| A slice object with integers | `data.iloc[1:6]` |
| A callable function with one argument (the calling Series or DataFrames) and returns valid output for indexing | |


<br>



**Examples**


```python
import pandas as pd

thedict = [{'a': 1, 'b': 2, 'c': 3, 'd': 4},
            {'a': 10, 'b': 20, 'c': 30, 'd': 40},
            {'a': 100, 'b': 200, 'c': 300, 'd': 400},
            {'a': 1000, 'b': 2000, 'c': 3000, 'd': 4000}]

df = pd.DataFrame(thedict)

print(df)
```


<br>

**1. Getting a row as a Series with a scalar integer**

```python
print(df.iloc[0])
```


**Output**

```
a    1
b    2
c    3
d    4
Name: 0, dtype: int64
```

<br> <br>

**2. Getting a row as a DataFrame with a list of integers**

```python
print(df.iloc[[2]])
print(df.iloc[[0,1]])
```


**Output**

```
     a    b    c    d
2  100  200  300  400

    a   b   c   d
0   1   2   3   4
1  10  20  30  40
```

<br> <br>

**3. Getting part of a DataFrame with a slice**

```python
print(df.iloc[:3])
```


**Output**

```
     a    b    c    d
0    1    2    3    4
1   10   20   30   40
2  100  200  300  400
```


<br> <br>

**4. Getting rows that fit a function**

```python
print(df.iloc[lambda x: x.index % 2 == 0])
```


**Output**

```
     a    b    c    d
0    1    2    3    4
2  100  200  300  400
```

<br> <br>

**5. Getting a specific value with scalar integer**

```python
print(df.iloc[0, 1])
print(df.iloc[1, 1])
```


**Output**

```
2
20
```

<br> <br>

**6. Getting multiple values with lists of integers**

```python
print(df.iloc[[0,1], [1,1]])
print(df.iloc[[1,3], [1,3]])
print(df.iloc[1:3, 1:3])
```


**Output**

```
    b   b
0   2   2
1  20  20

      b     d
1    20    40
3  2000  4000

     b    c
1   20   30
2  200  300
```

<br> <br> 

**7. Getting a part of DataFrame with a function**

```python
print(df.iloc[:, lambda df: [0,2]])
```

**Output**

```
      a     c
0     1     3
1    10    30
2   100   300
3  1000  3000
```
