# Ultimate Python Snippets
## Python Fundamentals
### Lists


<br>

---

#### Summary

* What is a list?
* Accessing List Item
* Changing List Item
* Concatenating Lists
* Unpacking lists
* Checking Items Are Equal
* Getting Unique Items
* Chunking List
* Getting Most Frequent
* `list()` : Making List
* `for` : Looping Through a List
* `enumerate()` : Numerating Items  
* `in` : Checking Item
* `len()` : Getting List Length
* `zip()` : Pairing List
* `.append()` : Adding New Item
* `.copy()` : Copying List
* `.count()` : Counting Item
* `.extend()` : Concatenating Lists
* `.index()` : Finding Item  
* `.insert()` : Adding New Item
* `.join()` : Making String
* `.pop()` : Removing An Item
* `.remove()` : Removing An Item
* `del` : Removing An Item
* `.clear()` : Emptying List
* `.reverse()` : Reversing List
* `reversed()` : Reversing List
* `.sort()` : Sorting List



<br>

-----

<br>

### What is a list?

A list is a collection consist of strings, numbers or even lists. A list is a collection which is ordered and changeable. In Python lists are written with square brackets.

```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

print(letters)
print(fruits)
print(numbers)
print(lists)
```

**Output**

```
['a', 'b', 'c', 'd', 'e']
['apple', 'banana', 'cherry']
[1, 2, 3, 4, 5]
[['a', 'b', 'c'], [1, 2], 35]
```


<br>

--------


<br>

### Accessing List Item

You access the list items by referring to the index number:

```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

print(letters[0])
print(fruits[1])
print(numbers[3])
print(lists[1])
```

**Output**

```
a
banana
4
[1, 2]
```


We can also use negative indexing. Negative indexing means beginning from the end, `-1` refers to the last item, `-2` refers to the second last item etc.


```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

print(letters[-3])
print(fruits[-1])
print(numbers[-2])
print(lists[-3])
```

**Output**

```
c
cherry
4
['a', 'b', 'c']
```


We can specify a range of indexes by specifying where to start and where to end the range. When specifying a range, the return value will be a new list with the specified items.


```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

print(letters[2:4])
print(fruits[1:2])
print(numbers[2:4])
print(lists[1:2])
```

**Output**

```
['c', 'd']
['banana']
[3, 4]
[[1, 2]]
```


We can also use range of negative indexes. Specify negative indexes if you want to start the search from the end of the list:

```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

print(letters[-4:-2])
print(fruits[-3:-1])
print(numbers[-3:-2])
print(lists[-3:-2])
```

**Output**

```
['b', 'c']
['apple', 'banana']
[3]
[['a', 'b', 'c']]
```

<br>

--------


<br>

### Changing List Item

Lists are mutable so any item in a list can be changed with the help of `index`. To change the value of a specific item, refer to the index number:

```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

letters[2] = "z"
fruits[0] = "berry"
numbers[1] = 9
lists[1] = [1,3,5]

print(letters)
print(fruits)
print(numbers)
print(lists)
```

**Output**

```
['a', 'b', 'z', 'd', 'e']
['berry', 'banana', 'cherry']
[1, 9, 3, 4, 5]
[['a', 'b', 'c'], [1, 3, 5], 35]
```


<br>

--------

<br>

### Concatenating Lists

There are several ways to join, or concatenate, two or more lists in Python.

One of the easiest ways are by using the `+` operator.


```python
fruit_1 = ["banana", "orange"]
fruit_2 = ["cherry", "berry", "apple"]
fruits = fruit_1 + fruit_2

list1 = ["one", "two"]
list2 = [3, 4, 5]
list3 = list1 + list2

print(fruits)
print(list3)
```

**Output**

```
['banana', 'orange', 'cherry', 'berry', 'apple']
['one', 'two', 3, 4, 5]
```

Another way to join two lists are by appending all the items from list2 into list1, one by one:

```python
fruit_1 = ["banana", "orange"]
fruit_2 = ["cherry", "berry", "apple"]

for fruit in fruit_2:
	fruit_1.append(fruit)

print(fruit_1)
```

**Output**

```
['banana', 'orange', 'cherry', 'berry', 'apple']
```

Or you can use the `extend()` method, which purpose is to add elements from one list to another list:


```python
fruit_1 = ["banana", "orange"]
fruit_2 = ["cherry", "berry", "apple"]

fruit_1.extend(fruit_2)

print(fruit_1)
```

**Output**

```
['banana', 'orange', 'cherry', 'berry', 'apple']
```


<br>

------

<br>

### Unpacking lists

When we want to assign a variable to each item in the list, we can do this with a single line.


```python
names = ["Sally", "Steven", "Chuck"]
name1, name2, name3 = names

print(name1)
print(name2)
print(name3)
```

**Output**

```
Sally
Steven
Chuck
```


If we need the first two elements in a list, we assign variables to these two elements, and we can use together the rest as a group by `*variable_name`.


```python
names = ["Sally", "Steven", "Chuck", "Zoe", "Alice"]
name1, name2, *others = names

print(name1)
print(name2)
print(others)
```

**Output**

```
Sally
Steven
['Chuck', 'Zoe', 'Alice']
```


If we need the first and last item in a list, we assign variables to these two elements, and the rest can be grouped by `*variable_name`.


```python
names = ["Sally", "Steven", "Chuck", "Zoe", "Alice"]
first, *others, last = names

print(first)
print(last)
print(others)
```

**Output**

```
Sally
Alice
['Steven', 'Chuck', 'Zoe']
```


We can print items of a list without brackets :


```python
names = ["Sally", "Steven", "Chuck", "Zoe", "Alice"]
numbers = [1,2,3,4,5]

print(*names)
print(*numbers)
```

**Output**

```
Sally Steven Chuck Zoe Alice
1 2 3 4 5
```


<br>

----


<br>

### Checking Items Are Equal

If we want to check the items of a list are equal, we can use `set` type :

```python
greetings = ["hi", "hi", "hi"]
print(len(set(greetings)) == 1)

words = ["hi", "hello", "hi"]
print(len(set(words)) == 1)
```

**Output**

```
True
False
```


We can also do the same thing with `count()` and `len()`

```python
greetings = ["hi", "hi", "hi"]
print(greetings.count(greetings[0]) == len(greetings))

words = ["hi", "hello", "hi"]
print(words.count(words[0]) == len(words))
```

**Output**

```
True
False
```

<br>

----

<br>

### Getting Unique Items

We can make a list from unique items of another list by `set()` :

```python
numbers = [1,3,5,6,2,5,2,6,8,1,9,2]
uniques = list(set(numbers))

print(uniques)
```

**Output**

```
[1, 2, 3, 5, 6, 8, 9]
```


<br>

----

<br>

### Chunking List

We can create a function that chunks a list into smaller lists of a specified size.

```python
names = ["Sally", "Steven", "Chuck", "Zoe", "Alice"]
numbers = [1,3,5,6,2,5,2,6,8,1,9,2]

def chunk(list, size):
    return [list[i:i+size] for i in range(0,len(list), size)]

print(chunk(names, 2))
print(chunk(numbers, 5))
```

**Output**

```
[['Sally', 'Steven'], ['Chuck', 'Zoe'], ['Alice']]
[[1, 3, 5, 6, 2], [5, 2, 6, 8, 1], [9, 2]]
```


<br>

----

<br>

### Getting Most Frequent

We can find the most frequent element that appears in a list.

```python
numbers = [1,3,5,6,2,5,2,6,8,1,9,2]
names = ["Chuck", "Alice", "Zoe", "Amber", "Zoe", "Alice", "Steven", "Alice"]

print(max(numbers, key = numbers.count))
print(max(names, key = names.count))
```

**Output**

```
2
Alice
```


<br>

---

<br>


### `list()` : Making List

We can make list by `list()` :

```python
fruits = list(("apple", "banana", "cherry"))

print(type(fruits))
print(fruits)
```

**Output**

```
<class 'list'>
['apple', 'banana', 'cherry']
```

We can make a list from a string :

```python
my_string = "hello world"
letters = list(my_string)
words = my_string.split()

print(letters)
print(words)
```

**Output**

```
['h', 'e', 'l', 'l', 'o', ' ', 'w', 'o', 'r', 'l', 'd']
['hello', 'world']
```



We can use the `range()` function to make a numeric list :


```python
nums_1 = list(range(10))
nums_2 = list(range(1,10))
nums_3 = list(range(1,10,2))

print(nums_1)
print(nums_2)
print(nums_3)
```

**Output**

```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 3, 5, 7, 9]
```


We can also make another Python type to list :

```python
my_tuple = ("apple", "banana", "cherry")
fruits = list(my_tuple)

print(type(fruits))
print(fruits)
```

**Output**

```
<class 'list'>
['apple', 'banana', 'cherry']
```

Another way to use `list()` is copying a list :


```python
fruits = ["apple", "banana", "cherry"]
new_list = list(fruits)

print(new_list)
```

**Output**

```
['apple', 'banana', 'cherry']
```


<br>

----


<br>

### `for` : Looping Through a List

We can process items in a list with the `for` loop.

```python
names = ["Sally", "Barry", "Chuck", "Steven"]

for name in names:
	print(name)
```

**Output**

```
Sally
Barry
Chuck
Steven
```


```python
verbs = ["walk", "edit", "work", "talk"]

for verb in verbs:
	print(verb + "ed")
```

**Output**

```
walked
edited
worked
talked
```

<br>

--------


<br>

### `enumerate()` : Numerating Items

We can use the `enumerate` method if we want a number to be given to the items in the list. This also gives us the `index` numbers of the items.


```python
names = ["Sally", "Barry", "Chuck", "Steven"]

num_names = enumerate(names)
print(num_names)

for name in num_names:
	print(name)

for name in enumerate(names):
	print(name[0], name[1])

for num, name in enumerate(names):
	print(num, name)
```

**Output**

```
<enumerate object at 0x10d2a3eb0>

(0, 'Sally')
(1, 'Barry')
(2, 'Chuck')
(3, 'Steven')

0 Sally
1 Barry
2 Chuck
3 Steven

0 Sally
1 Barry
2 Chuck
3 Steven
```



<br>

--------

<br>

### `in` : Checking Item

To determine if a specified item is present in a list use the `in` keyword:


```python
names = ["Sally", "Barry", "Chuck", "Steven"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]

print("Chuck" in names)
print("barry" in names)
print(2 in numbers)
print(2 in lists)
print([1, 2] in lists)
```

**Output**

```
True
False
True
False
True
```



<br>

--------


<br>

### `len()` : Getting List Length

To determine how many items a list has, use the `len()` method:


```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]


print(len(letters))
print(len(fruits))
print(len(lists))
```

**Output**

```
5
3
3
```



<br>

--------

<br>

### `zip()` : Pairing List

The `zip()` function returns a zip object, which is an iterator of tuples where the first item in each passed iterator is paired together, and then the second item in each passed iterator are paired together etc.

If the passed iterators have different lengths, the iterator with the least items decides the length of the new iterator.


```python
animals = ["lion", "cat", "dog", "couger"]
names = ["Simba", "Branson", "Fred", "Messi"]

print(zip(animals, names))
print(list(zip(animals, names)))
```

**Output**

```
<zip object at 0x1035cdf50>
[('lion', 'Simba'), ('cat', 'Branson'), ('dog', 'Fred'), ('couger', 'Messi')]
```


Pairing can also be used to transpose a 2D array.


```python
lists = [[1,2], ["lion", "cat"], ["Simba", "Branson"]]
paired = zip(*lists)

print(paired)
print(list(paired))
```

**Output**

```
<zip object at 0x10f28afa0>
[(1, 'lion', 'Simba'), (2, 'cat', 'Branson')]
```


We can make a dictionary from two lists :


```python
names = ["Chuck", "Steven", "Alice"]
ages = [46, 25, 3]

my_dict = dict(zip(names, ages))

print(my_dict)
```

**Output**

```
{'Chuck': 46, 'Steven': 25, 'Alice': 3}
```


<br>

----

<br>

### `.append()` : Adding New Item


To add an item to the end of the list, use the `append()` method:

```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

fruits.append("berry")
lists.append(["another", "little", "list", 3])

print(fruits)
print(lists)
```

**Output**

```
['apple', 'banana', 'cherry', 'berry']
[['a', 'b', 'c'], [1, 2], 35, ['another', 'little', 'list', 3]]
```


We can also add another list to a list as an item :



```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

lists.append(fruits)

print(lists)
```

**Output**

```
[['a', 'b', 'c'], [1, 2], 35, ['apple', 'banana', 'cherry']]
```



<br>

--------

<br>

### `.copy()` : Copying List

We cannot copy a list simply by typing `list2 = list1`, because: `list2` will only be a reference to `list1`, and changes made in `list1` will automatically also be made in `list2`.

There are ways to make a copy, one way is to use the built-in List method `copy()`.


```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

fru = fruits.copy()
lst = lists.copy()

print(fru)
print(lst)
```

**Output**

```
['apple', 'banana', 'cherry']
[['a', 'b', 'c'], [1, 2], 35]
```


<br>

--------

<br>

### `.count()` : Counting Item

The `count()` method returns the number of elements with the specified value.


```python
names = ["Chuck", "Alice", "Zoe", "Amber", "Zoe", "Alice", "Steven", "Alice"]
points = [1, 4, 2, 9, 7, 8, 9, 3, 1]

print(names.count("Alice"))
print(names.count("Zoe"))
print(points.count(9))
```


**Output**

```
3
2
2
```


We can also count nested lists :

```python
families = [[1,2], [1,3], [2,5], [2,9], [1,3], [3,6], [1,3]]

print(families.count([1,3]))
```


**Output**

```
3
```

<br>

----

<br>


### `.extend()` : Concatenating Lists

To add elements from one list to another list we can use `extend()` method :


```python
fruit_1 = ["banana", "orange"]
fruit_2 = ["cherry", "berry", "apple"]

fruit_1.extend(fruit_2)

print(fruit_1)
```

**Output**

```
['banana', 'orange', 'cherry', 'berry', 'apple']
```


We can also add another iterable such as set, tuple etc. :


```python
names = ["Chuck", "Henry"]
students = ("Alice", "Steven", "Becky")
names.extend(students)

print(names)
```

**Output**

```
['Chuck', 'Henry', 'Alice', 'Steven', 'Becky']
```

<br>


-----

<br>


### `.index()` : Finding Item

The `index()` method returns the position at the first occurrence of the specified value.


```python
letters = ["a", "b", "c", "d", "e"]
fruits = ["apple", "banana", "cherry"]
numbers = [1, 2, 3, 4, 5]
lists = [["a", "b", "c"], [1, 2], 35]


print(letters.index("d"))
print(fruits.index("cherry"))
print(numbers.index(4))
print(lists.index([1,2]))
```

**Output**

```
3
2
3
1
```


<br>

----


<br>

### `.insert()` : Adding New Item

To add an item at the specified index, use the `insert()` method:


```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

fruits.insert(1, "berry")
lists.insert(0, ["new", "list"])

print(fruits)
print(lists)
```

**Output**

```
['apple', 'berry', 'banana', 'cherry']
[['new', 'list'], ['a', 'b', 'c'], [1, 2], 35]
```


<br>

--------


<br>


### `.join()` : Making String

We can turn a list of strings into a single string with each element from the list separated by given seperator.


```python
words = ["this", "words", "can", "be", "a", "sentence", "together"]
numbers = ["1","2","3","4","5"]
hobby = ["reading", "swimming", "playing guitar"]

print(" ".join(words))
print("...".join(numbers))
print("My hobbies are", ", ".join(hobby))
```


**Output**

```
this words can be a sentence together
1...2...3...4...5
My hobbies are reading, swimming, playing guitar
```

<br>

----

<br>

### `.pop()` : Removing An Item

The `pop()` method removes the specified index or the last item if index is not specified :


```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

fruits.pop(1)
lists.pop()


print(fruits)
print(lists)
```

**Output**

```
['apple', 'cherry']
[['a', 'b', 'c'], [1, 2]]
```


<br>

-----

<br>

### `.remove()` : Removing An Item

The `remove()` method removes the specified item:

```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

fruits.remove("banana")
lists.remove(["a", "b", "c"])

print(fruits)
print(lists)
```

**Output**

```
['apple', 'cherry']
[[1, 2], 35]
```


<br>

--------

<br>

### `del` : Removing An Item

The `del` keyword removes the specified index:


```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

del fruits[2]
del lists[1]

print(fruits)
print(lists)
```

**Output**

```
['apple', 'banana']
[['a', 'b', 'c'], 35]
```


The `del` keyword can also delete the list completely:


```python
lists = [["a", "b", "c"], [1, 2], 35]
del lists

print(lists)
```

**Output**

```
Traceback (most recent call last):
  File "lists.py", line 3, in <module>
    print(lists)
NameError: name 'lists' is not defined
```


<br>

----


<br>

### `.clear()` : Emptying List

The `clear()` method removes all the elements from a list.


```python
fruits = ["apple", "banana", "cherry"]
lists = [["a", "b", "c"], [1, 2], 35]

fruits.clear()
lists.clear()

print(fruits)
print(lists)

```

**Output**

```
[]
[]
```


<br>

----

<br>

### `.reverse()` : Reversing List


The `reverse()` method reverses the sorting order of the elements.


```python
numbers = [1,2,3,4,5]
numbers.reverse()

print(numbers)
```

**Output**

```
[5, 4, 3, 2, 1]
```


<br>

---

<br>

### `reversed()` : Reversing List

The `reversed()` function returns a reversed iterator object.


```python
numbers = [1,2,3,4,5]
reversed = reversed(numbers)

print(reversed)
print(list(reversed))
```

**Output**

```
<list_reverseiterator object at 0x1066a80d0>
[5, 4, 3, 2, 1]
```


<br>

---

<br>


### `.sort()` : Sorting List

The `sort()` method sorts the list ascending by default.


```python
names = ["Sally", "Alice", "Chuck", "Henry"]
names.sort()

print(names)
```

**Output**

```
['Alice', 'Chuck', 'Henry', 'Sally']
```


We can sorting reverse with `reverse=True` parameter :


```python
names = ["Sally", "Alice", "Chuck", "Henry"]
names.sort(reverse=True)

print(names)
```

**Output**

```
['Sally', 'Henry', 'Chuck', 'Alice']
```



We can also sorting the list by a created function. For example we can sort a list by `lambda` and negative third character of items :


```python
names = ["Sally", "Alice", "Chuck", "Henry"]
names.sort(key= lambda x: x[-3])

print(names)
```

**Output**

```
['Alice', 'Sally', 'Henry', 'Chuck']
```

For example we can sort a list by length of items :

```python
def foo(item):
	return len(item)


brands = ["BMW", "Toyota", "Pringles"]
brands.sort(key=foo)
print(brands)

brands.sort(reverse=True)
print(brands)
```


**Output**

```
['BMW', 'Toyota', 'Pringles']
['Toyota', 'Pringles', 'BMW']
```


<br>

----
