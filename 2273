class Solution {
public:
    static array<int, 26> freq(string& s){
        array<int, 26> ans{};
        for(char c: s){
            ans[c-'a']++;
        }
        return ans;
    }
    static vector<string> removeAnagrams(vector<string>& words) {
        int n=words.size(), l=0, r=1;
        vector<string> ans={words[0]};
        array<int, 26> f0=move(freq(words[0]));
        for( ; r<n; r++){
            string s=words[r];
            auto x=move(freq(s));
            if (f0!=x){
                ans.push_back(s);
                l=r;
                f0=x;
            }
        }
        return ans;
    }
};
auto init = []()
{ 
    ios::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
    return 'c';
}();
