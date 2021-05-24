# Problem 1

> If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9. The sum of these multiples is 23.
> Find the sum of all the multiples of 3 or 5 below 1000.

My first thought was around arithmetic progressions - summing those and only doing it for 3 and 5 before I realised that this was actually something you were supposed to solve with code...

Anyways. The first comment I wrote was *can use modulo*, so I guess I was going in the right direction.



## First Solution

```python
threeOrFive = []

for number in range(1, 1000):
    if ((number % 3 == 0) or (number % 5 == 0)):
        threeOrFive.append(number)

threeOrFive = sum(threeOrFive)

print(threeOrFive)
```


...yeah, not the most refined or effective way. It's a product of the roadblocks I went through really. Obtaining the list of numbers was the easy part. Modulo really is handy for solving this problem in particular. Thought process was as follows. 

1. Check if number is divisible by 3 or by 5
If yes, return the number. 
`if ((number % 3 == 0) or (number % 5 == 0)):`

At first, I was just printing the answer and hoping to convert the printed list into an array, but then Google showed me the **.append** function. Hence, the code begins with me declaring an array, then iterating through the specified range, adding each number to the array, then summing the array, then printing it out.

I didn't try to improve on it at first - I just immediately submitted the answer I got. 


## Second Solution

```python
threeOrFive = 0

for number in range(1,1000):
    if ((number % 3 == 0) or (number % 5 == 0)):
        threeOrFive += number

print(threeOrFive)
```

I think from a logic perspective solution is more or less the same. However, instead of creating an array and summing the array, this just iterates through and adds to the number as it goes...which is the logical way to do it really. 


Anywho, first time doing anything like this. Quite fun really. 
