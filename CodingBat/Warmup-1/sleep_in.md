### sleep_in

> We sleep in if it is not a weekday or we're on vacation. Return True if we sleep in.
> * sleep_in(False, False) → True
> * sleep_in(True, False) → False
> * sleep_in(False, True) → True

``` python
def sleep_in(weekday, vacation):
  if (weekday == False or vacation == True):
    return True
  else:
    return False
```

The above was my initial solution to the problem - logically speaking, it works fine but it can be simplified rather heavily due to some of the characteristics that Python possesses. If weekday is __False__ or vacation is __True__ then we return a value of __True__ for sleep_in. 

In Python, checking if something is false can be done with the one command __not__, i.e. *not* weekday is the same as weekday == False.
Similarily, checking if something is true can be done by just leaving the name of the boolean variable, i.e. instead of vacation == True, *vacation* is automatically checking if it is true.

Combining these two concepts, you can thus simplify the __if__ statement to be the following

``` python
if (not weekday or vacation):
```

And again, like in Java, instead of having an if-else because there are only two possible outcomes you can just have it all on one line with the use of a return statement.  

``` python
return (not weekday or vacation):
```
