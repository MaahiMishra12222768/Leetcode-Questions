class Solution {
public:
    int numberOfBeams(vector<string>& bank) {
        if (bank.empty()) {
            return 0;
        }
        
        int totalBeams = 0;
        int prevRowDevices = countDevices(bank[0]);
        
        for (int i = 1; i < bank.size(); i++) {
            int currentRowDevices = countDevices(bank[i]);
            
            if (currentRowDevices == 0) {
                continue;
            }
            
            totalBeams += prevRowDevices * currentRowDevices;
            prevRowDevices = currentRowDevices;
        }
        
        return totalBeams;
    }
    
private:
    int countDevices(const string& row) {
        int deviceCount = 0;
        for (char cell : row) {
            if (cell == '1') {
                deviceCount++;
            }
        }
        return deviceCount;
    }
};
