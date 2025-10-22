class Solution {
public:
    int maxFrequency(vector<int>& nums, int k, int numOperations) {
        sort(nums.begin(),
             nums.end()); // Sort the array for sliding window approach

        int n = nums.size();
        int left1 = 0,
            right1 = 0;       // Window pointers for first frequency calculation
        int windowCount1 = 0; // Count of elements within [num - k, num + k]
        int maxFreq = 0;      // Final answer (maximum frequency)
        int left2 = 0;        // Second window left pointer for extended range
        int windowCount2 = 0; // Count of elements within [num - 2k, num]
        int sameValueCount = 0; // Frequency of current number
        int prevValue = -1;     // Previous number for counting duplicates

        for (auto num : nums) {
            // Update count of consecutive same numbers
            if (num == prevValue)
                sameValueCount++;
            else {
                prevValue = num;
                sameValueCount = 1;
            }

            // Shrink window1 if left element is out of range [num - k, num + k]
            while (nums[left1] < num - k) {
                windowCount1--;
                left1++;
            }

            // Expand window1 to include all elements <= num + k
            while (right1 < n && nums[right1] <= num + k) {
                windowCount1++;
                right1++;
            }

            // Maximize frequency by replacing up to numOperations elements
            maxFreq =
                max(maxFreq, sameValueCount + min(windowCount1 - sameValueCount,
                                                  numOperations));

            // Update secondary window for range [num - 2k, num]
            windowCount2++;
            while (nums[left2] < num - 2 * k) {
                windowCount2--;
                left2++;
            }

            // Consider extending range fully within 2*k window
            maxFreq = max(maxFreq, min(windowCount2, numOperations));
        }

        return maxFreq;
    }
};
