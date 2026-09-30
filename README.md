# Minimum-Distance-Between-BST-Nodes
# Definition for a binary tree node.
# class TreeNode:
#     def __init__(self, val=0, left=None, right=None):
#         self.val = val
#         self.left = left
#         self.right = right
class Solution:
    def minDiffInBST(self, root: TreeNode | None) -> int:
        r=[]
        def add(root,r):
            if root is None:
                return 
            r.append(root.val)
            add(root.left,r)
            add(root.right,r)
        add(root,r)
        r.sort()
        a=float('inf')
        for i in range(1,len(r)):
            a=min(a,r[i]-r[i-1])
        return a
