Code

```Python

class Solution:
    def postorderTraversal(self, root: Optional[TreeNode]) -> List[int]:
        if root is None:
            return []
        else:
            return self.postorderTraversal(root.left) + self.postorderTraversal(root.right) + [root.val]
        
```
