class Solution {
public:
    int sumRootToLeaf(TreeNode* root) {
        return dfs(root, 0);
    }

private:
    int dfs(TreeNode* node, int curr) {
        if (!node) return 0;

        curr = curr * 2 + node->val; // append this bit

        if (!node->left && !node->right) // leaf
            return curr;

        return dfs(node->left, curr) + dfs(node->right, curr);
    }
};
