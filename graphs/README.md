<h1  style="font-size:30px">TREE</h1>
A non-linear hierarchical data structure consisting of a collection of nodes such that each node of the tree stores a value, a list of references to nodes (the “children”).<br><br>
Each node in the tree can be connected to many children (depending on the type of tree), but must be connected to exactly one parent, except for the root node, which has no parent. These connections between nodes are called edges or links. By convention, trees are drawn with descendants going downwards. So, root node will be the topmost node of a tree. <br><br>
<div align="center">
<blockquote><b>We can say that a tree data structure has roots, branches, and leaves<br> connected with one another. </b></blockquote>
</div><br><br>
In contrast to linear data structures, many trees cannot be represented by relationships between neighboring nodes in a single straight line.
<br><br><br>
<h2>Some Terminology</h2><br>
<b>Parent Node:</b> A node that has links to one or more child nodes.<br>
<b>Child Node:</b> A node that is linked to an upper node (parent Node).<br>
<b>Siblings:</b> Children of the same parent node are called siblings<br>
<b>Leaf Node:</b> A node that doesn’t have any child Nodes.<br>
<b>Ancestor Nodes:</b> Nodes lying on the path from root node to that node.<br><br>
The figure below shows all the terminologies described above:<br>
<img style="padding-left:100px" src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/treebasics.png" height="180" width="500"><br>
PS:- The edges doesn't mean directed but pointed from parent to child.<br><br><br><br><br><br><br><br>
<div align="center">1</div>
<h3>Explanation:</h3>
In the figure above, 1 is the root as well as a parent node to child nodes 2, 3, and 4. Node 3 is a parent node to child nodes 6 and 7. As nodes, 2,3,4 share the same parent node 1, so they are siblings to each other. Similarly, 6 and 7 are also sibling nodes as their parent is the same, that is, 3. Consider node 7, as 1->3->7 is the path from the root node to this node, nodes 1 and 3 are said to be the ancestors of node 7.<br><br>
<h2>Subtree</h2>
A subtree is a portion of a tree that can be viewed as a complete tree on its own. Any node in a tree, together with all the connected nodes below it, comprise a subtree of the original tree. So, each child can be treated like the root node of its own subtree, making <b>recursion a useful technique for tree traversal</b>. <br><br>
<h2>Path</h2>
Every two nodes in a tree are connected and by exactly one path. The number of edges in a path is called the length of the path.<br><br>
<b>Depth</b> of a node n: The length of the path from a node n to the root node. The depth of the root node is 0.<br>
<b>Level</b> of a node n: (Depth of node n) + 1.<br>
<b>Height</b> of a node n: The length of the path from n to its deepest descendant. So the height of the tree itself is the height of the root node, and the height of leaf nodes is always 0.<br><br>
In the above figure for the node 3, height = 1, depth = 1, level = 2<br><br>
<h2 style="font-size:20px">Some Tree Types</h2>
Many different types of trees exist, which are optimized for particular use-cases. Each tree type offers its own particular structure and hence space-time complexity for different operations. Some commonly used trees include,<br>
<br><ul>
<li>Binary Trees</li>
<li>Binary Search Trees</li>
<li>AVL Trees</li>
<li>Red-Black Trees</li>
</ul><br><br>
<h3> N-ary Tree</h3>
An N-ary tree is a tree in which each node has no more than N children. 
<br><br><br><br><br><br><br><div align="center">2</div>
<h2 style="font-size:20px">Applications</h2><br>&nbsp;&nbsp;
The applications of tree data structures are as follows:<br><br>
• <b>Storing hierarchical data</b><br>
&nbsp;&nbsp;Tree data structures are used to store the hierarchical data, which means data<br>&nbsp; arranged in the form of order. <br> 
• <b>Binary Search Tree</b><br>
&nbsp;&nbsp;It is a type of tree data structure that helps in maintaining a sorted stream of<br>&nbsp; data. Used for efficient searching and finding the closest item. <br>
• <b>Heap</b><br>
&nbsp;&nbsp;It is also a tree data structure that can be represented in a form of array. It is<br>&nbsp; used to implement priority queues. Used for efficient sorting. <br>
• <b>Syntax tree</b><br>
&nbsp;&nbsp;Scanning, parsing , generation of code and evaluation of arithmetic expressions in<br>&nbsp; Compiler design.<br>
• <b>Trie</b><br>
&nbsp;&nbsp;It is the fast and efficient way for dynamic spell checking. It is also used for<br>&nbsp; locating specific keys from within a set. <br>
• <b>K-D Tree:</b><br>
&nbsp;&nbsp;A space partitioning tree used to organize points in K dimensional space.<br>
• <b>B-Tree and B+ Tree </b><br>
&nbsp;&nbsp;used to implement indexing in databases. <br>
• <b>Spanning trees</b><br>
&nbsp;&nbsp;It is the shortest path tree used in the routers to direct the packets to the<br>&nbsp; destination.<br>
• <b>Decision trees</b><br><br>
Also, JSON and YAML documents can be thought of as trees, but are typically represented by nested lists and dictionaries.<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">3</div>
<h1 style="font-size:30px">BINARY TREE</h1>
<div style="display:flex">
<div>
Binary trees are a commonly used tree, which constrain&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;   the number of children for each parent to exactly two. We&nbsp; &nbsp; &nbsp;  can refer to these children as the left and the right child. <br><br>
A recursive definition using just set theory notions is&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  that a (non-empty) binary tree is a tuple (L, S, R),&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  where L and R are binary trees or the empty set and S&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; is a singleton set containing the root.<br>
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/binarytree.png" height="150" width="150">
</div>
<br>
A binary tree is a special case of a ordered N-ary tree, where N is 2.
A Binary Tree node contains following parts. <br>
- Data<br>
- Pointer to left child<br>
- Pointer to right child<br><br><br><br>

<h2>Types of Binary Trees</h2>
<h3>Complete Binary Trees</h3>
A binary tree is a complete binary tree if all the levels are completely filled except possibly the last level and the last level has all keys as left as possible  <br>
<h3>Full Binary Trees</h3>
A binary tree is a full binary tree if every node has 0 or 2 children.
<h3>Perfect Binary Trees</h3>
A binary tree is said to be perfect if it is both full and complete. <br>
<h3>Degenerate (or pathological) tree</h3>
A tree where each parent node has one child node. This means that the tree will behave like a linked list data structure.
<h3>Skewed tree</h3>
A binary tree in which each node has either one or no child.<br>
In this type of tree, either all nodes are positioned to the left or the right. <br><br><br>
<b>Note</b>:- While solving any problems involving trees, take care of the base cases<br> i.e. root = NULL<br><br><br><br><br><br><div align="center">4</div>
<h1 style="font-size:30px">Traversal</h1>
Tree traversal refers to the process of visiting each node in a tree data structure, exactly once.<br> 
Unlike linked lists, one-dimensional arrays and other linear data structures, which are canonically traversed in linear order, trees may be traversed in multiple ways.<br><br>
They may be traversed in depth-first or breadth-first order. Such traversals are classified by the order in which the nodes are visited.<br>
The following algorithms are described for a binary tree, but they may be generalized to other trees as well.<br><br>
<h1>Depth first order</h1>
We go as deep as we can to look for a value, and when there is nothing new to discover, we retrace our steps to find something new. <br>
There are three common ways to traverse them in depth-first order: in-order, pre-order and post-order<br><br>
<h3>pre-order (DLR)</h3>
A traversal in which the parent node is traversed before its children.<br>
<h3>post-order (LRD)</h3>
A traversal in which the parent node is traversed before its children.<br>
<h3>in-order (LDR)</h3>
A traversal in which a node's left subtree, then the node itself, and finally its right subtree are traversed. This specifically assumes a binary tree as it is referring exactly to two subtrees.<br><br><br>
<div style="display:flex">
<img src="https://media.geeksforgeeks.org/wp-content/cdn-uploads/level_order_traversal.png" width="200" height="220">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<div>
preorder: 1 2 4 5 3 <br>
inorder: 4 2 5 1 3 <br>
postorder: 4 5 2 3 1 <br>
levelorder: 1 2 3 4 5 <br>
zigzag level order: 1 3 2 4 5 <br>
reverse level order: 4 5 2 3 1 <br>
diagonal order: 1 3 2 5 4 <br>
</div></div><br><br><br><div align="center">5</div>
<h1>Traversal Problems</h1>
Inorder&nbsp;&nbsp; <a href="#inrec">recursive</a> <a href="#inite">iterative</a> <br>
Preorder&nbsp; <a href="#prerec">recursive</a> <a href="#preite">iterative</a> <br>
Postorder <a href="#postrec">recursive</a> <a href="#postite">iterative</a> <br><br>
Levelorder <a href="#level">solution</a> <br>
Zigzag level order <a href="#zlevel">solution</a> <br>
Reverse level order <a href="#rlevel">solution</a> <br><br>
Diagonal order <a href="#diagonal">solution</a> <br>
Boundary order <a href="#boundary">solution</a> <br>
Vertical order <a href="#vertical">solution</a> <br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><br><br><div align="center">6</div>
<h1>Recursive implementations</h1>

```cpp
vector<int> depthFirstTraversal(Node* root){
    vector<int> res;
    xyzorder(root, res);
    return res;
}
```

All the three depth first traversals can be used in the place of <span style="background-color:#eee; border-radius: 2px;"><i>&nbsp;xyzorder&nbsp;</i></span><br><br>
<h2 id="inrec">Inorder</h2>

```cpp
void inorder(Node* root, vector<int> &res) {
    if (root == NULL) return;
    inorder(root->left, res);
    res.push_back(root->val);
    inorder(root->right, res);
}
```
<br><h2 id="prerec">Preorder</h2>

```cpp
void preorder(Node* root, vector<int> &res) {
    if (root == NULL) return;
    res.push_back(root->val);
    preorder(root->left, res);
    preorder(root->right, res);
}
```
<br><h2 id="postrec">Postorder</h2>

```cpp
void postorder(Node* root, vector<int> &res) {
    if (root == NULL) return;
    postorder(root->left, res);
    postorder(root->right, res);
    res.push_back(root->val);
}
```
<br><br><br><br><br><div align="center">6</div>
<h1>Iterative implementations</h1><br>
Stack is a useful data structure to convert a recursive code into an iterative code. Under the hood, the compiler uses a call stack to convert a recursive code into an iterative code.<br><br>
<h2 id="preite">Preorder</h2>

```cpp
vector<int> preorderTraversal(Node* root) {
    vector<int> res;
    if (root == NULL) return res;
    stack<Node*> s;
    s.push(root);
        
    while(!s.empty()){
        Node* temp = s.top();
        s.pop();
        res.push_back(temp->val);
        if (temp->right) s.push(temp->right);
        if (temp->left) s.push(temp->left);
    }
        
    return res;
}
```
<h2 id="postite">Postorder</h2>

```cpp
vector<int> postorderTraversal(Node* root) {
    vector<int> res;
    if (root == NULL) return res;
    stack<Node*> s;
    s.push(root);
        
    while(!s.empty()){
        Node* temp = s.top();
        s.pop();
        res.push_back(temp->val);
        if (temp->left) s.push(temp->left);
        if (temp->right) s.push(temp->right);
    }

    reverse(res.begin(), res.end());                             // reversing DRL
    return res;
}
```
<br><div align="center">7</div>
<h2 id="inite">Inorder</h2>

```cpp
vector<int> inorderTraversal(Node* root) {
    vector<int> res;
    if (root == NULL) return res;
    stack<Node*> s;
    Node* cur = root;
        
    while(cur || !s.empty()) {
        // at any point always try to reach the leftmost node (L)
        while (cur != NULL) {
            s.push(cur);
            cur = cur->left;
        }
        
        // when it is NULL, process its parent node as we are sure now left subtree is completed. (D)
        Node* temp = s.top();
        s.pop();
        res.push_back(temp->val);
        
        // after processing a node, reach to its right subtree (R)
        cur = temp->right;
    }
        
    return res;
}
```
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">8</div>
<h1>Breadth first order - BFS</h1><br>
A level-order traversal effectively performs a breadth-first search over the entirety of a tree; nodes are traversed level by level, where the root node is visited first, followed by its direct child nodes and their siblings, followed by its grandchild nodes and their siblings, etc., until all nodes in the tree have been traversed.<br><br>
While DFS uses recursion/stack to keep track of progress, BFS uses a queue (First In First Out). <br><br>
The Tree BFS pattern works by pushing the root node to the queue and then continually iterating until the queue is empty. For each iteration, we remove the node at the head of the queue and “visit” that node. After removing each node from the queue, we also insert all of its children into the queue.<br><br>
At any time, the queue contains at most two levels of nodes. We will smartly use the situation when the queue contains exactly one level of nodes while solving problems.<br><br>
<h3>Some important points</h3>
1. It uses a queue to keep track of all the nodes of a level before jumping onto it.<br>
2. It visits all the nodes in a level before starting to visit the next level.<br><br><br>

<h3>Complexities</h3>
The time complexity of the algorithm is O(N), where N is the total number of nodes in the tree as we traverse each node once.<br><br>
The space complexity of the algorithm is also O(N) as we need O(N) space for the queue.  Since we can have a maximum of N/2 nodes at a level (this could happen only at the last level), therefore we will need O(N) space to store them in the queue.<br><br><br><br>
<h2>How to identify the BFS pattern:</h2>
If the problem involves traversing trees in a level-by-level fashion (breadth-first search manner), it can be efficiently solved using this approach.<br><br>
<br><br><br><br><br><br><br><br><br><div align="center">10</div>
<h2>Problems featuring this pattern</h2>
<ul>
<li>Various types of <b>tree traversals</b> such as level order, zigzag order etc ... as they need to traverse the tree by level</li>
<li><b>Left and Right views</b>: As when the queue contains exactly one level of nodes, the first of them will be a part of the left view and the last of them will be a part of the right view</li>
<li><b>Minimum depth</b> of a tree: Since we search level by level, we are guaranteed to find the shallowest leaf node earlier than other leaf nodes.<br>
Note: But for finding the maximum depth, both are equally efficient interms of time as we need to visit each node.</li>
<li>Level averages, largest value on each level of a tree etc.. </li>
<li>Next right node of a given key, Connect Level Order Siblings
</ul>
<br><br><br><br><h2 id="level">Level order implementation</h2>

```cpp
vector<vector<int>> levelOrder(Node* root) {
    vector<vector<int>> res;
    if (root == NULL) return res;
    queue<Node*> q;
    q.push(root);
        
    while (!q.empty()) {
        int size = q.size();
        vector<int> level;
        while (size--) {
            Node* temp = q.front();
            q.pop();
            level.push_back(temp->val);
            if (temp->left) q.push(temp->left);
            if (temp->right) q.push(temp->right);
        }
        res.push_back(level);
    }
    
    return res;
}
```

<br><br><br><br><br><br><br><br><div align="center">11</div>
<h2 id="zlevel">Zig Zag Level order</h2>

```cpp
vector<vector<int>> zigzagLevelOrder(Node* root) {
    vector<vector<int>> res;
    if (root == NULL) return res;
    queue<Node*> q;
    q.push(root);
    int levelIndex = 0;
    while (!q.empty()) {
        int size = q.size();
        vector<int> level;
        while (size--) {
            Node* temp = q.front();
            q.pop();
            level.push_back(temp->val);
            if (temp->left) q.push(temp->left);
            if (temp->right) q.push(temp->right);
        }
        if (levelIndex&1) reverse(level.begin(), level.end());
        res.push_back(level);
        levelIndex++;
    }
    return res;
}
```
<br><br>
<h2 id="rlevel">Reverse Level Order</h2>
<ul>
<li>We will maintain a stack of vectors.</li>
<li>After having each level of nodes in the vector, we will push it to the stack, so that the top of the stack contains the last level and the bottom of the stack contains the first level (only root). </li>
<li>After traversing, we will push the top of the stack into result vector until the stack is empty.</li>
</ul>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">13</div>
<h2 id="diagonal">Diagonal Order</h2>

```cpp
void dlr(Node*root, int dval, map<int, vector<int>> &mp){
    if (root == NULL) return;
    mp[dval].push_back(root->val);
    dlr(root->left,dval+1,mp);
    dlr(root->right,dval,mp);
}
vector<int> diagonal(Node *root)
{
   vector<int> res;
   map<int, vector<int>> mp;
   dlr(root, 0, mp);
   for (auto it : mp) {
       res.insert(res.end(), it.second.begin(), it.second.end());
   }
   return res;
}
```
<br><h2>Connect Level Order Siblings</h2>
Given a binary tree, connect each node with its level order successor(right node). The last node of each level should point to a null node.<br><br>

```cpp
void connect(Node *root) {
    queue<TreeNode*> q;
    q.push(root);
    
    while (!q.empty()){
        int size = q.size();
        while (size--) {
            Node* temp = q.front();
            q.pop();
            if (temp->left) q.push(temp->left);
            if (temp->right) q.push(temp->right);
            if (size == 0) temp->next = NULL;
            else temp->next = q.front();
        }
    }
  } 
```
<br>
If the problem says "the last node of each level should point to the first node of the next level", modify the if condition as follows:

```cpp
if (!q.empty()) temp->next = q.front();
else temp->next = NULL;
```
<div align="center">10</div>
<h1 id="boundary">Boundary traversal</h1>
Given a Binary Tree, find its Boundary Traversal. The traversal should be in the following order: <br><br>
<b>Left boundary nodes</b>: defined as the path from the root to the left-most node ie- the leaf node you could reach when you always travel preferring the left subtree over the right subtree. <br>
<b>Leaf nodes</b>: All the leaf nodes except for the ones that are part of left or right boundary.<br>
<b>Reverse right boundary nodes</b>: defined as the path from the right-most node to the root. The right-most node is the leaf node you could reach when you always travel preferring the right subtree over the left subtree. Exclude the root from this as it was already included in the traversal of left boundary nodes.<br><br>
<b>Note</b>: If the root doesn't have a left subtree or right subtree, then the root itself is the left or right boundary. <br><br><br>
<h2>Solution</h2>
The complexity of this problem lies in separating this into separate problems so as to not to print any node twice. Care must be taken while writing code as the every two of the three can intersect.<br><br>
Also note that left boundary doesn't mean the path from root to the left node obtained while continously going left. The left boundary can have right pointers to when the nodes doesn't have left pointers.
<br><br><br><b>Solution starts in the next page.</b><br><br><br>

```cpp
// Helper function to print leaves
void lr(Node *root, vector<int> &res){
        if (root==NULL) return;
        if (root->left==NULL && root->right==NULL) {
            // print the leaf node
            res.push_back(root->data);
        } else {
            // left leaves should be printed before right ones always
            lr(root->left, res);
            lr(root->right, res);
        }
    }
```
<br><br><br>
<div align="center">11</div>

```cpp
vector <int> boundary(Node *root){
    vector<int> res;
    if (root==NULL) return res;
    // 1. print root first
    res.push_back(root->data);               
    
    // 2. left boundary except the leaf
    Node* temp = root->left;
    while (temp) {
        if (temp->left || temp->right) res.push_back(temp->data);
        // first priority to left child at each step
        if (temp->left) temp = temp->left;
        else temp = temp->right;
    }
    
    // 3. print all the leaves
    if (root->left || root->right) lr(root, res);
    
    // 4. right boundary except the leaf
    stack<int> s;
    temp = root->right;
    while (temp) {
        if (temp->left || temp->right) s.push(temp->data);
        // first priority to right child at each step
        if (temp->right) temp = temp->right;
        else temp = temp->left;
    }
    // reversing using stack
    while (!s.empty()) {
        res.push_back(s.top());
        s.pop();
    }

    return res;
}
```
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">12</div>

<h1>Height of a binary tree</h1>
The length of the path from root to its deepest descendant(leaf).<br><br>

```cpp
int height(Node* root){
    if (root == NULL) return 0;
    return 1 + max(height(root->left), height(root->right));
}
```

<br><br><br><br><br><h1>Diameter of a binary tree</h1>
Given the root of a binary tree, return the length of the diameter of the tree.<br>
The diameter of a binary tree is the length of the longest path between any two nodes in a tree. This path may or may not pass through the root.<br>
The length of a path between two nodes is represented by the number of edges between them.<br><br><br>

```cpp
int heights(Node* root, int &maxLen) {
    if (root == NULL) return 0;
    int left = heights(root->left, maxLen);
    int right = heights(root->right, maxLen);
    
    // At any node, the maximum possible length involving it is the sum of heights of the node using left and right subtrees. We will be smartly using recursion to return the heights each time.
    if ((left + right) > maxLen) maxLen = left + right;
    return 1 + max(left, right);
}

int diameterOfBinaryTree(Node* root) {
    int maxLen = 0;
    heights(root, maxLen);
    return maxLen;
}
````
<br><br><br><br><br><div align="center">13</div>
<h1>Maximum sum leaf to root path</h1>

```cpp
void func(Node* root, int sum, int &maxSum) {
    if (root == NULL) {
        if (sum > maxSum) maxSum = sum;
    } else {
        func(root->left, sum+root->data, maxSum);
        func(root->right, sum+root->data, maxSum);
    }
}
int maxPathSum(Node* root)
{
    int maxSum = 0;
    func(root, 0, maxSum);
    return maxSum;
}
```

<br><br><h1>Sum of the longest leaf to root path</h1>
If two or more paths compete for the longest path, then the path having maximum sum of nodes is being considered.<br>

```cpp
void func(Node* root, int level, int &maxLevel, int sum, int &maxSum) {
   if (root == NULL) {
   if (level > maxLevel) {
            maxLevel = level;
            maxSum = sum;
        } else if (level == maxLevel) {
            if (sum > maxSum) maxSum = sum;
        }
    } else {
        func(root->left,level+1,maxLevel,sum + root->data,maxSum);
        func(root->right,level+1,maxLevel,sum + root->data,maxSum);
    }
}
int sumOfLongRootToLeafPath(Node *root)
{
    int maxSum = 0;
    int maxLevel = -1;
    func(root, 0, maxLevel, 0, maxSum);
    return maxSum;
}
```
<br><br><div align="center">14</div>
<h1>Transform to Sum Tree</h1>
Given a Binary Tree, where each node can have positive or negative values. Convert this to a tree where each node contains the sum of the left and right sub trees of the original tree. The values of leaf nodes are changed to 0.
<br>

```cpp
void toSumTree(Node *root)
{
    if (root == NULL) return;
    int left = 0, right = 0;
    if (root->left) {
        left = root->left->data;
        toSumTree(root->left);
        left += root->left->data;
    }
    if (root->right) {
        right = root->right->data;
        toSumTree(root->right);
        right += root->right->data;
    }
    root->data = left + right;
}
```
<br><br><h1>Check if binary tree is Sum Tree</h1>

```cpp
bool isSumTree(Node* root)
{
    if (root == NULL) return true;
    if (root->left == NULL && root->right == NULL) return true;
    if (!isSumTree(root->left) || !isSumTree(root->right)) return false;
    int sum = 0;
    if (root->left) {
        sum += root->left->data;
        if (root->left->left || root->left->right) sum += root->left->data;
    }
    if (root->right) {
        sum += root->right->data;
        if (root->right->left || root->right->right) sum += root->right->data;
    }
    return (root->data == sum);
}
```
<br><br><br><div align="center">15</div>
<h1>Symmetric Tree</h1>
Given the root of a binary tree, check whether it is a mirror of itself (i.e., symmetric around its center).
<br><br><br>

```cpp
// Helper function to check two trees are mirrors of each other
bool areMirror(Node* r1, Node *r2){
    if (r1 == NULL && r2 == NULL) return true;
    if (r1 == NULL || r2 == NULL) return false;
    if (r1->val != r2->val) return false;
    return (areMirror(r1->left,r2->right) && areMirror(r1->right,r2->left));
}
bool isSymmetric(Node* root) {
    if (root == NULL) return true;
    return areMirror(root->left, root->right);
}
```
<br><br><br><h1 style="">Views of a tree</h1>
For a binary tree, there exists four types of views.<br><br>

- <b> Left View :</b><br>
The set of nodes visible when the tree is viewed from the left side.
- <b> Right View :</b><br>
The set of nodes visible when the tree is viewed from the right side.
- <b> Top View :</b><br>
The set of nodes visible when the tree is viewed from the top.
- <b> Bottom View :</b><br>
The set of nodes visible when the tree is viewed from the bottom.

<br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">16</div>
<h2>Left View</h2>
<h3>Recursive implementation</h3>

```cpp
void dlr(Node* temp, int level, int &maxLevel, vector<int> &res) {
    if (temp==NULL) return;
    if (level>maxLevel) {
        res.push_back(temp->data);
        maxLevel = level;
    }
    dlr(temp->left,level+1,maxLevel,res);
    dlr(temp->right,level+1,maxLevel,res);
}
vector<int> leftView(Node *root)
{
    vector<int> res;
    int maxLevel = -1;
    dlr(root,0,maxLevel,res);
    return res;
}
```
<br><h3>Iterative implementation</h3>

```cpp
vector<int> leftView(Node *root)
{
   vector<int> res;
   if (root==NULL) return res;
   queue<Node*> q;
   q.push(root);
   bool isLeftNode = true;
   
   while(!q.empty()){
        int size = q.size();
        while(size--) {
            Node* temp = q.front();
            q.pop();
            if (isLeftNode) {
                res.push_back(temp->data);
                isLeftNode = false;
            }
            if (temp->left) q.push(temp->left);
            if (temp->right) q.push(temp->right);
       }
       isLeftNode = true;
   }
   return res;
}
```
<div align="center">17</div>
<h2>Right View</h2>
<h3>Recursive implementation</h3>

```cpp
void drl(Node* temp, int level, int &maxLevel, vector<int> &res) {
    if (temp==NULL) return;
    if (level>maxLevel) {
        maxLevel = level;
        res.push_back(temp->data);
    }
    drl(temp->right,level+1,maxLevel,res);
    drl(temp->left,level+1,maxLevel,res);
}
vector<int> rightView(Node *root)
{
    vector<int> res;
    int maxLevel = -1;
    drl(root,0,maxLevel,res);
    return res;
}
```
<br><br><h3>Iterative implementation</h3>

```cpp
vector<int> rightView(Node *root)
{
    vector<int> res;
    if (root==NULL) return res;
    queue<Node*> q;
    q.push(root);
    
    while(!q.empty()){
        int size = q.size();
        int lastNode;
        while(size--) {
            Node* temp = q.front();
            q.pop();
            lastNode = temp->data;
            if (temp->left) q.push(temp->left);
            if (temp->right) q.push(temp->right);
        }
        res.push_back(lastNode);
    }
    return res;
}
```
<br><br><div align="center">18</div>

<h2>Top View (recursive)</h2>

```cpp
void ldr(Node* root, map<int, pair<int,int>> &mp, int vlevel, int hlevel) {
    if (root==NULL) return;
    if (mp.find(vlevel) == mp.end() || mp[vlevel].second > hlevel) {
        mp[vlevel] = {root->data,hlevel};
    }
    ldr(root->left,mp,vlevel-1,hlevel+1);
    ldr(root->right,mp,vlevel+1,hlevel+1);
}
vector<int> topView(Node *root)
{
    vector<int> res;
    map<int, pair<int,int>> mp;
    ldr(root, mp, 0, 0);
    for (auto it:mp) {
        res.push_back(it.second.first);
    }
    return res;
}
```
<br><br><br>
<h2>Bottom View (recursive)</h2>

```cpp
void ldr(Node* root, map<int, pair<int,int>> &mp, int vlevel, int hlevel) {
    if (root==NULL) return;
    if (mp.find(vlevel) == mp.end() || mp[vlevel].second <= hlevel) {
        mp[vlevel] = {root->data,hlevel};
    }
    ldr(root->left,mp,vlevel-1,hlevel+1);
    ldr(root->right,mp,vlevel+1,hlevel+1);
}
vector<int> bottomView(Node *root)
{
    vector<int> res;
    map<int, pair<int,int>> mp;
    ldr(root, mp, 0, 0);
    for (auto it:mp) {
        res.push_back(it.second.first);
    }
    return res;
}
```
<br><br><br><div align="center">19</div>
<h1>Check if Binary Tree is Isomorphic</h1>
Two trees are called isomorphic if one can be obtained from another by a series of flips, i.e. by swapping left and right children of several nodes. Any number of nodes at any level can have their children swapped. <br><br>

```cpp
bool isIsomorphic(Node *root1,Node *root2)
{
    if (root1 == NULL && root2 == NULL) return true;
    if (root1 == NULL || root2 == NULL) return false;
    if (root1->data != root2->data) return false;
    bool withoutSwap = isIsomorphic(root1->left,root2->left) && isIsomorphic(root1->right,root2->right);
    bool withSwap = isIsomorphic(root1->left,root2->right) && isIsomorphic(root1->right,root2->left);
    return (withSwap || withoutSwap);
}
```
