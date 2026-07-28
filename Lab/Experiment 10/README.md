# Experiment 10: Implementation of A* Search Algorithm

## Aim
To implement the A* Search Algorithm to find the shortest path between a start node and a goal node using heuristic values.

## Objective
- Understand the working of the A* Search Algorithm.
- Find the shortest path between the start node and the goal node.
- Use heuristic values to determine the optimal path.

---

## Flowchart

```text
                START
                  │
                  ▼
      Initialize Graph & Heuristic
                  │
                  ▼
      Add Start Node to Open List
                  │
                  ▼
        Is Open List Empty?
            ┌─────┴─────┐
          Yes          No
           │            │
           ▼            ▼
     No Path Found  Select Node with
                    Lowest f(n)
                         │
                         ▼
                  Is Goal Reached?
                    ┌────┴────┐
                  Yes        No
                   │          │
                   ▼          ▼
            Display Path   Expand Neighbors
                 │              │
                 ▼              ▼
              Display Cost  Update g, h, f
                     │          │
                     └──────┬───┘
                            │
                            ▼
                      Repeat Process
                            │
                            ▼
                           STOP
```

---

## Program

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

---

## Output

```text
Shortest Path: A -> B -> D -> G
Total Cost: 6
```

---

## Result

The A* Search Algorithm was successfully implemented, and the shortest path from the start node to the goal node was obtained.
