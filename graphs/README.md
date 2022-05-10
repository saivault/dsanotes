<h1 style="font-size: 60px;">Graphs</h1><br><br><br><br>
When we talk about graphs, what comes to mind are the conventional graphs used to model data. In computer science, the term "graph" has a completely different meaning.<br><br><br>
<a href="#intro">Introduction</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
<a href="#traversal">Traversal Algorithms</a> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="#bipartite">Bipartite check</a><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="#nop">Number of Paths</a><br>
<a href="#cycle">Cycle Detection</a><br>
<a href="#tree">Tree vs Graph</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
<a href="#grid">Matrix (grid) as graph</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#floodfill">Flood Fill</a>
&nbsp;&nbsp;&nbsp;&nbsp;<a href="#islands">Number of Islands</a><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="#knight">Minimum knight moves</a><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<a href="#covid">COVID spread</a><br>
<a href="#implicit">Implicit Graph</a>&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<a href="#snake">Snakes and Ladders</a><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <a href="#wordladder">Word Ladder</a><br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;  <a href="#circlestring">Circle of Strings</a><br>
<a href="#topo">Topological Sorting</a><br>
<a href="#reconstruct">re</a><br>
<a href="#task">Task scheduling</a><br>
<a href="#alien">Alien Dictionary</a><br>
<a>Haha</a><br>
<a>Haha</a><br>
<a>Haha</a><br>
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">0</div>
<h1 id="intro">Definition</h1>
A graph is a <b>non-linear</b> structure amounting to a finite set of objects in which some pairs of the objects are in some sense <b>related</b>. The objects correspond to mathematical abstractions called vertices (also called nodes) and each of the related pairs of vertices is called an edge (also called link).<br><br>
Typically, a graph is depicted in diagrammatic form as a set of dots or circles for the vertices, joined by lines or curves for the edges.<br><br><br>
<div align="center">
<img src="https://upload.wikimedia.org/wikipedia/commons/5/5b/6n-graf.svg"><br>
A graph with six vertices and seven edges
</div><br><br><br>
<h3>Concept of direction</h3>
The edges may be directed or undirected. <br>For example, if the vertices represent people at a party, and there is an edge between two people if they shake hands, then this graph is undirected because any person A can shake hands with a person B only if B also shakes hands with A. <br>In contrast, if any edge from a person A to a person B corresponds to A owes money to B, then this graph is directed, because owing money is not necessarily reciprocated.<br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">1</div>
<h2>Basic terminology</h2><br>
- <b>Adjacency</b><br>
&nbsp; Two vertices are said to be adjacent if there is an edge connecting them directly.<br>
- <b>Self-loop</b><br>
&nbsp; An edge which starts and ends on the same vertex.<br>
- <b>Parallel Edges</b><br> 
&nbsp; Two undirected edges are parallel if they have the same end vertices.<br>
&nbsp; Two directed edges are parallel if they have the same origin and destination.<br>
- <b>Simple graph</b><br> 
&nbsp; A  graph with no self-loops or parallel edges.<br>
- <b>Degree of a vertex</b><br>
&nbsp; The total number of edges connected to a vertex.<br> 
&nbsp; There are two types of degrees:<br> 
&nbsp; In-Degree: The total number of incoming edges connected to a vertex.<br> 
&nbsp; Out-Degree: The total number of outgoing edges connected to a vertex.<br><br>

<b>Note</b>:- A vertex in a graph may belong to no edge of it.<br><br><br>
<b>Graphs can be used to model several real-world situations:</b><br><br>
• How can we lay cable at minimum cost to make every telephone reachable from every other?<br>
• What is the fastest route between two given cities?<br>
• How can we assign n jobs to n people to get the best combination of people assigned to the jobs.<br>
• How many layers does a computer chip need so that wires in the same layer don’t cross?<br>
• How can the season of a sports league be scheduled into the minimum number of weeks?<br>
• In what order should a traveling salesman visit cities to minimize travel time?<br>
• Can we color the regions of every map using four colors so that neighboring regions receive different colors?<br>
• How to visualize people and their relationships in social networks ?
<br><br>
<blockquote>&nbsp; We will be dealing with simple graphs mostly.<br></blockquote><br>
<div style="display:flex">
<div>
<h2>Ways to Represent a Graph</h2>
The two most common ways to represent a graph are: &nbsp;&nbsp;<br><br>
<ol>
<li>Adjacency Matrix</li>
<li>Adjacency List</li>
</ol>
</div>
<img src="https://cdncontribute.geeksforgeeks.org/wp-content/uploads/undirectedgraph.png" height="100" width="180">
</div>
<br><br><br><br>
<div align="center">2</div>
<h2>Adjacency matrix</h2>
The adjacency matrix is a two dimensional matrix  where each cell can contain a 0 or 1. The row and column headings represent the vertices.<br>
If a cell contains 1, there exists an edge between the corresponding vertices<br>
<b>Eg:-</b> Matrix[i][j]=1 indicates that an edge exists between vertex i and j. Also, <br>
&nbsp;&nbsp;&nbsp;&nbsp; Matrix[i][j]=0 indicates that no edge exists between vertex i and j.<br><br>
For a directed graph, the usual convention is to think of the rows as sources and the columns as destinations.<br><br>
Adjacency matrix for the above graph is given by<br><br>
<div style="padding-left:170px;">
<table>
<tr><td></td><td><b>0</b></td><td><b>1</b></td><td><b>2</b></td><td><b>3</b></td><td><b>4</b></td></tr>
<tr><td><b>0</b></td><td>0</td><td>1</td><td>0</td><td>0</td><td>1</td></tr>
<tr><td><b>1</b></td><td>1</td><td>0</td><td>1</td><td>1</td><td>1</td></tr>
<tr><td><b>2</b></td><td>0</td><td>1</td><td>0</td><td>1</td><td>0</td></tr>
<tr><td><b>3</b></td><td>0</td><td>1</td><td>1</td><td>0</td><td>1</td></tr>
<tr><td><b>4</b></td><td>1</td><td>1</td><td>0</td><td>1</td><td>0</td></tr>
</table>
</div><br><br>
- As we can see, the adjacency matrix of an undirected graph is symmetric.<br>
which means if Matrix[i][j]=x then Matrix[j][i] = x<br>
- Adjacency Matrix is also used to represent weighted graphs. If adj[i][j] = w, then there is an edge from vertex i to vertex j with weight w. <br><br>

<h2>Adjacency List</h2>
An array of linked list is used to store all the edges in the graph. The size of the array is equal to the number of vertices.<br> Each index in this array represents a specific vertex in the graph. The entry at index i of the array contains a linked list containing the vertices that are adjacent to vertex i.<br><br>
Adjacency list for the above graph is given by<br><br>
<div style="padding-left:170px;">
<b>0</b> -> 1 -> 4 -> NULL<br>
<b>1</b> -> 0 -> 2 -> 3 -> 4 -> NULL<br>
<b>2</b> -> 1 -> 3 -> NULL<br>
<b>3</b> -> 1 -> 2 -> 4 -> NULL<br>
<b>4</b> -> 0 -> 1 -> 3 -> NULL
</div><br><br>
<br><br><br><div align="center">3</div>
Let us compare their complexities<br>
Take the graph G = (V, E) where V is the set of vertices and E is the set of edges.<br><br><br>
<h2>Space complexity</h2>
Space complexity of adjacency matrix is O(V<sup>2</sup>)<br>
Space complexity of adjacency list is O(V+E)<br><br>
<b>Proof :-</b><br>
Size of array is |V|. These |V| lists each have the degree which is denoted by deg(v). We add up all those, and apply the Handshaking Lemma ∑deg(v)=2|E|. <br>
So, you have |V| references (to |V| lists) plus the number of nodes in the lists, which never exceeds 2|E|. Therefore, the worst-case space (storage) complexity of an adjacency list is O(|V|+2|E|) = O(|V|+|E|).<br>
Note that E may vary between O(1) and O(V<sup>2</sup>), depending on how dense the graph is.<br><br><br>
<h2>Time complexity</h2><br>
<div style="padding-left:65px;">
<table>
<th><td><b>Adjacency Matrix</b></td><td><b>Adjacency List</b></td></th>
<tr><td><b>Add Vertex</b></td><td>O(V<sup>2</sup>)</td><td>O(1)</td></tr>
<tr><td><b>Remove Vertex</b></td><td>O(V<sup>2</sup>)</td><td>O(E)</td></tr>
<tr><td><b>Add Edge</b></td><td>O(1)</td><td>O(1)</td></tr>
<tr><td><b>Remove Edge</b></td><td>O(1)</td><td>O(E)</td></tr>
<tr><td><b>Querying for an edge</b></td><td>O(1)</td><td>O(V)</td></tr>
<tr><td><b>Finding neighbours</b></td><td>O(V)</td><td>O(V)</td></tr>
</table>
</div><br>
1. Vertex operations in adjacency matrix are performed in O(V<sup>2</sup>) time as we have to reconstruct the whole adjacency matrix with the new V.<br>
2. Edge operations in adjacency matrix are performed in constant time as we only need to manipulate the value in the particular cell.<br>
3. Adding an edge in adjacency list take constant time as we only need to insert at the head node of the corresponding vertex.<br>
4. Removing an edge in adjacency list takes O(E) time, because in the worst case, all the edges could be at a single vertex and, hence, we would have to traverse all E edges to reach the last one.

<br><br><br><br><br><br><div align="center">4</div>
<h2>Comparison</h2>
Both representations are suitable for different situations. <br>
An adjacency matrix is a popular and simple way to represent a graph. However, it is most suitable when your model does not frequently manipulate vertices. Adjacency matrices are good for storing dense graphs, but in most of the other cases, an adjacency list is better than an adjacency matrix.<br><br><br>
<h2>Important</h2>
The usual representation of graphs in problems is as follows:<br>
An undirected graph is given with n vertices, where each vertex is labeled from 0 to n - 1 (inclusive). The edges in the graph are represented as a 2D integer array <i>edges</i>, where each <i>edges[i] = [u<sub>i</sub>,v<sub>i</sub>]</i> denotes an edge between vertex u<sub>i</sub> and vertex v<sub>i</sub>.<br><br>
<b>What to do then ?</b><br>
Don't continue with this representation unless the problem can be solved in O(1).<br>
Otherwise, it adds unrequired long traversals and checks thereby increasing the time complexity and making the code difficult to handle. Instead create an adjacency list or matrix from it to solve the problem.<br><br><br>
<h3>Creation of Adjacency List</h3>

```cpp
vector<vector<int>> graph(n);
for(int i=0; i<edges.size(); i++) {
    graph[edges[i][0]].push_back(edges[i][1]);
    graph[edges[i][1]].push_back(edges[i][0]);
}
```
<br><br>
<h3>Creation of Adjacency Matrix</h3>

```cpp
vector<vector<int>> graph;
for (int i=0; i<n; i++) {
    vector<int> temp(n,0);
    graph.push_back(temp);
}
for(int i=0; i<edges.size(); i++) {
    graph[edges[i][0]][edges[i][1]] = 1;
    graph[edges[i][1]][edges[i][0]] = 1;
}
```
<br><br><br><div align="center">5</div>
<h1 id="traversal">Traversal Algorithms</h1>
There are two basic techniques used for graph traversal:<br>
- Breadth First Search<br>
- Depth First Search<br>

In order to understand these algorithms, we will have to view graphs from a slightly different perspective.<br><br>
Any traversal needs a starting point. As Graph is a non-linear data structure, <br>
<b>how do we give graph traversal a better sense of direction?</b><br>
Sol:- This is where the <b>concept of levels</b> is introduced. <br><br>Take any vertex as the starting point. This is the lowest level in your search. The next level consists of all the vertices adjacent to your vertex. A level higher would mean the vertices adjacent to these nodes.<br><br>
<h3>Important</h3> 
While traversing, we always need to make sure that no node is visited more than once. Coz, if we empowering our algorithm to reach a node more than once, it means that we are allowing ourselves into <b>infinite loops</b> which we never want.<br><br>
So, We use an extra <b>visited</b> variable to keep track of vertices we have already visited. This 'visited' can be any data structure that can answer existence queries quickly. For example, a hash set or an array where each element maps to a vertex in the graph can both do this in constant time. We do this by initializing every vertex as unvisited. And, as soon as you encounter a node, consider it visited.<br><br>
The structure we follow for visited is as follows :<br>

```cpp
// n is the number of nodes
vector<bool> isVisited(n, false);                            
```
PS:- applicable only in cyclic graphs<br><br><br>
<h2>Breadth First Search (BFS)</h2>
The BFS algorithm earns its name because it grows breadth-wise. All the nodes in a certain level are traversed before moving on to the next level.<br>
The level-wise expansion ensures that for any starting vertex, you can reach all others, one level at a time.<br><br>
Here, extra memory, usually a <b>queue</b>, is needed to keep track of the next level nodes that were encountered but not yet explored.<br><br><br><br><br>
<div align="center">6</div>
<h3>Implementation</h3>

```cpp
vector<int> bfsOfGraph(int n, vector<vector<int>> &graph) {
    queue<int> q;
    vector<bool> isVisited(n, false);
    q.push(0);
    isVisited[0] = true;

    vector<int> res;
    while (!q.empty()){
        int front = q.front();
        res.push_back(front);
        q.pop();

        for (int i=0; i<graph[front].size(); i++) {
            int adjacentNode = graph[front][i];
            if (!isVisited[adjacentNode]) {
                isVisited[adjacentNode] = true;
                q.push(adjacentNode);
            }
        }
    }

    return res;
}
```
<br><br><h3>Tracking levels / Finding distance</h3><br>
BFS is by-level traversal.<br>
Sometimes we need to track how many levels we have traversed.<br>
Sometimes we need to calculate the shortest distance between two nodes.<br>
We can do both of the above using BFS with slight code changes.<br><br>
These can be done in two ways : <br>
1. At the start of every level, We can get the number of nodes of that particular level from the queue size. So, after popping queueSize number of items we can increase our level index. <br>
2. Push an non-applicable element like null pointer or -1(sometimes) into the queue right after pushing root into the queue. And whenever we pop this non-applicable element from the queue, we can increase our level index and push this element again(when non-empty queue).<br><br><br><br><br><br>

<div align="center">7</div><h3>Implementation of first approach</h3>

```cpp
int level = 0;
q.push(startEle);
isVisited[startEle] = true;

while (!q.empty()){
    int numOfNodes = q.size();
    cout<<"Number of nodes in level "<<level<<" are "<<numOfNodes<<"\n";

    while (numOfNodes--)
        int front = q.front();
        res.push_back(front);
        q.pop();

        for (int i=0; i<graph[front].size(); i++) {
            int adjacentNode = graph[front][i];
            if (!isVisited[adjacentNode]) {
            cout<<"The shortest distance between start node and "<<adjacentNode<< " is "<<level+1<<"\n";
                isVisited[adjacentNode] = true;
                q.push(adjacentNode);
            }
        }
    }
    level++;
}
```

<br><br><br><h2>Depth First Traversal (DFS)</h2>
The DFS algorithm is the opposite of BFS in the sense that it grows depth-wise.<br>
Starting from any node, we keep moving to an adjacent node until we reach the farthest level, then we move back to the starting point and pick another adjacent node. Once again, we probe till the farthest level and move back. This process continues until all nodes are visited.<br><br>
DFS can be also used to calculate the shortest distance and the number of nodes in a particular level but with a TLE<br><br>
To go deeper into a node and to retrace back and follow a different path everytime, we can use recursion. If we don't want to use the recursion call stack, we can use our custom stack. Recursion approach is easy to code when solving problems. <br><br><br><br><br>
<div align="center">8</div>
<h3>Recursion approach</h3>

```cpp
vector<int> dfsOfGraph(int n, vector<vector<int>> &graph) {
    vector<bool> isVisited(n, false);
    vector<int> res;
    dfsAtNode(0, graph, isVisited, res);
    return res;
}
    
void dfsAtNode(int node, vector<vector<int>> &graph, vector<bool> &isVisited, vector<int> &res) {
    if (isVisited[node]) return;
    isVisited[node] = true;
    res.push_back(node);

    for (int i=0; i<graph[node].size(); i++) {
        dfsAtNode(graph[node][i], graph, isVisited, res);
    }
}
```
<br><br><br>
<h3>Stack approach</h3>

```cpp
vector<int> dfsOfGraph(int n, vector<int> graph[]) {
    vector<bool> isVisited(n, false);
    stack<int> s;
    s.push(0);
    vector<int> res;
        
    while(!s.empty()){
        int node = s.top();
        s.pop();
        if (!isVisited[node]){
            isVisited[node] = true;
            res.push_back(node);
            for (int i=graph[node].size()-1; i>=0; i--) {
                if (!isVisited[graph[node][i]]) {
                    s.push(graph[node][i]);
                }
            }
        }
    }
    return res;
}
```
<br><br><div align="center">9</div>
<h3>Time and Space complexities</h3>
Time complexity of either of the algorithms is the space complexity of the representation used as we are visiting each node only once.<br><br>
Auxiliary Space is O(n), since an extra visited array of size n is required.<br>
The additional stack/queue memory taken by each algorithm heavily depends on the structure of our graph. <br><br><br>
<h1>Some More Terminology</h1><br>
<h2>PATH</h2>
A finite or infinite sequence of edges which joins a sequence of vertices, which are all distinct. <br>
<h2>CYCLE</h2>
A path that starts and ends at the same vertex.<br>
<h2>CONNECTED GRAPH</h2>
A graph is said to be connected if there is a path between every pair of vertex.<br>
<h2>CYCLIC GRAPH</h2>
A graph with atleast one cycle.<br>
<h2>TREE</h2>
A tree is a special graph -  <b>connected acyclic</b> (cycle-less) graph.<br>
Traversals like BFS or DFS on a connected graph produces a tree.<br><br>
The depth–first search for trees can be implemented using preorder, inorder, and postorder, while the breadth–first search for trees can be implemented using level order traversal.<br>
<h2>FOREST</h2>
A forest is a <b>disconnected acyclic</b> graph. <br>
In other words, a disjoint collection of trees is known as forest.<br>
Traversals like BFS or DFS on a disconnected graph produces a forest.<br><br>
<b>Assumption taken:-</b> The above codes traverse only the vertices reachable from a given source vertex. We took the source vertex as zero.<br>
All the vertices may not be reachable from a given vertex (as in disconnected graph). To print all the vertices, we can modify each function to do traversal starting from all nodes one by one.<br><br>
Traversals for disconnected graphs are written as :
<br><br><br><div align="center">10</div>

```cpp
void traverse(int node, vector<vector<int>> &graph, vector<bool> &isVisited){
    // DFS or BFS
}

void traverseAll(int n, vector<vector<int>> &graph) {
    vector<bool> isVisited(n, false); 
    for (int i=0; i<n; i++) {
        if (!isVisited[i]) traverse(i, graph, isVisited)
    }
}
```
<br><br><h2>Questions</h2>
1) Which algorithm can be used to <b>check a path exists between two vertices</b> ?<br>
Sol:- Both. Start traversing from the source node. If any upcoming node is the destination node, it indicates the existence of a path.<br><br> 
2) Which algorithm can be used to <b>detect a cycle</b> ?<br>
Sol:- Both. While traversing, if we find an edge from the current node to an already visited node, a cycle is present. And that edge is called a back-edge. <br><br>
3) Which algorithm can be used to check a graph is <b>connected</b> or not ?<br>
Sol:- Both. we can start traversing from any vertex and check if all vertices are reachable or not from that vertex.<br><br>
4) Which algorithm is best for finding the <b>shortest distance between two points</b> ?<br>
Sol:- BFS<br>
Technically both. But in a large graph, DFS may go too far in the wrong direction, whereas BFS will traverse the closest points first, and therefore be more efficient.<br><br>
5) Which algorithm is best for <b>finding the nearest nodes</b> ?<br>
Sol:- BFS. That's why it is used in GPS Navigation, Peer to peer networks, Social networking sites etc...<br><br>
6) Which algorithm is best when working with <b>wide graphs</b> ?<br>
Sol:- DFS, as it uses less memory than BFS for wide graphs. Since BFS has to keep all the nodes in the queue, and for wide graphs this can be quite large.<br><br>
7) Which algorithm is best when working with <b>deep graphs</b> ?<br>
Sol:- BFS, as it uses less call stack memory than BFS for dense graphs. Since DFS is doing recursion calls using call stack, and for dense graphs this can be quite large. <br><br><br><br><br><br><br>
<div align="center">11</div>
Click <a href="https://practice.geeksforgeeks.org/problems/bfs-traversal-of-graph/1">here</a> for the BFS problem link<br>
Click <a href="https://practice.geeksforgeeks.org/problems/depth-first-traversal-for-a-graph/1">here</a> for the DFS problem link<br><br><br>

<h2>When to update 'visited' ?</h2>
Say we have a start node x in our traversal. Take another node y which can be reached from x in 2 paths of distances 2(xzy) and 4(xabcy).<br> Since in BFS, we complete level by level and if we are sure that y can be at a distance of 2 from x, as soon as we reach it in level 2, we should mark it visited. We will be storing only one instance of a node in the queue.<br><br>
<div align="center"><b>=> BFS ensures shortest distance.</b></div><br>
But in DFS, it may not be the case.<br>
y can be reached from x when the node reached in level is either z or a. If our traversal started with a, we will reach the y of level 4 first than level 2. Even though nodes of level 1 like z already has the neighbour a, we are not going to mark the node as visited. So, it is possible to multiple instances of a node in the stack.<br><br>
We are giving more importance to the path, whether all the nodes previous to it in its path from the start node are visited or not than encountering it first.<br><br><br><br><br>
<h2>BFS or DFS?</h2>
<h3>When should you use one over the other?</h3>
If you just have to visit each node once without memory constraints (e.g. number of islands problem), then it doesn't really matter which one you use. It comes down to your personal preference for recursion/stack vs queue.<br><br>
<b>BFS is better at:</b><br><ul>
<li>finding the shortest distance between two vertices.</li>
<li>graph of unknown size, e.g. word ladder, or even infinite size, e.g. knight shortest path</li></ul><br>
<b>DFS is better at:</b><br><ul>
<li>uses less memory than BFS for wide graphs, since BFS has to keep all the nodes in the queue, and for wide graphs this can be quite large.</li>
<li>finding nodes far away from the root, e.g. looking for an exit in a maze.</li><br><br><br><br><br><br><br><br>
<div align="center">34</div>
<h1 id="bipartite">Bipartite Graph check</h1>
Given a connected undirected graph, check whether it is bipartite or not.<br><br>
A bipartite graph is a graph whose vertices can be divided into two disjoint and independent sets U and V, such that every edge connects a vertex in U to vertex in V.<br><br><br>
Click <a href="https://practice.geeksforgeeks.org/problems/bipartite-graph/1/">here</a> for the problem link.
<br><br><br><br><br><br>

<h2>Solution</h2>
We will solve this problem by checking whether the graph can be coloured using two colors such that vertices in a set are colored with the same color and two adjacent nodes cannot have the same color<br><br>
f(x) = 1-x is a function which toggles its value between 0 and 1.<br><br>

```cpp
bool isBipartite(int n, vector<int> graph[]){
	queue<int> q;
    vector<int> color(n, -1);
    q.push(0);
    color[0] = 1;
	    
    while (!q.empty()) {
       int node = q.front();
       q.pop();
       for (int i=0; i<graph[node].size(); i++) {
           int adj = graph[node][i];
           if (color[adj] == -1) {
                // coloring adjacent node with different color
                color[adj] = 1 - color[node];
                q.push(adj);
           } else if (color[adj] == color[node]) {
                // two adjacent nodes cannot have the same color
                return false;
           }
	    }
	}
	    
	return true;
}
```
<br><div align="center">12</div>
<h1 id="nop">Number of paths</h1>
Given a directed acyclic graph(DAG) with n nodes labeled from 0 to n-1. Given edges, source and destination.<br> Count the number of ways to reach from source to destination. <br><br>
The edges in the graph are represented as a 2D integer array edges, where each edges[i] = [u<sub>i</sub>, v<sub>i</sub>] denotes an edge between vertex u<sub>i</sub> and vertex v<sub>i</sub>.<br><br>
These paths don’t contain a cycle, the simple enough reason is that a cycle contains an infinite number of paths and hence they create a problem.<br><br><br>
<b>Example:</b><br>
Input:  edges = {{0,1},{0,3},{1,2},{3,2}}, n = 4, src = 0, dest = 2<br>
Output: 2 <br>
Explanation: There are two ways to reach at 2 from 0. These are <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;1. 0->1->2 <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;2. 0->3->2<br><br><br>
<b>Constraints:</b><br>
1 <= n <= 15<br>
0 <= s, d <= n-1<br><br>
Click <a href="https://practice.geeksforgeeks.org/problems/count-the-paths4332/1">here</a> for the problem link <br><br><br>
<b>Follow-up:</b><br>
What if the graph contains a cycle ?<br>
Input:  edges = {{0,1},{0,2},{0,3},{1,2},{2,3},{3,3}, n = 4, src = 0, dest = 2<br>
Output: 2<br>
Explanation: 0->1->2, 0->2
<br><br><br>

```cpp
int countPaths(vector<vector<int>>edges, int n, int src, int dest) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><br><br><div align="center">12</div>

```cpp
int possible_paths(vector<vector<int>>edges, int n, int src, int dest){
	vector<vector<int>> graph(n);
    for(int i=0; i<edges.size(); i++) {
        graph[edges[i][0]].push_back(edges[i][1]);
    }
    return countPaths(graph, src, dest);
}
	
int countPaths(vector<vector<int>> &graph, int cur, int dest) {
	if (cur == dest) return 1;
    int ans = 0;
	for (int i=0; i<graph[cur].size(); i++) {
	    ans += countPaths(graph, graph[cur][i], dest);
    }
	return ans;
}
```

<br><br><br><br>Solution for the <b>follow up</b> problem is as follows : <br><br>
```cpp
int possible_paths(vector<vector<int>>edges, int n, int src, int dest){
    vector<vector<int>> graph(n);
    for(int i=0; i<edges.size(); i++) {
        graph[edges[i][0]].push_back(edges[i][1]);
    }
    vector<bool> isVisited(n, false);
    return countPaths(graph, src, dest, isVisited);
}
	
int countPaths(vector<vector<int>> &graph, int cur, int dest, vector<bool> &isVisited) {
	if (isVisited[cur]) return 0;
    if (cur == dest) return 1;
	isVisited[cur] = true;
    int ans = 0;
	for (int i=0; i<graph[cur].size(); i++) {
        ans += countPaths(graph, graph[cur][i], dest, isVisited);
	}
    isVisited[cur] = false;
	return ans;
}
```
<br><b>Important</b>:- We are making each node unvisited when reached to the deepest node and tracing back. Coz there can be different paths ending with the same set of vertices.<br><br><div align="center">13</div>
<h1 id="cycle">Cycle Detection</h1>
Given a graph with n vertices and e edges, check whether it contains any cycle or not.<br><br>
Graph is represented as adjacency list in the input<br>
Write code for both undirected and directed graphs<br><br><br>
<b>Example-1 :</b> undirected<br>
Input:  edges = {{0,1},{0,2},{2,3},{2,1}}, n = 4<br>
Output: True <br>
Explanation: 0->1->2->0 <br><br>
<b>Example-2 :</b> undirected<br>
Input:  edges = {{3,1},{0,1},{2,1}}, n = 4<br>
Output: False <br><br>
<b>Example-3 :</b> directed<br>
Input:  edges = {{0,1},{0,2},{2,3},{2,1}}, n = 4<br>
Output: True <br>
Explanation: 0->1->2->0 <br><br>
<b>Example-4 :</b> directed<br>
Input:  edges = {{3,1},{0,1},{2,1}}, n = 4<br>
Output: False <br><br><br>
<b>Constraints:</b><br>
1 ≤ n,e ≤ 10<sup>5</sup><br><br><br>
Click <a href="https://practice.geeksforgeeks.org/problems/detect-cycle-in-an-undirected-graph/1">here</a> for the undirected problem link<br>
Click <a href="https://practice.geeksforgeeks.org/problems/detect-cycle-in-a-directed-graph/1">here</a> for the directed problem link<br><br><br><br>

```cpp
bool isCyclic(int n, vector<int> graph[]) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><br><div align="center">14</div>
<h3>for Undirected graph</h3><br>

```cpp
bool isCyclic(int n, vector<int> graph[]) {
    vector<bool> isVisited(n,false);
    for (int i=0; i<n; i++) {
        // can pass -1 as nodes start from zero
        if (!isVisited[i] && isCycleDFS(i, graph, isVisited, -1)) return true;
    }
    return false;
}
    
bool isCycleDFS(int node, vector<int> graph[], vector<bool> &isVisited, int parent) {
    isVisited[node] = true;
    for (int i=0; i<graph[node].size(); i++) {
        int ele = graph[node][i];
        if (ele != parent) {
            if (isVisited[ele]) return true;
            else if (isCycleDFS(ele, graph, isVisited, node)) return true;
        }
    }
    return false;
}
```
<br><br><br><h3>Logic Used:</h3>
- While traversing and forming a path, if we encounter a node which is already present in the path, it indicates a cycle.<br>
- <b>BUT</b>, incase of an undirected graph, for every node, we will encounter the <b>parent node</b> which is already present in the path. This implies we are calling a single edge "a cycle". So the extra parent node check is added.<br>
- If we know that, on starting dfs from a particular node in the graph, a cycle cannot be found, then if we reach the same node again, we won't be interested in going deep again. So, everytime when we start dfs from a node, we make sure that the node is unvisited.

<br><br><br><br><br><br><br><br><br><br><div align="center">15</div>
<h3>for Directed graph</h3><br>

```cpp
 bool isCyclic(int n, vector<int> graph[]) {
    vector<bool> isVisited(n,false);
    vector<bool> isInPath(n,false);
    for (int i=0; i<n; i++) {
        if (!isVisited[i] && isCycleDFS(i, graph, isVisited, isInPath)) return true;
    }
    return false;
}
    
bool isCycleDFS(int node, vector<int> graph[], vector<bool> &isVisited, vector<bool> &isInPath) {
    isVisited[node] = true;
    isInPath[node] = true;
    for (int i=0; i<graph[node].size(); i++) {
        int ele = graph[node][i];
        if (isInPath[ele]) return true;
        else if (!isVisited[ele] && isCycleDFS(ele, graph, isVisited, isInPath)) return true;
    }
    isInPath[node] = false;
    return false;
}
```
<br><br><br><br><h3>Logic Used:</h3>
- While traversing and forming a path, if we encounter a node which is already present in the path, it indicates a cycle. That's why we are maintaining the isInPath array.<br>
- <b>why to do</b> isInPath[node] = false when ignoring the node ?<br>

<br><br><br><br><br><br><br><br><br><br><br><br><div align="center">16</div>
<h1 id="tree">Tree vs Graph</h1><br>
As we already know, a tree is a special graph - <b>connected acyclic</b> (cycle-less) graph.<br><br><br>
<div style="padding-left:130px">
<table>
<th><td><b>Tree</b></td><td><b>Graph</b></td></th>
<tr><td>1</td><td>nodes</td><td>vertices</td></tr>
<tr><td>2</td><td>children</td><td>neighbours</td></tr>
<tr><td>3</td><td>preorder, inorder, postorder</td><td>DFS</td></tr>
<tr><td>4</td><td>levelorder</td><td>BFS</td></tr>
</table>
</div><br><br><br>
Also a tree of n vertices has n-1 edges.<br>
And, there exists only one path between any two nodes<br><br>
<h3>Directed or Undirected</h3>
Trees are undirected graphs. Often we see pointers from parent to children but we can have a parent pointer for each children too.<br><br><br>
An undirected graph is tree if it has following properties. <br>
1) There is no cycle. <br>
2) The graph is connected. <br><br><br><br><br><br><br><br><br><br><br><br><br><br> <br><br><br><br><br><br><br><div align="center">17</div>
<h1 id="grid">Matrix(Grid) as graph</h1>
Very often, graph problems are represented as matrices.<br>
A matrix translates to a graph (adjacency list):
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/graphtolist.png" height="250" width="500"> <br>
When we code the problem, we have to build the graph as we go. Nodes/vertices are represented by coordinates of matrix.
<div style="display:flex">
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/rowandcolumn.png" height="200" width="200">
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/moves.png" style="padding-top:30px" height="200" width="200">
</div><br><br><br>
<h3>Getting neighboring node's coordinates</h3>
The core of BFS/DFS is to add neighbours 4 (or 8 if you are allowed to go diagonal) of the current vertex to a queue/stack. One way to get each neighbour's coordinates is to keep each neighbor's horizontal and vertical offsets (i.e. delta) in a list and adding them to the each vertex's coordinates. <br><br>
Also we cannot pass across the grid walls. So the horizontal and vertical indices of the new coordinate formed should be valid ones. <br><br><br><br><br>
<div align="center">29</div>

```cpp
// Currently we are located at the coordinate (x,y)
int dx = [-1,0,0,1];
int dy = [0,-1,1,0];

for (int i=0; i<4; i++) {
    int r = x + dx[i], c = y + dy[i];
    
    // valid coordinate check
    if (r>=0 && r<n && c>=0 && c<m) {
        // Use the new coordinate (r,c)
    }
}
```
<br><br><br><br><h3>'visited' alternative</h3>
Sometimes, we can overwrite the value in the matrix to keep track of the visited nodes without using a visited set. We'll see this in Number of Islands.<br><br><br>
<h3>Updation of 'levels' concept</h3>
Usually, we will maintain the nodes across various levels only from a particular node in BFS/DFS. But in some cases, the levels are defined based on their nearest node in the predefined set of vertices. So we will start with pushing all these set of predefined vertices into the queue and then continue solving the problem.
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">30</div>
<h1 id="floodfill">Flood Fill</h1>
An image is represented by an m x n integer grid image where image[i][j] represents the pixel value of the image.<br>
You are also given three integers sr, sc, and newColor. You should perform a flood fill on the image starting from the pixel image[sr][sc].<br><br>
To perform a flood fill, consider the starting pixel, plus any pixels connected 4-directionally to the starting pixel of the same color as the starting pixel, plus any pixels connected 4-directionally to those pixels (also with the same color), and so on. Replace the color of all of the aforementioned pixels with newColor.<br><br>
Return the modified image after performing the flood fill.<br><br>
<b>Example:-</b><br>
Input: image = [[1,1,1],[1,1,0],[1,0,1]], sr = 1, sc = 1, newColor = 2<br>
Output: [[2,2,2],[2,2,0],[2,0,1]]<br>
Explanation: <br>
1 1 1     &nbsp;&nbsp;         2 2 2<br>
1 1 0      =>      2 2 0<br>
1 0 1     &nbsp;&nbsp;         2 0 1<br><br>
Click <a href="https://leetcode.com/problems/flood-fill/">here</a> for the problem link<br><br>
<h2>Solution</h2>

```cpp
vector<vector<int>> floodFill(vector<vector<int>>& image, int sr, int sc, int newColor) {
    int oldColor = image[sr][sc];
    if (oldColor != newColor) {
        dfs(image, sr, sc, newColor, oldColor);
    }
    return image;
}
    
void dfs(vector<vector<int>>& image, int r, int c, int newColor, int oldColor) {
    if (r<0 || r>=image.size() || c<0 || c>=image[0].size() || image[r][c]!=oldColor){ 
        return;
    }
    image[r][c] = newColor;
    dfs(image, r, c+1, newColor, oldColor);
    dfs(image, r, c-1, newColor, oldColor);
    dfs(image, r-1, c, newColor, oldColor);
    dfs(image, r+1, c, newColor, oldColor);
}
```
<br><div align="center">31</div>
<h1 id="islands">Number of Islands</h1>
Given an m x n 2D binary grid grid which represents a map of '1's (land) and '0's (water), return the number of islands.<br><br>
An island is surrounded by water and is formed by connecting adjacent lands horizontally or vertically. You may assume all four edges of the grid are all surrounded by water.<br><br><br>
<b>Example - 1:</b><br>
Input: grid = [<br>
  ['1','1','1','1','0'],<br>
  ['1','1','0','1','0'],<br>
  ['1','1','0','0','0'],<br>
  ['0','0','0','0','0']<br>
]<br>
Output: 2<br><br>
<b>Example - 2:</b><br>
Input: grid = [<br>
  ['1','1','0','0','0'],<br>
  ['1','1','0','0','0'],<br>
  ['0','0','1','0','0'],<br>
  ['0','0','0','1','1']<br>
]<br>
Output: 3<br><br><br>
<h3>Follow up</h3>
The area of an island is the number of cells with a value 1 in the island.<br>
Return the maximum area of an island in grid.<br><br><br>
Click <a href="https://leetcode.com/problems/number-of-islands/">here</a> for the problem link<br>
Click <a href="https://leetcode.com/problems/max-area-of-island/">here</a> for the follow up problem link<br><br><br>

```cpp
int numIslands(vector<vector<char>>& grid) {
     // Your code ...
}
```
<br><br><br><br><br><br><br><div align="center">34</div>
```cpp
int numIslands(vector<vector<char>>& grid) {
    int count = 0;
    for (int i=0; i<grid.size(); i++) {
        for (int j=0; j<grid[0].size(); j++) {
            if (grid[i][j] == '1') {
                dfs(i,j,grid);
                count++;
            }
        }
    }
    return count;
}
    
void dfs(int x, int y, vector<vector<char>>& grid) {
    if (x<0 || x>=grid.size() || y<0 || y>=grid[0].size() || grid[x][y]=='0') return;
    grid[x][y] = '0';
    dfs(x,y+1,grid);
    dfs(x,y-1,grid);
    dfs(x-1,y,grid);
    dfs(x+1,y,grid);
}
```
<br><br><br>
To find an island, we can do BFS/DFS on a node and expand our search if the neighboring cell is also 1<br><br><br>
<h3>Hack Used</h3>
When visiting every neighbour, we are updating its value to 0 from 1 which is not required in the problem. Still, we are doing this because to save O(n*m) memory for isVisited array.<br>
Node with value zero - non reachable node or already visited node.<br><br><br>
<h3>Follow up solution</h3>
1. No need of maintaining the count variable<br>
2. Initialize area of an island as zero before starting the traversal. <br>
3. Pass this variable as a integer reference to the dfs() and increment it by one on<br>&nbsp;&nbsp; every new non-zero value node visit. At the end of each dfs, this reference will<br>&nbsp;&nbsp; store the area of that island<br>
4. Return the maximum of areas of all the possible islands<br><br><br><br><br>

<div align="center">33</div>
<h1 id="knight">Minimum Knight moves</h1>
On an infinitely large chessboard, a knight is located on [0, 0]. A knight can move in eight directions. Given a destination coordinate [x, y], determine the minimum number of moves from [0, 0] to reach it.<br>
It is guaranteed the answer exists.<br><br><br><br>
<b>Example 1:</b><br>
Input: x = 2, y = 1<br>
Output: 1<br>
Explanation: [0, 0] → [2, 1]<br><br>
<b>Example 2:</b><br>
Input: x = 5, y = 5<br>
Output: 4<br>
Explanation: [0, 0] → [2, 1] → [4, 2] → [3, 4] → [5, 5]<br><br>
<b>Constraints:</b><br>
|x| + |y| <= 300<br><br>
<br><br><br>

```cpp
int get_knight_shortest_path(int x, int y) {
    Your code ...
}
```
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">43</div>

```cpp
int get_knight_shortest_path(int x, int y) {
    queue<pair<int,int>> q;
    map<pair<int,int>, bool> isVisited;
    pair<int,int> temp = make_pair(0,0);
    q.push(temp);
    isVisited[temp] = true;
           
    // creating to move in 8 possible directions
    int dr[] = {1,1,2,2,-1,-1,-2,-2};
    int dc[] = {2,-2,1,-1,2,-2,1,-1};
    int dist = 0;
	    
    while (!q.empty()) {
       int size = q.size();
       while (size--) {
            pair<int, int> front = q.front();
            q.pop();
            int r = front.first, c = front.second;
            
            // traversing through all the neighbour nodes
            for (int i=0; i<8; i++) {
                int adjR = r+dr[i], adjC = c+dc[i];
                temp = make_pair(adjR, adjC);
                
                // visiting the not yet visited node
                // also every coordinate is valid in an infinite board
                if (!isVisited[temp]) {
                    if (adjR == x && adjC == y) return dist+1;
                    q.push(temp);
                    isVisited[temp] = true;
                }
            }
       }
       dist++;
    }
    return 0;
}
```
<br><br><br>
<h3>Approach</h3>
The problem asks for the minimum moves so BFS is our choice here. The chessboard being infinite is totally fine with BFS since we build the graph as we go.<br>
And since the chessboard is infinite, we no longer have to worry about bound checking unlike other grid columns which have n rows and m columns.<br><br><br><br><br>
<div align="center">34</div>
<h1 id="covid">COVID spread</h1>
Given a matrix arr[][], consisting of only 0, 1, and 2, that represents an empty ward, an uninfected patient, and an infected patient respectively. In one unit of time, an infected person at index (i, j) can infect an uninfected person adjacent to it i.e., at index (i – 1, j), (i + 1, j), (i, j – 1), and (i, j + 1). The task is to find the minimum amount of time required to infect all the patients. If it is impossible to infect all the patients, then print “-1”.<br><br>
<b>Example - 1 </b><br>
Input: arr[][] = {{2, 1, 0, 2, 1}, {1, 0, 1, 2, 1}, {1, 0, 0, 2, 1}}<br>
Output: 2<br>
Explanation:<br>
2 1 0 2 1<br>
1 0 1 2 1<br>
1 0 0 2 1<br>
At time t = 1: The patients at positions {0, 0}, {0, 3}, {1, 3} and {2, 3} will infect patient at {{0, 1}, {1, 0}, {0, 4}, {1, 2}, {1, 4}, {2, 4}} during 1st unit time.<br>
At time t = 2: The patient at {1,0} will get infected and will infect patient at {2,0}<br>
After the above time intervals all the uninfected patients are infected. Therefore, the total amount of time required is 2.<br><br><br>
<b>Example - 2 </b><br>
Input: arr[][] = {{2, 1, 0, 2, 1}, {0, 0, 1, 2, 1}, {1, 0, 0, 2, 1}}<br>
Output: -1<br>
Explanation:<br>
2 1 0 2 1<br>
0 0 1 2 1<br>
1 0 0 2 1<br>
The patient located at {2,0} can never be infected.<br><br><br>
Click <a href="https://practice.geeksforgeeks.org/problems/269f61832b146dd5e6d89b4ca18cbd2a2654ebbe/1/">here</a> for the problem link<br><br><br>

```cpp
int minTime(vector<vector<int>> hospital) {
    // Your code ...
}
```
<br><br><br><br><br><br><br><div align="center">36</div>

```cpp
int minTime(vector<vector<int>> hospital)
{
    int n=hospital.size(), m=hospital[0].size();
    int uninfected = 0;
    queue<pair<int,int>> q;
    int time = 0;
    int dr[] = {-1,0,0,1};
    int dc[] = {0,-1,1,0};
        
    for (int i=0; i<n; i++) {
        for (int j=0; j<m; j++) {
            if (hospital[i][j] == 1) uninfected++;
            else if (hospital[i][j] == 2) q.push(make_pair(i,j));
        }
    }
        
    while (!q.empty() && uninfected) {
        int size = q.size();
        int oldUninfected = uninfected;
        while (size--) {
            pair<int, int> front = q.front();
            q.pop();
            int r = front.first, c = front.second;
            for (int i=0; i<4; i++) {
                int x = r+dr[i], y = c+dc[i];
                if (x>=0 && x<n && y>=0 && y<m && hospital[x][y]==1) {
                    hospital[x][y] = 2;
                    q.push(make_pair(x,y));
                    uninfected--;
                }
            }
        }
        // in each iteration some should get infected
        if (oldUninfected == uninfected) break;
        time++;
    }
        
    if (uninfected == 0) return time;
    return -1;                                           // not able to infect all
}
```
<br><h3>Approach</h3>
Every node having value 2 is having the ability to infect others.
Here, In each iteration, we can push the unused infected vertices in a queue until all are getting infected or when we know we can never infect some.<br><br><br>
<div align="center">37</div><br>
<h1 id="implicit">Implicit graphs</h1>
The problems which come under section do not directly contain a graph with vertices and edges. Instead what we can do is : <br>
- Assume values of a certain data structure like integer, character or string etc.. as<br>&nbsp; vertices based on the problem's input data<br>
- Assume the relationships between them as directed (or) undirected edges as per the<br>&nbsp; problem's requirements<br><br>

<div align="center"><h3>=> Graph is ready</h3></div><br><br>
Then the problem falls into one of the classical graph problems like : <br>
1. Shortest Distance between two nodes<br>
2. Cycle Detection<br>
3. Topological Ordering<br>
and many more .......<br><br><br><br>

<h2>Creating the graph</h2>
In some problems, we have limited data. So the first thing we can do is construct the graph fully with all the possible edges and then move to the solving part.<br>
<b>Example:- </b>Snakes and Ladders.<br><br>
Whereas in some problems, <br>
(i) &nbsp;we will be having lots of different configurations (vertices) possible as in<br> &nbsp;&nbsp;&nbsp;&nbsp; problems like Open the lock, Sliding puzzle etc.. or <br> 
(ii) we can even have lots of unnecessary edges with a limited set of vertices as in<br>&nbsp;&nbsp;&nbsp;&nbsp; Word ladder etc..<br>
In such cases, we are never going to construct the graph fully <br>
=> we <b>only construct the subgraph we need</b> as we go through while traversing.
<br><br><br><br><br><br><br><br><br><br><br><br><br>
<div align="center">17</div>
<h1 id="snake">Snake and Ladder Problem</h1>
Given a 5x6 snakes and ladders board, find the minimum number of dice throws required to reach the destination or last cell (30<sup>th</sup> cell) from the source (1<sup>st</sup> cell).<br><br>
You are given an integer 'n' denoting the total number of snakes and ladders and an array arr[] of 2*n size where 2*i and (2*i + 1)th values denote the starting and ending point respectively of ith snake or ladder.<br><br><br>
<b>Example:- </b><br>
Input: n = 8, arr[] = {3, 22, 5, 8, 11, 26, 20, 29, 17, 4, 19, 7, 27, 1, 21, 9} <br>
Output: 3 <br>
Explanation: 2,6,2 <br>
start 1 + 2 = 3->22 + 6 = 28 + 2 = 30 end <br><br><br>
Click <a href="https://practice.geeksforgeeks.org/problems/snake-and-ladder-problem4816/1/">here</a> for the problem link<br><br><br><br><br><br>
<h2>Solution</h2><br>
<b>1. Construct a directed graph</b><br>
Every dice roll possibility (1 to 6) is an edge.<br>
Every snake is an edge.<br>
Every ladder is an edge.<br>

```cpp
vector<vector<int>> graph(31);
unordered_map<int, int> mp;
for (int i=0; i<=2*(n-1); i+=2) {
    mp[arr[i]] = arr[i+1];
}
for (int i=1; i<30; i++) {
    for (int j=1; j<=6; j++) {
        int value = i+j;
        if (value < 31) {
            if (mp[value] != 0) graph[i].push_back(mp[value]);
            else graph[i].push_back(value);
        }
    }
}
```
<b>2. Find the shortest distance between nodes 1 and 30</b></br>
Can be solved using BFS<br>
<div align="center">17</div>
<h1 id="wordladder">Word Ladder</h1>
Given a dictionary, and two words 'start' and 'target' (both of same length). Find length of the smallest chain from 'start' to 'target' if it exists, such that adjacent words in the chain only differ by one character and each word in the chain is a valid word i.e., it exists in the dictionary. <br><br> It may be assumed that the ‘target’ word exists in dictionary and length of all dictionary words is same. <br><br><br>
<b>Example - 1</b><br> 
Input: Dictionary = {POON, PLEE, SAME, POIE, PLEA, PLIE, POIN},<br> start = TOON, target = PLEA<br>
Output: 7<br>
Explanation: TOON – POON – POIN – POIE – PLIE – PLEE – PLEA<br><br>
<b>Example - 1</b><br> 
Input: Dictionary = {ABCD, EBAD, EBCD, XYZA}, start = ABCV, target = EBAD<br>
Output: 4<br>
Explanation: ABCV – ABCD – EBCD – EBAD<br><br><br>
Click <a href="https://practice.geeksforgeeks.org/problems/word-ladder/0/">here</a> for the problem link<br><br><br><br><br><br><br><br><br><br><br>
<h2>Solution Approach</h2><br>
1. If we see the words as nodes and edges are determined by words that are 1 letter<br>&nbsp;&nbsp; apart, then this problem becomes "find the minimum distance from one node in a<br>&nbsp;&nbsp; graph to the other". <br>
2. As minimum distance needs to be calculated, we can use BFS<br>
3. In the actual algorithm, however, we do not need to build up the graph before using<br>&nbsp;&nbsp; BFS; we can build the graph as we go: instead of storing the edges, we calculate<br>&nbsp;&nbsp; the set of neighbors for the current node only when we need to visit them.

<br><br><br><br><br><div align="center">18</div>
<h1 id="topo">Topological Sorting</h1>
Can also be referred as topological ordering.<br>
Topological Sort of a directed graph (a graph with unidirectional edges) is a linear ordering of its vertices such that for every directed edge (U, V) from vertex U to vertex V, U comes before V in the ordering.<br>
<div align="center"><b>( or )</b></div>
Topological sort or of a directed graph is an ordering of nodes such that every node appears in the ordering before all the nodes it points to. <br><br><br><br>
<div style="display:flex">
<div>
<b>Example:</b> Vertices = 5, <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Edges = [4, 2], [4, 3], [2, 0], [2, 1], [3, 1] &nbsp;&nbsp;<br>
Following are all valid topological sorts:<br>
<ul>
<li>4, 2, 3, 0, 1</li>
<li>4, 3, 2, 0, 1</li>
<li>4, 3, 2, 1, 0</li>
<li>4, 2, 3, 1, 0</li>
<li>4, 2, 0, 3, 1</li>
</ul>
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/topeg1.png" height="160" width="180">
</div><br><br>
<div style="display:flex">
<div>
<b>Example:</b> Vertices = 4, <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Edges = [4, 2], [2, 1], [3, 1]<br>
Following are all valid topological sorts: &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;<br>
<ul>
<li>4, 2, 3, 1</li>
<li>4, 3, 2, 1</li>
<li>3, 4, 2, 1</li>
</ul>
As we can see, Node 3 is completely independent of nodes 2 and 4, and it can be anywhere in the order as long as it is before node 1 which depends on it.
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/topeg2.png" height="120" width="180">
</div><br><br>
<div align="center"><blockquote><b>=> topological sorts are not unique</b></blockquote></div><br>
<div style="display:flex">
<div>
This graph has a cycle which means vertices will have cyclic dependencies. So, it is impossible to find a linear ordering among these vertices.<br><br>
Circular dependency is a common problem in real-world software engineering.
</div>
<img src="https://raw.githubusercontent.com/saivault/dsanotes/main/store/topeg3.png" height="90" width="100">
</div>
<br><br><br><br><br><div align="center">18</div>
<h3>Fundamental terms</h3>
<b>Source:</b> Any node that has no incoming edge and has only outgoing edges.<br>
<b>Sink:</b> Any node that has only incoming edges and no outgoing edge.<br><br>
So, we can say that a topological ordering starts with one of the sources and ends at one of the sinks. <br><br><br><br>
<h2>Algorithm</h2>
<h3>1. Store indegrees</h3>
Store indegrees for all the vertices.<br>
<h3>2. Initialise Queue</h3>
All vertices with ‘0’ in-degrees will be our sources and will be stored in a queue.<br>
If no such node exists then there exists a cycle and there does not exist a solution to the problem (because if there isn't a cycle then we can always find a node that does not depend on any other node).
<h3>3. Get the order </h3>
a) For each source, do the following things:<br>
- Add it to the sorted list.<br>
- Get all of its children from the graph.<br>
- Decrement the in-degree of each child by 1.<br>
- If a child’s in-degree becomes ‘0’, add it to the sources Queue.<br>

b) Repeat step a, until the source queue is empty.
<br><br><br>
<h3>Time Complexity</h3>
In step 'a', each vertex will become a source only once and each edge will be accessed and removed once. Therefore, the time complexity of the above algorithm will be O(V+E).<br><br>
<h3>Space Complexity</h3>
The space complexity will be O(V+E) as we are using adjacency list. 
<br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">19</div>
<h2>Implementation</h2><br>

```cpp
vector<int> topoSort(int n, vector<int> graph[]) 
{
	// 1. Store Indegrees
	vector<int> inDegree(n,0);
	for (int i=0; i<n; i++) {
	    for (int j=0; j<graph[i].size(); j++){
	       inDegree[graph[i][j]]++;
	    }
	}

    // 2. Initialize queue
	queue<int> q;
    for (int i=0; i<n; i++) {
	    if (inDegree[i] == 0) q.push(i);
    }
	    
	// 3. Get the order
	vector<int> res;
    while(!q.empty()){
	    int temp = q.front();
	    q.pop();
	    res.push_back(temp);
	    for (int i=0; i<graph[temp].size(); i++) {
	       int ele = graph[temp][i];
	       inDegree[ele]--;
	       if (inDegree[ele] == 0) {
	           q.push(ele);
	       }
	   }
	}
	    
	return res;
}
```
<br><br><br><br>
<b>Q) Detect cycle in a directed graph</b><br>
Sol:- If we can’t determine the topological ordering of all the vertices of a directed graph, the graph has a cycle in it. 

```cpp
if (topologicalOrder.size() != numberOfVertices) cout<<"Cycle is present"
else cout<<"Cycle is not present"
```
<br><br><div align="center">20</div>
<h1 id="task">Task Scheduling</h1>
There are N tasks, labeled from 0 to N-1. Each task can have some requirement tasks which need to be completed before it can be scheduled.<br> Each requirement will be in the form of a list [a, b], where task 'a' needs to be completed first before task 'b' can be completed.<br><br>
Given the number of tasks and a list of requirement pairs, find out if it is possible to schedule all the tasks.<br><br><br><br>
<b>Modelling into our pattern,</b><br>
&nbsp;&nbsp;1. Consider every task as a node<br>
&nbsp;&nbsp;2. If a task b has a requirement task a, <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;then add a directed edge from node a to node b <br>
&nbsp;&nbsp;3. Is topological ordering possible for this graph ?<br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;Further, is this graph not having a cycle?<br><br><br><br>
If we use the word course instead of task and prerequisite instead of requirement, then this becomes the problem <b> Course Scheduling</b>.
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<br><br><br><br><br><br><div align="center">21</div>
<h1 id="alien">Alien Dictionary</h1>
There is a dictionary containing words from an alien language for which we don’t know the ordering of the alphabets. Write a method to find the correct order of the alphabets in the alien language. It is given that the input is a valid dictionary and there exists an ordering among its alphabets.<br><br>
<b>Note:</b><br>
- You may assume all letters are in lowercase.<br>
- Every letter that appears in the input must also appear in the output, and your output cannot have characters not in the input. (shortest supersequence)<br>
- Say two strings s and t such that s.length < t.length and s is a prefix of t. Then s is smaller than t.<br>
- There may be multiple valid orders. If that's the case, return the smallest in normal lexicographical order. <br><br><br>

<b>Example - 1</b><br>
Input: Words: ["ba", "bc", "ac", "cab"]<br>
Output: bac<br>
Explanation: Given that the words are sorted lexicographically by the rules of the alien language, so
from the given words we can conclude the following ordering among its characters:<br>
1. From "ba" and "bc", we can conclude that 'a' comes before 'c'.<br>
2. From "bc" and "ac", we can conclude that 'b' comes before 'a'<br>

From the above two points, we can conclude that the correct character order is: "bac"<br><br>
<b>Example - 2</b><br>
Input: Words: ["ywx", "wz", "xww", "xz", "zyy", "zwz"]<br>
Output: ywxz
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">22</div>
<h2>Solution</h2>
<h3>1. Creation of Graph</h3>
Since the words are given in lexicographical order in the alien language, you can use it to deduce the ordering of letters in that language. Because a lexicographical order is a <b>total ordering</b>, regardless of the ordering of the letters, we only need to consider words adjacent to each other.<br>
The knowledge we get from pair (i,i+2) can be already known from pairs (i,i+1) and (i+1,i+2). This helps in decreasing our number of comparisons from n*(n-1)/2 to n-1.<br><br>
For each adjacent words, we compare each character of the string until we find a different character. Then, we can deduce that the character(say a) from the first string is lexicographically smaller than the character(say b) from the second string. We can have a directed edge from a to b.<br><br>
After parsing through all the strings, we get a directed graph.<br><br>
<h3>2. How to find the ordering ?</h3>
Perform a topological sort on the obtained directed graph.<br><br>
<h3>3. How to guarantee the smallest ordering ?</h3>
By using a min heap instead of a regular queue in the algorithm.<br><br>
<h3>4. Are parallel edges going to create a problem ?</h3>
No, Say a node x has n parallel edges to node y<br>
Then, in the adjacency list of x, we will have n occurences of y.<br>
And after traversing through the adjacency list of x, indegree of y will be decremented by 1 exactly n times which ensures us no problem.
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><div align="center">23</div>
<h3>Alien Order Solution</h3>

```cpp
string alien_order(vector<string> words) {
    int n = words.size();
    unordered_map<char, vector<char>> graph;
    unordered_map<char, int> inDegree;
    
    // initialize in degree for every alphabet as zero
    for (int i=0; i<n; i++){
        for (int j=0; j<words[i].size(); j++) {
            inDegree[words[i][j]] = 0;
        }
    }
    
    // create a directed graph and update all the indegrees
    for (int i=0; i<n-1; i++) {
        int index = diffIndex(words[i],words[i+1]);
        if (index != -1) {
            graph[words[i][index]].push_back(words[i+1][index]);
            inDegree[words[i+1][index]]++;
        }
    }
    
    unordered_map<char, int>:: iterator itr;
    priority_queue <char, vector<char>, greater<char>> q;
    
    // store the initial zero indegree nodes in a minheap
    for (itr = inDegree.begin(); itr != inDegree.end(); itr++)
    {
        if (inDegree[itr->first] == 0) q.push(itr->first);
    }
    
    // find ordering using BFS
    string res = "";
    while (!q.empty()) {
        char node = q.top();
        q.pop();
        res += node;
        for (int i=0; i<graph[node].size(); i++) {
            char adjNode = graph[node][i];
            inDegree[adjNode]--;
            if (inDegree[adjNode] == 0) q.push(adjNode);
        }
    }
    if (res.size() == graph.size()) return res;
    return "";
}

```
<br><br><div align="center">24</div>
<h1 id="reconstruct">Reconstructing a sequence</h1>
Given a sequence originalSeq and an array of sequences, write a method to find if originalSeq can be uniquely reconstructed from the array of sequences.<br>
originalSeq is a permutation of the integers from 1 to n.<br><br>
Reconstruction means building a shortest common supersequence of the sequences in seqs (i.e., a shortest sequence so that all sequences in seqs are subsequences of it).<br><br>
Determine whether there is only one sequence that can be reconstructed from seqs and it is the orginal sequence.

<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1 id="circlestring">Circle of strings</h1>
Given an array of strings, find if the given strings can be chained to form a circle. A string X can be put before another string Y in circle if the last character of X is same as first character of Y. <br><br><br>
<b>Example - 1</b><br>
Input: arr[] = {"for", "geek", "rig", "kaf"}<br>
Output: Yes, the given strings can be chained.<br>
The strings can be chained as "for", "rig", "geek" and "kaf"<br><br>
<b>Example - 2</b><br>
Input : arr[] = [“ijk”, “kji”, “abc”, “cba”]<br>
Output : No<br>
<br><br><br><br><br><br><br><br><br><br>
<h2>Solution Approach</h2>
We solve this problem by treating this as a graph problem, where vertices will be the first and last character of strings, and we will draw an edge between two vertices if they are the first and last character of the same string, so a number of edges in the graph will be same as the number of strings in the array. <br><br>
Now it can be clearly seen after graph representation that if a loop among graph vertices is possible then we can reorder the strings otherwise not. As in the above diagram’s example, a loop can be found in the first and third array of string but not in the second array of string.<br><br>

Now to check whether this graph can have a loop which goes through all the vertices, we’ll check two conditions, <br>
- Indegree and Outdegree of each vertex should be the same.<br>
- The graph should be strongly connected.<br><br>

First condition should be satisfied because if 'x' strings end at some particular letter then we need to have 'x' strings to start at the same particular letter.<br>
Second condition should be satisfied because we need to have a cycle involving all the vertices. 
<br><br><br>
<div align="center">17</div>vrg

<h3>Prove that a directed graph contains a cycle if it has no node of indegree zero</h3><br>
Sol:- Let's take a directed graph G. <br>
Let P = (v<sub>1</sub>, v<sub>2</sub>, . . . , v<sub>k</sub>) be a directed path of maximum length in G.<br><br>
As indegree of v<sub>1</sub> is greater than zero, say a node x having an edge to node v<sub>1</sub>. Then three cases arise<br>
<b>Case-1 :</b><br>
if x = v<sub>i</sub>, where is any value 2 to k then we can say a cycle exists v<sub>i</sub>, v<sub>1</sub>, v<sub>2</sub>,........,v<sub>i</sub><br>
<b>Case-2 :</b><br>
if x = v<sub>1</sub>, then it indicates a self-loop (cycle)<br>
<b>Case-3 :</b><br>
Then (x,  v<sub>1</sub>, v<sub>2</sub>, . . . , v<sub>k</sub>) will be a much bigger path which contradicts our assumption of maximum path.<br><br>
So, it definitely contains a cycle.
<br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br><br>
<h1 id="spwg">Shortest Path in a Weighted Graph</h1>
Graph's edges can have weight. For example, a graph that represents city connections and edges weights represent the distance between cities.<br>
So in a weighted graph, every edge is now assigned a weight and our distance increases by the weight instead of 1. This is the reason why <b>BFS</b> doesn't work anymore as they are designed for unweighted graphs. <br><br>
The previous algorithms assumed each edge was equal so only need to visit each node once. That no longer works as the first time we visit a node does not guarantee minimum distance and we may need to revisit the node if we find a shorter path.<br><br><br>
<h2>The Shortest-Path Faster Algorithm</h2>
SPFA can be thought of as a BFS variant.<br>
Instead of checking whether or not the neighbour node has been visited we instead see if we can improve our distance by checking the neighbor nodes and if it possible to update to a smaller distance and push the node into our queue. If it is greater then we want to update the node's distance since we have found a shorter path and push the node into our queue. This algorithm runs in worst case O(V*E) <br><br>

```cpp
vector <int> spfa(int n, vector<vector<int>> graph[], int src)
{
    vector<int> dist(n, INT_MAX);
    queue<int> q;
    dist[src] = 0;
    q.push(src);
        
    while (!q.empty()) {
        int node = q.front();
        q.pop();
        for (int i=0; i<graph[node].size(); i++) {
            int adj = graph[node][i][0];
            int weight = graph[node][i][1];
            if (dist[adj] > dist[node] + weight) {
                dist[adj] = dist[node] + weight;
                q.push(adj);
            }
        }
    }
    
    return dist;
}
```
<br><br><br><div align="center">45</div>
This algorithm works for smaller graphs and is easy to implement, so if you are in a rush and can afford to have a less efficient algorithm, you may want to use SPFA. Can we do better though?
