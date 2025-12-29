class Solution {
public:
    bool can(int i,string n,string b,unordered_map<string,vector<char>> &mp,unordered_map<string,bool> &me){
        if(b.size()==1) return true;
        if(i==b.size()-1){
            if(me.count(n))
            return me[n];
            return me[n]=can(0,"",n,mp,me);
        }
        string k=b.substr(i,2);
        if(mp.find(k)==mp.end()) return false;
        for(char ch:mp[k]){
            if(can(i+1,n+ch,b,mp,me)) return true;
        }
        return false;
    }
    bool pyramidTransition(string bottom, vector<string>& allowed) {
        unordered_map<string,vector<char>>mp;
        unordered_map<string,bool>me;
        for(string &s:allowed)
        mp[s.substr(0,2)].push_back(s[2]);
        return can(0,"",bottom,mp,me);
    }
};
