Code

```Python
class Solution:
    def isValidBST(self, root: Optional[TreeNode]) -> bool:
        return self.checker(float('-inf'), float('inf'), root)
    def checker(self, lo, hi, root):
        if root == None:
            return True
        elif root.val <= lo or root.val >= hi:
            return False
        else:
            return self.checker(lo, root.val, root.left) and self.checker(root.val, hi, root.right)
```
