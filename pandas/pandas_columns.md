# Ultimate Python Snippets
## Pandas
### `data.columns`


<br>

-----


#### What is `.columns` for?

Returns the column labels of the DataFrame.


**Syntax**

```python
data.columns  
data.columns.values
data.columns.values.tolist()
```


We have an example database called `drinks`. Let's look at the first few rows to have an idea.



```python
import pandas as pd

drinks = pd.read_csv("files/drinks.csv")
print(drinks.head())
```

**Output**

```
      country  beer_servings  spirit_servings  wine_servings  total_litres_of_pure_alcohol continent
0  Afghanistan              0                0              0                           0.0      Asia
1      Albania             89              132             54                           4.9    Europe
2      Algeria             25                0             14                           0.7    Africa
3      Andorra            245              138            312                          12.4    Europe
4       Angola            217               57             45                           5.9    Africa
```

<br>


We can get the information of column names by `.columns` command.


```python
print(drinks.columns)
```

**Output**

```
Index(['country', 'beer_servings', 'spirit_servings', 'wine_servings', 'total_litres_of_pure_alcohol', 'continent'],
      dtype='object')
```

<br>


The `.columns` is an iterable object so we can iterate over it.


```python
for column in drinks.columns:
    print(column)
```

**Output**

```
country
beer_servings
spirit_servings
wine_servings
total_litres_of_pure_alcohol
continent
```

<br>


With `.columns.values`, we can get the column names as a numpy array.


```python
print(drinks.columns.values)
print(type(drinks.columns.values))
```

**Output**

```
['country' 'beer_servings' 'spirit_servings' 'wine_servings'
 'total_litres_of_pure_alcohol' 'continent']
 <class 'numpy.ndarray'>
```


<br>


We can also get the column names as a list by `.columns.values.tolist()`


```python
print(drinks.columns.values.tolist())
print(type(drinks.columns.values.tolist()))
```

**Output**

```
['country', 'beer_servings', 'spirit_servings', 'wine_servings', 'total_litres_of_pure_alcohol', 'continent']
<class 'list'>
```

--------
