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
