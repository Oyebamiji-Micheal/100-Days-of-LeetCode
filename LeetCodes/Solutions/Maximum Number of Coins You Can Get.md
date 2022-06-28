### Explanation (Greedy Approach)
 - The problem does not involve dynamic programming but greedy approach.
 - Since we know for sure Alice will take the maximum in any pile and Bob the smallest, we can consider the whole array by removing the maximum and minimum.
 - We then need to pick the maximum number from the remaining array and add it to our coins.
 - We repeat this process until we have picked all 'maximums' and 'minimums'. 

Code
```
class Solution:
    def maxCoins(self, piles: List[int]) -> int:
        piles.sort(reverse=True)
        s = 0
        i = 1
        N = len(piles)
        count = 0
        
        while  count < N - i + 1:
            s += piles[i]
            i += 2 
            count += 1
            
        return s
        
        
    ```
