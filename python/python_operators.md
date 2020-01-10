# Ultimate Python Snippets
## Python Fundamentals
### Operators

<br>



### Python Operator Types

Operators are used to perform operations on variables and values.

Python divides the operators in the following groups:

* Arithmetic operators
* Assignment operators
* Comparison operators
* Logical operators
* Identity operators
* Membership operators
* Bitwise operators


<br>

---

<br>

### Arithmetic Operators

Arithmetic operators are used with numeric values to perform common mathematical operations:


<br>

| Operator	| Name	| Example	|
|--|--|--|
| `+`	 | Addition	| `x + y`	|
| `-`	| Subtraction	| `x - y`	|
| `*`	| Multiplication	| `x * y` |
| `/`	| Division	| `x / y`	|
| `%`	| Modulus	| `x % y`	|
| `**`	| Exponentiation	| `x ** y` |
| `//`	| Floor division	| `x // y` |

<br>

```python
x = 10
y = 3

print("x + y =", (x+y))
print("x - y =", (x-y))
print("x * y =", (x*y))
print("x / y =", (x/y))
print("x % y =", (x%y))
print("x ** y =", (x**y))
print("x // y =", (x//y))
```

**Output**

```
x + y = 13
x - y = 7
x * y = 30
x / y = 3.3333333333333335
x % y = 1
x ** y = 1000
x // y = 3
```

<br>

---

<br>

### Assignment Operators

Assignment operators are used to assign values to variables:


<br>

| Operator	| Example	| Same As	|
|--|--|--|
| `=`	| `x = 5`	| `x = 5`	|
| `+=`	| `x += 3`	| `x = x + 3`	|
| `-=`	| `x -= 3`	| `x = x - 3`	|
| `*=`	| `x *= 3`	| `x = x * 3`	|
| `/=`	| `x /= 3`	| `x = x / 3`	|
| `%=`	| `x %= 3`	| `x = x % 3`	|
| `//=`	| `x //= 3`	| `x = x // 3` |
| `**=`	| `x **= 3`	| `x = x ** 3` |
| `&=`	| `x &= 3`	| `x = x & 3`	|
| `|=`	| `x |= 3`	| `x = x | 3`	|
| `^=`	| `x ^= 3`	| `x = x ^ 3`	|
| `>>=`	| `x >>= 3`	| `x = x >> 3` |
| `<<=`	| `x <<= 3`	| `x = x << 3` |

<br>

```python
x = 5
print("x = ", x)
x = 5
x += 3
print("x += 3 -->", x)
x = 5
x -= 3
print("x -= 3 -->", x)
x = 5
x *= 3
print("x *= 3 -->", x)
x = 5
x /= 3
print("x /= 3 -->", x)
x = 5
x %= 3
print("x %= 3 -->", x)
x = 5
x //= 3
print("x //= 3 -->", x)
x = 5
x **= 3
print("x **= 3 -->", x)
x = 5
x &= 3
print("x &= 3 -->", x)
x = 5
x |= 3
print("x |= 3 -->", x)
x = 5
x ^= 3
print("x ^= 3 -->", x)
x = 5
x >>= 3
print("x >>= 3 -->", x)
x = 5
x <<= 3
print("x <<= 3 -->", x)
```

**Output**

```
x =  5
x += 3 --> 8
x -= 3 --> 2
x *= 3 --> 15
x /= 3 --> 1.6666666666666667
x %= 3 --> 2
x //= 3 --> 1
x **= 3 --> 125
x &= 3 --> 1
x |= 3 --> 7
x ^= 3 --> 6
x >>= 3 --> 0
x <<= 3 --> 40
```

<br>

---

<br>

### Comparison Operators

Comparison operators are used to compare two values:

<br>

| Operator	| Name	| Example	|
|--|--|--|
| `==`	| Equal	| `x == y` |
| `!=`	| Not equal	| `x != y` |
| `>`	| Greater than	| `x > y`	|
| `<`	| Less than	| `x < y`	|
| `>=`	| Greater than or equal to |	`x >= y` |
| `<=`	| Less than or equal to	| `x <= y` |


<br>

```python
x = 5
y = 3

print("x == y :", (x == y))
print("x != y :", (x != y))
print("x > y :", (x > y))
print("x < y :", (x < y))
print("x >= y :", (x >= y))
print("x <= y :", (x <= y))
```

**Output**

```
x == y : False
x != y : True
x > y : True
x < y : False
x >= y : True
x <= y : False
```

<br>

---

<br>

### Logical Operators

Logical operators are used to combine conditional statements:

<br>

| Operator	| Description	| Example	|
|--|--|--|
| `and` |	Returns `True` if both statements are true	| `x < 5 and x < 10`	|
| `or`	| Returns `True` if one of the statements is true	| `x < 5 or x < 4` |
| `not`	| Reverse the result, returns `False` if the result is true	| `not(x < 5 and x < 10)`|

<br>

```python
x = 5

print("x > 3 and x < 10  : ", (x > 3 and x < 10))
print("x > 3 or x < 10  : ", (x > 3 or x < 10))
print("not(x > 3 and x < 10)  : ", (not(x > 3 and x < 10)))
print("not(x > 3 or x < 10)  : ", (not(x > 3 or x < 10)))
```

**Output**

```
x > 3 and x < 10  :  True
x > 3 or x < 10  :  True
not(x > 3 and x < 10)  :  False
not(x > 3 or x < 10)  :  False
```

<br>

---

<br>

### Identity Operators

Identity operators are used to compare the objects, not if they are equal, but if they are actually the same object, with the same memory location:

<br>

| Operator	| Description	| Example	|
|--|--|--|
| `is` 	| Returns true if both variables are the same object	| `x is y` |
| `is not`	| Returns true if both variables are not the same object	| `x is not y` |

<br>

```python
x = 5
y = 3
z = 5
t = x

print("x is y  : ", (x is y))
print("x is z  : ", (x is z))
print("x is t  : ", (x is t))
print("x is not y  : ", (x is not y))
print("x is not z  : ", (x is not z))
print("x is not t  : ", (x is not t))
```

**Output**

```
x is y  :  False
x is z  :  True
x is t  :  True
x is not y  :  True
x is not z  :  False
x is not t  :  False
```

<br>

---


<br>

### Membership Operators

Membership operators are used to test if a sequence is presented in an object:

<br>

| Operator	| Description	| Example	|
|--|--|--|
| `in` 	| Returns `True` if a sequence with the specified value is present in the object	| `x in y` |
| `not in`	| Returns `True` if a sequence with the specified value is not present in the object	| `x not in y` |

<br>

```python
x = "some string"
y = "ing"
z = "apple"
q = 4
r = 5
t = ["orange", "string", "cherry", 3, 7, 5]


print("y in x  : ", (y in x))
print("y in t  : ", (y in t))
print("z in t  : ", (z in t))
print("q in t  : ", (q in t))
print("r in t  : ", (r in t))

print("y not in x  : ", (y not in x))
print("y not in t  : ", (y not in t))
print("z not in t  : ", (z not in t))
print("q not in t  : ", (q not in t))
print("r not in t  : ", (r not in t))
```

**Output**

```
y in x  :  True
y in t  :  False
z in t  :  False
q in t  :  False
r in t  :  True

y not in x  :  False
y not in t  :  True
z not in t  :  True
q not in t  :  True
r not in t  :  False
```

<br>

---


<br>

### Bitwise Operators

Bitwise operators are used to compare (binary) numbers:

<br>

| Operator	| Name	| Description |
|--|--|--|
| `&` 	| `AND`	| Sets each bit to 1 if both bits are 1 |
| `|`	| `OR`	| Sets each bit to 1 if one of two bits is 1 |
| `^`	| `XOR`	| Sets each bit to 1 if only one of two bits is 1 |
| `~` 	| `NOT`	| Inverts all the bits |
| `<<`	| `Zero fill left shift`	| Shift left by pushing zeros in from the right and let the leftmost bits fall off |
| `>>`	| `Signed right shift`	| Shift right by pushing copies of the leftmost bit in from the left, and let the rightmost bits fall off |

<br>

```python
x = 10
y = 4

print("x & y =", (x & y), "--- binary : ", bin(x & y))
print("x | y =", (x | y), "--- binary : ", bin(x | y))
print("x | y =", (x | y), "--- binary : ", bin(x | y))
print("~x =", (~x), "--- binary : ", bin(~x))
print("x << 2 =", (x << 2), "--- binary : ", bin(x << 2))
print("x >> 2 =", (x >> 2), "--- binary : ", bin(x >> 2))
```

**Output**

```
x & y = 0 --- binary :  0b0
x | y = 14 --- binary :  0b1110
x | y = 14 --- binary :  0b1110
~x = -11 --- binary :  -0b1011
x << 2 = 40 --- binary :  0b101000
x >> 2 = 2 --- binary :  0b10
```

<br>

---
