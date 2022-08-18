Code
```Python
from collections import deque

class Solution:
    def maxSlidingWindow(self, nums: List[int], k: int) -> List[int]:
        left = right = 0
        res = []
        indices = deque()
        
        while right < len(nums):
            while indices and nums[right] > nums[indices[-1]]:
                indices.pop()
            indices.append(right)
            
            if left > indices[0]:
                indices.popleft()
            
            if right + 1 >= k:
                res.append(nums[indices[0]])
                left += 1
            
            right += 1
        
    
        return res
            
        
        
        
```
