## sorta_sum


> Given 2 ints, a and b, return their sum. However, sums in the range 10..19 inclusive, are forbidden, so in that case just return 20.
> * sorta_sum(3, 4) → 7
> * sorta_sum(9, 4) → 20
> * sorta_sum(10, 11) → 21

```python
def sorta_sum(a, b):
  if (a + b) < 20 and (a + b) >= 10:
    return 20
  return a+b
```

Despite what it looks like, this problem can be boiled down to essentially one condition - if the sum is between 10 and 19. If it is, then return 20. If it isn't, then return the sum. Once I stepped through this logically, writing it up was relatively easy as it builds upon previously touched upon topics/ideas. 
