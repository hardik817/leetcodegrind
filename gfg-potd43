/*
class Node {
  public:
    int data;
    Node* left;
    Node* right;

    Node(int val) {
        data = val;
        left = NULL;
        right = NULL;
    }
};
*/

class Solution {
  public:
    void solve(Node* node, vector<int>&ans){
        if(!node) return;
        solve(node->left, ans);
        solve(node->right, ans);
        ans.push_back(node->data);
    }
  
    vector<int> postOrder(Node* root) {
        // code here
        vector<int>ans;
        solve(root, ans);
        return ans;
    }
};