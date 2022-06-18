### Brute Force Approach
- Write a helper function which computes the power value for a given number using recursion
- Store all numbers in the range ```lo``` to ```hi``` in a dictionary with their corresponding "power value" as key
- Sort the resulting dictionary by value
- Return the ```kth(1-indexed)``` key in the sorted dictionary

### Optimized Approach
- Because values may be recomputed for different number in the interval ```[lo, hi]```, store intermediate results in another dictionary to avoid repeated computations


Code (Optimized)
```Python
def helper(i, memo):
    if i == 1:
        return 0
    
    if memo.get(i) != None:
        return memo[i]
    
    if i % 2 == 0:
        memo[i] = 1 + helper(int(i/2), memo)
        
    else:
        memo[i] = 1 + helper(i*3+1, memo)
        
    return memo[i]
        

class Solution:
    def getKth(self, lo: int, hi: int, k: int) -> int:
        memo = {1:0}
        res = {}
        for i in range(lo, hi+1):
            helper(i, memo)
            res[i] = memo[i]
        
        return ([key for key, v in sorted(res.items(), key=lambda item: item[1])])[k-1]
        
```

