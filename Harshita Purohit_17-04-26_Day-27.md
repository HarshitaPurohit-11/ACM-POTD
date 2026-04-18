POTD DAY 27
DATE: 17-04-2026

QUESTION:
Diameter of Binary Tree

SOLUTION:
class Solution {
public:
    int diameter=0;

    int height(TreeNode* node) {
        if (node==nullptr) return 0;

        int left=height(node->left);
        int right=height(node->right);

        diameter=max(diameter, left+right);

        return 1+max(left,right);
    }

    int diameterOfBinaryTree(TreeNode*root) {
        height(root);
        return diameter;
    }
};

ALGORITHM:

1. Initialize diameter = 0
2. Use a recursive function height(node):
        If node is NULL, return 0
        Recursively get:
                left = height(node->left)
                right = height(node->right)
        Update: diameter = max(diameter, left + right)
        Return: 1 + max(left, right)
3. Call height(root)
4. Return diameter


COMPLEXITY:

Time Complexity
O(n) : each node is visited once

Space Complexity
O(h) : recursion stack (h=height of tree)

SCREENSHOTS:

<img width="1366" height="768" alt="Screenshot (1082)" src="https://github.com/user-attachments/assets/1e78e5cc-9181-45a9-a763-91a09d2f9d4d" />
<img width="1366" height="768" alt="Screenshot (1081)" src="https://github.com/user-attachments/assets/a4ac53ac-80a5-4a9d-82bd-d9b5bb5b2396" />
