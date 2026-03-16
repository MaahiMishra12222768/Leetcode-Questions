unsigned diag[100][51], antid[100][51]; 
const int OFFSET=50;

class Solution {
public:
    static inline int rhombusSum(int i, int j, int d, vector<vector<int>>& grid) {
        if (d==0) return grid[i][j];
        
        const int l=j-d, r=j+d, u=i-d, b=i+d ;
        
        // Diagonals with corner (\) 
        const int i0=u-j+OFFSET, i1=i-l+OFFSET;
        int sum=diag[i0][r+1]-diag[i0][j];
        sum+=diag[i1][j+1]-diag[i1][l];
        
        // Anti-diagonals without corners (/) 
        const int j0=u+j, j1=b+j;
        sum+=antid[j0][i]-antid[j0][u+1];
        sum+=antid[j1][b]-antid[j1][i+1];

        return sum;
    }

    static vector<int> getBiggestThree(vector<vector<int>>& grid) {
        const int m=grid.size(), n=grid[0].size();
    //  no need for reset    
    //    memset(diag, 0, sizeof(diag));
    //    memset(antid, 0, sizeof(antid));

        for (int i=0; i< m; i++) {
            for (int j = 0; j < n; j++) {
                const int i0=i-j+OFFSET, j0=i+j;
                const int x=grid[i][j];
                // diag over j, antid over i
                diag[i0][j+1]=diag[i0][j]+x;
                antid[j0][i+1]=antid[j0][i]+x;
            }
        }

        int dM=min(m, n)/2; 
        vector<int> x(3, -1);
        for (int d=0; d<=dM; d++) {
            for (int i=d; i<m-d; i++) {
                for (int j=d; j<n-d; j++) {
                    const int y=rhombusSum(i, j, d, grid);

                    // Skip if y is already in our top 3 
                    if (y==x[0] || y==x[1] || y==x[2]) continue;

                    if (y>x[0]) {
                        x[2]=x[1]; x[1]=exchange(x[0], y);
                    }
                    else if (y>x[1]) x[2]=exchange(x[1], y);
                    else if (y>x[2]) x[2]=y;
                }
            }
        }
        for(int i=2; i>=0; i--) 
            if (x[i]==-1) x.pop_back();
        return x;
    }
};
