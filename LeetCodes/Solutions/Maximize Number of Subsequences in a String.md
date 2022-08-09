Code

```Python
class Solution:
    def maximumSubsequenceCount(self, text: str, pattern: str) -> int:
        if pattern[0] == pattern[1]:
            res = 0
            temp = 1

            for char in text:
                if char == pattern[0]:
                    res += temp
                    temp += 1    
            return res
            
        start = 0
        end = 0
        res = 0
        
        for char in text:
            if char == pattern[0]:
                start += 1
            elif char == pattern[1]:
                end += 1
                res += start
                
                        
        
        return max(start+res, end+res)
        
        
```
