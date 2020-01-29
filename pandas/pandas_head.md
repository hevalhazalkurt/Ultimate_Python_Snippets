# Ultimate Python Snippets
## Pandas
### `data.head()`


<br>

-----


#### What is `data.head()` for?

This function returns the first `n` rows for the object based on position. It is useful for quickly testing if your object has the right type of data in it.

**Syntax**

```python
DataFrame.head(n=5)
```


Let's look at our example data :

```python
import pandas as pd

data = pd.read_csv("datasets/uk-500.csv")
```


<br><br>


**Viewing the first 5 lines**

```python
print(data.head())
```

***Output***

```
  first_name   last_name  ...                       email                                   web
0    Aleshia  Tomkiewicz  ...     atomkiewicz@hotmail.com  http://www.alandrosenburgcpapc.co.uk
1       Evan   Zigomalas  ...    evan.zigomalas@gmail.com     http://www.capgeminiamerica.co.uk
2     France     Andrade  ...  france.andrade@hotmail.com      http://www.elliottjohnwesq.co.uk
3    Ulysses   Mcwalters  ...         ulysses@hotmail.com          http://www.mcmahanbenl.co.uk
4     Tyisha      Veness  ...   tyisha.veness@hotmail.com        http://www.champagneroom.co.uk

[5 rows x 11 columns]
```


<br><br>


**Viewing the first `n` lines**

```python
print(data.head(3))
```

***Output***

```
  first_name   last_name  ...                       email                                   web
0    Aleshia  Tomkiewicz  ...     atomkiewicz@hotmail.com  http://www.alandrosenburgcpapc.co.uk
1       Evan   Zigomalas  ...    evan.zigomalas@gmail.com     http://www.capgeminiamerica.co.uk
2     France     Andrade  ...  france.andrade@hotmail.com      http://www.elliottjohnwesq.co.uk

[3 rows x 11 columns]
```


<br><br>


**Viewing the first `n` lines of a Series**

```python
print(data.first_name.head())
```

***Output***

```
0    Aleshia
1       Evan
2     France
3    Ulysses
4     Tyisha
Name: first_name, dtype: object
```

<br><br>


**Viewing the first lines of a few Series**

```python
print(data.loc[:, ["first_name", "last_name"]].head())
```

***Output***

```
  first_name   last_name
0    Aleshia  Tomkiewicz
1       Evan   Zigomalas
2     France     Andrade
3    Ulysses   Mcwalters
4     Tyisha      Veness
```

<br><br>


**Viewing the first lines of a slice**

```python
print(data[30:40].head())
```

***Output***

```
   first_name  last_name  ...                      email                                       web
30       Reed  Weisinger  ...   reed_weisinger@yahoo.com         http://www.berickjosephgesq.co.uk
31     German     Zelaya  ...         german@hotmail.com  http://www.jacksonheitmachinecoinc.co.uk
32      Milly    Savidge  ...            milly@gmail.com   http://www.bridgewayplanforhealth.co.uk
33       Luis        Ear  ...           luis@hotmail.com     http://www.wainstforplcystudies.co.uk
34      Ciara    Cobbley  ...  ciara_cobbley@hotmail.com                   http://www.wmglfm.co.uk

[5 rows x 11 columns]
```


<br>

```python
print(data.loc[30:40, ["first_name", "last_name"]].head())
```

***Output***

```
   first_name  last_name
30       Reed  Weisinger
31     German     Zelaya
32      Milly    Savidge
33       Luis        Ear
34      Ciara    Cobbley
```



<br><br>


**Viewing the first lines of fits a condition**

```python
print(data[data["county"] == "Greater London"].loc[:, ["first_name", "last_name", "county"]].head())
```

***Output***

```
   first_name  last_name          county
39      Craig        Cua  Greater London
53     Dustin  Klingaman  Greater London
68    Abraham     Cratch  Greater London
69   Giuseppe    Rohaley  Greater London
75      Billy      Venus  Greater London
```
