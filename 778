//Greedy & Union Find
class UnionFind {    
    vector<int> root, rank;
public:
    UnionFind(int n) : root(n), rank(n) {
        rank.assign(n, 1);
        iota(root.begin(), root.end(), 0);
    }

    int Find(int x) {
        return (x == root[x])?x:root[x]=Find(root[x]);
    }

    void Union(int x, int y) {
        x= Find(x), y= Find(y);
        if (x == y)  return;
        if (rank[x] > rank[y]) swap(x, y);   
        root[x] = y;
        if (rank[x]==rank[y]) rank[y]++;
    }
};
class Solution {
public:
    using int3=tuple<int, int, int>; // (wt, v, w)
    int n;
    int to1D(int i, int j){
        return i*n+j;
    }
    int swimInWater(vector<vector<int>>& grid) {
        n=grid.size();
        if (n==1) return 0;// edge case
        //Build edges (wt, v, w)
        vector<int3> edges;
        for(int i=0; i<n; i++){
            for(int j=0; j<n; j++){
                if (i<n-1){
                    int wt=max(grid[i][j], grid[i+1][j]);
                    edges.emplace_back(wt, to1D(i, j), to1D(i+1, j));
                }
                if (j<n-1){
                    int wt=max(grid[i][j], grid[i][j+1]);
                    edges.emplace_back(wt, to1D(i, j), to1D(i, j+1));
                }
            }
        }
        sort(edges.begin(), edges.end());
        int V=n*n;
        UnionFind uf(V);
        for(auto& [wt, v, w]: edges){
            if (uf.Find(v)!=uf.Find(w))
                uf.Union(v, w);
            if (uf.Find(0)==uf.Find(V-1))
                return wt;
        }
        return 0;
    }
};
