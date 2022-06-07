### Permutations II  
Given a collection of numbers, nums, that might contain duplicates, return all possible unique permutations in any order.  
#### BACKTRACKING SOLUTION 

```c++
lass Solution {
public:
    vector<vector<int>> permuteUnique(vector<int>& nums) {
        sort(nums.begin(),nums.end());
        vector<vector<int>>v;
        helper(nums,0,v);
        return v;
    }
    void helper(vector<int> nums, int i, vector<vector<int>>& v){
        if(i==nums.size())
            v.push_back(nums);
        else{
            for(int j=i;j<nums.size();j++){
                if(i==j || nums[i]!=nums[j]){
                    swap(nums[i],nums[j]);
                     helper(nums,i+1,v);
                }
            }
        }
    }
};
```

Again one question based on BackTracking and Recursion. Though I had to check the discussion part to solve this, my concepts are getting cleared slowly. 
