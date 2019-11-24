# Ultimate Python Snippets
## Python Functions
### `sorted()`


<br>

-----


#### What is `sorted()` for?

`sorted()` sorts any sequence (list, tuple) and returns a list with the elements in sorted manner, without modifying the original sequence.

You can specify ascending or descending order. Strings are sorted alphabetically, and numbers are sorted numerically.

**Syntax**

```python
sorted(iterable, *, key=None, reverse=False)
```

<br>

| Parameter | Default | Describe |
|--|--|--|
| `iterable` | | The sequence to sort, list, dictionary, tuple etc. |
| `key` | `None` | Optional. A Function to execute to decide the order. |
| `reverse` | `False` | Optional. A Boolean. False will sort ascending, True will sort descending. |

<br>

--------

<br>


#### Sorting numeric sequence


```python
mylist = [2,5,9,1,24,4,48, 23]
mytuple = (83,28,3,45,6,14)
mydict = {1: "one", 4: "four", 2: "two", 17: "seventeen", 11: "eleven"}

print(sorted(mylist))
print(sorted(mytuple))
print(sorted(mydict))
```

**Output**

```
[1, 2, 4, 5, 9, 23, 24, 48]
[3, 6, 14, 28, 45, 83]
[1, 2, 4, 11, 17]
```

<br>

--------

<br>


#### Sorting alphabetic sequence


```python
mylist = ["h", "f", "a", "z", "p", "e"]
mytuple = ("o", "d", "l", "e", "c", "q")
mydict = {"d": 12, "p": 12, "a": 12, "s": 12, "c": 12, "a": 12}

print(sorted(mylist))
print(sorted(mytuple))
print(sorted(mydict))
```

**Output**

```
['a', 'e', 'f', 'h', 'p', 'z']
['c', 'd', 'e', 'l', 'o', 'q']
['a', 'c', 'd', 'p', 's']
```

<br>

--------


<br>


#### Reversing sorted sequence

***Numeric sequence***

```python
mylist = [2,5,9,1,24,4,48, 23]
mytuple = (83,28,3,45,6,14)
mydict = {1: "one", 4: "four", 2: "two", 17: "seventeen", 11: "eleven"}

print(sorted(mylist, reverse=True))
print(sorted(mytuple, reverse=True))
print(sorted(mydict, reverse=True))
```

**Output**

```
[48, 24, 23, 9, 5, 4, 2, 1]
[83, 45, 28, 14, 6, 3]
[17, 11, 4, 2, 1]
```

<br>

***Alphabetic sequence***

```python
mylist = ["h", "f", "a", "z", "p", "e"]
mytuple = ("o", "d", "l", "e", "c", "q")
mydict = {"d": 12, "p": 12, "a": 12, "s": 12, "c": 12, "a": 12}

print(sorted(mylist, reverse=True))
print(sorted(mytuple, reverse=True))
print(sorted(mydict, reverse=True))
```

**Output**

```
['z', 'p', 'h', 'f', 'e', 'a']
['q', 'o', 'l', 'e', 'd', 'c']
['s', 'p', 'd', 'c', 'a']
```

<br>

--------

<br>


#### Sorting sequence based lengths


```python
mylist = ["aaaa", "aa", "a", "aaaaa", "aaaaaaaa"]

print(sorted(mylist, key=len))
print(sorted(mylist, key=len, reverse=True))
```

**Output**

```
['a', 'aa', 'aaaa', 'aaaaa', 'aaaaaaaa']
['aaaaaaaa', 'aaaaa', 'aaaa', 'aa', 'a']
```

<br>

--------

<br>


#### Sorting sequence based second item


```python
def second(seq):
    return seq[1]


mylist = [(2, 2), (3, 4), (4, 1), (1, 3)]

print(sorted(mylist))
print(sorted(mylist, key= second))
```

**Output**

```
[(1, 3), (2, 2), (3, 4), (4, 1)]
[(4, 1), (2, 2), (1, 3), (3, 4)]
```

<br>

--------

<br>


#### Sorting dictionary based its value


```python
mydict = {"a": 18, "h": 11, "t": 3, "p": 29, "z": 5}

print(sorted(mydict))
print(sorted(mydict, key= lambda x: mydict[x]))
```

**Output**

```
['a', 'h', 'p', 't', 'z']
['t', 'z', 'h', 'a', 'p']
```

<br>

--------

<br>


#### Sorting sequence based item's remainder



```python
def bythree(seq):
    return seq % 3


mylist = [48, 94, 58, 28, 19, 3, 14]

print(sorted(mylist))
print(sorted(mylist, key=bythree))
```

**Output**

```
[3, 14, 19, 28, 48, 58, 94]
[48, 3, 94, 58, 28, 19, 14]
```

<br>

--------

<br>


#### Sorting sequence based its reverses



```python
def reverse(seq):
    return seq[::-1]

mylist = ["strawberry", "banana", "peach", "kiwi", "apple"]

print(sorted(mylist))
print(sorted(mylist, key=reverse))
print(sorted(mylist, key=lambda x: x[::-1]))
print(sorted(mylist, key=lambda x: x[::-1], reverse=True))
```

**Output**

```
['apple', 'banana', 'kiwi', 'peach', 'strawberry']
['banana', 'apple', 'peach', 'kiwi', 'strawberry']
['banana', 'apple', 'peach', 'kiwi', 'strawberry']
['strawberry', 'kiwi', 'peach', 'apple', 'banana']
```

<br>

--------
