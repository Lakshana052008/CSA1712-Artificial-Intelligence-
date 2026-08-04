# Experiment 13: Minimax Algorithm for Gaming

## Aim

To implement the Minimax Algorithm in Python for selecting the optimal move in a two-player game.

## Objective

- To understand the concept of the Minimax Algorithm.
- To implement game tree search using Minimax.
- To determine the best move for the maximizing player.
- To apply decision-making techniques in Artificial Intelligence.

## Algorithm

1. Start the program.
2. Define the game state and possible moves.
3. Check if the current state is a terminal state.
4. If the maximizing player's turn, choose the maximum score.
5. If the minimizing player's turn, choose the minimum score.
6. Recursively evaluate all possible moves.
7. Return the optimal score to the parent node.
8. Display the best possible outcome.
9. Stop the program.

## Flowchart

```text
                   START
                     │
                     ▼
          Define Game State
                     │
                     ▼
        Is Terminal State Reached?
             ┌───────┴────────┐
            Yes              No
             │                │
             ▼                ▼
       Return Score      Maximizing Player?
                             ┌────┴────┐
                            Yes       No
                             │         │
                             ▼         ▼
                      Choose Max   Choose Min
                             │         │
                             └────┬────┘
                                  │
                                  ▼
                      Evaluate Next States
                                  │
                                  ▼
                           Return Best Score
                                  │
                                  ▼
                                 STOP
```

## Python Code

```python
def minimax(depth, nodeIndex, maximizingPlayer, values, maxDepth):

    if depth == maxDepth:
        return values[nodeIndex]

    if maximizingPlayer:
        return max(
            minimax(depth + 1, nodeIndex * 2, False, values, maxDepth),
            minimax(depth + 1, nodeIndex * 2 + 1, False, values, maxDepth)
        )
    else:
        return min(
            minimax(depth + 1, nodeIndex * 2, True, values, maxDepth),
            minimax(depth + 1, nodeIndex * 2 + 1, True, values, maxDepth)
        )

values = [3, 5, 6, 9, 1, 2, 0, -1]

result = minimax(0, 0, True, values, 3)

print("The optimal value is:", result)
```

## Output

```text
The optimal value is: 5
```
<img width="1372" height="782" alt="image" src="https://github.com/user-attachments/assets/6696a064-f139-4116-bcb2-a6f26158ace0" />


## Result

The Minimax Algorithm was successfully implemented in Python, and the optimal value for the maximizing player was determined.

## Conclusion

The Minimax Algorithm efficiently evaluates all possible game states and selects the optimal move by maximizing the player's score while minimizing the opponent's score. It is widely used in Artificial Intelligence for decision-making in games such as Tic Tac Toe, Chess, and Checkers.
