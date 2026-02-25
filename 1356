class Solution {
public:
    vector<int> sortByBits(vector<int>& arr) {
        const int len = arr.size();
        vector<pair<int,int>>ones;
        for(int&num:arr){
            int number = num;
            int count = 0;
            while(number){
                if(number&1){++count;}
                number>>=1;
            }
            ones.push_back({count,num});
        }
        sort(ones.begin(),ones.end());
        for(int i=0;i<len;++i){
            arr[i]=ones[i].second;
        }
        return arr;
    }
};
