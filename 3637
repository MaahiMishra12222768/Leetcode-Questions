class Solution {
public:
    bool isTrionic(vector<int>& nums) {
        int n = nums.size(), i = 0;
        // Phase 1: Up
        while (i + 1 < n && nums[i] < nums[i + 1]) i++;
        if (i == 0 || i == n - 1) return false;
        
        int p = i;
        // Phase 2: Down
        while (i + 1 < n && nums[i] > nums[i + 1]) i++;
        if (i == p || i == n - 1) return false;
        
        // Phase 3: Up
        while (i + 1 < n && nums[i] < nums[i + 1]) i++;
        return i == n - 1;
    }
};
