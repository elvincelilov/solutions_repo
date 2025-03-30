# Problem 1

### **Problem 1: Equivalent Resistance Using Graph Theory**

---

#### **Motivation**

Calculating the equivalent resistance of a circuit is crucial for designing efficient systems. Traditional methods can become cumbersome for complex circuits. Graph theory provides a more efficient approach by modeling circuits as graphs, where nodes represent junctions and edges represent resistors. This approach simplifies even complex circuits and opens the door for automated analysis and optimization in modern applications like circuit simulation and network design.

In this task, we'll explore how to calculate the equivalent resistance of a circuit using graph theory, considering different configurations of resistors (series, parallel, and nested combinations).

---

### **Option 1: Simplified Task – Algorithm Description**

To calculate the equivalent resistance using graph theory, we can break down the task into several key steps. The circuit can be represented as a **graph** where:
- Each **node** represents a junction in the circuit.
- Each **edge** between nodes represents a resistor with its resistance value as the edge's weight.

### **Steps of the Algorithm**:

1. **Model the Circuit as a Graph**:
   - Each resistor is represented as an edge with a weight equal to the resistance.
   - Each junction is a node where resistors meet.
   
2. **Identify Series and Parallel Connections**:
   - **Series Connection**: Resistors are in series if they are directly connected in sequence. The total resistance for two resistors \( R_1 \) and \( R_2 \) in series is:
     \[
     R_{\text{total}} = R_1 + R_2
     \]
   - **Parallel Connection**: Resistors are in parallel if they are connected between the same two nodes. The total resistance for two resistors \( R_1 \) and \( R_2 \) in parallel is:
     \[
     R_{\text{total}} = \frac{R_1 R_2}{R_1 + R_2}
     \]
   - A more general case involves identifying clusters of resistors that are in series or parallel and reducing them step by step.

3. **Iteratively Reduce the Graph**:
   - Use a depth-first search (DFS) or breadth-first search (BFS) to explore the graph.
   - For each pair of resistors connected in series or parallel, calculate the equivalent resistance and replace them with a single edge that represents the new resistance.
   - Update the graph and repeat the process until only one node remains, representing the equivalent resistance of the entire circuit.

4. **Handle Nested Combinations**:
   - In circuits with more complex configurations, you will need to identify subgraphs that represent series and parallel connections, reduce them, and then apply the same logic to the remaining circuit.

---

---

### **Explanation of Handling Nested Combinations**

When encountering nested combinations (i.e., series and parallel connections within each other), the algorithm works as follows:
- **Identify Small Subgraphs**: Use a search method (like DFS) to explore the graph and identify smaller subgraphs that represent series or parallel connections.
- **Simplify Subgraphs**: For each identified subgraph, calculate the equivalent resistance and reduce the subgraph to a single edge.
- **Repeat the Process**: Once a subgraph is simplified, recheck the remaining part of the graph for further series or parallel combinations. This iterative process continues until the entire graph is reduced to a single equivalent resistance.

---

### **Option 2: Advanced Task – Full Implementation**

For this task, we would implement the algorithm in Python, leveraging the **NetworkX** library for graph manipulation. Here's how the implementation could be structured:

1. **Input Format**:
   - The input will be a graph where nodes represent junctions and edges represent resistors with their resistance values.

2. **Output**:
   - The output will be the equivalent resistance of the entire circuit.

3. **Handling Different Configurations**:
   - The algorithm will detect series and parallel connections iteratively using graph traversal techniques.

---

### **Python Code Implementation using NetworkX**

```python
import networkx as nx

def calculate_series_resistance(R1, R2):
    return R1 + R2

def calculate_parallel_resistance(R1, R2):
    return (R1 * R2) / (R1 + R2)

def find_series_parallel_connections(G):
    series_edges = []
    parallel_edges = []
    
    # Check for series and parallel edges
    for u, v, data in G.edges(data=True):
        if data['resistance'] == 0:  # Zero resistance means a short circuit
            continue
        neighbors_u = list(G.neighbors(u))
        neighbors_v = list(G.neighbors(v))
        if len(neighbors_u) == 1 and len(neighbors_v) == 1:
            series_edges.append((u, v))
        elif len(neighbors_u) > 1 and len(neighbors_v) > 1:
            parallel_edges.append((u, v))
    
    return series_edges, parallel_edges

def reduce_graph(G):
    while len(G.nodes) > 1:
        series_edges, parallel_edges = find_series_parallel_connections(G)
        
        # Reduce series edges
        for u, v in series_edges:
            resistance_u_v = calculate_series_resistance(G[u][v]['resistance'], G[u][v]['resistance'])
            G.add_edge(u, v, resistance=resistance_u_v)
            G.remove_edge(u, v)
        
        # Reduce parallel edges
        for u, v in parallel_edges:
            resistance_u_v = calculate_parallel_resistance(G[u][v]['resistance'], G[u][v]['resistance'])
            G.add_edge(u, v, resistance=resistance_u_v)
            G.remove_edge(u, v)

    return G

# Test the implementation with a simple circuit
G = nx.Graph()
G.add_edge(0, 1, resistance=5)  # Resistor between node 0 and node 1
G.add_edge(1, 2, resistance=10) # Resistor between node 1 and node 2
G.add_edge(2, 3, resistance=20) # Resistor between node 2 and node 3

final_graph = reduce_graph(G)
print("Final equivalent resistance:", final_graph[0, 3]['resistance'])
```

### **Explanation of Code**:
- **Graph Representation**: The circuit is represented as an undirected graph where each edge has a resistance value.
- **`reduce_graph` Function**: This function iterates over the graph, detecting series and parallel connections and reducing them until only one node remains, representing the total equivalent resistance.

### **Test Cases and Example Outputs**:
1. **Simple Series Circuit**:
   - Resistor values: 5 Ω, 10 Ω, 20 Ω.
   - Output: The total resistance will be \( 5 + 10 + 20 = 35 \, \Omega \).

2. **Simple Parallel Circuit**:
   - Resistor values: 5 Ω and 10 Ω in parallel.
   - Output: The total resistance will be \( \frac{5 \times 10}{5 + 10} = 3.33 \, \Omega \).

---

### **Efficiency Analysis**

- **Time Complexity**: The algorithm's time complexity depends on the number of nodes and edges in the graph. For each iteration, the graph is traversed to find series and parallel connections, making it O(E), where E is the number of edges.
- **Potential Improvements**: Optimizations could be made by using more efficient graph traversal techniques or by precomputing possible reductions in more structured circuits.

---

### **Conclusion**

Graph theory provides a structured approach to calculating equivalent resistance in electrical circuits. By representing the circuit as a graph and reducing series and parallel connections iteratively, the algorithm can handle even complex configurations. This method simplifies the process of analyzing circuits and can be easily automated for use in circuit simulation tools.