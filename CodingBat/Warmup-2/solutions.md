# General Comments

So I started these problems thinking that they would be relatively easy, but I quickly realised that they are actually harder than expected - as such, this solutions document will only have the first two problems. The rest of them will each have their own writeups as I go through my thought processes and the learning experiences I had from each. 

## string_times 

> Given a string and a non-negative int n, return a larger string that is n copies of the original string.
> * string_times('Hi', 2) → 'HiHi'
> * string_times('Hi', 3) → 'HiHiHi'
> * string_times('Hi', 1) → 'Hi'

```python
def string_times(str, n):
  return str * n
```

Because we are told that the int __n__ will be non-negative, we don't have to worry about checking for values. The asterisk "*" in Python can be used to multiply strings, which we learned in the String-1 excercises.



## front_times

> Given a string and a non-negative int n, we'll say that the front of the string is the first 3 chars, or whatever is there if the string is less than length 3. Return n copies of the front;
> * front_times('Chocolate', 2) → 'ChoCho'
> * front_times('Chocolate', 3) → 'ChoChoCho'
> * front_times('Abc', 3) → 'AbcAbcAbc'

```python
def front_times(str, n):
  return str[:3] * n
```

Again, this concept was also explored in the String-1 problem collection. We are told that __n__ is a non-negative int, and we can just use the string[] index command to return the first 3 characters. 
