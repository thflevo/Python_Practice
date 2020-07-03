## squirrel_play

> The squirrels in Palo Alto spend most of the day playing. In particular, they play if the temperature is between 60 and 90 (inclusive). Unless it is summer, then the upper limit is 100 instead of 90. Given an int temperature and a boolean is_summer, return True if the squirrels play and False otherwise.
> * squirrel_play(70, False) → True
> * squirrel_play(95, False) → False
> * squirrel_play(95, True) → True

```python
def squirrel_play(temp, is_summer):
  if (temp >= 60 and temp <= 90):
    return True
  if is_summer and (temp >= 60 and temp <= 100):
    return True
  return False
```

For this one, it is very similar to cigar_party, and my initial code for it is written in almost the exact same manner as my code for that problem. There's actually close to no variation in the logic behind it. They are both questions which operate on the following basis - If X, then Y. If Not X, then modified Y, and then the final 'else' catchall which accounts for all the A's B's and C's. 


As such, the simplified code for this problem is the same as cigar_party

```python
if is_summer:
  return (temp >= 60 and temp <= 100)
return (temp >= 60 and temp <= 90)
```
