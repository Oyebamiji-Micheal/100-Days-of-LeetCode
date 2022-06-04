Code
```Python
class Solution:
    def checkIfExist(self, arr: List[int]) -> bool:
        r = {}
        
        for i in arr:
            if i/2 in r or i*2 in r:
                return True
            else:
                r[i] = 0

        return False
```
