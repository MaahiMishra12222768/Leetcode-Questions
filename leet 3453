class Solution {
public:
    // Compute the total area above y
    static double area_geq_y(vector<vector<int>>& squares, const double y) {
        double A=0;
        for (auto& s : squares) {
            double L=s[2], y0=s[1]+L; // y0 is the top boundary
            if (y>=y0) continue;  // the square is below y

            double h=min(L, y0-y);  // the valid height above y
            A+=L*h;
        }
        return A;
    }

    static double separateSquares(vector<vector<int>>& squares) {
        double A0=area_geq_y(squares, -1e9);  // Compute total area
        double A2=A0/2.0;  // Half the total area

        double minY=INT_MAX, maxY=INT_MIN;
        for (auto& s : squares) {
            double L=s[2], y0=s[1];
            minY=min(minY, y0);
            maxY=max(maxY, y0+L);
        }

        double l=minY, r=maxY, m;
        const double epsilon=1e-5;  

        while (r-l> epsilon) {
            m=(l+r)/ 2;
            double A=area_geq_y(squares, m);

            if (A>A2) l=m;  
            else r=m;  
        }
        return l;
    }
};
