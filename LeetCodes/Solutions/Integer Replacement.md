### Brute Force
A bruth force approach will be to 
>- compute all possible ways to reduce the number to zero. i.e. for every ```n```, compute ```n/2``` when n is even, ```n-1``` and ```n+1``` when ```n``` is odd. 
>- Repeat the same step for every three new numbers generated until ```n``` is one. 
>- Then take minimum

### Optimized approach
> However, the problem has overlapping substructure. Thus dynamic programming can be used to reduce computations by storing intermediate results

### Greedy approach
> Somehow we know that when ```n``` is even we can get to one faster. Hence when ```n``` is odd we choose to increment ```n``` by 1 so that when we divide we can get an even number.  

Code
```Python
def is_even(n):
    if n % 2 == 0:
        return True
    else:
        return False

def checker(n):
    res = 0
    while n != 1:
        if n == 3:
            return res + 2
        
        if is_even(n):
            n = int(n/2)
            res += 1
            
        else:
            option1 = n - 1
            option2 = n + 1
            if is_even(option1/2):
                n = option1
                res += 1
            else:
                n = option2
                res += 1
        
    return res
    
    
class Solution:
    def integerReplacement(self, n: int) -> int:
        return checker(n)


```
