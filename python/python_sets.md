# Ultimate Python Snippets
## Python Fundamentals
### Sets

<br>


#### Summary

* What is a set?
* `set()` : Making Set
* `del` : Deleting Set
* `for` : Looping Through Set
* `in` : Checking an Item
* `add()` : Adding Item
* `clear()` : Making Empty
* `copy()` : Copying Set
* `difference()` : Getting Difference
* `difference_update()` : Deleting Mutual
* `discard()` : Removing Item
* `intersection()` : Getting Mutual
* `intersection_update()` : Deleting Uniques
* `isdisjoint()` : Checking Item in Sets
* `issubset()` : Checking Subset
* `issuperset()` : Checking Superset
* `len()` : Getting Length
* `pop()` : Removing Item
* `remove()` : Removing Item
* `symmetric_difference()` : Getting Uniques
* `symmetric_difference_update()` : Deleting Mutual
* `union()` : Joining Two Sets
* `update()` : Adding Multiple Item



<br>

-----

<br>

### What is a set?

A set is a collection which is unordered and unindexed. In Python sets are written with curly brackets.


```python
my_set = {"apple", "cherry", "banana"}
print(type(my_set))
print(my_set)
```

**Output**

```
<class 'set'>
{'apple', 'cherry', 'banana'}
```


<br>

--------


<br>

### `set()` : Making Set


It is possible to use the `set()` constructor to make a set.



```python
my_set = set(("apple", "banana", "kiwi"))
print(type(my_set))
print(my_set)
```


**Output**

```
<class 'set'>
{'banana', 'apple', 'kiwi'}
```


<br>

--------


<br>

### `del` : Deleting Set

The `del` keyword will delete the set completely.


```python
my_set = {"apple", "cherry", "banana"}
del my_set
print(my_set)
```

**Output**

```
Traceback (most recent call last):
  File "sets.py", line 3, in <module>
    print(my_set)
NameError: name 'my_set' is not defined
```


<br>

--------


<br>

### `for` : Looping Through Set  

We can loop through the set items using a `for` loop.



```python
my_set = {"apple", "cherry", "banana"}

for item in my_set:
    print(item)
```

**Output**

```
banana
cherry
apple
```


<br>

--------


<br>

### `in` : Checking an Item


We can check if a specified value is present in a set, by using the `in` keyword.


```python
my_set = {"apple", "cherry", "banana"}

print("cherry" in my_set)
print("kiwi" in my_set)
```

**Output**

```
True
False
```


<br>

--------


<br>

### `add()` : Adding Item

To add one item to a set we can use the `add()` method.


```python
my_set = {"apple", "cherry", "banana"}
print(my_set)

my_set.add("kiwi")
print(my_set)
```

**Output**

```
{'banana', 'cherry', 'apple'}
{'kiwi', 'banana', 'cherry', 'apple'}
```


<br>

--------


<br>

### `clear()` : Making Empty


The `clear()` method empties the set.


```python
my_set = {"apple", "banana", "kiwi"}
print(my_set)

my_set.clear()
print(my_set)
```

**Output**

```
{'kiwi', 'banana', 'apple'}
set()
```


<br>

--------


<br>

### `copy()` : Copying Set

The `copy()` method copies the set.


```python
my_set = {"apple", "banana", "kiwi"}
fruits = my_set.copy()

print(fruits)
```

**Output**

```
{'apple', 'banana', 'kiwi'}
```


<br>

--------


<br>

### `difference()` : Getting Difference

The `difference()` method returns a set that contains the difference between two sets.


```python
fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}

dif_1 = fruits.difference(words)
dif_2 = words.difference(fruits)

print(dif_1)
print(dif_2)
```

**Output**

```
{'banana', 'apple'}
{'hello', 'world'}
```


<br>

--------


<br>

### `difference_update()` : Deleting Mutual


The `difference_update()` method removes the items that exist in both sets.


```python
fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}

fruits.difference_update(words)
print(fruits)


fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}

words.difference_update(fruits)
print(words)
```

**Output**

```
{'apple', 'banana'}
{'world', 'hello'}
```


<br>

--------


<br>

### `discard()` : Removing Item

To remove an item in a set, we can use `discard()` method. It the item doesn't exist in the set, you don't get an error.


```python
my_set = {"apple", "banana", "cherry", "kiwi"}
print(my_set)

my_set.discard("cherry")
print(my_set)
```

**Output**

```
{'apple', 'cherry', 'banana', 'kiwi'}
{'apple', 'banana', 'kiwi'}
```


<br>

--------


<br>

### `intersection()` : Getting Mutual

The `intersection()` method returns a set that contains the similarity between two or more sets.


```python
fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}

mutual = fruits.intersection(words)
print(mutual)
```

**Output**

```
{'kiwi'}
```


We can also use `intersection()` method more than two sets.

```python
fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}
snacks = {"snickers", "pretzel", "kiwi"}

mutual = fruits.intersection(words, snacks)
print(mutual)
```

**Output**

```
{'kiwi'}
```


<br>

--------


<br>

### `intersection_update()` : Deleting Uniques


The intersection_update() method removes the items that is not present in both sets (or in all sets if the comparison is done between more than two sets).


```python
fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}

fruits.intersection_update(words)
print(fruits)



fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}
snacks = {"snickers", "pretzel", "kiwi"}

words.intersection_update(fruits, snacks)
print(words)
```

**Output**

```
{'kiwi'}
{'kiwi'}
```


<br>

--------


<br>

### `isdisjoint()` : Checking Item in Sets

The `isdisjoint()` method returns `True` if none of the items are present in both sets, otherwise it returns `False`.


```python
fruits = {"banana", "apple", "kiwi"}
words = {"hello", "kiwi", "world"}
numbers = {1, 3, 8, 2}

joint1 = fruits.isdisjoint(words)
joint2 = words.isdisjoint(numbers)

print(joint1)
print(joint2)
```

**Output**

```
False
True
```


<br>

--------


<br>

### `issubset()` : Checking Subset

The `issubset()` method returns `True` if all items in the set exists in the specified set, otherwise it retuns `False`.


```python
letters1 = {1,2,3,4}
letters2 = {9,8,7,6,5,4,3,2,1}

letters3 = letters1.issubset(letters2)
letters4 = letters2.issubset(letters1)

print(letters3)
print(letters4)
```

**Output**

```
True
False
```


<br>

--------


<br>

### `issuperset()` : Checking Superset

The `issuperset()` method returns `True` if all items in the specified set exists in the original set, otherwise it retuns `False`.


```python
letters1 = {1,2,3,4}
letters2 = {9,8,7,6,5,4,3,2,1}

letters3 = letters1.issuperset(letters2)
letters4 = letters2.issuperset(letters1)

print(letters3)
print(letters4)
```

**Output**

```
False
True
```


<br>

--------


<br>

### `len()` : Getting Length


To determine how many items a set has, use the `len()` method.


```python
my_set = {"banana", "cherry", "apple"}
print(len(my_set))
```

**Output**

```
3
```


<br>

--------



<br>

### `pop()` : Removing Item


We can also use the `pop()`, method to remove an item, but this method will remove the last item. Remember that sets are unordered, so we will not know what item that gets removed.


```python
my_set = {"banana", "apple", "kiwi", "cherry"}
print(my_set)

my_set.pop()
print(my_set)

my_set.pop()
print(my_set)
```

**Output**

```
{'cherry', 'kiwi', 'apple', 'banana'}
{'kiwi', 'apple', 'banana'}
{'apple', 'banana'}
```


<br>

--------


<br>

### `remove()` : Removing Item

To remove an item in a set, we can use `remove()` method. It the item doesn't exist in the set, you get error.


```python
my_set = {"apple", "cherry", "banana", "kiwi"}
print(my_set)

my_set.remove("cherry")
print(my_set)
```

**Output**

```
{'cherry', 'apple', 'banana', 'kiwi'}
{'apple', 'banana', 'kiwi'}
```


<br>

--------


<br>

### `symmetric_difference()` : Getting Uniques

The `symmetric_difference()` method returns a set that contains all items from both set, but not the items that are present in both sets.


```python
fruits = {"banana", "apple", "kiwi"}
words = {"orange", "kiwi", "peach"}

uniques = fruits.symmetric_difference(words)
print(uniques)
```

**Output**

```
{'peach', 'apple', 'orange', 'banana'}
```


<br>

--------


<br>

### `symmetric_difference_update()` : Deleting Mutual


The `symmetric_difference_update()` method updates the original set by removing items that are present in both sets, and inserting the other items.


```python
fruits = {"banana", "apple", "kiwi"}
words = {"orange", "kiwi", "peach"}

fruits.symmetric_difference_update(words)
print(fruits)
```

**Output**

```
{'peach', 'orange', 'banana', 'apple'}
```


<br>

--------


<br>

### `union()` : Joining Two Sets

We can use the `union()` method that returns a new set containing all items from both sets.


```python
numbers = {2, 3, 1, 8}
fruits = {"banana", "kiwi", "orange"}

my_set = numbers.union(fruits)
print(my_set)
```

**Output**

```
{1, 2, 3, 'kiwi', 8, 'banana', 'orange'}
```


<br>

--------


<br>

### `update()` : Adding Multiple Item

We can add more than one item to a set by using `update()` method.


```python
my_set = {"apple", "cherry", "banana"}
print(my_set)

my_set.update(["kiwi", "orange", "peach"])
print(my_set)
```

**Output**

```
{'cherry', 'banana', 'apple'}
{'apple', 'orange', 'peach', 'cherry', 'kiwi', 'banana'}
```

<br>

We can also use `update()` method to insert the items one set to another.

```python
numbers = {2, 3, 1, 8}
fruits = {"banana", "kiwi", "orange"}

numbers.update(fruits)
print(my_set)
```

**Output**

```
{'kiwi', 'orange', 'cherry', 'peach', 'apple', 'banana'}
```

<br>

--------
