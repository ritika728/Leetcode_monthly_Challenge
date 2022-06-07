### Combination Sum III
Find all valid combinations of k numbers that sum up to n such that the following conditions are true:  
Only numbers 1 through 9 are used.  
Each number is used at most once.  
Return a list of all possible valid combinations. The list must not contain the same combination twice, and the combinations may be returned in any order.   

**APPROACH** : BackTracking 
```c++
void ans(int k, int n, vector<vector<int>>&a,vector<int>&v,int s){
    if(k==0 && n==0){
        a.push_back(v);
        return;
    }
    for(int i=s;i<=9;i++){
        v.push_back(i);
        ans(k-1,n-i,a,v,i+1);  //recursive call
        v.pop_back();   // Backtracking
    }
    return;
}

class Solution {
public:
    vector<vector<int>> combinationSum3(int k, int n) {
        vector<vector<int>> a;
        vector<int>v;
        ans(k,n,a,v,1);
        return a;
    }
};
```

Runtime: 0 ms, faster than 100.00% of C++ online submissions 😍
