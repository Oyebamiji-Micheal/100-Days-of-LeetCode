Code
```Python
class Solution:
    def nextGreaterElements(self, nums: List[int]) -> List[int]:
        if len(nums) == 1: 
            return [-1]
        
        stack = []
        res = [0] * len(nums)
        
        for idx, num in enumerate(nums):
            if stack:
                while stack and num > nums[stack[-1]]: 
                    res[stack[-1]] = num
                    stack.pop()
                stack.append(idx)
            else:
                stack.append(idx)
        
        for idx in range(len(nums)):
            if stack and idx >= stack[0]: 
                if nums[stack[-1]] < nums[stack[0]]:
                    res[stack[-1]] = nums[stack[0]]
                    stack.pop()
                else:
                    res[stack[-1]] = -1
                    stack.pop()
            
            else:
                while stack and nums[idx] > nums[stack[-1]]:
                    res[stack[-1]] = nums[idx]
                    stack.pop()
            
        return res
                
                
        
                
        
        
```
