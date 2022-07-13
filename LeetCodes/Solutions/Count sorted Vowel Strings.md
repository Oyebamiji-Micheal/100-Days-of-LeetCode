Code
```Python

from itertools import combinations_with_replacement

class Solution:
    def countVowelStrings(self, n: int) -> int:
        return len(list(combinations_with_replacement('aeiou', n)))
```
