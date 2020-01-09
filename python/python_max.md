# Ultimate Python Snippets
## Python Functions
### `max()`


<br>

-----


#### What is `max()` for?

`max()` function returns the largest item in an iterable. It can also be used to find the largest item between two or more parameters.

**Syntax**

```python
max(iterable, key)
```

<br>

| Parameter | Default | Describe |
|--|--|--|
| `iterable` | | An iterable such as list, tuple, set, dictionary, etc. |
| `key` | optional | Key function where the iterables are passed and comparison is performed based on its return value |


<br>



```python
def maxlen(i):
    return len(i)

names = ["Sally", "Steven", "Chuck", "Zoe", "Alice"]
numbers = [1,3,5,6,2,5,2,6,8,1,9,2]
square = {2: 4, -3: 9, -1: 1, -2: 4}


print(max(4, -5, 23, 5))
print(max(numbers))

print(max(names))
print(max(names, key=maxlen))

print(max(square))
print(max(square, key=abs))
print(max(square, key = lambda k: square[k]))
print(square[max(square, key = lambda k: square[k])])
```

**Output**

```
23
9

Zoe
Steven

2
-3
-3
9
```

<br>

--------
