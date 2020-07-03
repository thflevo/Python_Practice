## date_fashion

> You and your date are trying to get a table at a restaurant. The parameter "you" is the stylishness of your clothes, in the range 0..10, and "date" is the stylishness of your date's clothes. The result getting the table is encoded as an int value with 0=no, 1=maybe, 2=yes. If either of you is very stylish, 8 or more, then the result is 2 (yes). With the exception that if either of you has style of 2 or less, then the result is 0 (no). Otherwise the result is 1 (maybe).
> * date_fashion(5, 10) → 2
> * date_fashion(5, 2) → 0
> * date_fashion(5, 5) → 1

```python
def date_fashion(you, date):
  if (you <= 2) or (date <= 2):
    return 0
  if (you >= 8) or (date >= 8):
    return 2
  return 1
```

Although the question itself is worded a little strangely, the actual logic behind it is pretty straightforward. However, the key point to this excercise is __precedence__. Different results may have different levels of importance - they aren't all equal. In this case, the "0" result of having either you or your date possessing a stylishness of 2 or below is the most important. Thus, the code has to be written to reflect this.

What this means is that when the code is checking the two parameters, it has to first check if any are 2 or below, then check if any are 8 or above. Because even if either of the parameters have a score of above 8, if the other has a score of 2 or lower the result is still a no/0. Thus the code must reflect this train of thought. 

I must admit that I more or less solved this accidentally - I wanted to just see how many I would pass and work from there but I ended up writing pretty much the simplest code that you can get for this problem. 
