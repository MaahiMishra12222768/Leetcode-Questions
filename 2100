class Solution {
public:
    long long getDescentPeriods(vector<int>& prices) {
        long long ans = 1, count = 1;
        for(int i = 0; i < prices.size() - 1; i++) {
            if(prices[i] == prices[i + 1] + 1) count++;
            else count = 1;
            ans += count;
        }
        return ans;
    }
};
