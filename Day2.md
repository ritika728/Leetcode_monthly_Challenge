### Sort Array By Parity  
Given an integer array nums, move all the even integers at the beginning of the array followed by all the odd integers.  
Return any array that satisfies this condition.  
```c++
class Solution {
public:
    vector<int> sortArrayByParity(vector<int>& nums) {
        vector<int>v;
        for(int i=0;i<nums.size();i++){
            if(nums[i]%2==0)
                v.push_back(nums[i]);
        }
        for(int i=0;i<nums.size();i++){
            if(nums[i]%2!=0)
                v.push_back(nums[i]);
        }
        return v;
    }
};
```
