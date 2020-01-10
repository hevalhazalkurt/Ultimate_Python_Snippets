# Ultimate Python Snippets
## Python Fundamentals
### Numbers

<br>

#### Summary

* Numeric Types in Python
* Getting Type of Numeric Variable
* Limiting Float Number
* `int()` : Converting to Integer
* `float()` : Converting to Float
* `complex()` : Converting to Complex
* `abs()` : Absolute Number
* `bin()` : Getting Binary Version
* `divmod()` : Getting Quotient and Remainder
* `max()` : Finding Maximum
* `min()` : Finding Minimum
* `pow()` : Power of Number
* `random` : Random Number
* `range()` : Create Number Sequence
* `round()` : Rounding Number
* `sum()` : Calculating Sum

<br>

-----

<br>

### Numeric Types in Python   

There are three numeric types in Python :

* int
* float
* complex


```python
x = 1			# int
y = 2.8		# float
z = 1j		# complex
```


<br>

-----

<br>

### Getting Type of Numeric Variable   

To verify the type of any object in Python, we can use the `type()` function.


```python
x = 1
y = 2.8
z = 1j


print(type(x))
print(type(y))
print(type(z))
```

**Output**

```
<class 'int'>
<class 'float'>
<class 'complex'>
```

<br>

-----

<br>

### Limiting Float Number

We can limit the number of decimal places to show when we print the value of the float.

```python
x = 1.7000000000000002

print(f"x = {x:.1f}")
print(f"x = {x:.2f}")
print(f"x = {x:.3f}")
print(f"x = {x:.4f}")
```

**Output**

```
x = 1.7
x = 1.70
x = 1.700
x = 1.7000
```


<br>

-----

<br>

### `int()` : Converting to Integer     

Int, or integer, is a whole number, positive or negative, without decimals, of unlimited length.

```python
x = 2
y = 30948403
z = -87020

print(type(x))
print(type(y))
print(type(z))
```

**Output**

```
<class 'int'>
<class 'int'>
<class 'int'>
```

<br>

We can convert from one type to integer with `int()` function.

```python
x = 1.11
y = 2.0
z = 46.2908
t = -21.09

print(int(x))
print(int(y))
print(int(z))
print(int(t))
```

**Output**

```
1
2
46
-21
```

<br>

When you try to convert a complex number to integer Python you can get a result but don't trust that converting. Because you cannot convert complex numbers into another number type.

```python
x = 35e3
y = 12E4
z = -87.7e100

print(int(x))
print(int(y))
print(int(z))
```


**Output**

```
35000
120000
-876999999999999953141299176594128207296085227481859399976488364482518445137613994205637190836616691712
```



<br>

-----


<br>

### `float()` : Converting to Float   

Float, or "floating point number" is a number, positive or negative, containing one or more decimals.


```python
x = 1.11
y = 2.0
z = 46.2908
t = -21.09


print(type(x))
print(type(y))
print(type(z))
print(type(t))
```

**Output**

```
<class 'float'>
<class 'float'>
<class 'float'>
<class 'float'>
```

<br>

Float can also be scientific numbers with an "e" to indicate the power of 10.

```python
x = 35e3
y = 12E4
z = -87.7e100

print(type(x))
print(type(y))
print(type(z))
```


**Output**

```
<class 'float'>
<class 'float'>
<class 'float'>
```

<br>

We can convert from one type to float with `float()` function.

```python
x = 2
y = 30948
z = -87020

print(float(x))
print(float(y))
print(float(z))
```


**Output**

```
2.0
30948.0
-87020.0
```

<br>

-----


<br>

### `complex()` : Converting to Complex   

Complex numbers are written with a "j" as the imaginary part:


```python
x = 3+5j
y = 5j
z = -5j


print(type(x))
print(type(y))
print(type(z))
```

**Output**

```
<class 'complex'>
<class 'complex'>
<class 'complex'>
```

<br>

We can convert from one type to complex with `complex()` function.

```python
x = 2
y = -30948
z = 870.20

print(complex(x))
print(complex(y))
print(complex(z))
```


**Output**

```
(2+0j)
(-30948+0j)
(870.2+0j)
```


<br>


-----

<br>

### `abs()` : Absolute Number

Python number method `abs()` returns absolute value of x - the (positive) distance between x and zero.


```python
x = 3
y = -3
z = 3.4
t = 394
q = (3 - 4j)

print(abs(x))
print(abs(y))
print(abs(z))
print(abs(t))
print(abs(q))

print(abs(x - y))
print(abs(x - z))
print(abs(y - z))
```

**Output**

```
3
3
3.4
394
5.0

6
0.3999999999999999
6.4
```


<br>


--------

<br>

### `bin()` : Getting Binary Version

The `bin()` function returns the binary version of a specified integer.


```python
print(bin(3))
print(bin(-3))
print(bin(25))
print(bin(800))
```

**Output**

```
0b11
-0b11
0b11001
0b1100100000
```

<br>

-----

<br>

### `divmod()` : Getting Quotient and Remainder

The `divmod()` function returns a tuple containing the quotient  and the remainder when argument1 (divident) is divided by argument2 (divisor).


```python
print(divmod(5,2))
print(divmod(10,3))
print(divmod(150,4))
print(divmod(-10,3))
print(divmod(4,100))
print(divmod(23.6,2.4))
print(divmod(3, 8.0))
```

**Output**

```
(2, 1)
(3, 1)
(37, 2)
(-4, 2)
(0, 4)
(9.0, 2.000000000000002)
(0.0, 3.0)
```

<br>

------


<br>

### `max()` : Finding Maximum

The `max()` function returns the largest item in an iterable or the largest of two or more arguments.

```python
print(max(3,3.1))
print(max(3.1,-3.2))
print(max(3,-3.2))
print(max(3,5))
print(max(3,3.1,-3.2,5))
```

**Output**

```
3.1
3.1
3
5
5
```


<br>

--------

<br>

### `min()` : Finding Minimum

The `min()` function returns the smallest item in an iterable or the smallest of two or more arguments.

```python
print(min(3,3.1))
print(min(3.1,-3.2))
print(min(3,-3.2))
print(min(3,5))
print(min(3,3.1,-3.2,5))
```

**Output**

```
3
-3.2
-3.2
3
-3.2
```


<br>

--------

<br>

### `pow()` : Power of Number

The `pow()` method returns x to the power of y. If the third argument (z) is given, it returns x to the power of y modulus z, i.e. `pow(x, y) % z`.

```python
print(pow(2,2))
print(pow(-2,2))
print(pow(-2,-2))
print(pow(2,20))
print(pow(2,0))
print(pow(2,2,2))
print(pow(2,4,2))
print(pow(2,20,6))
```

**Output**

```
4
4
0.25
1048576
1
0
0
4
```


<br>

--------


<br>

### `random` : Random Number   

Python has a built-in module called `random` that can be used to make random numbers.


```python
import random

print(random.randrange(1,10))
```

**Output**

```
6
```


<br>


-----

<br>

### `range()` : Create Number Sequence

The `range()` function returns a sequence of numbers, starting from 0 by default, and increments by 1 (by default), and ends at a specified number.

```python
x = range(10)
y = range(1,10)
z = range(1,10,2)

print(list(x))
print(list(y))
print(list(z))


print(*list(x))
```

**Output**

```
[0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 2, 3, 4, 5, 6, 7, 8, 9]
[1, 3, 5, 7, 9]
0 1 2 3 4 5 6 7 8 9
```


<br>

------


<br>

### `round()` : Rounding Number

Python number method `round()` returns x rounded to n digits from the decimal point.


```python
print(round(1.5))
print(round(1.3))
print(round(2.5))
print(round(2.3))
print(round(2.7))
print(round(-87.6))
print(round(-87.4))
```

**Output**

```
2
1
2
2
3
-88
-87
```


Also we can reduce decimal places to given value.

```python
print(round(1.53456927, 1))
print(round(1.53456927, 2))
print(round(1.53456927, 3))
print(round(1.53456927, 4))
print(round(1.53456927, 5))
print(round(1.53456927, 6))
print(round(1.53456927, 7))
```

**Output**

```
1.5
1.53
1.535
1.5346
1.53457
1.534569
1.5345693
```

<br>

--------


<br>

### `sum()` : Calculating Sum

The `sum()` function returns a number, the sum of all items in an iterable.


```python
x = (1,2,3,4,5)
y = [1,2,3,4,5]
z = sum(y)

print(sum(x))
print(sum(x, 7))
print(sum(y))
print(sum(y,7))
print(sum(x, z))
```

**Output**

```
15
22
15
22
30
```


<br>

--------
