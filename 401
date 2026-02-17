class Solution {
public:
    vector<string> readBinaryWatch(int k) {
        if (k == 0) return {"0:00"};
        if (k > 8) return {};
        vector<string> res;
        int q = (1 << k) - 1;

        while (q < (1 << 10)) {
            string time = isValid(q);
            if (!time.empty()) res.push_back(time);
            int r = q & -q;
            int n = q + r;
            //Find the Next Bit Combination (with the same hamming weight)
            //0000000111 -> 0000001011 -> 0000001101 -> 0000001110 -> 0000010011
            //0000010101 -> 0000010110 -> 0000011001 -> 0000011010 -> 0000011100 
            q = (((n ^ q) >> 2) / r) | n;
        }
        return res;
    }

    string isValid(int q) {
        int hour = q >> 6;
        int min = q & 63;
        if (hour >= 12 || min >= 60) return "";
        //return format("{}:{:02}", hour, min);
        return to_string(hour) + ":" + (min < 10 ? "0" : "") + to_string(min);
    }
};
