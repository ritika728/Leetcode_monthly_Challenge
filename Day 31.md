```c++
class Solution {
public:
    bool hasAllCodes(string s, int k) {
        unordered_set<string>p;
        if(k>s.size()) 
            return false;
        for(int i =0;i<=s.size()-k;i++)
        p.insert(s.substr(i,k));
        if(p.size()==pow(2,k))
            return true;
        return false;
    }
};
    
    
```
