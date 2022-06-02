## My Approach
* Created a new matrix ans.
* Syntax : vector<vector<int>> name(no. of rows, vector <int> no. of columns)  (inserion operator not appearing in preview)  
* Iterate through nested loops, and assign the values to the new matrix.
```c++
class Solution {
public:
    vector<vector<int>> transpose(vector<vector<int>>& matrix) {
        vector<vector<int>>ans(matrix[0].size(),vector<int>(matrix.size(),0));;
        for(int i=0;i<matrix.size();i++){
            for(int j=0;j<matrix[i].size();j++){
                ans[j][i]=matrix[i][j];
            }
        }
        return ans;
    }
};
  ```
