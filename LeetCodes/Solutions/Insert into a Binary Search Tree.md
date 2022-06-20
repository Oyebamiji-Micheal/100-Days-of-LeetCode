Code

```Python
class Solution:
    def insertIntoBST(self, root: Optional[TreeNode], val: int) -> Optional[TreeNode]:
        if root == None:
            return TreeNode(val)
        
        def checker(root, val):
        
            if val > root.val:
                if root.right == None:
                    root.right = TreeNode(val)
                else:
                    checker(root.right, val)

            else:
                if root.left == None:
                    root.left = TreeNode(val)
                else:
                    checker(root.left, val)
               
        checker(root, val)

        return root
```
