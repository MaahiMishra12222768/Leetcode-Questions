class Solution {
public:
    void inorder(TreeNode* node, vector<int>& vals) {
        if(!node) return;
        inorder(node->left, vals);
        vals.push_back(node->val);
        inorder(node->right, vals);
    }
    TreeNode* build(const vector<int>& vals, int l, int r) {
        if(l > r) return nullptr;
        int mid = (l + r) / 2;
        TreeNode* node = new TreeNode(vals[mid]);
        node->left  = build(vals, l, mid - 1);
        node->right = build(vals, mid + 1, r);
        return node;
    }
    TreeNode* balanceBST(TreeNode* root) {
        vector<int> vals;
        inorder(root, vals);
        return build(vals, 0, (int)vals.size() - 1);
    }
};
