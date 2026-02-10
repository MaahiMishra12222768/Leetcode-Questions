class Solution {
public:
    inline static uint32_t seen[100001] = {};
    inline static uint32_t leet = 0;
    int longestBalanced(vector<int>& nums) {
        leet++;
        int n = nums.size();
        int res = 0;

        for (int i = 0; i < n && n - i > res; i++) {
            int A[2] = {0, 0};
            uint32_t marker = (leet << 16) | (uint32_t)(i + 1);
            for (int j = i; j < n; j++) {
                int val = nums[j];
                if (seen[val] != marker) {
                    seen[val] = marker;
                    A[val & 1]++;
                }
                if (A[0] == A[1])
                    res = max(res, j - i + 1);
            }
        }

        return res;
    }
};
