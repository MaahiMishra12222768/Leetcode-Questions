class Solution {
public:
    using ll = long long;
    ll largestSquareArea(vector<vector<int>>& bl, vector<vector<int>>& tr) {
        int s = 0;
        int n = bl.size();
        for (int i = 0; i < n; i++) {
            for (int j = i + 1; j < n; j++) {
                int minX = max(bl[i][0], bl[j][0]);
                int maxX = min(tr[i][0], tr[j][0]);
                int minY = max(bl[i][1], bl[j][1]);
                int maxY = min(tr[i][1], tr[j][1]);

                if (minX < maxX && minY < maxY) {
                    int len = min(maxX - minX, maxY - minY);
                    s = max(s, len);
                }
            }
        }
        return (ll)s * s;
    }
};
