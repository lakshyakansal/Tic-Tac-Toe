# Tic-Tac-Toe with Minimax AI

A command-line Tic-Tac-Toe game in Python where you play against an unbeatable AI. The AI uses the **Minimax algorithm** to evaluate every possible game state and always pick the optimal move.

## Features

- Play in the terminal against a computer opponent
- AI built on the Minimax algorithm (exhaustive game-tree search)
- Win, loss, and draw detection
- Simple, dependency-free code (standard library only)

## Requirements

- Python 3.6 or higher

No external packages are needed.

## How to Run

1. Save the code as `tictactoe.py`.
2. Run it from the terminal:



## How to Play

- You play as **`O`** and move first. The AI plays as **`X`**.
- On your turn, enter the row and column separated by a space. Indexing starts at **0**.

```
Enter your move (row and column): 1 1
```

The board coordinates are:

```
(0,0) | (0,1) | (0,2)
-----------------------
(1,0) | (1,1) | (1,2)
-----------------------
(2,0) | (2,1) | (2,2)
```

- The game ends when someone gets three in a row (horizontally, vertically, or diagonally) or the board is full.

### Example Session

```
Welcome to Tic-Tac-Toe!
  |   |  
---------
  |   |  
---------
  |   |  
---------
Enter your move (row and column): 1 1
  |   |  
---------
  | O |  
---------
  |   |  
---------
AI's move:
X |   |  
---------
  | O |  
---------
  |   |  
---------
```

## How It Works

### Minimax Algorithm

Minimax is a recursive decision algorithm used in two-player, turn-based games. It simulates all possible future moves and assumes both players play optimally.

- **`X` (AI)** is the *maximizing* player and tries to get the highest score.
- **`O` (human)** is the *minimizing* player and tries to get the lowest score.

Terminal states are scored as follows:

| Outcome    | Score |
|------------|-------|
| `X` wins   | `+1`  |
| `O` wins   | `-1`  |
| Draw       | `0`   |

For each empty cell, the AI tries a move, recursively evaluates the resulting board, undoes the move, and keeps the move with the best score.

### Code Structure

| Function | Description |
|----------|-------------|
| `print_board(board)` | Prints the current board to the console. |
| `check_winner(board, player)` | Returns `True` if the given player has three in a row. |
| `check_draw(board)` | Returns `True` if the board is full. |
| `minimax(board, depth, is_maximizing)` | Recursively scores a board position. |
| `best_move(board)` | Returns the `(row, col)` of the AI's best move. |
| `play_game()` | Main game loop handling input, turns, and results. |

## Notes and Limitations

- The AI is **unbeatable**: the best result you can achieve is a draw.
- Input is not fully validated. Entering coordinates outside `0-2`, or non-numeric input, will raise an error.
- The `depth` parameter in `minimax` is currently tracked but not used in scoring.
- No alpha-beta pruning is used. This is fine for a 3x3 board, but it would be needed for larger boards.

## Possible Improvements

- Add input validation and error handling
- Let the player choose `X` or `O`, or choose who goes first
- Add alpha-beta pruning for better performance
- Use depth in scoring so the AI prefers faster wins and slower losses
- Add a GUI (e.g., Tkinter or Pygame)

## License

This project is open for educational use. Add a license of your choice (e.g., MIT) if you plan to distribute it.
<div align="center">

Developed by Lakshya Kansal

</div>

