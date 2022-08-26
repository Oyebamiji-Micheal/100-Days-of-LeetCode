Code

```Python

def helper(image, sr, sc, x, newcolor):
    image[sr][sc] = str(newcolor)
    directions = [(sr-1, sc), (sr+1, sc), (sr, sc-1), (sr, sc+1)]

    for row, column in directions:
        if row >= 0 and column >= 0 and row < len(image) and column < len(image[0]) and image[row][column] == x:
            helper(image, row, column, x, newcolor)

def checker(image, sr, sc, newcolor):
    x = image[sr][sc]
    
    helper(image, sr, sc, x, newcolor)        
    return image


class Solution:
    def floodFill(self, image: List[List[int]], sr: int, sc: int, newColor: int) -> List[List[int]]:
        if __name__ == '__main__':
            return checker(image, sr, sc, newColor)
            
```
