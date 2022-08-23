Code
```Python
class Solution:
    def sumOfThree(self, num: int) -> List[int]:
        
        if num == 0:
            return [-1, 0, 1]
        
        if num % 3 != 0:
            return []
        
        x = num // 3 
        return [x-1, x, x+1]
        
```
