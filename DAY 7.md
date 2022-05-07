### 132 Pattern
Given an array of n integers nums, a 132 pattern is a subsequence of three integers nums[i], nums[j] and nums[k] such that i < j < k and nums[i] < nums[k] < nums[j].  
Return true if there is a 132 pattern in nums, otherwise, return false.  

#### BRUTE FORCE [89/102 Test cases passed]
```c++
class Solution {
public:
    bool find132pattern(vector<int>& a) {
        if (a.size() < 3) {
            return false;
        }
        for (int i = 0;i<a.size()-2; i++) {
            for (int j=i+1;j<a.size()-1;j++) {
                for (int k=j+1;k<a.size();k++) {
                    if (a[k] >a[i] && a[k]<a[j]) {
                        return true;
                    }
                }
            }
        }
        return false;
    }
};
```
#### USING STACK
```c++
class Solution {
public:
    bool find132pattern(vector<int>& nums) {
       int r=INT_MIN;
        stack<int>q;
        for( int i=nums.size()-1;i >= 0;i -- ){
            if(nums[i]<r) 
                return true;
            else{
                while(!q.empty() && q.top()<nums[i]){ 
                   r=q.top();
                   q.pop(); 
                }       
            q.push(nums[i]); 
            }
         }             
        return false; 
    }
};
```

And this question was quite difficult, had to check the solution for the stack approach and understand how is it performed.
