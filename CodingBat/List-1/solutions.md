# General Comments

Only the first couple of problems within this set are actually within this solutions document. As I progressed through the problem set, I realised that the harder questions needed their own individual writeups and I've done that for the ones which are not present in this document. With that being said, these four problems are based around using the 'first' and 'last' element commands by referencing their indexes within a list. Nothing new, and actually quite similar conceptually to some previous problems. 

## first_last6

> Given an array of ints, return True if 6 appears as either the first or last element in the array. The array will be length 1 or more.
> * first_last6([1, 2, 6]) → True
> * first_last6([6, 1, 2, 3]) → True
> * first_last6([13, 6, 1, 2, 3]) → False

```python
def first_last6(nums):
  return (nums[0] == 6 or nums[-1]  == 6)
```

Conceptually this one was pretty simple. You just have to check two cases - the first and last elements in an array. You are told that it will be an array of ints, and that the length will be one or more, therefore you don't have to worry about non-int values or empty arrays and can just directly code to check.


## same_first_last

> Given an array of ints, return True if the array is length 1 or more, and the first element and the last element are equal.
> * same_first_last([1, 2, 3]) → False
> * same_first_last([1, 2, 3, 1]) → True
> * same_first_last([1, 2, 1]) → True

```python
def same_first_last(nums):
  return len(nums) > 0 and (nums[0] == nums[-1])
```

Very similar to the previous, checking two cases. Number 1, if the length is bigger than 0, and number two, if the first and last numbers are the same and then returning the end result. 

## make_pi 

> Return an int array length 3 containing the first 3 digits of pi, {3, 1, 4}.
> * make_pi() → [3, 1, 4]

```python
def make_pi():
  pie = [3, 1, 4]
  return pie
```

or

```python
def make_pi():
  return [3, 1, 4]
```


## common_end 

> Given 2 arrays of ints, a and b, return True if they have the same first element or they have the same last element. Both arrays will be length 1 or more.
> * common_end([1, 2, 3], [7, 3]) → True
> * common_end([1, 2, 3], [7, 3, 2]) → False
> * common_end([1, 2, 3], [1, 3]) → True

```python
def common_end(a, b):
  return (a[0] == b[0] or a[-1] == b[-1])
```
