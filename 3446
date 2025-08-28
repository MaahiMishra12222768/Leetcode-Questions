int diag[10];
class Solution {
public:
    static vector<vector<int>> sortMatrix(vector<vector<int>>& grid) {
        const int n=grid.size();
        for(int d=n-2; d>0; d--){
            for(int i=0; i<n-d; i++)
                diag[i]=grid[i][i+d];
            sort(diag, diag+(n-d));
            for(int i=0; i<n-d; i++)
                grid[i][i+d]=diag[i];
        }
        for (int d=0; d<n-1; d++){
            for(int j=0; j<n-d; j++)
                diag[j]=grid[j+d][j];
            sort(diag, diag+(n-d), greater<>());
            for(int j=0; j<n-d; j++)
                grid[j+d][j]=diag[j];
        }
        return grid;
    }
};
