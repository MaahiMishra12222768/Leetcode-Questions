int Sum[2][1001];
int seenX[2][1001];
class Solution {
public:
    static int numberOfSubmatrices(vector<vector<char>>& grid) {
        const int r=grid.size(), c=grid[0].size();
        memset(Sum[0], 0, (c+1)*sizeof(int));
        memset(Sum[1], 0, (c+1)*sizeof(int));
        memset(seenX[0], 0, (c+1)*sizeof(int));
        memset(seenX[1], 0, (c+1)*sizeof(int));
        int cnt=0;
        for(int i=0; i<r; i++){
            bool iEven=(i&1)==0, prv=!iEven;
            for(int j=0; j<c; j++){
                const char c=grid[i][j];
                bool isX=c=='X', isY=c=='Y';
                Sum[iEven][j+1]=isX-isY+Sum[iEven][j]+Sum[prv][j+1]-Sum[prv][j];
                seenX[iEven][j+1]=isX+seenX[iEven][j]+seenX[prv][j+1]-seenX[prv][j];
                cnt+=((Sum[iEven][j+1]==0) & (seenX[iEven][j+1]>0));
            }
        }
        return cnt;
    }
};
