```c++
class Solution {
    static bool compare(vector<int>& a, vector<int>& b){
        if(a[0]==b[0]) 
            return a[1]>b[1];
        return a[0]<b[0];
    }
public:
    int m(vector<vector<int>>& e) {
        vector<int>p;
        int n = e.size();
        sort(e.begin(),e.end(),compare);
        for(int i = 0;i<e.size();i++){
            int q=e[i][1];
            int r = lower_bound(p.begin(),p.end(),e)-p.begin();
            if(r>=p.size()) 
                p.push_back(e);
            else p[r] = e;
        }
        
        return r.size();
    }
};
```
