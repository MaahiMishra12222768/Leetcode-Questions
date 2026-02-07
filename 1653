class Solution {
public:
    static int minimumDeletions(string& s) {
        int cnt=0, ans=0;
        for(char c: s)
            ans=min(ans+=(c=='a'), cnt+=(c=='b'));
        return ans;
    }
};


auto init = []() {
    ios::sync_with_stdio(false);
    cin.tie(nullptr);
    cout.tie(nullptr);
    return 'c';
}();
