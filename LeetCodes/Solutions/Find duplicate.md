### Explanation
>- Iterate ```nums``` once and Store each value in a list, say, ```result```
>- During iteration, check if current element is in ```result```
>- If true, return the element otherwise repeat step 2 until true

### Algorithm and Data Structure
>- Searching in a list is O(n) operation. Thus the complexity for the above process is O(n²)
>- Using a set however reduces the overall process to O(n) since searching in a list has amortized constant time complexity

Code
``` python
def checker(nums):
    res = set()
    for i in nums:
        if i in res:
            return i
        else:
            res.add(i)
            continue
            
class Solution:
    def findDuplicate(self, nums: List[int]) -> int:
        return checker(nums)
        
```
