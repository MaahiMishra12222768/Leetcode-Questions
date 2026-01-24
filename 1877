class Solution {
public:
    int minPairSum(vector<int>& nums) {
        int min = INT_MAX, max = INT_MIN;
        int freq[100001] = {0};
        for(int i = 0; i < nums.size(); i++) {
            if(nums[i] < min) min = nums[i];
            if(nums[i] > max) max = nums[i];
            freq[nums[i]]++;
        }
        int max_sum = 0, l = min, r = max;
        while(l <= r) {
            if(freq[l] == 0) l++;
            else if(freq[r] == 0) r--;
            else {
                max_sum = fmax(max_sum, l + r);
                freq[l]--;
                freq[r]--;
            }
        }
        return max_sum;
    }
};
