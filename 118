class Solution {
public:
    vector<vector<int>> generate(int numRows) {
        vector<vector<int>> pascal;
        for(int i = 0; i<numRows; i++){
            vector<int> row(i+1, 1);
            for(int j = 1; j< i; j++){
                row[j] = pascal[i-1][j-1] + pascal[i-1][j];
            }
            pascal.push_back(row);
        }
        return pascal;
    }
};
