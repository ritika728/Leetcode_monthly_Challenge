## Backspace String Compare
Probelm difficulty : Easy  
Given two strings s and t, return true if they are equal when both are typed into empty text editors. '#' means a backspace character.
Note that after backspacing an empty text, the text will continue empty.

```c++
class Solution {
public:
    bool backspaceCompare(string s, string t) {  
        int k=0,q=0;  
        for(int i=0;i<s.size();i++){  
            if(s[i]=='#'){  
                k--;  
                k=max(k,0);  
            }  
            else{  
                s[k]=s[i];  
                k++;  
            }  
        }  
        for(int i=0;i<t.size();i++){  
            if(t[i]=='#'){  
                q--;  
                q=max(q,0);  
            }  
            else{  
                t[q]=t[i];  
                q++;  
            }    
        }  
        if(k!=q)  
            return false;  
        for(int i=0;i<k;i++){  
            if(s[i]!=t[i])  
                return false;  
        }  
        return true;      
    }  
};  
```

#### Space Complexity: O(1)
#### Time Complexity: O(n)
