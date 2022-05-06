### Implement Stack using Queues  
Implement a last-in-first-out (LIFO) stack using only two queues. The implemented stack should support all the functions of a normal stack (push, top, pop, and empty).  
```c++
class MyStack {
public:
    queue<int>q;
    
    void push(int x) {
       q.push(x); 
    }
    
    int pop() {
        for(int i=0;i<q.size()-1;i++){
            q.push(q.front());
            q.pop();
        }
        int t=q.front();
        q.pop();
        return t;
    }
    
    int top() {
        return q.back();
    }
    
    bool empty() {
        return !q.size()?true:false;
    }
};

```
