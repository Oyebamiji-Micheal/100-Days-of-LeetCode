Code

```Python
def checker(height):
    left = 0
    right = len(height)-1
    area = 0

    while left < right:
        area = max(area, min(height[left], height[right])*(right - left))

        if height[left] >= height[right]:
            right -= 1
        
        else:
            left += 1
         
    return area 

class Solution:
    def maxArea(self, height: List[int]) -> int:
        if __name__ == '__main__':
            return checker(height)
```
