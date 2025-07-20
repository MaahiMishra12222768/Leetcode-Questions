class Solution {
public:
    struct Node {
        map<string, Node*> children;
        bool deleted = false;
    };

    void insert(Node* root, const vector<string>& path) {
        Node* node = root;
        for (const string& name : path) {
            if (!node->children.count(name)) {
                node->children[name] = new Node();
            }
            node = node->children[name];
        }
    }

    string encode(Node* node, unordered_map<string, vector<Node*>>& map) {
        if (node->children.empty()) return "()";
        vector<string> parts;
        for (auto& [key, child] : node->children) {
            parts.push_back(key + encode(child, map));
        }
        sort(parts.begin(), parts.end());
        string sign = "(" + accumulate(parts.begin(), parts.end(), string()) + ")";
        map[sign].push_back(node);
        return sign;
    }

    void markDuplicates(unordered_map<string, vector<Node*>>& map) {
        for (auto& [sign, nodes] : map) {
            if (nodes.size() > 1) {
                for (Node* node : nodes) {
                    node->deleted = true;
                }
            }
        }
    }

    void collect(Node* node, vector<string>& path, vector<vector<string>>& res) {
        for (auto& [key, child] : node->children) {
            if (child->deleted) continue;
            path.push_back(key);
            res.push_back(path);
            collect(child, path, res);
            path.pop_back();
        }
    }

    vector<vector<string>> deleteDuplicateFolder(vector<vector<string>>& paths) {
        Node* root = new Node();

        for (const auto& path : paths) {
            insert(root, path);
        }

        unordered_map<string, vector<Node*>> map;
        encode(root, map);
        markDuplicates(map);

        vector<vector<string>> res;
        vector<string> curr;
        collect(root, curr, res);
        return res;
    }
};
