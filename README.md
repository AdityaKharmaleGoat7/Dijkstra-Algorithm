# Dijkstra-Algorithm
This repository contains an implementation of Dijkstra's Algorithm in C++ by Aditya Kharmale. Dijkstra's Algorithm is used to find the shortest path between nodes in a graph.

**Usage**
To use this implementation, follow these steps:

Clone the repository to your local machine or download the source code file.
Compile the code using a C++ compiler (e.g., g++).
Run the compiled executable.
The code provided in main() demonstrates the usage of the algorithm. It creates a graph, adds edges between nodes, and calculates the shortest distances from a specified source node to all other nodes using Dijkstra's Algorithm.

The result is displayed as a vector of distances, where each index represents a node in the graph.

**cpp**
vector<int> distance(4);
// ...

for(auto i: distance){
    cout<<i<<" ";
}

Algorithm Overview
Dijkstra's Algorithm works as follows:

Initialize a set of distances with infinity (INT_MAX) for each node in the graph.
Set the distance of the source node to 0.
Create a set to store the nodes with their corresponding distances. Initialize it with the source node and its distance.
While the set is not empty, do the following:
Extract the node with the minimum distance from the set.
For each neighbor of the extracted node, update its distance if a shorter path is found.
If the distance is updated, remove the previous entry from the set and insert the updated distance and node.
After the algorithm finishes, the vector of distances will contain the shortest distances from the source node to all other nodes in the graph.
Adjacency List Representation
The graph is represented using an unordered map, adj, which maps each node to a list of pairs. Each pair represents an adjacent node and the weight of the edge between them.

**cpp**
unordered_map<int, list<pair<int,int>>> adj;
The Graph class provides a method, addEdge(), to add edges between nodes by updating the adjacency list.

**cpp**
void addEdge(int u, int v, int weight){
    pair<int, int> p = make_pair(v, weight);
    adj[u].push_back(p);
    p = make_pair(u, weight);
    adj[v].push_back(p);
}

**Here are some situations where Dijkstra's algorithm may not be the best choice:**
**Negative edge weights:** Dijkstra's algorithm assumes that all edge weights are non-negative. If there are negative edge weights in the graph, the algorithm may produce incorrect results. In such cases, algorithms like Bellman-Ford or Floyd-Warshall are more appropriate.

**Large graphs:** Dijkstra's algorithm has a time complexity of O((V + E) log V), where V is the number of vertices and E is the number of edges. In very large graphs with millions of vertices and edges, the algorithm can become slow and impractical. Alternative algorithms like A* search, which use heuristics to guide the search, can be more efficient.

**Non-uniform edge costs**: Dijkstra's algorithm assumes that the cost of traversing each edge is the same. In some cases, the edge costs may vary depending on certain factors or conditions. For example, in road networks, the travel time may depend on traffic conditions or road quality. In such scenarios, algorithms like Contraction Hierarchies or Customized Route Planning algorithms may be more appropriate.

**Sparse graphs with negative cycles:** Dijkstra's algorithm can handle graphs with negative edge weights, as long as there are no negative cycles. However, if the graph contains negative cycles, Dijkstra's algorithm may enter an infinite loop. In such cases, algorithms like Bellman-Ford or the use of topological sorting are more appropriate.

These are some scenarios where Dijkstra's algorithm may not be the most suitable choice. It's important to consider the characteristics of the graph and the specific requirements of the problem at hand to choose the most appropriate algorithm.

**Additional Notes**
The code includes a commented-out function, printAdj(), which can be used to print the adjacency list representation of the graph.
The algorithm assumes that the graph is connected and does not contain negative edge weights.
This implementation uses a set (st) to efficiently find the node with the minimum distance in each iteration.
The code provides an example with a graph consisting of four nodes, but you can modify it to work with any graph.
