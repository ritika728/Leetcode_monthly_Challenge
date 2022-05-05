### Shortest Unsorted Continuous Subarray  
Given an integer array nums, you need to find one continuous subarray that if you only sort this subarray in ascending order, then the whole array will be sorted in ascending order.  
Return the shortest such subarray and output its length.  
```c++
class Solution {
public:
    int findUnsortedSubarray(vector<int>& nums) {
      int e=-1,m=nums[0],p=0,min=nums[nums.size()-1];
        for(int i=1;i<nums.size();i++){
            if(m>nums[i])
                e=i; 
            else
                m= nums[i];
        }
        for(int i=nums.size()-2;i >= 0;i--){
            if(min<nums[i])
                p=i; 
            else
                min=nums[i];
        }
        return e-p+1;  
    }
};
```
