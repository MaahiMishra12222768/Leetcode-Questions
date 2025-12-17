struct Data{
    long long profit=0, buy=0, sell=0;
    Data(long long profit=0, long long buy=0, long long sell=0):
        profit(profit), buy(buy), sell(sell) {}
};
Data dp[1000][501];
class Solution {
public:
    static long long maximumProfit(vector<int>& prices, int k) {
        const int x0=prices[0];
        const int n=prices.size();
        fill(dp[0], dp[0]+(k+1), Data(0, -x0, x0));
        for(int i=1; i<n; i++){
            const int x=prices[i];
            for(int t=1; t<=k; t++){
                auto [p, b, s]=dp[i-1][t];
                const long long prevP=dp[i-1][t-1].profit;
                p=max(p, max(b+x, s-x));
                b=max(b, prevP-x);
                s=max(s, prevP+x);
                dp[i][t]=Data(p, b, s);
            }
        }
        return dp[n-1][k].profit;
    }
};
