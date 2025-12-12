class Solution {
public:
    static bool cmp(vector<string>a, vector<string>b){
        int timeA = stoi(a[1]);
        int timeB = stoi(b[1]);
        return timeA == timeB ? a[0] > b[0] : timeA < timeB;
    }

    void handleMessage(vector<string>event, vector<int>&mentions, vector<int>&offlineTime){

        int timestamp = stoi(event[1]);

        vector<string>ids;
        //collecting all ids separated by space
        stringstream s(event[2]);
        string word;
        while(s >> word){
            ids.push_back(word);
        }

        for(string id: ids){
            if(id == "ALL"){
                for(int i = 0; i<mentions.size(); i++){
                    mentions[i]++;
                }
            }
            else if(id == "HERE"){
                for(int i = 0; i<mentions.size(); i++){
                    if(offlineTime[i] == 0 || offlineTime[i] + 60 <= timestamp){
                        mentions[i]++;
                    }
                }
            }
            else{
                int idNum = stoi(id.substr(2)); //id1 me se idNum ko 1 assign kar rahe hai
                mentions[idNum]++;
            }
        }

    }

    void handleOffline(vector<string>event, vector<int>&mentions, vector<int>&offlineTime){
        
        int timestamp = stoi(event[1]);
        int id = stoi(event[2]);

        offlineTime[id] = timestamp;
    }
    vector<int> countMentions(int numberOfUsers, vector<vector<string>>& events) {
        vector<int>mentions(numberOfUsers);
        vector<int>offlineTime(numberOfUsers);

        sort(events.begin(), events.end(), cmp);

        for(vector<string>event: events){
            if(event[0] == "MESSAGE"){
                handleMessage(event, mentions, offlineTime);
            }
            else if(event[0] == "OFFLINE"){
                handleOffline(event, mentions, offlineTime);
            }
        }

        return mentions;
    }
};
