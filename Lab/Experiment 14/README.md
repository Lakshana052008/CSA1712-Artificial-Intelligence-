# Experiment 14: Implementation of Alpha-Beta Pruning Algorithm for Gaming

## Aim

To implement the Alpha-Beta Pruning Algorithm in Python to optimize the Minimax Algorithm for game playing.

## Objective

- To understand the Alpha-Beta Pruning technique.
- To implement Alpha-Beta Pruning using Minimax.
- To reduce the number of nodes evaluated during game tree search.
- To determine the optimal move efficiently.

## Algorithm

1. Start the program.
2. Define the game tree and terminal node values.
3. Initialize alpha as negative infinity and beta as positive infinity.
4. Check whether the current node is a terminal node.
5. If the current player is the maximizing player, update the maximum score and alpha value.
6. If the current player is the minimizing player, update the minimum score and beta value.
7. If alpha becomes greater than or equal to beta, prune the remaining branches.
8. Continue recursively until the optimal value is obtained.
9. Display the optimal value.
10. Stop the program.

## Flowchart

```text
                    START
                      │
                      ▼
          Initialize Alpha & Beta
                      │
                      ▼
          Is Terminal Node Reached?
              ┌───────┴────────┐
             Yes              No
              │                │
              ▼                ▼
        Return Score     Maximizing Player?
                              ┌────┴────┐
                             Yes       No
                              │         │
                              ▼         ▼
                    Update Alpha   Update Beta
                              │         │
                              ▼         ▼
                    Alpha ≥ Beta ?
                       ┌────┴────┐
                      Yes       No
                       │         │
                       ▼         ▼
                 Prune Branch  Continue Search
                       │         │
                       └────┬────┘
                            │
                            ▼
                    Return Best Score
                            │
                            ▼
                           STOP
```

## Python Code

```python
import math

def alphabeta(depth, nodeIndex, maximizingPlayer, values, alpha, beta, maxDepth):

    if depth == maxDepth:
        return values[nodeIndex]

    if maximizingPlayer:
        best = -math.inf

        for i in range(2):
            value = alphabeta(depth + 1, nodeIndex * 2 + i, False,
                              values, alpha, beta, maxDepth)
            best = max(best, value)
            alpha = max(alpha, best)

            if beta <= alpha:
                break

        return best

    else:
        best = math.inf

        for i in range(2):
            value = alphabeta(depth + 1, nodeIndex * 2 + i, True,
                              values, alpha, beta, maxDepth)
            best = min(best, value)
            beta = min(beta, best)

            if beta <= alpha:
                break

        return best


values = [3, 5, 6, 9, 1, 2, 0, -1]

result = alphabeta(
    0,
    0,
    True,
    values,
    -math.inf,
    math.inf,
    3
)

print("The optimal value is:", result)
```

## Output

```text
The optimal value is: 5
```
<img width="1282" height="841" alt="image" src="https://github.com/user-attachments/assets/f580670f-b88a-4d54-9389-e3cfe2a49e18" />


## Result

The Alpha-Beta Pruning Algorithm was successfully implemented in Python, and the optimal value was obtained while reducing the number of nodes evaluated.

## Conclusion

The Alpha-Beta Pruning Algorithm improves the efficiency of the Minimax Algorithm by eliminating unnecessary branches without affecting the final decision. It significantly reduces computation time and is widely used in AI-based games such as Chess, Tic Tac Toe, Checkers, and Connect Four.
