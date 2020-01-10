# Ultimate Python Snippets
## Python Fundamentals
### Data Types


#### Summary

* Python Variable Types
* Setting the Data Type
* `type()` : Getting Data Type

<br>

-----

<br>

### Python Variable Types   

Variables can store data of different types, and different types can do different things. Python has the following data types built-in by default, in these categories:


|  | |
|--|--|
| Text Type | `str` |
| Numeric Types | `int` <br> `float` <br> `complex` |
| Sequence Types | `list` <br> `tuple` <br> `range` |
| Mapping Type | `dict` |
| Set Types | `set` <br> `frozenset` |
| Boolean Type | `bool` |
| Binary Types | `bytes` <br> `bytearray` <br> `memoryview` |


<br>

-----

<br>


### Setting the Data Type

|  | |
|--|--|
| `x = "Hello World"` | `str` |
| `x = 20` | `int` |
| `x = 20.5` | `float` |
| `x = 1j` | `complex` |
| `x = ["apple", "banana", "cherry"]` | `list` |
| `x = ("apple", "banana", "cherry")` | `tuple` |
| `x = range(6)` | `range` |
| `x = { "name": "John", "age": 36}` | `dict` |
| `x = {"apple", "banana", "cherry"}` | `set` |
| `x = frozenset({"apple", "banana", "cherry"})` | `frozenset` |
| `x = True` | `bool` |
| `x = b"Hello"` | `bytes` |
| `x = bytearray(5)` | `bytearray` |
| `x = memoryview(bytes(5))` | `memoryview` |



<br>

----

<br>

### Setting the Specific Data Type

If we want to specify the data type, we can use the following constructor functions:


|  | |
|--|--|
| `x = str("Hello World")` | `str` |
| `x = int(20)` | `int` |
| `x = float(20.5)` | `float` |
| `x = complex(1j)` | `complex` |
| `x = list(("apple", "banana", "cherry"))` | `list` |
| `x = tuple(("apple", "banana", "cherry"))` | `tuple` |
| `x = range(6)` | `range` |
| `x = dict(name = "John", age = 36)` | `dict` |
| `x = set(("apple", "banana", "cherry"))` | `set` |
| `x = frozenset({"apple", "banana", "cherry"})` | `frozenset` |
| `x = bool(5)` | `bool` |
| `x = bytes(5)` | `bytes` |
| `x = bytearray(5)` | `bytearray` |
| `x = memoryview(bytes(5))` | `memoryview` |


<br>

----

<br>

### `type()` : Getting Data Type


We can get the data type of any object by using the `type()` function



```python
x = 5
y = "Hello"
z = [1, 3, "blog"]
t = {"name": "Steven", "last name": "Jr."}
s = ("name", "last name")
r = 3.4

print(type(x))
print(type(y))
print(type(z))
print(type(t))
print(type(s))
print(type(r))
```

**Output**

```
<class 'int'>
<class 'str'>
<class 'list'>
<class 'dict'>
<class 'tuple'>
<class 'float'>
```

<br>

---
