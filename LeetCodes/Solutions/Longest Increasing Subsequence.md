Longest increasing subsequence (lis)

### Explanation
This question exhibits two properties:
- overlapping subproblems 
- optimal substructures  

Hence it can be solved using dynamic programming!

Code (Dynamic Programming)
``` Python
def checker(nums):
    N = len(nums)
    lis = [1] * N
    
    for i in range(1, N):
        for j in range(i):
            if nums[i] > nums[j] and lis[i] < lis[j] + 1:
                lis[i] = lis[j] + 1
                
    return max(lis)


class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        return checker(nums)
```



However, there is another solution to this question. Since the result is an increasing sequence, a python function known as [bisect_left](https://docs.python.org/3/library/bisect.html) can be used to get the longest subsequence. Then its length can be returned  
Code(faster)
```Python
def checker(nums):
    n = len(nums)
    res = [nums[0]]
    
    for i in nums:
        x = bisect_left(res, i)
        if x == len(res):
            res.append(i)
        elif res[x] > i:
            res[x] = i
     
    
    return len(res)
    
class Solution:
    def lengthOfLIS(self, nums: List[int]) -> int:
        return checker(nums)
        
```
