# Ultimate Python Snippets
## Python Functions
### `all()`


<br>

-----


#### What is `all()` for?

`all()` function returns `True` if all items in an iterable are true, otherwise it returns `False`.

If the iterable object is empty, the `all()` function also returns `True`.

**Syntax**

```python
all(iterable)
```

<br>

| Parameter | Default | Describe |
|--|--|--|
| `iterable` | | The sequence to sort, list, dictionary, tuple etc. |


<br>

--------

<br>


#### `all()` with booleans


```python
bools = [True, True, True]
print(all(bools))

bools = [True, True, False]
print(all(bools))
```

**Output**

```
True
False
```

<br>

--------

<br>


#### `all()` with empty iterable


```python
a_list = []
print(all(a_list))

a_dict = {}
print(all(a_dict))
```

**Output**

```
True
True
```

<br>

--------


<br>


#### `all()` with list of strings


```python
strs = ["True", "True"]
print(all(strs))

strs = ["True", "true"]
print(all(strs))

strs = ["abc", "true"]
print(all(strs))

strs = ["", "true"]
print(all(strs))
```

**Output**

```
True
True
True
False
```

<br>

--------
<br>


#### `all()` with list of numbers


```python
nums = [1, 3, 4, 5]
print(all(nums))

nums = [0, False]
print(all(nums))

nums = [1, 3, 4, 0]
print(all(nums))

nums = [0, False, 5]
print(all(nums))
```

**Output**

```
True
False
False
False
```

<br>

--------

<br>


#### `all()` with strings


```python
st = "This is good"
print(all(st))

st = "000"
print(all(st))

st = ""
print(all(st))
```

**Output**

```
True
True
True
```

<br>

--------
<br>


#### `all()` with custom objects


```python
class Person:
    name = ""

    def __init__(self, n):
        self.name = n


objs = [Person("Pankaj"), Person("Lisa")]
print(all(objs))

objs = [Peson("A"), Person("David")]
print(all(objs))
```

**Output**

```
True
True
```

<br>

--------

<br>


#### `all()` with dictionaries


```python
a_dict = {0, 1, 0}
print(all(a_dict))

a_dict = {0 : "Apple", 1 : "Orange"}
print(all(a_dict))

a_dict = {0: 'False', 1: 'False'}
print(all(a_dict))

a_dict = {1: 'True', 2: 'True'}
print(all(a_dict))

a_dict = {1: 'True', False: 0}
print(all(a_dict))

a_dict = {'0': 'True'}
print(all(a_dict))

a_dict = {}
print(all(a_dict))
```

**Output**

```
False
False
False
True
False
True
True
```

<br>

--------
