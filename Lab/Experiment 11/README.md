# Experiment 11: Map Coloring using Constraint Satisfaction Problem (CSP)

## Aim

To implement the Map Coloring problem using the Constraint Satisfaction Problem (CSP) approach in Python.

## Objective

- To understand the concept of Constraint Satisfaction Problems (CSP).
- To implement the Map Coloring problem using backtracking.
- To assign colors to regions such that no two adjacent regions have the same color.
- To find a valid solution satisfying all constraints.

## Algorithm

1. Start the algorithm.
2. Define the map with its neighboring regions.
3. Define the available colors.
4. Select an unassigned region.
5. Assign a color that satisfies the constraints.
6. Check whether any adjacent region has the same color.
7. If the constraint is satisfied, proceed to the next region.
8. Otherwise, backtrack and assign another color.
9. Repeat until all regions are assigned valid colors.
10. Display the final color assignment.
11. Stop the algorithm.

## Flowchart

```text
                  START
                    │
                    ▼
         Define Map and Colors
                    │
                    ▼
        Select an Unassigned Region
                    │
                    ▼
           Assign a Valid Color
                    │
                    ▼
      Are Constraints Satisfied?
             ┌──────┴──────┐
            No            Yes
            │              │
            ▼              ▼
      Try Another      Assign Next
         Color           Region
            │              │
            └──────┬───────┘
                   │
                   ▼
     Are All Regions Assigned?
            ┌──────┴──────┐
           No            Yes
            │              │
            ▼              ▼
      Repeat Process   Display Solution
                            │
                            ▼
                           STOP
```

## Python Code

```python
graph = {
    'A': ['B', 'C', 'D'],
    'B': ['A', 'C'],
    'C': ['A', 'B', 'D'],
    'D': ['A', 'C']
}

colors = ['Red', 'Green', 'Blue']

color_assignment = {}

def is_safe(region, color):
    for neighbor in graph[region]:
        if neighbor in color_assignment and color_assignment[neighbor] == color:
            return False
    return True

def map_coloring():
    for region in graph:
        for color in colors:
            if is_safe(region, color):
                color_assignment[region] = color
                break

    return color_assignment

solution = map_coloring()

print("Color Assignment:")
for region, color in solution.items():
    print(region, ":", color)
```

## Output

```text
Color Assignment:
A : Red
B : Green
C : Blue
D : Green
```
<img width="1391" height="795" alt="image" src="https://github.com/user-attachments/assets/0faf15eb-0d6f-4a69-a51e-ab98b6dc5e93" />


## Result

The Map Coloring problem was successfully solved using the Constraint Satisfaction Problem (CSP) approach by assigning different colors to adjacent regions.

## Conclusion

The Constraint Satisfaction Problem (CSP) approach successfully assigned colors to all regions while satisfying the adjacency constraints. This technique is widely used in scheduling, planning, resource allocation, and artificial intelligence applications.
