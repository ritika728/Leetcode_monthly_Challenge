###  Flatten Nested List Iterator
You are given a nested list of integers nestedList. Each element is either an integer or a list whose elements may also be integers or other lists. Implement an iterator to flatten it.  
Implement the NestedIterator class:  
NestedIterator(List<NestedInteger> nestedList) Initializes the iterator with the nested list nestedList.  
int next() Returns the next integer in the nested list.  
boolean hasNext() Returns true if there are still some integers in the nested list and false otherwise.  
Your code will be tested with the following pseudocode:  
```
initialize iterator with nestedList
res = []
while iterator.hasNext()
    append iterator.next() to the end of res
return res
 ```
If res matches the expected flattened list, then your code will be judged as correct.  
 ```c++
class NestedIterator {
public:
    int i=0,n;
    vector<int>v;
    void ques(NestedInteger x){
        if(x.isInteger())
            v.push_back(x.getInteger());
        else{
            for(auto &&y : x.getList())
                ques(y);
        }
    }
    NestedIterator(vector<NestedInteger> &nestedList) {
        for(auto &&j : nestedList)
            ques(j);
        n=v.size();
    }
    
    int next() {
        i++;
        return v[i-1];
    }
    
    bool hasNext() {
        if(i==n)
            return false;
        return true;
    }
};
```
  
 The problem is not that difficult, just need to analyse the problem statement clearly.  
