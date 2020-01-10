# Ultimate Python Snippets
## Python Fundamentals
### Strings

<br>

#### Summary

* String Literals
* String Concatenation
* `len()` : Finding Length
* `in` : Checking a Character
* `index` : Getting a Character
* `.capitalize()` : Converting UpperCase
* `.casefold()` : Converting LowerCase
* `.center()` : Centering String
* `.count()` : Counting a Character
* `.endswith()` : Checking Ending Characters
* `.encode()` : Encoding String
* `.expandtabs()` : Setting the Tab Size
* `.find()` : Finding Characters
* `.format()` : Formatting String
* `.isalnum()` : Checking Alphanumeric Characters
* `.isalpha()` : Checking Alphabet Characters
* `.isdecimal()` : Checking Decimal Characters
* `.isdigit()` : Checking Digit Characters
* `.isidentifier()` : Checking Valid Identifier
* `.islower()` : Checking LowerCase
* `.isnumeric()` : Checking Numeric Characters
* `.isprintable()` : Checking Characters Printable
* `.isspace()` : Checking Whitespace String
* `.istitle()` : Checking Title Text
* `.isupper()` : Checking UpperCase
* `.join()` : Converting Iterable to String
* `.ljust()` : Making Left Align
* `.lower()` : Converting LowerCase
* `.lstrip()` : Deleting Left Whitespaces
* `.partition()` : Spliting into Tuple
* `.replace()` : Replacing a Character
* `.rfind()` : Finding Character Index
* `.rindex()` : Finding Character Index
* `.rjust()` : Making Right Align
* `.rpartition()` : Spliting into Tuple
* `.rsplit()` : Spliting into List
* `.rstrip()` : Deleting Right Whitespaces
* `.split()` : Spliting into List
* `.splitlines()` : Spliting into List
* `.startswith()` : Checking Starting Characters
* `.strip()` : Deleting Whitespaces
* `.swapcase()` : Swapping Letter Cases
* `.title()` : Converting Text to Title
* `.upper()` : Converting UpperCase
* `.zfill()` : Adding Zero
* Checking Anagram
* Checking Palindrome
* Escape Character
* Finding Unique Characters
* Reversing a String
* String Comparison


<br>

-----

<br>

### String Literals

String literals in python are surrounded by either single quotation marks, or double quotation marks.

```python
my_string = "hello"
print(my_string)

my_string = 'hello'
print(my_string)
```

**Output**

```
hello
hello
```

We can assign a multiline string to a variable by using three quotes:


```python
my_string = """Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua."""

print(my_string)
```

**Output**

```
Lorem ipsum dolor sit amet,
consectetur adipiscing elit,
sed do eiusmod tempor incididunt
ut labore et dolore magna aliqua.
```

<br>

--------

<br>

### String Concatenation

To concatenate, or combine, two strings we can use the + operator.


```python
a_string = "Hello"
b_string = "World"

print(a_string + b_string)
print(a_string + " " + b_string)
```

**Output**

```
HelloWorld
Hello World
```

Also we can use `,` for formatting `print()` function but remember, it's not a concatenation.


```python
a_string = "Hello"
b_string = "World"

print(a_string , b_string)
```

**Output**

```
Hello World
```


We cannot combine strings and numbers

```python
name = "Hello. My name is Jack and I'm "
age = 27

print(name + age)
```

**Output**

```
Traceback (most recent call last):
  File "strings.py", line 56, in <module>
    print(name + age)
TypeError: can only concatenate str (not "int") to str
```


However we can fix this with `str()` function

```python
name = "Hello. My name is Jack and I'm "
age = 27
dot = "."

print(name + str(age) + dot)
```

**Output**

```
Hello. My name is Jack and I'm 27.
```


<br>

-----

<br>

### `len()` : Finding Length

We use the `len()` function to learn the length of a string.

```python
my_string = "Here is a string."
print(len(my_string))
```

**Output**

```
17
```

<br>

---

<br>

### `in` : Checking a Character

The `in` method is used to check for a character or character part in the string.

```python
sentence = "Here is a string."
print("str" in sentence)
print("hey" in sentence)
```

**Output**

```
True
False
```

<br>

----

<br>

### `index` : Getting a Character

We use the `index` function to access a character of a string.

```python
my_string = "Here is a string."
print(my_string[0])
print(my_string[-2])
print(my_string[8])
print(my_string[5:9])
```

**Output**

```
H
g
a
is a
```

<br>


----

<br>

### `.capitalize()` : Converting UpperCase

The `capitalize()` method returns a string where the first character is upper case.


```python
my_string = "here is a string."
print(my_string.capitalize())
```

**Output**

```
Here is a string.
```


<br>

-----

<br>

### `.casefold()` : Converting LowerCase

The `casefold()` method returns a string where all the characters are lower case.

This method is similar to the `lower()` method, but the `casefold()` method is stronger, more aggressive, meaning that it will convert more characters into lower case, and will find more matches when comparing two strings and both are converted using the `casefold()` method.


```python
my_string = "HERE IS A STRING."
print(my_string.casefold())
```

**Output**

```
here is a string.
```


<br>

----

<br>

### `.center()` : Centering String

We can center align the string with `.center()` method. Also we can define a filling character.


```python
my_string = "banana"

print(my_string.center(20))
print(my_string.center(20, "-"))
```

**Output**

```
       banana
-------banana-------
```

<br>

----

<br>

### `.count()` Method : Counting a Character

We can count a character with using `.count()` method.

```python
my_string = "Here is a string."
print(my_string.count("i"))
```

**Output**

```
2
```


<br>

----

<br>

### `.endswith()` Method : Checking Ending Characters

We can check the string is end with a character(s) or not.

```python
my_string = "Here is a string."

print(my_string.endswith("."))
print(my_string.endswith("ng."))
print(my_string.endswith("ng"))
```

**Output**

```
True
True
False
```

<br>

----


<br>


### `.encode()` Method : Encoding String

The `encode()` method encodes the string, using the specified encoding. If no encoding is specified, UTF-8 will be used.


```python
my_string = "My name is Ståle"

print(my_string.encode())
print(my_string.encode(encoding="ascii",errors="backslashreplace"))
print(my_string.encode(encoding="ascii",errors="ignore"))
print(my_string.encode(encoding="ascii",errors="namereplace"))
print(my_string.encode(encoding="ascii",errors="replace"))
print(my_string.encode(encoding="ascii",errors="xmlcharrefreplace"))
print(my_string.encode(encoding="ascii",errors="strict"))
```

**Output**

```
b'My name is St\xc3\xa5le'
b'My name is St\\xe5le'
b'My name is Stle'
b'My name is St\\N{LATIN SMALL LETTER A WITH RING ABOVE}le'
b'My name is St?le'
b'My name is St&#229;le'
Traceback (most recent call last):
  File "Strings.py", line 54, in <module>
    print(my_string.encode(encoding="ascii",errors="strict"))
UnicodeEncodeError: 'ascii' codec can't encode character '\xe5' in position 13: ordinal not in range(128)
```

<br>

-----

<br>

### `.expandtabs()` Method : Setting the Tab Size

The `expandtabs()` method sets the tab size to the specified number of whitespaces.

```python
my_string = "H\te\tl\tl\to"

print(my_string.expandtabs())
print(my_string.expandtabs(2))
print(my_string.expandtabs(5))
print(my_string.expandtabs(10))

```

**Output**

```
H       e       l       l       o
H e l l o
H    e    l    l    o
H         e         l         l         o
```

<br>

----

<br>

### `.find()` Method : Finding Characters

The `.find()` method is used to find a specific character or group of characters in the string. The result gives the index number of the searched part.

```python
my_string = "Here is a string."

print(my_string.find("a"))
print(my_string[8])
```

**Output**

```
5
```

<br>

-----

<br>

### `.format()` Method : Formatting String

It is possible to shape a string with the format method.

```python
first = "Steven"
last = "Jr."
job = "developer"
city = "İstanbul"

print(f"{first} {last} works as a {job} in {city}.")
print("{} {} works as a {} in {}.".format(first, last, job, city))
print("{0} {1} works as a {2} in {3}. Say hello to {0}!".format(first, last, job, city))
```

**Output**

```
Steven Jr. works as a developer in İstanbul.
Steven Jr. works as a developer in İstanbul.
Steven Jr. works as a developer in İstanbul. Say hello to Steven!
```

It is also possible to define that a value should be padded to a specific length.


```python
first = "Steven"
last = "Jr."
job = "developer"
city = "İstanbul"

print("{:>10} {}".format(first, last))
print("{:10} {}".format(first, last))
print("{:_>10} {}".format(first, last))
print("{:_<10} {}".format(first, last))
print("{:_^10} {}".format(first, last))
```

**Output**

```
    Steven Jr.
Steven     Jr.
____Steven Jr.
Steven____ Jr
__Steven__ Jr.
```

It is also possible to truncate overly long values to a specific number of characters.


```python
job = "developer"
city = "İstanbul"

print("{:.3} from {}".format(job, city))
```

**Output**

```
dev from İstanbul
```


<br>


-----

<br>

### `.isalnum()` Method : Checking Alphanumeric Characters

The `isalnum()` method returns True if all the characters are alphanumeric, meaning alphabet letter (a-z) and numbers (0-9).


```python
my_string = "Age15"
print(my_string.isalnum())

my_string = "Age 15"
print(my_string.isalnum())
```


**Output**


```
True
False
```

<br>

----

<br>

### `.isalpha()` Method : Checking Alphabet Characters

The `isalpha()` method returns True if all the characters are alphabet letters (a-z).


```python
my_string = "AgeX"
print(my_string.isalpha())

my_string = "Age 15"
print(my_string.isalpha())
```


**Output**


```
True
False
```

<br>

-----

<br>

### `.isdecimal()` Method : Checking Decimal Characters

The `isdecimal()` method returns True if all the characters are decimals (0-9).

```python
my_string = "Age15"
print(my_string.isdecimal())

my_string = "3615"
print(my_string.isdecimal())
```


**Output**


```
False
True
```

<br>

---

<br>

### `.isdigit()` : Checking Digit Characters

The `isdigit()` method returns `True` if all the characters are digits, otherwise `False`.


```python
my_string = "46580"
print(my_string.isdigit())

my_string = "34Company"
print(my_string.isdigit())
```

**Output**

```
True
False
```

<br>

----

<br>

### `.isidentifier()` : Checking Valid Identifier

A string is considered a valid identifier if it only contains alphanumeric letters (a-z) and (0-9), or underscores `(_)`. A valid identifier cannot start with a number, or contain any spaces. The `isidentifier()` method returns `True` if the string is a valid identifier, otherwise `False`.


```python
my_string = "MyFolder"
print(my_string.isidentifier())

my_string = "My_Folder"
print(my_string.isidentifier())

my_string = "MyFolder01"
print(my_string.isidentifier())

my_string = "Folder_01"
print(my_string.isidentifier())

my_string = "01Folder"
print(my_string.isidentifier())

my_string = "My Folder"
print(my_string.isidentifier())
```

**Output**

```
True
True
True
True
False
False
```


<br>

----

<br>

### `.islower()` : Checking LowerCase

The `islower()` method returns `True` if all the characters are in lower case, otherwise `False`. Numbers, symbols and spaces are not checked, only alphabet characters.


```python
my_string = "Here is a string."
print(my_string.islower())

my_string = "here is a string."
print(my_string.islower())

my_string = "mynameisEarl"
print(my_string.islower())

my_string = "my age 13"
print(my_string.islower())
```

**Output**

```
False
True
False
True
```


<br>

----

<br>

### `.isnumeric()` : Checking Numeric Characters

The `isnumeric()` method returns `True` if all the characters are numeric (0-9), otherwise `False`.


```python
my_string = "3974"
print(my_string.isnumeric())

my_string = "folder3974"
print(my_string.isnumeric())

my_string = "folder 3974"
print(my_string.isnumeric())
```

**Output**

```
True
False
False
```


<br>

----

<br>


### `.isprintable()` : Checking Characters Printable

The `isprintable()` method returns `True` if all the characters are printable, otherwise `False`. Example of none printable character can be carriage return and line feed.


```python
my_string = "Hello! Are you #1?"
print(my_string.isprintable())


my_string = "Hello!\nAre you #1?"
print(my_string.isprintable())
```

**Output**

```
True
False
```


<br>

-----

<br>

### `.isspace()` : Checking Whitespace String

The `isspace()` method returns `True` if all the characters in a string are whitespaces, otherwise `False`.


```python
my_string = "     "
print(my_string.isspace())


my_string = "   a   "
print(my_string.isspace())
```

**Output**

```
True
False
```


<br>

-----

<br>

### `.istitle()` : Checking Title Text

The `istitle()` method returns `True` if all words in a text start with a upper case letter, AND the rest of the word are lower case letters, otherwise `False`. Symbols and numbers are ignored.

```python
my_string = "HELLO WORLD!"
print(my_string.istitle())

my_string = "hello world!"
print(my_string.istitle())

my_string = "Hello world!"
print(my_string.istitle())

my_string = "Hello World!"
print(my_string.istitle())

my_string = "01 Article"
print(my_string.istitle())
```

**Output**

```
False
False
False
True
True
```


<br>

------

<br>

### `.isupper()` : Checking UpperCase

The `isupper()` method returns `True` if all the characters are in upper case, otherwise `False`. Numbers, symbols and spaces are not checked, only alphabet characters.


```python
my_string = "HELLO WORLD!"
print(my_string.isupper())

my_string = "hello world!"
print(my_string.isupper())

my_string = "Hello 123!"
print(my_string.isupper())
```

**Output**

```
True
False
False
```

<br>

----

<br>

### `.join()` : Converting Iterable to String

The `join()` method takes all items in an iterable and joins them into one string. A string must be specified as the separator.


```python
my_list = ["My", "name", "is", "Earl"]
print(" ".join(my_list))

my_list = ["1", "2", "3", "4", "5"]
print("".join(my_list))

my_dict = {"name": "John", "lastname": "Bright"}
print(" ".join(my_dict))
print(" and ".join(my_dict))
```

**Output**

```
My name is Earl
12345
name lastname
name and lastname
```


<br>

----

<br>

### `.ljust()` : Making Left Align

The `ljust()` method will left align the string, using a specified character (space is default) as the fill character.


```python
my_string = "banana"
print(my_string.ljust(20))
print(my_string.ljust(20, "-"))
```

**Output**

```
banana
banana--------------
```

<br>

-----

<br>

### `.lower()` : Converting LowerCase

The `lower()` method returns a string where all characters are lower case. Symbols and Numbers are ignored.


```python
my_string = "Hello World"
print(my_string.lower())

my_string = "HELLO WORLD"
print(my_string.lower())


my_string = "hello WORLD"
print(my_string.lower())
```

**Output**

```
hello world
hello world
hello world
```



<br>

----

<br>

### `.lstrip()` : Deleting Left Whitespaces



```python
my_string = "     banana     "
print(my_string.lstrip())

my_string = "--!--!----!!!--banana"
print(my_string.lstrip("-!"))

my_string = "--na!an-s-na--banana"
print(my_string.lstrip("-!nas"))
```

**Output**

```
banana
banana
banana
```


<br>

-----

<br>

### `.partition()` : Spliting to Tuple

The `partition()` method searches for a specified string, and splits the string into a tuple containing three elements. The first element contains the part before the specified string. The second element contains the specified string. The third element contains the part after the string.


```python
my_string = "Hey honey! Do you want some honey?"
print(my_string.partition("honey"))


my_string = "Some honey for my honey cup"
print(my_string.partition("honey"))
```

**Output**

```
('Hey ', 'honey', '! Do you want some honey?')
('Some ', 'honey', ' for my honey cup')
```



<br>

----

<br>

### `.replace()` Method : Replacing a Character

The `.replace()` method is used to find a character in the string and replace it with another character.


```python
my_string = "Here is a string."
print(my_string.replace("i", "u"))

my_string = "one one was a race horse, two two was one too."
print(my_string.replace("one", "three"))


my_string = "one one was a race horse, two two was one too."
print(my_string.replace("one", "three", 2))
```

**Output**

```
Here us a strung.
three three was a race horse, two two was three too.
three three was a race horse, two two was one too.
```

<br>

----

<br>

### `.rfind()` : Finding Character Index

The `rfind()` method finds the last occurrence of the specified value. The method is almost the same as the `rindex()` method but `rfind()` method returns `-1` if the value is not found don't get an error.

We can also define finding the letter only search between positions.


```python
my_string = "one one was a race horse, two two was one too."
print(my_string.rfind("one"))
print(my_string.rfind("four"))
print(my_string.rfind("e", 5, 10))
```

**Output**

```
38
-1
6
```

<br>

-----

<br>

### `.rindex()` : Finding Character Index

The `rindex()` method finds the last occurrence of the specified value and raises an exception if the value is not found. We can also define finding the letter only search between positions.


```python
my_string = "one one was a race horse, two two was one too."
print(my_string.rindex("one"))
print(my_string.rindex("e", 5, 10))
```

**Output**

```
38
6
```


<br>

-----

<br>


### `.rjust()` : Making Right Align

The `rjust()` method will right align the string, using a specified character (space is default) as the fill character.


```python
my_string = "banana"
print(my_string.rjust(20))
print(my_string.rjust(20, "-"))
```

**Output**

```
              banana
--------------banana
```


<br>

----

<br>


### `.rpartition()` : Spliting to Tuple

The `rpartition()` method searches for the last occurrence of a specified string, and splits the string into a tuple containing three elements. The first element contains the part before the specified string. The second element contains the specified string. The third element contains the part after the string.


```python
my_string = "Hey honey! Do you want some honey?"
print(my_string.rpartition("honey"))


my_string = "Some honey for my honey cup"
print(my_string.rpartition("honey"))
```

**Output**

```
('Hey honey! Do you want some ', 'honey', '?')
('Some honey for my ', 'honey', ' cup')
```


<br>

---

<br>

### `.rsplit()` : Spliting into List

The `rsplit()` method splits a string into a list, starting from the right. If no "max" is specified, this method will return the same as the `split()` method.


```python
my_string = "one one was a race horse, two two was one too."
print(my_string.rsplit("one"))
print(my_string.rsplit("one", 2))
```

**Output**

```
['', ' ', ' was a race horse, two two was ', ' too.']
['one ', ' was a race horse, two two was ', ' too.']
```


<br>

----

<br>

### `.rstrip()` : Deleting Right Whitespaces

The `rstrip()` method removes any trailing characters (characters at the end a string), space is the default trailing character to remove.


```python
my_string = "     banana     "
print(my_string.rstrip())

my_string = "     banana,,e!--,,...!"
print(my_string.rstrip(",e!-."))

my_string = "banana,,e!--,,...!"
print(my_string.rstrip(",e!-."))
```

**Output**

```
     banana
     banana
banana
```



<br>

----

<br>

### `.split()` : Spliting into List


```python
my_string = "Hey honey! Do you want some honey?"
print(my_string.split("honey"))

my_string = "one,two,three,four,five"
print(my_string.split(","))

my_string = "one one was a race horse two two was one too"
print(my_string.split())

my_string = "one one was a race horse two two was one too"
print(my_string.split(" ", 2))
```

**Output**

```
['Hey ', '! Do you want some ', '?']
['one', 'two', 'three', 'four', 'five']
['one', 'one', 'was', 'a', 'race', 'horse', 'two', 'two', 'was', 'one', 'too']
['one', 'one', 'was a race horse two two was one too']
```


<br>

----

<br>

### `.splitlines()` : Spliting into List

The `splitlines()` method splits a string into a list. The splitting is done at line breaks.


```python
my_string = "Thank you for the music\nWelcome to the jungle"
print(my_string.splitlines())
print(my_string.splitlines(True))

my_string = """Thank you for the music
Welcome to the jungle"""
print(my_string.splitlines())
print(my_string.splitlines(True))
```

**Output**

```
['Thank you for the music', 'Welcome to the jungle']
['Thank you for the music\n', 'Welcome to the jungle']
['Thank you for the music', 'Welcome to the jungle']
['Thank you for the music\n', 'Welcome to the jungle']
```

<br>

----

<br>

### `.startswith()` Method : Checking Starting Characters

We can check the string is start with a character(s) or not.

```python
my_string = "Here is a string."

print(my_string.startswith("H"))
print(my_string.startswith("Her"))
print(my_string.startswith("h"))
print(my_string.startswith("is"))
```

**Output**

```
True
True
False
False
```

<br>

----

<br>

### `.strip()` : Deleting Whitespaces

The `strip()` method removes any leading (spaces at the beginning) and trailing (spaces at the end) characters (space is the default leading character to remove)


```python
my_string = "     banana     "
print(my_string.strip())

my_string = "..?e--...banana...--??ee--"
print(my_string.strip(".?-e"))
```

**Output**

```
banana
banana
```


<br>

----

<br>

### `.swapcase()` : Swapping Letter Cases

The `swapcase()` method returns a string where all the upper case letters are lower case and vice versa.


```python
my_string = "Hello World"
print(my_string.swapcase())

my_string = "HELLO world"
print(my_string.swapcase())

my_string = "HeLLo WoRLd"
print(my_string.swapcase())
```

**Output**

```
hELLO wORLD
hello WORLD
hEllO wOrlD
```


<br>

----

<br>

### `.title()` : Converting Text to Title

The `title()` method returns a string where the first character in every word is upper case. Like a header, or a title. If the word contains a number or a symbol, the first letter after that will be converted to upper case.


```python
my_string = "travelling around"
print(my_string.title())

my_string = "01 travelling around"
print(my_string.title())

my_string = "Travelling around"
print(my_string.title())
```

**Output**

```
Travelling Around
01 Travelling Around
Travelling Around
```


<br>

----

<br>

### `.upper()` : Converting UpperCase

The `upper()` method returns a string where all characters are in upper case. Symbols and Numbers are ignored.


```python
my_string = "travelling around"
print(my_string.upper())

my_string = "01 travelling around"
print(my_string.upper())

my_string = "Travelling around"
print(my_string.upper())
```

**Output**

```
TRAVELLING AROUND
01 TRAVELLING AROUND
TRAVELLING AROUND
```


<br>

-----

<br>

### `.zfill()` : Adding Zero


```python
my_string = "50"
print(my_string.zfill(10))

my_string = "10.000"
print(my_string.zfill(10))

my_string = "hey you"
print(my_string.zfill(10))

my_string = "welcome to the jungle"
print(my_string.zfill(10))
```

**Output**

```
0000000050
000010.000
000hey you
welcome to the jungle
```


<br>

----

<br>

### Checking Anagram

An anagram is a word or phrase formed by rearranging the letters of a different word or phrase. We can check two strings are anagram or not by `Counter`

```python
from collections import Counter

str_1, str_2, str_3 = "acbde", "abced", "abcda"
cnt_1, cnt_2, cnt_3 = Counter(str_1), Counter(str_2), Counter(str_3)

if cnt_1 == cnt_2:
    print("1 and 2 anagram")
if cnt_1 == cnt_3:
    print("1 and 2 anagram")
if cnt_2 == cnt_3:
    print("2 and 3 anagram")
```

**Output**

```
1 and 2 anagram
```

<br>

----

<br>

### Checking Palindrome

We can check a string is a palindrome or not by reversing the string.

```python
my_string = "abcba"

if my_string == my_string[::-1]:
    print("palindrome")
else:
    print("not polindrome")
```

**Output**

```
palindrome
```


<br>

----


<br>


### Escape Character

Quotation marks in a string can be confusing for Python, and therefore give an error.

```python
# Problem
my_string = 'Here is a string and it's good!'
print(my_string)
```

**Output**

```
File "Strings.py", line 39
	my_string = 'Here is a string and it's good!'
																			 ^
SyntaxError: invalid syntax
```

To avoid this, we use the `\` sign before the quotation mark called the escape character.

```python
my_string = 'Here is a string and it\'s good!'
print(my_string)
```

**Output**

```
Here is a string and it's good!
```


The escape character is also used to move to a new line by `\n`.

```python
multiline = 'Here is a string. \nLearn all about it!'
print(multiline)
```

**Output**

```
Here is a string.
Learn all about it!
```

Other escape characters used in Python:


|Code |	Result|
|--|--|
| `\'`	| Single Quote	|
| `\\`	| Backslash	|
| `\n`	| New Line |
| `\r`	| Carriage Return	|
| `\t`	| Tab	|
| `\b`	| Backspace	|
| `\f`	| Form Feed	|
| `\ooo`	| Octal value	|
| `\xhh`	| Hex value |


<br>


---

<br>

### Finding Unique Characters

We can find the unique elements in a string by using sets. First we need to convert string to a set, then we combine the characters in set by `.join()` method.

```python
my_string = "aavvccccddddeee"
print(my_string)

unique_chars = set(my_string)
print(unique_chars)

my_string_unique = "".join(unique_chars)
print(my_string_unique)
```

**Output**

```
aavvccccddddeee
{'a', 'v', 'e', 'c', 'd'}
avecd
```


<br>

----

<br>

### Reversing a String

The slicing method can use for reversing a string.

```python
my_string = "Here is a string."
print(my_string[::-1])
```


**Output**

```
.gnirts a si ereH
```

<br>


----

<br>

### String Comparison

The comparison operators work on strings but this comparison is slightly different from the real world. Alphabetic order of letters is important in the comparison between words. Capital letters are always lower than lowercase letters.

A < a

z < a

Chuck < Glenn

Glenn < chuck


```python
str_1 = "banana"
str_2 = "Banana"
str_3 = "Cherry"
str_4 = "cherry"

print(str_1 > str_2)
print(str_3 > str_4)
print(str_1 > str_3)
print(str_2 > str_4)
print(str_1 > str_4)
```

**Output**

```
True
False
True
False
False
```

<br>

----
 
