# Binary-Tree-Maximum-Path-Sum
Leetcode Hard sum
class Solution:
    def maxPathSum(self, root: Optional[TreeNode]) -> int:
        def maxgain(node):
            nonlocal maxsum
            if not node:
                return 0
            lg=max(maxgain(node.left),0)
            rg=max(maxgain(node.right),0)
            pnp=node.val+lg+rg
            maxsum=max(maxsum,pnp)
            return node.val+max(lg,rg)
        maxsum=float('-inf')
        maxgain(root)
        return maxsum
