# Graphs

A graph is a non-linear data structure that can be looked at as a collection of vertices (or nodes) potentially connected by line segments named edges.

Here is some common terminology used when working with Graphs:

- Vertex - A vertex, also called a “node”, is a data object that can have zero or more adjacent vertices.
- Edge - An edge is a connection between two nodes.
- Neighbor - The neighbors of a node are its adjacent nodes, i.e., are connected via an edge.
- Degree - The degree of a vertex is the number of edges connected to that vertex.

## Undirected Graphs
An Undirected Graph is a graph where each edge is undirected or bi-directional. This means that the undirected graph does not move in any direction.

For example, in the graph below, `Node C` is connected to `Node A`, `Node E` and `Node B`. There are no “directions” given to point to specific vertices. The connection is bi-directional.
![Undiracted Graph](UndirectedGraph.png)

## Directed Graphs (Digraph)
A `Directed Graph` also called a `Digraph` is a graph where every edge is directed.

Unlike an `undirected graph`, a `Digraph` has direction. Each node is directed at another node with a specific requirement of what node should be referenced next.

Compare the visual below with the `undirected graph` above. The `Digraph` has arrows pointing to specific nodes.
![DirectedGraph](DirectedGraph.png)  

## Complete vs Connected vs Disconnected

There are 3 types pf graphs:
- Completed
- Connected
- Disconnected

## Complete Graphs

A complete graph is when all nodes are connected to all other nodes.
![CompleteGraph](CompleteGraph.png)

## Connected Graphs

A connected graph is graph that has all of `vertices/nodes` have at least one edge.

![ConnectedGraph](ConnectedGraph.png)

## Disconnected Graph
A disconnected graph is a graph where some vertices may not have edges.
![DisconnectedGraph](DisconnectedGraph.png)

## Acyclic vs Cyclic
In addition to undirected and directed graphs, we also have acyclic and cyclic graphs.

## Acyclic Graph
An [Acyclic graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/threeAcyclic.png) is a directed graph without cycles.

A cycle is when a node can be traversed through and potentially end up back at itself.

## Cyclic Graphs
A [Cyclic graph](https://codefellows.github.io/common_curriculum/data_structures_and_algorithms/Code_401/class-35/resources/assets/cyclic.PNG) is a graph that has cycles.

A cycle is defined as a path of a positive length that starts and ends at the same vertex.

## Graph Representation
We represent graphs through:

- Adjacency Matrix
- Adjacency List

## Adjacency Matrix
An Adjacency matrix is represented through a 2-dimensional array. If there are n vertices, then we are looking at an n x n Boolean matrix

Each Row and column represents each vertex of the data structure. The elements of both the column and the row must add up to 1 if there is an edge that connects the two, or zero if there isn’t a connection.


![AdjMatrix](AdjMatrix.png)

A few things to note from the above:

1. Looking at the graph we are representing, you can see that `Vertex A` connects to both `Vertex D` and `Vertex C`. To show this, we place a 1 in the position of (a,c) and (a,d).
2. We follow this same pattern for the other vertex’s and where they are connected.
3. If there is not an edge/connection between the vertex’s, we represent this by placing a 0 in the appropriate point of the matrix.

### Sparse graph 
- when there are very few connections. 

### Dense graph
- When there are many connections.

Within an adjacency matrix, an undirected graph will always be symmetric. This is not the case for a directed graph.

## Adjacency List
An adjacency list is the most common way to represent graphs.

An adjacency list is a collection of linked lists or array that lists all of the other vertices that are connected.

![AdjList](AdjList.png)

## Weighted Graphs
A weighted graph is a graph with numbers assigned to its edges. These numbers are called weights.

![weightGraph](weightGraph.png)

### Weighted Graph Adjacency Lists
![weightList](weightList.png)

## Traversals

### Breadth First

Here is what the algorithm breadth first traversal looks like:

1. Enqueue the declared start node into the Queue.
2. Create a loop that will run while the node still has nodes present.
3. Dequeue the first node from the queue
4. If the Dequeue‘d node has unvisited child nodes, add the unvisited children to visited set and insert them into the queue.

### Breadth First Psuedo Code
```
ALGORITHM BreadthFirst(vertex)
    DECLARE nodes <-- new List()
    DECLARE breadth <-- new Queue()
    DECLARE visited <-- new Set()

    breadth.Enqueue(vertex)
    visited.Add(vertex)

    while (breadth is not empty)
        DECLARE front <-- breadth.Dequeue()
        nodes.Add(front)

        for each child in front.Children
            if(child is not visited)
                visited.Add(child)
                breadth.Enqueue(child)   

    return nodes;
```

## Depth First Traversal

The algorithm for a depth first traversal is as follows:

1. Push the root node into the stack
2. Start a while loop while the stack is not empty
3. Peek at the top node in the stack
4. If the top node has unvisited children, mark the top node as visited, and then Push any unvisited children back into the stack.
5. If the top node does not have any unvisited children, Pop that node off the stack
6. Repeat until the stack is empty.

