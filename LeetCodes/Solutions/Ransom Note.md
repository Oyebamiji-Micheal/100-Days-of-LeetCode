Code
```Python
def checker(ransom_note, magazine):
    for i in ransom_note:
        if i not in magazine:
            return False 
        else:
            magazine = magazine.replace(i, '', 1)
    return True

class Solution:
    def canConstruct(self, ransomNote: str, magazine: str) -> bool:
        if __name__ == "__main__":
            return checker(ransomNote, magazine)
```
