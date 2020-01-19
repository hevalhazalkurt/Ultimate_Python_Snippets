# Ultimate Python Snippets
## Pandas
### `data.iterrows()`


<br>

-----


#### What is `data.iterrows()` for?

The `iterrows()` function is used to iterate over DataFrame rows as (index, Series) pairs.

Iterates over the DataFrame columns, returning a tuple with the column name and the content as a Series.

To iterate through rows of a DataFrame, use `DataFrame.iterrows()` function which returns an iterator yielding index and row data for each row.

**Syntax**

```python
DataFrame.iterrows(self)
```

<br>

**Yields**

| Name | Description | Type / Default Value | Required / Optinal |
|--|--|--|--|--|
| index | The index of the row. A tuple for a MultiIndex. | label or tuple of label | Required |
| data | The data of the row as a Series. | Series | Required |
| it | A generator that iterates over the rows of the frame. | generator | Required |


<br> <br>

**Example 1**

```python
import pandas as pd

data = {'name': ['Somu', 'Kiku', 'Amol', 'Lini'],
	'physics': [68, 74, 77, 78],
	'chemistry': [84, 56, 73, 69],
	'algebra': [78, 88, 82, 87]}

df_marks = pd.DataFrame(data)

for row_index, row in df_marks.iterrows():
    print("row number:", row_index, "\n---------")
    print(row)
    print("")
```

**Output**

```
row number: 0
---------
name         Somu
physics        68
chemistry      84
algebra        78
Name: 0, dtype: object

row number: 1
---------
name         Kiku
physics        74
chemistry      56
algebra        88
Name: 1, dtype: object

row number: 2
---------
name         Amol
physics        77
chemistry      73
algebra        82
Name: 2, dtype: object

row number: 3
---------
name         Lini
physics        78
chemistry      69
algebra        87
Name: 3, dtype: object
```


<br><br>

**Example 2**

```python
import pandas as pd

data = {'name': ['Somu', 'Kiku', 'Amol', 'Lini'],
	'physics': [68, 74, 77, 78],
	'chemistry': [84, 56, 73, 69],
	'algebra': [78, 88, 82, 87]}

df_marks = pd.DataFrame(data)


for row_index, row in df_marks.iterrows():
    print(row["name"])
```

**Output**

```
Somu
Kiku
Amol
Lini
```

<br>
