class Solution {
public:
    int countTrapezoids(vector<vector<int>>& points) {
        unordered_map<int, long long> mp;
        long long sum = 0;
        long long ans = 0;
        const long long MOD = 1e9 + 7;

        // Step 1: Count how many points lie on each horizontal line (same y-coordinate)
        for (int i = 0; i < points.size(); i++) {
            mp[points[i][1]]++;  // y-coordinate as key
        }

        // Step 2: For each y-coordinate, compute number of ways to choose 2 points (nC2)
        // This gives the number of horizontal segments that can form a side of a trapezoid
        for (auto& it : mp) {
            long long count = it.second;
            long long pairs = (count * (count - 1)) / 2;
            sum += pairs;  // Total number of horizontal segments
        }

        // Step 3: Pick two such horizontal lines and multiply their segment counts
        for (auto& it : mp) {
            long long count = it.second;
            long long pairs = (count * (count - 1)) / 2;
            sum -= pairs;             // Remove current count to avoid counting the same pair twice
            ans += pairs * sum;       // Combine current with the rest
        }

        return ans % MOD;
    }
};
