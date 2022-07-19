Code
```Python
class Solution:
    def checkStraightLine(self, coordinates: List[List[int]]) -> bool:
        if len(coordinates) == 1:
            return False
        if len(coordinates) == 2:
            return True
        
        def gradient(point1, point2):
            if point2[0] - point1[0] == 0:
                return 'inf'
            return (point2[1] - point1[1]) / (point2[0] - point1[0])
        
        m = gradient(coordinates[0], coordinates[1])
       
        for i in range(2, len(coordinates)):
            if gradient(coordinates[0], coordinates[i]) != m:
                return False
            
        return True
```
