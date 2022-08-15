Code

```Python
class Solution:
    def checkIfPangram(self, sentence: str) -> bool:
        hashmap = set();
        for i in sentence:
            if i not in hashmap:
                hashmap.add(i);
        return len(hashmap)==26;
        
```
