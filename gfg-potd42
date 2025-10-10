/*
class Node {
public:
    int data;
    Node *left;
    Node *right;

    Node(int x) {
        data = x;
        left = NULL;
        right = NULL;
    }
};
*/

class Solution {
  public:
    Node* Solve(int &i, int &j, vector<int> &pre, vector<int> &post){
        
        Node* node = new Node(pre[i]);
        i++;
        
        // no child
        if(node->data == post[j]){
            j++;
            return node;
        }
        
        Node* left = Solve(i, j, pre, post);
        node->left = left;
        Node* right = Solve(i, j, pre, post);
        node->right = right;
        
        // node value match post order value
        j++;
        return node;
    }
    Node *constructTree(vector<int> &pre, vector<int> &post) {
        int i = 0;
        int j = 0;
        return Solve(i, j, pre, post);
    }
};