### Explanation
>- Find the maximum number in the list, say max_num.
>- Then check for all numbers in the range ```1 <= x <= max_num ```
>- Return the number that satisfies the requirement

### Algorithm
>- As ```x``` tends to ```max_num```, the sum over the array decreases. Thus, we can use binary search to optimize our code
    
Code
```python
class Solution:
    def smallestDivisor(self, nums: List[int], threshold: int) -> int:
        
        def calculate(nums, i):
            s = 0
            for j in nums:
                s += ceil(j/i)
            return s

        res = float('inf')
        p = max(nums)

        lo = 1
        hi = p
        while lo <= hi:
            mid = (lo + hi) // 2
            x = calculate(nums, mid)

            if x > threshold:
                lo = mid + 1
            elif x == threshold:
                if mid < res:
                    res = mid
                hi = mid - 1
            else:
                if mid < res:
                    res = mid
                hi = mid - 1

        return res

```
