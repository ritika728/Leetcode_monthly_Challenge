```c++
class Solution {
public:
    int missingNumber(vector<int>& nums) {
        int n=nums.size(),i,s=0,t;
        t=(n*(n+1)/2);
        for(i=0;i<n;i++){
            s=s+nums[i];
        }
        return t-s;
    }
};
```
