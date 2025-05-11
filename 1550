class Solution {
public:
    bool threeConsecutiveOdds(vector<int>& arr) {
        int consecutiveOdds = 0;

        // Loop through each element in the array
        for (int i = 0; i < arr.size(); i++) {
            // Increment the counter if the number is odd,
            // else reset the counter
            if (arr[i] % 2 == 1) {
                consecutiveOdds++;
            } else {
                consecutiveOdds = 0;
            }

            // Check if there are three consecutive odd numbers
            if (consecutiveOdds == 3) {
                return true;
            }
        }

        return false;
    }
};
