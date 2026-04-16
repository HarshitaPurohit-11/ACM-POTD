POTD Day 25
Date: 15-04-2026

QUESTION:
Maximum Depth of Binary Tree

SOLUTION: 
class Solution {
public:
    int maxDepth(TreeNode* root) {
        if (root==nullptr) return 0;

        int leftDepth=maxDepth(root->left);
        int rightDepth=maxDepth(root->right);

        return 1+max(leftDepth, rightDepth);
    }
};

COMPLEXITY:
Time: O(n) → visit each node once
Space: O(h) → recursion stack (h = height of tree)

ALGORITHM: 

1. If root is NULL, return 0
2. Recursively find depth of left and right subtree
3. Return 1+ max(left,right)



SCREENSHOT:

<img width="1366" height="768" alt="Screenshot (1067)" src="https://github.com/user-attachments/assets/ae7dc42f-81f3-4d50-91d1-5e6d4069f649" />
