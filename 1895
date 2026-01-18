const int N = 51;
int rowSum[N][N], colSum[N][N], diag[N][N], antidiag[N][N];
class Solution {
public:
    int r, c;
    inline bool isMagic(int k) {
        for (int i = 0; i <= r - k; i++) {
            for (int j = 0; j <= c - k; j++) {
                int sum = diag[i + k][j + k] - diag[i][j];
                int antiD = antidiag[i + k][j] - antidiag[i][j + k];
                bool match = (sum == antiD);

                for (int m = 0; m < k && match; m++) {
                    match = (sum == rowSum[i + m + 1][j + k] -
                                        rowSum[i + m + 1][j] &&
                             sum == colSum[i + k][j + m + 1] -
                                        colSum[i][j + m + 1]);
                }

                if (match)
                    return 1;
            }
        }
        return 0;
    }

    int largestMagicSquare(vector<vector<int>>& grid) {
        r = grid.size(), c = grid[0].size();
        rowSum[0][0] = colSum[0][0] = diag[0][0] = antidiag[0][0] = 0;

        for (int i = 0; i < r; i++) {
            for (int j = 0; j < c; j++) {
                int x = grid[i][j];
                rowSum[i + 1][j + 1] = rowSum[i + 1][j] + x;
                colSum[i + 1][j + 1] = colSum[i][j + 1] + x;
                diag[i + 1][j + 1] = diag[i][j] + x;
                antidiag[i + 1][j] = antidiag[i][j + 1] + x;
            }
        }

        for (int k = min(r, c); k >= 2; k--) {
            if (isMagic(k))
                return k;
        }

        return 1;
    }
};

auto init = []() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    cout.tie(nullptr);
    return 'c';
}();
