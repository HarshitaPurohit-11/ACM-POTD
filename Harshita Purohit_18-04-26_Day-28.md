POTD DAY 28
DATE : 18-04-2026

QUESTION:
Subtree of Another Tree

SOLUTION:
class Solution {
public:
    bool isSame(TreeNode* a,TreeNode*b) {
        if (!a && !b) return true;
        if (!a || !b) return false;
        if (a->val != b->val) return false;

        return isSame(a->left, b->left) && isSame(a->right,b->right);
    }

    bool isSubtree(TreeNode* root, TreeNode* subRoot) {
        if (!root) return false;

        if (isSame(root,subRoot)) return true;

        return isSubtree(root->left,subRoot) || 
               isSubtree(root->right,subRoot);
    }
};

ALGORITHM:

1. Traverse each node of root
2. At each node:
          Check if subtree starting here is identical to subRoot (isSame)
3. If match found -> return true
4. Else recursively check left and right subtrees
5. If no match anywhere -> return false

COMPLEXITY:
Time Complexity
O(nxm) (n=nodes in root,m=nodes in subRoot)

Space Complexity
O(h) recursion stack (h=height of tree)

SCREENSHOT:
<img width="1366" height="768" alt="Screenshot (1085)" src="https://github.com/user-attachments/assets/db516262-599b-43c3-8257-931ec2790042" />
