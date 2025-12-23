class Solution {
public:
    int maxTwoEvents(vector<vector<int>>& events) {
        int n = events.size();
        sort(events.begin(), events.end());
        vector<int> maxSuffix(n);
        maxSuffix[n - 1] = events[n - 1][2];

        for (int i = n - 2; i >= 0; i--) {
            maxSuffix[i] = max(maxSuffix[i + 1], events[i][2]);
        }

        int ans = 0;

        for (int i = 0; i < n; i++) {
            int currValue = events[i][2];
            ans = max(ans, currValue);

            int nextStart = events[i][1] + 1;
            int low = i + 1, high = n - 1, idx = -1;
            while (low <= high) {
                int mid = (low + high) / 2;
                if (events[mid][0] >= nextStart) {
                    idx = mid;
                    high = mid - 1;
                } else {
                    low = mid + 1;
                }
            }

            if (idx != -1) {
                ans = max(ans, currValue + maxSuffix[idx]);
            }
        }

        return ans;
    }
};
