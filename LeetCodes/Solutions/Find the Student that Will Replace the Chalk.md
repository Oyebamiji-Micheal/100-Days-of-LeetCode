
### Explanation and Algorithm
>- Instead of going through the list over and over again until there's no more chalk, we can simply take the sum of all elements in the list and store it in a variable, say, ```s```
>- Then find the remainder when ```s``` is divided by ```k```, the total number of chalks. let's say this is called ```remainder```
>- The variable, ```remainder```, tells us how many times we can go through the list without finding the index of the student
>- Setting ```k = remainder``` implies that by going through the list once, we will find the index of the student


Code
```python

class Solution:
    def chalkReplacer(self, chalk: List[int], k: int) -> int:
        
        s = sum(chalk)
        if s <= k:
            k = k % s
        
        for i in range(len(chalk)):
            if chalk[i] <= k:
                k = k - chalk[i]
            else:
                return i
```

