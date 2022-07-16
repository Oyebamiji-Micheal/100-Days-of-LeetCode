Code

```Python
def checker(data):
    result = set()
    hashmap = {}
    for i in range(len(data)):
         hashmap[data[i]] = i
    
    for i in range(len(data)):
        for j in range(i+1, len(data)):
            complement = 0 - data[i] - data[j]
            if complement in hashmap and hashmap[complement] > j:
                value = [data[i], data[j], complement]
                value.sort()
                result.add(tuple(value))
            else:
                pass            
                     
    return result


class Solution:
    def threeSum(self, nums: List[int]) -> List[List[int]]:
        return checker(nums)
        
```
