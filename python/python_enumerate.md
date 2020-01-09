# Ultimate Python Snippets
## Python Functions
### `enumerate()`


<br>

-----


#### What is `enumerate()` for?

`enumerate()` method adds counter to an iterable and returns it (the enumerate object).

**Syntax**

```python
enumerate(iterable, start=0)
```

<br>

| Parameter | Default | Describe |
|--|--|--|
| `iterable` | | An sequence, an iterator, or objects that supports iteration |
| `start` | optional | starts counting from this number. If `start` is omitted, 0 is taken as start. |


<br>



```python
names = ["Sally", "Barry", "Chuck", "Steven"]
numnames = enumerate(names)


print(numnames)
print(list(numnames))


for name in numnames:
    print(name)


for name in numnames:
    print("{}: {}".format(name[0], name[1]))
```

**Output**

```
<enumerate object at 0x1047dec30>
[(0, 'Sally'), (1, 'Barry'), (2, 'Chuck'), (3, 'Steven')]

(0, 'Sally')
(1, 'Barry')
(2, 'Chuck')
(3, 'Steven')

0: Sally
1: Barry
2: Chuck
3: Steven
```


<br><br>


```python
names = ["Sally", "Barry", "Chuck", "Steven"]
numnames10 = enumerate(names, start=10)

print(numnames10)
print(list(numnames10))

for name in numnames10:
    print(name)
```

**Output**

```
<enumerate object at 0x10b245c30>
[(10, 'Sally'), (11, 'Barry'), (12, 'Chuck'), (13, 'Steven')]

(10, 'Sally')
(11, 'Barry')
(12, 'Chuck')
(13, 'Steven')

10: Sally
11: Barry
12: Chuck
13: Steven
```

--------
