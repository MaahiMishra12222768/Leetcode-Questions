// with packing data into uint64
using u16=unsigned short;
using u64=unsigned long long;
using info=pair<unsigned, u16>; // (distance, vertex)

const int N=50000;
vector<u64> adj[N];
unsigned dist[N];

class Solution {
public:
    static inline u64 pack(int w, int v){ return ((u64)w<<16)|v; }
    static inline void build_adj(int n, vector<vector<int>>& edges) {
        for (int i=0; i<n; i++) adj[i].clear();

        for (const auto& e : edges) {
            int w=e[2], u=e[0], v=e[1];
            adj[u].push_back(pack(w, v));     // normal edge
            adj[v].push_back(pack(2*w, u));   // reversed edge
        }
    }

    static int minCost(int n, vector<vector<int>>& edges) {
        build_adj(n, edges);

        priority_queue<u64, vector<u64>, greater<>> pq;

        memset(dist, 255, sizeof(unsigned)*n);// fill with UINT_MAX

        dist[0]=0;
        pq.emplace(0);

        while (!pq.empty()) {
            u64 data=pq.top();
            int d=data>>16, u=data&USHRT_MAX;
            pq.pop();

            if (d>dist[u]) continue;
            if (u==n-1) return d;

            for (auto& wv : adj[u]) {
                int w=wv>>16, v=wv&USHRT_MAX;
                unsigned d2=d+w;

                if (d2<dist[v]) {
                    dist[v]=d2;
                    pq.push(pack(d2, v));
                }
            }
        }
        return -1;
    }
};
