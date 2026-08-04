# Experiment 10: Implementation of A* Search Algorithm

## Aim

To implement the A* Search Algorithm in Python to find the shortest path between a start node and a goal node using heuristic values.

## Objective

- To understand the concept of informed search.
- To implement the A* Search Algorithm.
- To determine the shortest path using cost and heuristic values.
- To analyze the efficiency of heuristic-based pathfinding.

## Algorithm

1. Start the algorithm.
2. Initialize the graph and heuristic values.
3. Add the start node to the open list.
4. Select the node with the lowest f(n) = g(n) + h(n).
5. Check whether the selected node is the goal node.
6. If the goal node is reached, display the shortest path and total cost.
7. Otherwise, expand all neighboring nodes.
8. Update the cost values and add neighbors to the open list.
9. Repeat the process until the goal is reached or the open list becomes empty.
10. Stop the algorithm.

## Flowchart

```text
                    START
                      │
                      ▼
      Initialize Graph & Heuristic Values
                      │
                      ▼
         Add Start Node to Open List
                      │
                      ▼
          Is Open List Empty?
              ┌───────┴────────┐
             Yes              No
              │                │
              ▼                ▼
        No Path Found   Select Node with
                         Lowest f(n)
                              │
                              ▼
                    Is Goal Node Reached?
                        ┌─────┴─────┐
                       Yes         No
                        │           │
                        ▼           ▼
              Display Path      Expand Neighbors
              & Total Cost            │
                        │             ▼
                        │      Update g, h & f
                        │             │
                        └──────┬──────┘
                               │
                               ▼
                           Repeat Loop
                               │
                               ▼
                              STOP
```

## Python Code

```python
import heapq

graph = {
    'A': [('B', 1), ('C', 3)],
    'B': [('D', 3), ('E', 6)],
    'C': [('F', 5)],
    'D': [('G', 2)],
    'E': [('G', 1)],
    'F': [('G', 2)],
    'G': []
}

heuristic = {
    'A': 7,
    'B': 6,
    'C': 4,
    'D': 2,
    'E': 1,
    'F': 2,
    'G': 0
}

def astar(start, goal):
    pq = []
    heapq.heappush(pq, (heuristic[start], 0, start, [start]))
    visited = set()

    while pq:
        f, g, node, path = heapq.heappop(pq)

        if node == goal:
            return path, g

        if node in visited:
            continue

        visited.add(node)

        for neighbor, cost in graph[node]:
            if neighbor not in visited:
                new_g = g + cost
                new_f = new_g + heuristic[neighbor]
                heapq.heappush(pq, (new_f, new_g, neighbor, path + [neighbor]))

    return None

path, cost = astar('A', 'G')

if path:
    print("Shortest Path:", " -> ".join(path))
    print("Total Cost:", cost)
else:
    print("No Path Found")
```

## Output

```text
Shortest Path: A -> B -> D -> G
Total Cost: 6
```
<img width="1445" height="840" alt="image" src="https://github.com/user-attachments/assets/d4254931-28e1-474e-a961-28272690040e" />


## Result

The A* Search Algorithm was successfully implemented in Python, and the shortest path from the start node to the goal node was obtained.

## Conclusion

The A* Search Algorithm efficiently finds the optimal path by combining the actual path cost with heuristic estimates. It is widely used in artificial intelligence, robotics, and navigation systems due to its accuracy and efficiency.
