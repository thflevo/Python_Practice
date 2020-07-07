# General Comments

Almost all of these string problems involved the use of the string[] index command and the various ways you can manipulate it, whether it be via the use of string[x:], string[:x] or negative indexes. Although the questions themselves are rather simple, and can (probably) be done even without any knowledge of the aforementioned commands by doing them and attempting to optimise them through testing/looking at solutions posted by others/CodingBat I was able to learn quite a bit about the behaviour of strings and the string[] index command. 

## hello_name

> Given a string name, e.g. "Bob", return a greeting of the form "Hello Bob!".
> * hello_name('Bob') → 'Hello Bob!'
> * hello_name('Alice') → 'Hello Alice!'
> * hello_name('X') → 'Hello X!'

```python
def hello_name(name):
  return "Hello " + name + "!"
```
Very simple concatenation of strings



## make_abba

> Given two strings, a and b, return the result of putting them together in the order abba, e.g. "Hi" and "Bye" returns "HiByeByeHi".
> * make_abba('Hi', 'Bye') → 'HiByeByeHi'
> * make_abba('Yo', 'Alice') → 'YoAliceAliceYo'
> * make_abba('What', 'Up') → 'WhatUpUpWhat'

```python
def make_abba(a, b):
  return (a + b + b + a)
```

Playing upon the property that whenever input is sourced in python, the default variable type is a string, so you can just concatenate them directly.



## make_tags

> The web is built with HTML strings like "<i>Yay</i>" which draws Yay as italic text. In this example, the "i" tag makes <i> and </i> which surround the word "Yay". Given tag and word strings, create the HTML string with tags around the word, e.g. "<i>Yay</i>".
> * make_tags('i', 'Yay') → '<i>Yay</i>'
> * make_tags('i', 'Hello') → '<i>Hello</i>'
> * make_tags('cite', 'Yay') → '<cite>Yay</cite>'

```python
def make_tags(tag, word):
  return "<" + tag + ">" + word + "</" + tag + ">"
```

Again, same as the previous two.



## make_out_word

> Given an "out" string length 4, such as "<<>>", and a word, return a new string where the word is in the middle of the out string, e.g. "<<word>>".
> * make_out_word('<<>>', 'Yay') → '<<Yay>>'
> * make_out_word('<<>>', 'WooHoo') → '<<WooHoo>>'
> * make_out_word('[[]]', 'word') → '[[word]]'

```python
def make_out_word(out, word):
  return (out[:2] + word + out[2:])
```

This one is a bit more complex, making use of the string[] index command to acheive it but a similar concept is explored in the Warmup-1 questions



## extra_end

> Given a string, return a new string made of 3 copies of the last 2 chars of the original string. The string length will be at least 2.
> * extra_end('Hello') → 'lololo'
> * extra_end('ab') → 'ababab'
> * extra_end('Hi') → 'HiHiHi'

```python
def extra_end(str):
  end = len(str)
  return (str[end - 2:end]) + (str[end - 2:end]) + (str[end - 2:end])
```

Although I'm pretty sure this one can actually be simplified, I'm not sure to what extent. The most obvious first step is to perhaps make each iteration of the last two characters a new variable, perhaps named "lastTwo" and then use that three times but otherwise, I cannot think of any other ways which can be used to simplify this solution

EDIT: I've just realised that you can do this in one line - indexes can be negative numbers in Python, they will return counting from the back. You can also multiply strings instead of repeating it x amount of times. i.e.
```python
return str[-2:] * 3
```

## first_two

> Given a string, return the string made of its first two chars, so the String "Hello" yields "He". If the string is shorter than length 2, return whatever there is, so "X" yields "X", and the empty string "" yields the empty string "".
> * first_two('Hello') → 'He'
> * first_two('abcdefg') → 'ab'
> * first_two('ab') → 'ab'

```python
def first_two(str):
  if len(str) >= 2:
    return str[:2]
  return str
```

Added condition that you have to first check if the str is longer than two characters.


## first_half

> Given a string of even length, return the first half. So the string "WooHoo" yields "Woo".
> * first_half('WooHoo') → 'Woo'
> * first_half('HelloThere') → 'Hello'
> * first_half('abcdef') → 'abc'

```python
def first_half(str):
  return str[:(len(str)/2)]
```

Because of the fact that all the strings will be __even__, and that the len(str) command returns an integer, in order to get the first half we can just divide the length by 2. This, combined with the string[] index command can be used to solve this in a pretty sleek fashion.



## without_end

> Given a string, return a version without the first and last char, so "Hello" yields "ell". The string length will be at least 2.
> * without_end('Hello') → 'ell'
> * without_end('java') → 'av'
> * without_end('coding') → 'odin'

```python
def without_end(str):
  return str[1:(len(str) - 1)]
```

Again, just mostly fiddling around with the string[] index command, and combining it with the len(str) command. We want to remove the first and last, so we just start from 1 (indexes start counting at 0) and we end at the second last character (length of the string - 1).

A more effecient way to solve this question would be the following
```python
return str[1:-1]
```

This is because the "-1" index is the second last character starting from the back. 



## combo_string

> Given 2 strings, a and b, return a string of the form short+long+short, with the shorter string on the outside and the longer string on the inside. The strings will not be the same length, but they may be empty (length 0).
> * combo_string('Hello', 'hi') → 'hiHellohi'
> * combo_string('hi', 'Hello') → 'hiHellohi'
> * combo_string('aaa', 'b') → 'baaab'

```python
def combo_string(a, b):
  if len(a) > len(b):
    return b + a + b
  return a + b + a
```

I just hardcoded both possibilities in this solution, as we are told that the strings will not be the same length. There is perhaps a better way to do this, but I cannot think of it at the moment. 



## non_start

> Given 2 strings, return their concatenation, except omit the first char of each. The strings will be at least length 1.
> * non_start('Hello', 'There') → 'ellohere'
> * non_start('java', 'code') → 'avaode'
> * non_start('shotl', 'java') → 'hotlava'

```python 
def non_start(a, b):
  return a[1:] + b[1:]
```

This one again makes use of the intricacies of the string[] index command. string[x:] will go from x to the end, so there is no need to add a specific endpoint.



## left2

> Given a string, return a "rotated left 2" version where the first 2 chars are moved to the end. The string length will be at least 2.
> * left2('Hello') → 'lloHe'
> * left2('java') → 'vaja'
> * left2('Hi') → 'Hi'

```python
def left2(str):
  return str[2:] + str[:2] 
```

Similar to previous, but making use of the fact that string[:x] will go from the start of the string to x.

