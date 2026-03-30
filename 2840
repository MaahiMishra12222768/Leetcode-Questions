class Solution {
public:
    static bool checkStrings(string& s1, string& s2) {
        array<array<int, 26>, 2> freq{};
        constexpr array<array<int, 26>, 2> zero{};
        const int n=s1.size();
        for(int i=0; i<n; i++){
            bool iOdd=i&1;
            freq[iOdd][s1[i]-'a']++;
            freq[iOdd][s2[i]-'a']--;
        }
        return freq==zero;
    }
};

auto init = []() {
    ios::sync_with_stdio(0);
    cin.tie(0);
    cout.tie(0);
    return 'c';
}();
