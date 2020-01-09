# Ultimate Python Snippets
## Python Functions
### `clear()`


<br>

-----


#### What is `clear()` for?

The `clear()` method removes all the elements from a list, dictionary or set.


**Syntax**

```python
sequence.clear()
```


<br>

---

<br>

#### `reversed()` with lists


```python
names = ["Tom", "Sally", "Steven", "Zoe"]
print(names)

names.clear()
print(names)

```

**Output**

```
['Tom', 'Sally', 'Steven', 'Zoe']
[]
```


<br>

---

<br>

#### `clear()` with dictionary



```python
names = {"Tom": 27, "Sally": 20, "Steven": 49, "Zoe": 12}
print(names)

names.clear()
print(names)
```

**Output**

```
{'Tom': 27, 'Sally': 20, 'Steven': 49, 'Zoe': 12}
{}
```

<br>

--------

<br>

#### `clear()` with set


```python
numbers = {1, 3, 5, 6}
print(numbers)

numbers.clear()
print(numbers)
```

```
{1, 3, 5, 6}
set()
```
