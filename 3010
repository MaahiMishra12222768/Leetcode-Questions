class Solution {
public:
    int minimumCost(vector<int>& A) {
        int a = 51, b = 51;

        for (int i = 1; i < A.size(); i++) {
            if (A[i] < a) {
                b = a;
                a = A[i];
            } else if (A[i] < b)
                b = A[i];

            if (a == 1 && b == 1) break;
        }

        return A[0] + a + b;
    }
};
