const int mod=1e9+7;
using matrix=vector<vector<int>>;
const matrix I={
    {1, 0},
    {0, 1}
};
const matrix M={
    {3, 2},
    {2, 2}
};

static matrix operator*(const matrix& A, const matrix& B) {
    const int m=A.size(), n=A[0].size(), p=B[0].size();
    matrix C(m, vector<int>(p, 0));
    for (int i=0; i<m; i++) {
        for (int k=0; k<n; k++) {
            for (int j = 0; j<p; j++) {
                C[i][j]=(C[i][j]+1LL*A[i][k]*B[k][j])%mod;
            }
        }
    }
    return C;
}
// Matrix exponentiation (LSBF)
static matrix pow(const matrix& M, int n) {
    matrix ans = I, P=M;
    for (; n > 0; n >>= 1) {
        if (n & 1)
            ans = ans * P;
        P = P * P;
    }
    return ans;
}
class Solution {
public:
    int numOfWays(int n) {
        if (n==1) return 12;
        matrix A=pow(M, n-1);
        return 6LL*(1LL*A[0][0]+A[0][1]+A[1][0]+A[1][1])%mod;
    }
};
