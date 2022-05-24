```c++
class Solution {
public:
  int longestValidParentheses(string s) {
	stack<int> st;
	for(int i = 0; i < s.size(); i++) {
		if(s[i] == '(') 
    st.push(i);
		else if(st.size()) {
			s[st.top()] = s[i] = '*';
			st.pop();
		}
	}
	int r=0,t=0;
	for(int i = 0; i <= s.size(); i++) {
		if(s[i] == '*') 
    t++;
		else {
			t= max(t,r);
			r=0;
		}
	}
	return max(r,t);
}
};
```
