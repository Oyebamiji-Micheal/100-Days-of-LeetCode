Code
```Python
class Solution:
    def largestAltitude(self, gain: List[int]) -> int:
        N = len(gain)
        for i in range(1, N):
            gain[i] = gain[i] + gain[i-1]        
        
        if gain[0] < 0:
            gain[0] = 0
        
        return max(gain)
        
```
