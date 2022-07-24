Code 

```Python
class Solution:
    def mostCompetitive(self, nums: List[int], k: int) -> List[int]:
        
        N = len(nums)
        stack = []

        for i in range(N):
            if stack:
                if nums[i] < stack[-1]:
                    num_rem = N - i

                    while nums[i] < stack[-1] and len(stack) + num_rem > k:
                        stack.pop()
                        if not stack:
                            break
                    stack.append(nums[i])

                elif len(stack) < k:
                    stack.append(nums[i])
            else:
                stack.append(nums[i])

        return stack

        
```
