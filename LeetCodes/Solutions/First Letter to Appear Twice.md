Code

```python
class Solution:
    def repeatedCharacter(self, s: str) -> str:
        hashmap = set()
        for char in s:
            if char in hashmap:
                return char
            else:
                hashmap.add(char)
```
