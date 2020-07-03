# General Comments

This series of problems was a lot easier than the Java counterparts. This was twofold - not only did the logic behind many of the problems remain the same as the Java ones, but Python is also a lot more user friendly(In my opinion at least).

Throughout all these solutions, I tried to refine them to make them as simplified as possible, but I do recognise that in some situations perhaps they are a little oversimplified and a less compact solution would be easier for other people to read. Nevertheless, a key component which I use throughout all the solutions is the fact that in Python, when you create an if statement you don't actually need an 'else' statement, you can just directly return the else case. 


## monkey_trouble

> We have two monkeys, a and b, and the parameters a_smile and b_smile indicate if each is smiling. We are in trouble if they are both smiling or if neither of them is smiling. Return True if we are in trouble.
> * monkey_trouble(True, True) → True
> * monkey_trouble(False, False) → True
> * monkey_trouble(True, False) → False

```python
def monkey_trouble(a_smile, b_smile):
  return (a_smile == b_smile)
```

Condition is if __both__ are True or __both__ are False.



## sum_double

> Given two int values, return their sum. Unless the two values are the same, then return double their sum.
> * sum_double(1, 2) → 3
> * sum_double(3, 2) → 5
> * sum_double(2, 2) → 8

```python
def sum_double(a, b):
  if (a == b):
    return (2 * (a+b))
  return (a + b)
```

First check if they are a equal, if they are, return double their sum, otherwise return their sum.



## diff21

> Given an int n, return the absolute difference between n and 21, except return double the absolute difference if n is over 21.
> * diff21(19) → 2
> * diff21(10) → 11
> * diff21(21) → 0

```python
def diff21(n):
  if (n > 21):
    return (2 * (abs(n - 21)))
  return (abs(n - 21))
```

Same as __sum_double__, check if the number is above 21. If they are, return double the absolute difference, otherwise return the absolute difference.
This works because Python has an inbuilt __abs()__ function which returns the absolute value of a number.



## parrot_trouble

> We have a loud talking parrot. The "hour" parameter is the current hour time in the range 0..23. We are in trouble if the parrot is talking and the hour is before 7 or after 20. Return True if we are in trouble.
> * parrot_trouble(True, 6) → True
> * parrot_trouble(True, 7) → False
> * parrot_trouble(False, 6) → False

```python
def parrot_trouble(talking, hour):
  return (talking and (hour < 7 or hour > 20))
```

This one relies on the correct nesting of the __logical operators__ - you need to check if the hour is between 7 and 20, and then check if the parrot is talking.



## makes10

> Given 2 ints, a and b, return True if one if them is 10 or if their sum is 10.
> * makes10(9, 10) → True
> * makes10(9, 9) → False
> * makes10(1, 9) → True

```python
def makes10(a, b):
  return (a == 10 or b == 10 or (a + b == 10))
```

Basically stacking the __logical operator__ "or", and just having more than two cases. 



## near_hundred

> Given an int n, return True if it is within 10 of 100 or 200. Note: abs(num) computes the absolute value of a number.
> * near_hundred(93) → True
> * near_hundred(90) → True
> * near_hundred(89) → False

```python
def near_hundred(n):
  if ((abs(100 - n) <= 10) or (abs(200 - n) <= 10)):
    return True
  return False
```

Same logic as the Java counterpart problem, checking that the __abs(100/200 -n) <= 10__ 



## pos_neg

> Given 2 int values, return True if one is negative and one is positive. Except if the parameter "negative" is True, then return True only if both are negative.
> * pos_neg(1, -1, False) → True
> * pos_neg(-1, 1, False) → True
> * pos_neg(-4, -5, True) → True

```python
def pos_neg(a, b, negative):
  if negative:
    return (a < 0 and b < 0)
  return (a < 0 and b > 0) or (a > 0 and b < 0)
```

First check if the __boolean__ negative is **True**, and if so return the output of both a & b smaller than zero. Otherwise, check if a or b are smaller than zero



## not_string

> Given a string, return a new string where "not " has been added to the front. However, if the string already begins with "not", return the string unchanged.
> * not_string('candy') → 'not candy'
> * not_string('x') → 'not x'
> * not_string('not bad') → 'not bad'

```python
def not_string(str):
  if len(str) >= 3 and str[:3] == "not":
    return str
  return "not " + str
```

Using some inbuilt Python commands to do this one - namely, __len(x)__ and __str[x]__ to complete this one. 

- __len(x)__
  - returns the length of the string provided as an integer
- __str[x]__
  - returns the characters or series of characters at the specified index locations.

By combining these two commands and concatenating the result you can pretty easily solve this problem.



## missing_char

> Given a non-empty string and an int n, return a new string where the char at index n has been removed. The value of n will be a valid index of a char in the original string (i.e. n will be in the range 0..len(str)-1 inclusive).
> * missing_char('kitten', 1) → 'ktten'
> * missing_char('kitten', 0) → 'itten'
> * missing_char('kitten', 4) → 'kittn'

```python
def missing_char(str, n):
  return str[0:n] + str[n+1:len(str)]
```

Again, using the __str[x]__ command to basically just isolate the provided character, and return the string before and string after.



## front_back

> Given a string, return a new string where the first and last chars have been exchanged.
> * front_back('code') → 'eodc'
> * front_back('a') → 'a'
> * front_back('ab') → 'ba'

```python
def front_back(str):
  if len(str) >= 2:
    return str[len(str) -1] + str[1:len(str) - 1] + str[0]
  return str
```

Very similar to the one before, except this time you have to first check if the string length is longer than 2, as otherwise the swap cannot go ahead. Once it has been checked, splitting it into the last character, first character and the middle section and then re-concatenating them as required.



## front3

> Given a string, we'll say that the front is the first 3 chars of the string. If the string length is less than 3, the front is whatever is there. Return a new string which is 3 copies of the front.
> * front3('Java') → 'JavJavJav'
> * front3('Chocolate') → 'ChoChoCho'
> * front3('abc') → 'abcabcabc'

```python
def front3(str):
  if len(str) < 3:
    return str + str + str
  return str[:3] + str[:3] + str[:3]
```

As per the prompt, if the string is less than 3 characters, return it three times, otherwise return the first three characters three times.
