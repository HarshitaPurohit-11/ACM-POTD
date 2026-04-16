POTD DAY 26
DATE: 26-04-2026

QUESTION:
Invert Binary Tree

SOLUTION:
class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if (root==nullptr) return nullptr;

        TreeNode* temp=root->left;
        root->left=root->right;
        root->right=temp;

        invertTree(root->left);
        invertTree(root->right);

        return root;
    }
};

COMPLEXITY:
Time Complexity
O(n) → visit each node once
Space Complexity
O(h) → recursion stack (h = height of tree)


ALGORITHM:
1. If root is NULL, return NULL
2. Swap root->left and root->right
3. Recursively invert left and right subtrees
4. Return root

SCREENSHOT:
<img width="1366" height="768" alt="Screenshot (1068)" src="https://github.com/user-attachments/assets/019429e8-fd30-4bd4-9074-0f97f48bb032" />
