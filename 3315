class Solution {
public:
    vector<int> minBitwiseArray(vector<int>& nums) {
        vector<int> ans;
        for(int n : nums) {
            if(n != 2) ans.push_back(n - ((n + 1) & (-n - 1)) / 2);
            else ans.push_back(-1);
        }   
        return ans;
    }
};
