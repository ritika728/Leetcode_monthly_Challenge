## My Approach:
* To get O(1) Space Complexity, I have not decalred a new vector, rather have made changes to the given vector nums.
* Here, Time Complexity = O(n)

```c++
class Solution {
public:
    vector<int> runningSum(vector<int>& nums) {
        for(int i=1;i<nums.size();i++){
            nums[i]=nums[i-1]+nums[i];
        }
        return nums;
    }
};
```
