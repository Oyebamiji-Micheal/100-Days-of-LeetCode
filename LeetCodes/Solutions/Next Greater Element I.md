Code

```Python
class Solution:
    def nextGreaterElement(self, nums1: List[int], nums2: List[int]) -> List[int]:
        stack = []
        hashmap = {}
        
        for idx in range(len(nums2)):
            if stack:
                while stack and nums2[idx] > nums2[stack[-1]]:
                    top = stack.pop()
                    hashmap[nums2[top]] = nums2[idx]
                stack.append(idx)
            else:
                stack.append(idx)
        
        for idx in stack:
            hashmap[nums2[idx]] = -1
            
        for idx, num in enumerate(nums1):
            nums1[idx] = hashmap[num]
            
        return nums1
        
```
