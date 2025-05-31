class Solution {
public:
    long long minCost(vector<int>& basket1, vector<int>& basket2) {
        unordered_map<int, int> cnt;
        for (auto c: basket1) cnt[c]++;
        for (auto c: basket2) cnt[c]--;
        vector<int> last;
        for (auto &[k, v]: cnt) {
            // if v is odd, an even distribution is never possible
            if (v % 2) return -1;
            // the count of transferred k is |v|/2
            for (int i = 0; i < abs(v) / 2; ++i)
                last.push_back(k);
        }
        // find the min of two input arrays as the intermediate
        int minx = min(*min_element(basket1.begin(), basket1.end()),
                       *min_element(basket2.begin(), basket2.end()));
        // sort(last.begin(), last.end()) can be used as well
        nth_element(last.begin(), last.begin() + last.size() / 2, last.end());
        return accumulate(last.begin(), last.begin() + last.size() / 2, 0ll, 
            [&](long long s, int x) -> long long { return s + min(2*minx, x); }
        );
    }
};
