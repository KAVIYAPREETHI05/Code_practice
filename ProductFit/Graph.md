## Graph

A graph is a non-linear data structure consisting of nodes (vertices) and edges (connections between nodes). 

It is widely used in real-world applications such as social networks, maps, computer networks, and recommendation systems.

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

```java



