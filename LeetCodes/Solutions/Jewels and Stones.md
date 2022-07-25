Code

```Python

def checker(str1, str2):
    res = {}
    l = 0
    for i in range(len(str1)):
        res[str1[i]] = 0
    for i in str2:
        if i in res:
            l += 1   
    return l

class Solution:
    def numJewelsInStones(self, jewels: str, stones: str) -> int:
        return checker(jewels, stones)
        
  ```
