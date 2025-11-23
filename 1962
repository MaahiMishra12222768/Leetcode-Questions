int dp[40000][3];

class Solution {
public:
    static int f(int i, int mod, vector<int>& nums){
        if (i<0) return mod==0? 0:-1e9; 
        if (dp[i][mod]!=-1) return dp[i][mod];

        const int x=nums[i];
        int modPrev=mod-x%3; modPrev+=(-(modPrev<0)) & 3;

        int take=x+f(i-1, modPrev, nums);
        int skip=f(i-1, mod, nums);

        return dp[i][mod]=max(take, skip);
    }

    static int maxSumDivThree(vector<int>& nums) {
        const int n=nums.size();
        memset(dp, -1, sizeof(int)*n*3);
        return max(0, f(n-1, 0, nums));
    }
};
