class Solution {
public:
    long long MOD = 1e9 + 7;
    long long ans = 0;

    long long dfs(TreeNode* node) {
        if (!node) return 0;

        node->val += dfs(node->left) + dfs(node->right);
        return node->val;
    }

    int maxProduct(TreeNode* root) {
        long long total = dfs(root);

        queue<TreeNode*> q;
        q.push(root);

        while (!q.empty()) {
            TreeNode* node = q.front();
            q.pop();

            if (!node) continue;

            long long cur = (total - node->val) * node->val;
            ans = max(ans, cur);

            if (node->left) q.push(node->left);
            if (node->right) q.push(node->right);
        }

        return ans % MOD;
    }
};
