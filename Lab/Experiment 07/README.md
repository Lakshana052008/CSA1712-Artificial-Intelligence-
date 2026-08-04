# Experiment 7: Breadth-First Search (BFS) Using Python

## Aim

To implement the Breadth-First Search (BFS) algorithm using Python for graph traversal.

## Objective

- To understand the Breadth-First Search (BFS) algorithm.
- To implement BFS using Python.
- To traverse all vertices of a graph in level-by-level order.
- To demonstrate graph traversal using a queue.

## Algorithm

1. Create a graph using an adjacency list.
2. Select the starting vertex.
3. Initialize an empty queue and a visited set.
4. Add the starting vertex to the queue and mark it as visited.
5. Remove a vertex from the front of the queue.
6. Visit and display the vertex.
7. Add all unvisited neighboring vertices to the queue.
8. Repeat until the queue becomes empty.

## Flowchart

```mermaid
flowchart TD
    A([Start]) --> B[Create Graph]
    B --> C[Initialize Queue and Visited Set]
    C --> D[Visit Starting Node]
    D --> E{Queue Empty?}
    E -->|No| F[Remove Front Node]
    F --> G[Visit Adjacent Nodes]
    G --> E
    E -->|Yes| H([Stop])
```

## Python Program

```python
from collections import deque

def bfs(graph, start):
    visited = set()
    queue = deque([start])
    traversal = []

    while queue:
        node = queue.popleft()

        if node not in visited:
            visited.add(node)
            traversal.append(node)

            for neighbour in graph[node]:
                if neighbour not in visited:
                    queue.append(neighbour)

    return traversal

graph = {
    'A': ['B', 'C'],
    'B': ['D', 'E'],
    'C': ['F'],
    'D': [],
    'E': [],
    'F': []
}

start = 'A'
result = bfs(graph, start)

print("BFS Traversal")
print()
print("Starting Node :", start)
print()
print("Traversal Order:")
print(" → ".join(result))
print()
print("Traversal Completed Successfully.")
```

## Output

```text
BFS Traversal

Starting Node : A

Traversal Order:
A → B → C → D → E → F

Traversal Completed Successfully.
```
<img width="1232" height="767" alt="image" src="https://github.com/user-attachments/assets/f71debd0-8109-4cef-a2d3-0b7cabdb3cce" />


## Result

The Breadth-First Search (BFS) algorithm was successfully implemented in Python. The graph was traversed level by level starting from the selected source node.

## Conclusion

The BFS algorithm was successfully implemented using Python. It traversed the graph in breadth-first order using a queue and visited every reachable vertex exactly once. This experiment demonstrated the application of BFS in graph traversal and Artificial Intelligence search problems.
