Code
```Python
class Solution:
    def minimumDeletions(self, nums: List[int]) -> int:
        min_num_idx = max_num_idx = -1
        min_num = float('inf')
        max_num = float('-inf')
                        
        for idx, num in enumerate(nums):
            if num < min_num:
                min_num = num
                min_num_idx = idx
            if num > max_num:
                max_num = num
                max_num_idx = idx
                
        max_idx = max(min_num_idx, max_num_idx)
        min_idx = min(min_num_idx, max_num_idx)
        
        case1 = max_idx + 1
        case2 = len(nums) - min_idx
        case3 = min_idx + 1 + len(nums) - max_idx
        
        return min(case1, case2, case3)
    
            
        
```
