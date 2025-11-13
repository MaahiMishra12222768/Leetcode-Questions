// branchless version
class Solution {
public:
    static int maxOperations(string& s) {
        int cnt=0, n=s.size(), cnt1=(s[0]=='1');
        for(int i=1; i<n; i++){
            cnt1+=s[i]=='1';
            cnt+=(-(s[i]=='0' &&s[i-1]=='1'))&cnt1;
        }
        return cnt;
    }
};
