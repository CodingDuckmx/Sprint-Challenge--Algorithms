#### Please add your answers to the ***Analysis of  Algorithms*** exercises here.

## Exercise I

a)
```python
  a = 0
    while (a < n * n * n):
      a = a + n * n
```

The time complexity of a) is O(n).
Meanwhile the limit for the while loop increases in cube 
terms, the result increments quadratic, so the difference, or
time complexity is achieved by 'dividing' the n^3 by n^2.

The space complexity is O(1). Whe are not creating new space in memory n-dependant. 


b)
```
sum = 0
    for i in range(n):
      j = 1
      while j < n:
        j *= 2
        sum += 1
```

The time complexity of this snippet is O(n log n).
For the first loop we have O(n) of time complexity, it is looping between each number from zero to n.
The while loop increments in terms of 2^x, so the time complexity turns to be O(log n). 
Because both loops are nested, we multiply both time complexities, getting O(n log n).

A side comment, as we are not using i elsewhere, we can omit it using and underscore (_). And this code could be refactored. We can do it without the first loop, and just muliply the result of the second loop

```
    sum = 0
    j = 1
    while j < n:
        j *= 2
        sum += 1
    return sum * n
```

And the time complexity drops down to O(log n).


The space complexity is O(1). Whe are not creating new space in memory n-dependant, in either case.

c)

```
def bunnyEars(bunnies):
    if bunnies == 0:
    return 0

    return 2 + bunnyEars(bunnies-1)
```

Its space complexity turns to be O(n), because we have a recursive algorithm and the maximum depth is n+1.

The time complexity is O(n) as well, we have a tree with one branch of length n+1.



## Exercise II


Because we can only be sure the egg will be broken after throwing it, we will have to throw an egg from each floor
an see if it is broken. It is not, go up to the next floor and try again

Stop at the time the first egg is broken.

The time complexity of this is O(n) because in the worst scenario, no egg gets broken, even in the nth floor.

broken = False
numer_of_floor = 0

while numer_of_floor <= n and  not broken:

    throw the egg
    (turns broken maybe)

    if broken:
        
        return num_of_floor
    
    else:
        numer_of_floor += 1