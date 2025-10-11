class Solution {
public:
    long long maximumTotalDamage(vector<int>& power) {
        unordered_map<int, long long> freq;
        for (int p : power) freq[p]++;
        vector<int> keys;
        for (auto& [k, _] : freq) keys.push_back(k);
        sort(keys.begin(), keys.end());
        int n = keys.size();
        vector<long long> dp(n);
        dp[0] = freq[keys[0]] * keys[0];
        for (int i = 1; i < n; i++) {
            long long take = freq[keys[i]] * keys[i];
            int prev = upper_bound(keys.begin(), keys.begin() + i, keys[i] - 3) - keys.begin() - 1;
            if (prev >= 0) take += dp[prev];
            dp[i] = max(dp[i - 1], take);
        }
        return dp[n - 1];
    }
};
