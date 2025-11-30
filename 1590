class Solution {
public:
    int minSubarray(vector<int>& nums, int p) {
        long total = 0;
        for (int x : nums) total += x;

        long target = total % p;
        if (target == 0) return 0;

        unordered_map<int, int> mp;
        mp[0] = -1;

        long prefix = 0;
        int res = nums.size();

        for (int i = 0; i < nums.size(); i++) {
            prefix = (prefix + nums[i]) % p;
            int need = (prefix - target + p) % p;

            if (mp.count(need))
                res = min(res, i - mp[need]);

            mp[(int)prefix] = i;
        }

        return res == nums.size() ? -1 : res;
    }
};
