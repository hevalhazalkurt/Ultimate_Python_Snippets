# Ultimate Python Snippets
## Python Fundamentals
### Booleans


<br>

Booleans represent one of two values: `True` or `False`.

In programming you often need to know if an expression is `True` or `False`.

You can evaluate any expression in Python, and get one of two answers, `True` or `False`.

When you compare two values, the expression is evaluated and Python returns the Boolean answer:


```python
print(12 > 4)
print(12 == 4)
print(12 < 4)
```

**Output**

```
True
False
False
```

<br>


When you run a condition in an if statement, Python returns `True` or `False`. In the example below, print a message based on whether the conditions is `True` or `False`:

```python
x = 125
y = 20


if x > y:
	print("x is greater than y")
else:
	print("x is not greater than y")
```

**Output**

```
x is greater than y
```


<br>

The `bool()` function allows you to evaluate any value, and give you True or False in return. Almost any value is evaluated to `True` if it has some sort of content.

Any string is `True`, except empty strings.

Any number is `True`, except 0.

Any list, tuple, set, and dictionary are `True`, except empty ones.


```python
print(bool("Hello"))
print(bool(15))
print(bool(["apple", "cherry", "orange"]))
print(bool({"name": "Jack", "age": 27}))
```

**Output**

```
True
True
True
True
```

In fact, there are not many values that evaluates to `False`, except empty values, such as `()`, `[]`, `{}`, `""`, the number `0`, and the value `None`. And of course the value `False` evaluates to `False`.

```python
print(bool(False))
print(bool(None))
print(bool(0))
print(bool(""))
print(bool(()))
print(bool([]))
print(bool({}))
```

**Output**

```
False
False
False
False
False
False
False
```



One more value, or object in this case, evaluates to `False`, and that is if you have an objects that are made from a class with a `__len__` function that returns `0` or `False`:


```python
class myclass():
  def __len__(self):
    return 0

myobj = myclass()
print(bool(myobj))
```

**Output**

```
False
```

--------
