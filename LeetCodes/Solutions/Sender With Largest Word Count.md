Code

```Python
class Solution:
    def largestWordCount(self, messages: List[str], senders: List[str]) -> str:
        hashmap = {}
            
        for idx in range(len(messages)):
            temp = 1
            for char in messages[idx]:
                if char.isspace():
                    temp += 1
            
            if senders[idx] in hashmap:
                hashmap[senders[idx]] += temp
                
            else:
                hashmap[senders[idx]] = temp
        
        res_key = ''
        res_val = 0
        for key, val in hashmap.items():
            if val > res_val:
                res_val = val
                res_key = key
            elif val == res_val:
                res_key = max(res_key, key)
                
        return res_key
        
```
