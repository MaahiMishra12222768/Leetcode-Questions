
class MovieRentingSystem {
public:
    vector<set<pair<int, int>>> available = vector<set<pair<int, int>>> (10010);            //List of movies not rented
    vector<set<pair<int, int>>> getPrice = vector<set<pair<int, int>>> (10010);
    
    set<pair<int, pair<int, int>>> rented;
    
    MovieRentingSystem(int n, vector<vector<int>>& e){
        for(auto v: e){
            available[v[1]].insert({v[2], v[0]});            //available[movie].insert({price, shop})   --> each movie vector will be sorted by the price 
            getPrice[v[1]].insert({v[0], v[2]});             //checkPrice[movie].insert({shop, price}) --> each movie vector will be sorted by shop
        }
    }
    
    vector<int> search(int movie){
        vector<int> ans;
        int i=0;
        for(auto d: available[movie]){                               //get top 5 cheapest movies if present otherwise return all present in available list
            ans.push_back(d.second);
            i++;
            if(i>=5){
                break;
            }
        }
        return ans;
    }
    
    void rent(int shop, int movie){
        
        auto it = getPrice[movie].lower_bound({shop, INT_MIN});   // to know the price of the movie
        int price = (*it).second;
        
        available[movie].erase({price, shop});                       // remove the movie form available list
        
        rented.insert({price, {shop, movie}});                      // add movie to the rented set
    }
    
    void drop(int shop, int movie) {
        
        auto it = getPrice[movie].lower_bound({shop, INT_MIN});   // to know the price of the movie
        int price = (*it).second;
        
        available[movie].insert({price, shop});                      // add movie to the available set
        
        rented.erase({price, {shop, movie}});                       // remove the movie form rented list
    }
    
    vector<vector<int>> report() {
        vector<vector<int>> ans;
        int i=0;
        for(auto d: rented){                                         //get top 5 cheapest movies if present otherwise return all present in rented list
            ans.push_back({d.second.first, d.second.second});
            i++;
            if(i>=5){
                break;
            }
        }
        return ans;
    }
};
//fast i/o
static bool     _foo = ios::sync_with_stdio(false);
static ostream* _bar = cin.tie(NULL);
