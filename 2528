class Solution {
public:
    static bool check(long long minPower, vector<int> stations, int r, long long k, int n) {
        // power for 1st window
        long long power=reduce(stations.begin(), stations.begin()+r+1, 0LL);

        // sliding window
        for (int i=0; i<n; i++) {
            if (power<minPower) {
                long long need=minPower-power;
                if (need>k) return 0;
                k-=need;

                int pos=min(n-1, i+r);// take right end of window
                stations[pos]+=need;// greedy add
                power+=need;
            }

            if (i>=r)// move left end of window
                power-=stations[i-r];
            if (i+r+1<n) // move right end of window
                power+=stations[i+r+1];
        }
        return 1;
    }

    static long long maxPower(vector<int>& stations, int r, int k) {
        const int n=stations.size();
        long long left=0, right=reduce(stations.begin(), stations.end(), 0LL)+k;
        long long ans=0;

        while (left<=right) {
            long long mid = left+(right-left) / 2;;
            if (check(mid, stations, r, k, n)) {
                ans=mid;
                left=mid+1;
            } 
            else 
                right=mid-1;
        }
        return ans;
    }
};
