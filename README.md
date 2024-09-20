# Symmetric-Tree

This solution checks whether a given binary tree is a mirror of itself, i.e., symmetric around its center. A tree is symmetric if the left and right subtrees are mirror images of each other. The task involves determining whether the tree satisfies this property by comparing corresponding nodes in the left and right subtrees.

Approach:
Recursively compare the left and right subtrees to ensure they are mirror images of each other.
Alternatively, an iterative approach using a queue can be employed to compare nodes level by level.
The solution operates in O(n) time, where n is the number of nodes in the tree.

class Solution:
    def isSymmetric(self, root: Optional[TreeNode]) -> bool:
        
        def is_mirror(n1, n2): 
            if not n1 and not n2:
                return True
            
            if not n1 or not n2:
                return False
            
            return n1.val == n2.val and is_mirror(n1.left, n2.right) and is_mirror(n1.right, n2.left)
        
        return is_mirror(root.left, root.right)
