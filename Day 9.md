### Letter Combinations of a Phone Number
Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order.  
A mapping of digit to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.  

#### RECURSION & BACKTRACKING
```c++
class Solution {
public:
    vector<string>m={"abc","def","ghi","jkl","mno","pqrs","tuv","wxyz"};  //to store values
    vector<string>a;  //store final result
    vector<string> letterCombinations(string digits) {
        if(digits.size()==0)  //if there are no digits
            return a;
        string r="";  declaring an empty string
        ques(digits,0,r);  //function call
        return a;
    }
    void ques(string &digits,int i,string &r){
        if(digits.size()==i){  // ex. for digits=2, if i==2 means we need to append that in our answer, and stop making further 2> combinations
            a.push_back(r);
            return;
        }
        for(auto j:m[digits[i]-'2']){  //to iterate all over, eg. for 23, first to a then to b  //-2 because we need from index 0 to 7
            r.push_back(j);  // push 2
            ques(digits,i+1,r); //recursive call to make combinations eg, ad,ac etc.
            r.pop_back();  //backtracking, to remove d from ad and ahead.
        }
    }
    
};
```
Was an interesting one. I took quite a long time though.  
Runtime: 0 ms, faster than 100.00% of C++ online submissions for Letter Combinations of a Phone Number 💫

