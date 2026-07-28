# Experiment 12: Tic Tac Toe Game using Python

## Aim

To implement the Tic Tac Toe game in Python using a simple two-player approach.

## Objective

- To understand the implementation of a Tic Tac Toe game.
- To develop a two-player game using Python.
- To apply conditional statements, loops, and functions.
- To determine the winner or declare a draw based on the game rules.

## Algorithm

1. Start the program.
2. Create a 3×3 game board.
3. Display the empty board.
4. Allow Player X to enter a valid position.
5. Update the board with Player X's move.
6. Check for a winning condition or draw.
7. If the game is not over, allow Player O to make a move.
8. Repeat the process until a player wins or the board is full.
9. Display the game result.
10. Stop the program.

## Flowchart

```text
                  START
                    │
                    ▼
            Create Game Board
                    │
                    ▼
             Display the Board
                    │
                    ▼
         Get Player's Valid Move
                    │
                    ▼
            Update the Board
                    │
                    ▼
          Check Win or Draw?
            ┌──────┴──────┐
           Yes           No
            │             │
            ▼             ▼
     Display Result   Switch Player
            │             │
            └──────┬──────┘
                   │
                   ▼
                Repeat
                   │
                   ▼
                  STOP
```

## Python Code

```python
board = [' ' for _ in range(9)]

def print_board():
    print()
    print(board[0] + ' | ' + board[1] + ' | ' + board[2])
    print('--+---+--')
    print(board[3] + ' | ' + board[4] + ' | ' + board[5])
    print('--+---+--')
    print(board[6] + ' | ' + board[7] + ' | ' + board[8])
    print()

def check_winner(player):
    win_positions = [
        [0,1,2],[3,4,5],[6,7,8],
        [0,3,6],[1,4,7],[2,5,8],
        [0,4,8],[2,4,6]
    ]
    for pos in win_positions:
        if all(board[i] == player for i in pos):
            return True
    return False

current_player = 'X'

for turn in range(9):
    print_board()
    move = int(input(f"Player {current_player}, enter position (1-9): ")) - 1

    if board[move] == ' ':
        board[move] = current_player

        if check_winner(current_player):
            print_board()
            print(f"Player {current_player} Wins!")
            break

        current_player = 'O' if current_player == 'X' else 'X'
    else:
        print("Position already occupied!")
        continue
else:
    print_board()
    print("Match Draw!")
```

## Output

```text
  |   |  
--+---+--
  |   |  
--+---+--
  |   |  

Player X, enter position (1-9): 1
Player O, enter position (1-9): 5
Player X, enter position (1-9): 2
Player O, enter position (1-9): 8
Player X, enter position (1-9): 3

X | X | X
--+---+--
  | O |  
--+---+--
  | O |  

Player X Wins!
```

## Result

The Tic Tac Toe game was successfully implemented in Python, allowing two players to play the game and correctly determine the winner or a draw.

## Conclusion

The Tic Tac Toe game was successfully developed using Python. The program correctly handled player turns, validated moves, detected winning conditions, and declared the game result. This experiment demonstrates the use of decision-making, loops, functions, and game logic in Python.
