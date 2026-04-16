class Solution {
public:
    TreeNode* invertTree(TreeNode* root) {
        if (root == NULL) return NULL;

        // swap left and right
        TreeNode* temp = root->left;
        root->left = root->right;
        root->right = temp;

        // recurse on children
        invertTree(root->left);
        invertTree(root->right);

        return root;
    }
};
