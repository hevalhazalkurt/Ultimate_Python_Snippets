# Ultimate Python Snippets
## Python Fundamentals
### Dictionaries

<br>

#### Summary

* What is a dictionary?
* Accessing Items
* Adding Item
* Changing Value
* Nested Dictionaries
* `dict()` : Making Dictionary
* `for` : Looping Through
* `in` : Checking Key
* `len()` : Getting Length
* `copy()` : Copying Dictionary
* `fromkeys()` : Making Dictionary
* `setdefault()` : Setting Default
* `update()` : Inserting Item
* `has_key()` : Checking Key
* `get()` : Getting Value
* `items()` : Getting Items
* `keys()` : Getting Keys
* `values()` : Getting Values
* `pop()` : Removing Item
* `popitem()` : Removing Last
* `del` : Removing Item
* `clear()` : Making Empty



<br>

-----

<br>

### What is a dictionary?

A dictionary is a collection which is unordered, changeable and indexed. In Python dictionaries are written with curly brackets, and they have keys and values.

```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(type(the_car))
print(the_car)
```

**Output**

```
<class 'dict'>
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
```


<br>

--------


<br>

### Accessing Items

We can access the items of a dictionary by referring to its key name, inside square brackets:

```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(the_car["brand"])
print(the_car["year"])
```

**Output**

```
Ford
1964
```



<br>

--------


<br>

### Adding Item

Adding an item to the dictionary is done by using a new index key and assigning a value to it


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(the_car)

the_car["color"] = "Red"
print(the_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'Red'}
```



<br>

--------


<br>

### Changing Value

We can change the value of a specific item by referring to its key name :

```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(the_car["year"])

the_car["year"] = 1975
print(the_car["year"])
print(the_car)
```

**Output**

```
1964
1975
{'brand': 'Ford', 'model': 'Mustang', 'year': 1975}
```


<br>

-------


<br>

### Nested Dictionaries

A dictionary can contain many dictionaries, this is called nested dictionaries.


```python
childrens = {
  "child1" : {
    "name" : "Emil",
    "year" : 2004
  },
  "child2" : {
    "name" : "Tobias",
    "year" : 2007
  },
  "child3" : {
    "name" : "Linus",
    "year" : 2011
  }
}


print(childrens)
print("")
print(childrens["child1"])
print("")
print(childrens["child2"]["name"])
print("")
print(childrens["child3"]["year"])
```

**Output**

```
{'child1': {'name': 'Emil', 'year': 2004}, 'child2': {'name': 'Tobias', 'year': 2007}, 'child3': {'name': 'Linus', 'year': 2011}}

{'name': 'Emil', 'year': 2004}

Tobias

2011
```


<br>

-------


<br>

### `dict()` : Making Dictionary


It is possible to use the `dict()` constructor to make a new dictionary.


```python
the_car = dict(brand="Ford", model="Mustang", year=1964, color="Red")

print(type(the_car))
print(the_car)
```

**Output**

```
<class 'dict'>
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'Red'}
```


<br>

-------


<br>

### `for` : Looping Through

We can loop through a dictionary by using a `for` loop. When looping through a dictionary, the return value are the keys of the dictionary.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

for k in the_car:
	print(k)
```

**Output**

```
brand
model
year
```


If we want to accessing values of keys, we can use `for` loop like this :


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

for k in the_car:
	print(the_car[k])
```

**Output**

```
Ford
Mustang
1964
```

<br>

--------


<br>

### `in` : Checking Key


To find if a specified key is present in a dictionary we can use the `in` keyword


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}


print("model" in the_car)
print("color" in the_car)
```

**Output**

```
True
False
```


<br>

--------


<br>

### `len()` : Getting Length


To find how many items (key-value pairs) a dictionary has, we can use the `len()` method.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}


print(len(the_car))
```

**Output**

```
3
```


<br>

--------


<br>

### `copy()` : Copying Dictionary


We can `copy()` method to copy a dictionary.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

my_car = the_car.copy()
print(my_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
```


<br>

--------


<br>

### `fromkeys()` : Making Dictionary


The `fromkeys()` method returns a dictionary with the specified keys and values.


```python
x = ("key1", "key2", "key3")
y = 0

pairs = dict.fromkeys(x,y)
print(pairs)

print("")

z = ('key1', 'key2', 'key3')
nones = dict.fromkeys(x)

print(nones)
```

**Output**

```
{'key1': 0, 'key2': 0, 'key3': 0}

{'key1': None, 'key2': None, 'key3': None}
```


<br>

--------


<br>

### `setdefault()` : Setting Default


The `setdefault()` method returns the value of the item with the specified key. If the key does not exist, insert the key, with the specified value.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

x = the_car.setdefault("model", "Bronco")
y = the_car.setdefault("color", "Red")

print(x)
print(y)
```

**Output**

```
Mustang
Red
```


<br>

--------


<br>

### `update()` : Inserting Item


The `update()` method inserts the specified items to the dictionary. The specified items can be a dictionary, or an iterable object.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}


the_car.update({"color": "Red", "plate": "CA"})
print(the_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'Red', 'plate': 'CA'}
```


<br>

--------



<br>

### `get()` : Getting Value

We can get the value of a key by `get()` method.

```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(the_car.get("model"))
print(the_car.get("year"))
```

**Output**

```
Mustang
1964
```


<br>

--------


<br>

### `items()` : Getting Items

The `items()` method returns a view object. The view object contains the key-value pairs of the dictionary, as tuples in a list.

```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}


print(the_car.items())


for k,v in the_car.items():
	print(k, v)
```

**Output**

```
dict_items([('brand', 'Ford'), ('model', 'Mustang'), ('year', 1964)])

brand Ford
model Mustang
year 1964
```


<br>

--------


<br>

### `keys()` : Getting Keys

The `keys()` method returns a view object. The view object contains the keys of the dictionary, as a list.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(the_car.keys())

for k in the_car.keys():
	print(k)
```

**Output**

```
dict_keys(['brand', 'model', 'year'])

brand
model
year
```


<br>

--------


<br>

### `values()` : Getting Values


The `values()` method returns a view object. The view object contains the values of the dictionary, as a list.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}


print(the_car.values())

for v in the_car.values():
	print(v)
```

**Output**

```
dict_values(['Ford', 'Mustang', 1964])

Ford
Mustang
1964
```


<br>

--------


<br>

### `pop()` : Removing Item


The `pop()` method removes the item with the specified key name


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964
}

print(the_car)

the_car.pop("brand")
print(the_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
{'model': 'Mustang', 'year': 1964}
```


<br>

--------


<br>

### `popitem()` : Removing Last


The `popitem()` method removes the last inserted item.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964,
		"color" : "Red"
}

print(the_car)

the_car.popitem()
print(the_car)

the_car.popitem()
print(the_car)

the_car.popitem()
print(the_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'Red'}
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
{'brand': 'Ford', 'model': 'Mustang'}
{'brand': 'Ford'}
```


<br>

--------


<br>

### `del` : Removing Item


The `del` keyword removes the item with the specified key name.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964,
		"color" : "Red"
}


print(the_car)

del the_car["color"]
print(the_car)

del the_car["model"]
print(the_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'Red'}
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964}
{'brand': 'Ford', 'year': 1964}
```


We can also delete a dictionary completely.  

```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964,
		"color" : "Red"
}


del the_car
print(the_car)
```

**Output**

```
Traceback (most recent call last):
  File "dictionaries.py", line 10, in <module>
    print(the_car)
NameError: name 'the_car' is not defined
```

<br>

--------


<br>

### `clear()` : Making Empty


The `clear()` keyword empties the dictionary.


```python
the_car = {
		"brand" : "Ford",
		"model" : "Mustang",
		"year" : 1964,
		"color" : "Red"
}

print(the_car)

the_car.clear()
print(the_car)
```

**Output**

```
{'brand': 'Ford', 'model': 'Mustang', 'year': 1964, 'color': 'Red'}
{}
```


<br>

--------
