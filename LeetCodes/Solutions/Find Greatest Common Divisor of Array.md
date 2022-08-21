Code

```Python
from math import gcd


class Solution:
    def findGCD(self, nums: List[int]) -> int:
        min_num = float('inf')
        max_num = float('-inf')
        
        for num in nums:
            if num > max_num:
                max_num = num
            if num < min_num:
                min_num = num
                
        return gcd(min_num, max_num)
        
```
