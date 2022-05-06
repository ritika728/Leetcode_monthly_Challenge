### Remove All Adjacent Duplicates in String II  
You are given a string s and an integer k, a k duplicate removal consists of choosing k adjacent and equal letters from s and removing them, causing the left and the right side of the deleted substring to concatenate together.  
We repeatedly make k duplicate removals on s until we no longer can.  
Return the final string after all such duplicate removals have been made. It is guaranteed that the answer is unique.  
### First Approach (18/20) Test Cases   [Recursive]
```c++
class Solution {
public:
    string removeDuplicates(string s, int k) {
        int c=1;
        for(int i=1;i<s.size();i++){
            if(s[i]!=s[i-1])
                c=1;
            else if(s[i]==s[i-1])
                c++;
            if(c==k)
                return removeDuplicates((s.substr(0,i-k+1)+s.substr(i+1)),k);
        }
        return s;
    }
};
```
### Second Approach  [Stack]
```c++
class Solution {
public:
    string removeDuplicates(string s, int k) {
        stack<pair<char,int>>q;
        for(int i=0;i<s.size();i++){
            if(!q.empty() && q.top().first==s[i]){
                q.top().second++;
                if(q.top().second==k)
                    q.pop();
            }
            else{
                q.push({s[i],1});
            }
        }
        string r;
        while(!q.empty()){
            for(int i=0;i<q.top().second;i++){
                r.push_back(q.top().first);
            }
            q.pop();
        }
        reverse(r.begin(),r.end());
        return r;
    }
};
```
This approach took a large amount of time [had to take some hints too], but indeed I did it!
