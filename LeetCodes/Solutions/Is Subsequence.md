Code
```Python

class Solution(object):
    def isSubsequence(self, s, t):
        if not s:
            return True
            
        i = 0
        
        for char in t:
            if char == s[i]:
                i += 1
            if i == len(s):
                break
        return i == len(s)
        
```
