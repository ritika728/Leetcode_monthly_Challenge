### Max Number of K-Sum Pairs  
You are given an integer array nums and an integer k.  
In one operation, you can pick two numbers from the array whose sum equals k and remove them from the array.  
Return the maximum number of operations you can perform on the array.

```c++
class Solution {
public:
    int maxOperations(vector<int>& nums, int k) {
        sort(nums.begin(),nums.end());
        int i=0,j=nums.size()-1,c=0;
        while(i<j){
            if((nums[i]+nums[j])==k){
                i++; j--; c++;
            }
            else if((nums[i]+nums[j])<k)
                i++;
            else if((nums[i]+nums[j])>k)
                j--;
        }
        return c;
        
    }
};
```

 
