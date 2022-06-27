Code

```Python
class Solution:
    def validMountainArray(self, arr: List[int]) -> bool:
        N = len(arr)
        check = 0

        while check+1 < N and arr[check] < arr[check+1]:
            check += 1

        if check == 0 or check == N-1:
            return False

        while check+1 < N and arr[check] > arr[check+1]:
            check += 1

        return check == N-1
        
```
