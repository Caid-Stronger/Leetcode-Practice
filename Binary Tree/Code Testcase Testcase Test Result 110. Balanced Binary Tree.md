![image](https://github.com/user-attachments/assets/f903ba59-5988-41cb-b101-6169b3446753)
![image](https://github.com/user-attachments/assets/b3a741c8-432d-4bff-9a11-a5c5f7861d3c)

Python Code 
```
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def isBalanced(self, root: Optional[TreeNode]) -> bool:
        if self.get_height(root) != -1: 
            return True 
        else: 
            return False 

    def get_height(self, cur): 
        if not  cur: 
            return 0 

        if (left_height := self.get_height(cur.left)) == -1: 
            return -1 
        if (right_height := self.get_height(cur.right)) == -1: 
            return -1 c
        if abs(left_height - right_height) > 1:
            return -1 
        else: 
            return 1 + max(left_height, right_height)     

```

