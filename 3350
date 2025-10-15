class Solution {
public:
    static int maxIncreasingSubarrays(vector<int>& nums) {
        const int n=nums.size();
        int len=1, prev=0, k=0;
        for(int i=1; i<n; i++){
            if(nums[i]>nums[i-1]) len++; 
            else{
                k=max({k, len/2, min(len, prev)}); 
                prev=len;
                len=1;
            }
        }
        return max({k, len/2, min(len, prev)});
    }
};


auto init = []()
{ 
    ios::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
    return 'c';
}();
