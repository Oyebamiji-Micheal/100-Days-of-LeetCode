### Brute Force (list)
- Searching in a list takes a time complexity of O(n)

### Optimized Approach 
- By using a dictionary, the time complexity can be reduced significantly. This is because the dictionary data structure is designed to support quick insertion and search

Code
```Python
class Solution:
    def findLonely(self, nums: List[int]) -> List[int]:
        hashmap = {}
        res = []
        
        for i in nums:
            if i in hashmap:
                hashmap[i] += 1
            else:
                hashmap[i] = 1
                
        for key, value in hashmap.items():
            if value == 1 and key-1 not in hashmap and key+1 not in hashmap:
                res.append(key)
        return res
            
   ```
