# Ultimate Python Snippets
## Pandas
### `data.loc[]`


<br>

-----


#### What is `data.loc[]` for?

It selects data by row label from a DataFrame.

**Syntax**

```python
DataFrame.loc["row selection"]
DataFrame.loc[["row selection"], ["column selection"]]
```

Allowed inputs are :

| Allowed inputs | Example |
|--|--|
| A single label | `data.loc["a"]` |
| A list of array of labels | `data.loc["a", "b", "c"]` |
| A slice object with labels | `data.loc["a":"f"]` |
| A boolean array of the same lenght as the axis being sliced | `data.loc[True, False, True]` |
| A callable function with one argument (the calling Series or DataFrames) and returns valid output for indexing | |


The Pandas `loc` indexer can be used with DataFrames for two different use cases:

1. Selecting rows by label/index
2. Selecting rows with a boolean / conditional lookup


<br>



**Examples**

We have two DataFrames to work on it. First one is :

```python
import pandas as pd

data = pd.DataFrame([[1, 2], [4, 5], [7, 8]],
                    index=['cobra', 'viper', 'sidewinder'],
                    columns=['max_speed', 'shield'])

df = pd.DataFrame(data)
print(df)
```

***Output***

```               
            max_speed  shield
cobra               1       2
viper               4       5
sidewinder          7       8
```

Second one is :

```python
uk = pd.read_csv("pandas/datasets/uk-500.csv", index_col="last_name")
print(uk.shape)
print(uk.head())
print(uk.columns)
```

**Output**

```
(500, 11)

           first_name             company_name  ...                       email                                   web
last_name                                       ...                                                                  
Tomkiewicz    Aleshia  Alan D Rosenburg Cpa Pc  ...     atomkiewicz@hotmail.com  http://www.alandrosenburgcpapc.co.uk
Zigomalas        Evan       Cap Gemini America  ...    evan.zigomalas@gmail.com     http://www.capgeminiamerica.co.uk
Andrade        France      Elliott, John W Esq  ...  france.andrade@hotmail.com      http://www.elliottjohnwesq.co.uk
Mcwalters     Ulysses           Mcmahan, Ben L  ...         ulysses@hotmail.com          http://www.mcmahanbenl.co.uk
Veness         Tyisha           Champagne Room  ...   tyisha.veness@hotmail.com        http://www.champagneroom.co.uk

Index(['first_name', 'last_name', 'company_name', 'address', 'city', 'county',
       'postal', 'phone1', 'phone2', 'email', 'web'],
      dtype='object')
```


<br>

**1. Getting a row as a Series with a row label**

```python
print(df.loc["cobra"])
```


***Output***

```
max_speed    1
shield       2
Name: cobra, dtype: int64
```

<br><br>


```python
print(uk.loc["Andrade"])
```


***Output***

```
first_name                                France
company_name                 Elliott, John W Esq
address                             8 Moor Place
city              East Southbourne and Tuckton W
county                               Bournemouth
postal                                   BH6 3BE
phone1                              01347-368222
phone2                              01935-821636
email                 france.andrade@hotmail.com
web             http://www.elliottjohnwesq.co.uk
Name: Andrade, dtype: object
```

<br> <br>


**2. Getting a row as a DataFrame with a list of labels**

```python
print(df.loc[["viper", "sidewinder"]])
```


***Output***

```
            max_speed  shield
viper               4       5
sidewinder          7       8
```

<br><br>

```python
print(uk.loc[["Andrade", "Veness"]])
```


***Output***

```
          first_name         company_name            address  ...        phone2                       email                               web
last_name                                                     ...                                                                            
Andrade       France  Elliott, John W Esq       8 Moor Place  ...  01935-821636  france.andrade@hotmail.com  http://www.elliottjohnwesq.co.uk
Veness        Tyisha       Champagne Room  5396 Forth Street  ...  01290-367248   tyisha.veness@hotmail.com    http://www.champagneroom.co.uk

[2 rows x 10 columns]
```

<br> <br>


**3. Getting single label value from a DataFrame**

```python
print(df.loc["cobra", "shield"])
```


**Output**

```
2
```

<br><br>

```python
print(uk.loc["Veness", "first_name"])
```


**Output**

```
Tyisha
```


<br> <br>

**4. Getting part of a DataFrame with a slice**

Note that both the start and stop of the slice are included.

```python
print(df.loc["cobra": "viper", "max_speed"])
```


**Output**

```
cobra    1
viper    4
Name: max_speed, dtype: int64
```

<br><br>

```python
print(uk.loc["Andrade": "Veness", "first_name"])
```


**Output**

```
last_name
Andrade       France
Mcwalters    Ulysses
Veness        Tyisha
Name: first_name, dtype: object
```

<br> <br>

**5. Getting values that fit a conditional**

```python
print(df["shield"] > 6)

print(df[df["shield"] > 6])

print(df.loc[df["shield"] > 6, ["max_speed"]])
```


**Output**

```
cobra         False
viper         False
sidewinder     True
Name: shield, dtype: bool


            max_speed  shield
sidewinder          7       8


            max_speed
sidewinder          7
```

<br><br>

```python
print(uk["county"] == "Bournemouth")

print(uk[uk["county"] == "Bournemouth"])

print(uk.loc[uk["county"] == "Bournemouth", ["first_name"]])
```


**Output**

```
last_name
Tomkiewicz    False
Zigomalas     False
Andrade        True
Mcwalters     False
Veness        False
              ...  
Veit          False
Euresti       False
Brenning      False
Keeny         False
Richan        False
Name: county, Length: 500, dtype: bool



          first_name         company_name        address  ...        phone2                       email                               web
last_name                                                 ...                                                                            
Andrade       France  Elliott, John W Esq   8 Moor Place  ...  01935-821636  france.andrade@hotmail.com  http://www.elliottjohnwesq.co.uk
Weissmann   Domitila  Ciocia, James A Esq  28 Berwick St  ...  01928-189722          domitila@gmail.com  http://www.ciociajamesaesq.co.uk

[2 rows x 10 columns]



          first_name
last_name           
Andrade       France
Weissmann   Domitila
```

<br> <br>

**6. Getting rows that fit a function**

```python
print(df.loc[lambda df: df["shield"] > 6])
```


**Output**

```
            max_speed  shield
sidewinder          7       8
```

<br><br>

```python
print(uk.loc[lambda uk: uk["first_name"].str[0] == "Z", ["first_name", "county"]])
```


**Output**

```
           first_name              county
last_name                                
Speltz           Zita  Greater Manchester
Freeburger    Zachary          Derbyshire
```

<br> <br>


**7. Setting value for all items matching the list of labels**

```python
df.loc[["viper", "sidewinder"], ["shield"]] = 50
print(df)
```

**Output**

```
            max_speed  shield
cobra               1       2
viper               4      50
sidewinder          7      50
```

<br><br>

```python
uk.loc[["Andrade", "Veness"], ["web"]] = "no_web"
print(uk.head())
```

**Output**

```

           first_name             company_name            address  ...        phone2                       email                                   web
last_name                                                          ...                                                                                
Tomkiewicz    Aleshia  Alan D Rosenburg Cpa Pc       14 Taylor St  ...  01944-369967     atomkiewicz@hotmail.com  http://www.alandrosenburgcpapc.co.uk
Zigomalas        Evan       Cap Gemini America        5 Binney St  ...  01714-737668    evan.zigomalas@gmail.com     http://www.capgeminiamerica.co.uk
Andrade        France      Elliott, John W Esq       8 Moor Place  ...  01935-821636  france.andrade@hotmail.com                                no_web
Mcwalters     Ulysses           Mcmahan, Ben L      505 Exeter Rd  ...  01302-601380         ulysses@hotmail.com          http://www.mcmahanbenl.co.uk
Veness         Tyisha           Champagne Room  5396 Forth Street  ...  01290-367248   tyisha.veness@hotmail.com                                no_web

[5 rows x 10 columns]
```


<br> <br>

**8. Setting value for an entire row**

```python
df.loc["cobra"] = 10
print(df)
```

**Output**

```
            max_speed  shield
cobra              10      10
viper               4      50
sidewinder          7      50
```

<br><br>

```python
uk.loc["Tomkiewicz"] = "no_data"
print(uk.loc[["Tomkiewicz"]])
```

**Output**

```
           first_name company_name  address     city   county   postal   phone1   phone2    email      web
last_name                                                                                                 
Tomkiewicz    no_data      no_data  no_data  no_data  no_data  no_data  no_data  no_data  no_data  no_data
```



<br> <br>

**9. Setting value for an entire column**

```python
df.loc[:, "max_speed"] = 30
print(df)
```

**Output**

```
            max_speed  shield
cobra              30      10
viper              30      50
sidewinder         30      50
```



<br><br>

```python
uk.loc[:, "web"] = "no_web"
print(uk.loc[:, ["first_name", "web"]])
```

**Output**

```
           first_name     web
last_name                    
Tomkiewicz    no_data  no_web
Zigomalas        Evan  no_web
Andrade        France  no_web
Mcwalters     Ulysses  no_web
Veness         Tyisha  no_web
...               ...     ...
Veit            Avery  no_web
Euresti          Reid  no_web
Brenning    Charlette  no_web
Keeny       Celestina  no_web
Richan             Mi  no_web

[500 rows x 2 columns]
```


<br> <br>

**10. Setting value for rows matching a condition**

```python
df.loc[df["shield"] > 35] = 0
print(df)
```

**Output**

```
            max_speed  shield
cobra              30      10
viper               0       0
sidewinder          0       0
```

<br><br>

```python
uk.loc[uk["first_name"] == "France"] = "FR"
print(uk.head())
print(df)
```

**Output**

```
           first_name        company_name            address  ...        phone2                      email     web
last_name                                                     ...                                                 
Tomkiewicz    no_data             no_data            no_data  ...       no_data                    no_data  no_web
Zigomalas        Evan  Cap Gemini America        5 Binney St  ...  01714-737668   evan.zigomalas@gmail.com  no_web
Andrade            FR                  FR                 FR  ...            FR                         FR      FR
Mcwalters     Ulysses      Mcmahan, Ben L      505 Exeter Rd  ...  01302-601380        ulysses@hotmail.com  no_web
Veness         Tyisha      Champagne Room  5396 Forth Street  ...  01290-367248  tyisha.veness@hotmail.com  no_web

[5 rows x 10 columns]
```


<br> <br>

**11. Getting values where a column ends with an string**

```python
print(uk.loc[uk["email"].str.endswith("hotmail.com")])
```

**Output**

```
          first_name                    company_name                 address  ...        phone2                       email     web
last_name                                                                     ...                                                  
Mcwalters    Ulysses                  Mcmahan, Ben L           505 Exeter Rd  ...  01302-601380         ulysses@hotmail.com  no_web
Veness        Tyisha                  Champagne Room       5396 Forth Street  ...  01290-367248   tyisha.veness@hotmail.com  no_web
Grasmick        Marg   Wrangle Hill Auto Auct & Slvg        7457 Cowl St #70  ...  01362-620532            marg@hotmail.com  no_web
Manzella        Lura                 Bizerba Usa Inc        929 Augustine St  ...  01340-713951            lura@hotmail.com  no_web
Julio         Dewitt            Rittenhouse Motor Co           7 Richmond St  ...  01241-964675    dewitt.julio@hotmail.com  no_web
...              ...                             ...                     ...  ...           ...                         ...     ...
Gaucher       Sophia               T C E Systems Inc  88 Upper Harrington St  ...  01254-919378  sophia.gaucher@hotmail.com  no_web
Ausdemore     Rosita               Jurdem, Scott Esq    8 Heathfield St #657  ...  01997-765432      rausdemore@hotmail.com  no_web
Stancil         Huey                   Lindner Funds             275 Peel Sq  ...  01468-195646        hstancil@hotmail.com  no_web
Fiorino       Elbert            Donald, G Nelson Esq  726 Westmoreland Place  ...  01992-537553          elbert@hotmail.com  no_web
Richan            Mi  Nelson Wright Haworth Golf Crs         6 Norwood Grove  ...  01202-738406              mi@hotmail.com  no_web

[112 rows x 10 columns]
```


<br> <br>

**12. Getting values that has a value**

```python
print(uk.loc[uk['first_name'].isin(['France', 'Tyisha', 'Eric'])])
```

**Output**

```
          first_name             company_name            address  ...        phone2                      email     web
last_name                                                         ...                                                 
Veness        Tyisha           Champagne Room  5396 Forth Street  ...  01290-367248  tyisha.veness@hotmail.com  no_web
Rampy           Eric  Thompson, Michael C Esq       9472 Lind St  ...  01545-817375         erampy@rampy.co.uk  no_web

[2 rows x 10 columns]
```
