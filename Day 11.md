## Count Sorted Vowel Strings  
Given an integer n, return the number of strings of length n that consist only of vowels (a, e, i, o, u) and are lexicographically sorted.  
A string s is lexicographically sorted if for all valid i, s[i] is the same as or comes before s[i+1] in the alphabet.  
#### BACKTRACKING SOLUTION  
```c++
class Solution {
public:
    vector<char>m = {'a','e','i','o','u'};
    int countVowelStrings(int n) {
        int c=0;
        helper(n,c,' ');
        return c;
    }
    void helper(int n, int &c, char l){
        if(n==0)
            c++;
        else{
            for(auto j: m){
                if(l<=j)
                    helper(n-1,c,j);
            }
        }
    }
};
```
Runtime: 692 ms, faster than 5.11% of C++ online submissions for Count Sorted Vowel Strings.



