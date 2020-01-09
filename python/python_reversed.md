# Ultimate Python Snippets
## Python Functions
### `reversed()`


<br>

-----


#### What is `reversed()` for?

The `reversed()` method returns an iterator that accesses the given sequence in the reverse order.

**Syntax**

```python
reversed(sequence)
```


<br> <br>



#### `reversed()` with strings

```python
word = "bug"

print(reversed(word))
print(list(reversed(word)))

for char in reversed(word):
    print(char)
```

**Output**

```
<reversed object at 0x10fce8490>
['g', 'u', 'b']

g
u
b
```


<br><br>


#### `reversed()` with lists


```python
names = ["Sally", "Barry", "Chuck", "Steven"]

print(reversed(names))
print(list(reversed(names)))
```

**Output**

```
<list_reverseiterator object at 0x10825bf50>
['Steven', 'Chuck', 'Barry', 'Sally']
```


<br><br>


#### `reversed()` with tuples



```python
names = ("one", "two", "three", "four")
doubles = ((1,1), (2,4), (3,9))

print(reversed(names))
print(tuple(reversed(names)))

print(reversed(doubles))
print(tuple(reversed(doubles)))
```

**Output**

```
<reversed object at 0x10ddf9f50>
('four', 'three', 'two', 'one')

<reversed object at 0x10ddf9fd0>
((3, 9), (2, 4), (1, 1))
```

--------
