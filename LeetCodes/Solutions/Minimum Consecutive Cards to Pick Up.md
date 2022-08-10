Code

```Python
class Solution:
    def minimumCardPickup(self, cards: List[int]) -> int:
        res = float('inf')
        hashmap = {}
        for idx, card in enumerate(cards):
            if card in hashmap:
                res = min(res, idx - hashmap[card] + 1)
                hashmap[card] = idx
            else:
                hashmap[card] = idx
                
        if res == float('inf'):
            return -1
        return res
        
```
