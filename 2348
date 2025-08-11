class Solution {
public:
    vector<int> productQueries(int n, vector<vector<int>>& queries) {
        // vector<int> power;
      vector<int> power;
        int temp = n;
        int i = 0;

        while (temp > 0) {
            int curr = pow(2, i);
            if (temp % 2 == 1) {
                power.push_back(curr);
            }
            temp /= 2;
            ++i;
        }
        // int product =1;
        // vector<int> result;
         int mod = 1e9 + 7;
        vector<int> result;
        for (auto& q : queries) {
            int product = 1;
            for (int i = q[0]; i <= q[1]; ++i) {
                product = (1LL * product * power[i]) % mod;
            }
            result.push_back(product);
        }

        return result;
    }




    
};
