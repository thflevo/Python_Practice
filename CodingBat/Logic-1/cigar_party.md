## cigar_party

> When squirrels get together for a party, they like to have cigars. A squirrel party is successful when the number of cigars is between 40 and 60, inclusive. Unless it is the weekend, in which case there is no upper bound on the number of cigars. Return True if the party with the given values is successful, or False otherwise.
> * cigar_party(30, False) → False
> * cigar_party(50, False) → True
> * cigar_party(70, True) → True

``` python
def cigar_party(cigars, is_weekend):
  if (cigars >= 40 and cigars <= 60):
    return True
  if (is_weekend and cigars >= 40):
    return True
   return False
```

My solution for the problem works fine as is, but it can definitely be simplified. Just stepping through the logic behind this one though, it's rather simple. There are two conditions present - amount of cigars and whether or not it is a weekend. Fortunately, each does not affect the other in a way that would require precedence, and so you can simply write up two if statements, one for each condition.

* The first condition of not being a weekend, and needing the cigars to be between 40 and 60 
* The second condition of being a weekend and having more than 40 cigars

Because I am writing this using two separate if statements, I don't actually need an __else__ - it is implied. Thus, I can just have the indented __return__ statement which will generate a __False__ output if neither of the two if statements are fulfilled. 


After looking around for some better, cleaner solutions I've found the following.

Instead of coding for each of the two conditions and returning True if they are met, the conditions themselves actually output a boolean value anyways. As such, you can have something like the following.

``` python
if is_weekend:
  return (cigars >= 40)
return (cigars >= 40 and cigars <= 60)
```

Stepping through the logic above, we can see how if the "is_weekend" variable is True, then we return whether or not there are more than 40 cigars (These are the two conditions specified in the if statement that I wrote) and alternatively, if "is_weekend" is not True, then we just return the other condition. 

Although I understand logically how this works, I don't think I'm at the level where I can comfortably use it in my own solutions yet. 


