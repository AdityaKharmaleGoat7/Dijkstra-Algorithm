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
Additional Notes
The code includes a commented-out function, printAdj(), which can be used to print the adjacency list representation of the graph.
The algorithm assumes that the graph is connected and does not contain negative edge weights.
This implementation uses a set (st) to efficiently find the node with the minimum distance in each iteration.
The code provides an example with a graph consisting of four nodes, but you can modify it to work with any graph.
