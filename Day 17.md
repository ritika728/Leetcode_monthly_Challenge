### Find a Corresponding Node of a Binary Tree in a Clone of That Tree
Given two binary trees original and cloned and given a reference to a node target in the original tree.  
The cloned tree is a copy of the original tree.  
Return a reference to the same node in the cloned tree.  
Note that you are not allowed to change any of the two trees or the target node and the answer must be a reference to a node in the cloned tree.  
```c++
/**
 * Definition for a binary tree node.
 * struct TreeNode {
 *     int val;
 *     TreeNode *left;
 *     TreeNode *right;
 *     TreeNode(int x) : val(x), left(NULL), right(NULL) {}
 * };
 */

class Solution {
public:
    TreeNode* getTargetCopy(TreeNode* original, TreeNode* cloned, TreeNode* target) {
        if(original==target || original==NULL)
            return cloned;
        TreeNode* check =getTargetCopy(original->right,cloned->right,target);
        return check ? check: getTargetCopy(original->left,cloned->left,target);
    }
};
```

Was an easy one!⭐
 
