## Graph

A graph is a non-linear data structure consisting of nodes (vertices) and edges (connections between nodes). 

It is widely used in real-world applications such as social networks, maps, computer networks, and recommendation systems.

Array of root is called forest. two or more disconnected trees is called forest.

### Types of Graph

 - **Based on Direction**
     - **Undirected Graph**: The edges have no direction, meaning connections are bidirectional.
     -  **Directed Graph (Digraph)**: The edges have a direction, meaning a connection goes from one node to another.
 - **Based on Weight**
     - **Unweighted Graph**: All edges have the same value or no weight.
     - **Weighted Graph**: Each edge has a weight (or cost) associated with it.
  - **Based on Connectivity**
     - **Connected Graph**: There is a path between every pair of vertices.
     - **Disconnected Graph**: Some vertices cannot be reached from others.
  - **Based on Cycles**
     - **Cyclic Graph**: Contains at least one cycle (a path where a node connects back to itself).
     - **Acyclic Graph**: Does not contain any cycles.
     - **DAG (Directed Acyclic Graph)**: A directed graph with no cycles.
   
  ### Graph Representation

***Adjacency matrix***

```
     0  1  2  3
  0 [0, 1, 1, 0]
  1 [1, 0, 0, 1]
  2 [1, 0, 0, 1]
  3 [0, 1, 1, 0]

```

***Adjacency List***

```
0 -> [1, 2]
1 -> [0, 3]
2 -> [0, 3]
3 -> [1, 2]

```


### Grap Algorithms

***Shortest Path Algorithms***
- Dijkstra’s Algorithm (Greedy, best for weighted graphs)
- Bellman-Ford Algorithm (Handles negative weights)
- Floyd-Warshall Algorithm (All-pairs shortest path)
***Minimum Spanning Tree (MST) Algorithms***
- Kruskal’s Algorithm (Greedy, uses sorting and union-find)
- Prim’s Algorithm (Greedy, uses priority queues)
***Topological Sorting***
- Used for scheduling tasks (like course prerequisites).
- Works only on Directed Acyclic Graphs (DAGs).
***Cycle Detection***
- DFS-based cycle detection (for directed & undirected graphs)
- Union-Find (Disjoint Set) (for undirected graphs)


### Graph Traversal

**BFS**

```java
class Solution {
    public ArrayList<Integer> bfsOfGraph(int V, ArrayList<ArrayList<Integer>> adj) {
        ArrayList<Integer> arr=new ArrayList<>();
        Queue<Integer>q=new LinkedList<>();

        boolean visited[]=new boolean[V];
        
        q.add(0);
        visited[0]=true;
        
        while(!q.isEmpty()){
            int node=q.poll();
            arr.add(node);
            
            for(int i=0;i<adj.get(node).size();i++){
                int neighbor=adj.get(node).get(i);
                if(!visited[neighbor]){
                    visited[neighbor]=true;
                    q.offer(neighbor);
                }
            }
        }
        return arr;
    }
}
```

**DFS**




## Topology Sort

Topological Sorting is a linear ordering of vertices in a Directed Acyclic Graph (DAG) such that for every directed edge u → v, vertex u appears before vertex v in the ordering.

 If one task depends on another, topological sorting helps determine the correct order to complete tasks.

 If topological sorting is not possible, the graph contains a cycle.

**207. Course Schedule**

```java
class Solution {
    public boolean canFinish(int numCourses, int[][] prerequisites) {
        List<List<Integer>> adj=new ArrayList<>();

        for(int i=0;i<numCourses;i++){
            adj.add(new ArrayList<>());
        }

        for(int[] preReq :prerequisites){
            int v=preReq[0];
            int u=preReq[1];

            adj.get(u).add(v);

        }

        int[ ] inDegree=new int[numCourses];

        for(int[] preReq: prerequisites){
            int v=preReq[0];
            int u=preReq[1];

            inDegree[v]++;

        }
        Queue<Integer> q= new LinkedList<>();

            for(int i=0;i<numCourses;i++){
                if(inDegree[i]==0){

                    q.add(i);

                }
            }
            while(!q.isEmpty()){
                int curr=q.poll();
                for(int nei:adj.get(curr)){
                    inDegree[nei]--;
                    if(inDegree[nei]==0){
                        q.add(nei);
                    }
                }
            }
            for(int i=0;i<numCourses;i++){
                if(inDegree[i]!=0){
                    return false;
                }
            }
            return true;

        }
        
    }

```

## Bipartite

A Bipartite Graph is a graph whose vertices can be divided into two independent sets, say U and V, such that every edge connects a vertex from U to a vertex from V (i.e., there are no edges between vertices within the same set).

A graph is bipartite if and only if it does not contain an odd-length cycle.

Bipartite graphs are 2-colorable (can be colored with two colors without conflicts).

Helps in finding maximum matching (e.g., assigning workers to tasks).

Ensures that two adjacent regions do not share the same color.

Helps in dividing teams (e.g., two groups that should not compete against each other directly).


**785. Is Graph Bipartite**
```java
class Solution {
    public boolean isBipartite(int[][] graph) {
        

        int[] colors=new int[graph.length];
        Arrays.fill(colors,-1);

    Queue<Integer>q=new LinkedList<>();

    q.add(0);
    colors[0]=1;

    while(!q.isEmpty()){
        int currNode=q.poll();

        int currNodeColor=colors[currNode];

        for(int neiNode: graph[currNode]){
            int neiNodeColor=colors[neiNode];
            if(neiNodeColor!=-1 && neiNodeColor==currNodeColor){
                return false;
            }
            if(neiNodeColor!=-1 && neiNodeColor!=currNodeColor){
                continue;
            }

            colors[neiNode]=currNodeColor==1?0:1;

            q.add(neiNode);

        }


    }

    

return true;
        
    }
}
```

## Disjoint set algorithm

The Disjoint Set algorithm, also known as Union-Find, is a data structure used to efficiently manage and merge disjoint sets. It supports two main operations:

Find (x): Determines which set the element x belongs to.
Union (x, y): Merges the sets that contain x and y.

**Application**


- Kruskal's Minimum Spanning Tree Algorithm
- Cycle detection in graphs
- Connected components in graphs
- Network connectivity problems




