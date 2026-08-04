# Experiment 8: Depth-First Search (DFS) Using Python

## Aim

To implement the Depth-First Search (DFS) algorithm using Python for graph traversal.

## Objective

- To understand the Depth-First Search (DFS) algorithm.
- To implement DFS using Python.
- To traverse all vertices of a graph using depth-first traversal.
- To demonstrate graph traversal using recursion.

## Algorithm

1. Create a graph using an adjacency list.
2. Select the starting vertex.
3. Mark the starting vertex as visited.
4. Visit and display the current vertex.
5. Recursively visit each unvisited adjacent vertex.
6. Continue until all reachable vertices are visited.
7. Stop when the traversal is complete.

## Flowchart

```mermaid
flowchart TD
    A([Start]) --> B[Create Graph]
    B --> C[Select Starting Node]
    C --> D[Mark Node as Visited]
    D --> E[Display Node]
    E --> F{Unvisited Adjacent Node?}
    F -->|Yes| G[Visit Adjacent Node Recursively]
    G --> D
    F -->|No| H{More Nodes?}
    H -->|Yes| F
    H -->|No| I([Stop])
```

## Python Program

```python
graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': ['F'],
    'F': []
}

visited = set()
traversal = []

def dfs(node):
    if node not in visited:
        visited.add(node)
        traversal.append(node)

        for neighbour in graph[node]:
            dfs(neighbour)

start = 'A'
dfs(start)

print("DFS Traversal")
print()
print("Starting Node :", start)
print()
print("Traversal Order:")
print(" → ".join(traversal))
print()
print("Traversal Completed Successfully.")
```

## Output

```text
DFS Traversal

Starting Node : A

Traversal Order:
A → B → D → E → F → C

Traversal Completed Successfully.
```
<img width="1387" height="786" alt="image" src="https://github.com/user-attachments/assets/d85bab46-074d-4fcd-bb91-07d7ef073130" />


## Result

The Depth-First Search (DFS) algorithm was successfully implemented in Python. The graph was traversed by exploring each branch completely before backtracking.

## Conclusion

The DFS algorithm was successfully implemented using Python. It traversed the graph in depth-first order using recursion and visited every reachable vertex exactly once. This experiment demonstrated the application of DFS in graph traversal and Artificial Intelligence search problems.
