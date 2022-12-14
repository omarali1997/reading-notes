# Read 27 - Graphs
# Graphs

### A graph is a non-linear data structure that can be looked at as a collection of `vertices` (or `nodes`) potentially connected by line segments named `edges`.





## Here is some common terminology used when working with Graphs:

1. Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
2. Edge - An edge is a connection between two nodes.
3. Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
4. Degree - The degree of a vertex is the number of edges connected to that vertex.



# Directed vs Undirected
## Undirected Graphs
### An `Undirected Graph` is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

### For example, in the graph below, Node `C` is connected to` Node A`, `Node E` and `Node B`. There are no “directions” given to point to specific vertices. The connection is bi-directional.


<img src="https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/UndirectedGraph.PNG"/>




### The undirected graph we are looking at has 6 vertices and 7 undirected edges.

### Vertices/Nodes = {a,b,c,d,e,f}

### Edges = {(a,c),(a,d),(b,c),(b,f),(c,e),(d,e),(e,f)}


## Directed Graphs (Digraph)
### A `Directed Graph` also called a `Digraph` is a graph where every edge is directed.

### Unlike an undirected graph, a `Digraph` has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

### Compare the visual below with the undirected graph above. Can you see the difference? The `Digraph` has arrows pointing to specific nodes.


<img src= "https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/DirectedGraph.PNG"/>


### The directed graph above has six vertices and eight directed edges

### Vertices = {a,b,c,d,e,f}

### Edges = {(a,c),(b,c),(b,f),(c,e),(d,a),(d,e)(e,c)(e,f)}















