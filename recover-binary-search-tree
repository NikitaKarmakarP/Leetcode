/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode() : val(0), left(nullptr), right(nullptr) {}
 *     TreeNode(int x) : val(x), left(nullptr), right(nullptr) {}
 *     TreeNode(int x, TreeNode *left, TreeNode *right) : val(x), left(left), right(right) {}
 * };
 */

class Solution {
public:
    TreeNode* firstMistake = nullptr;
    TreeNode* secondMistake = nullptr;
    TreeNode* pre = nullptr;

    void recoverTree(TreeNode* root) {
        pre = new TreeNode(INT_MIN);  // Initialize pre with a minimum value node
        inorder(root);  // Perform in-order traversal to find the mistakes
        swap(firstMistake->val, secondMistake->val);  // Swap the values of the mistaken nodes
    }

    void inorder(TreeNode* root) {
        if (root == nullptr)
            return;

        inorder(root->left);  // Traverse the left subtree

        // Detect the first mistake
        if (firstMistake == nullptr && root->val < pre->val)
            firstMistake = pre;

        // Detect the second mistake
        if (firstMistake != nullptr && root->val < pre->val)
            secondMistake = root;

        pre = root;  // Update pre to the current node

        inorder(root->right);  // Traverse the right subtree
    }
};
