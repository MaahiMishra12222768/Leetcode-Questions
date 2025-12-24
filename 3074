class Solution {
public:
    int minimumBoxes(vector<int>& apple, vector<int>& capacity) {
        int hash[51] = {0}, ans = 0, sum = 0;
        for(int i = 0; i < apple.size(); i++) sum += apple[i];
        for(int i = 0; i < capacity.size(); i++) hash[capacity[i]]++;
        for(int i = 50; i > 0; i--) {
            while(hash[i] > 0) {
                sum -= i;
                hash[i]--;
                ans++;
                if(sum <= 0) return ans;
            }
        }
        return ans;
    }
};
