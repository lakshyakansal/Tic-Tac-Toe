# Tic-Tac-Toe with Minimax AI

A command-line Tic-Tac-Toe game in Python where you play against an unbeatable AI. The AI uses the **Minimax algorithm with alpha-beta pruning** to evaluate game states and always pick the optimal move.

## Features

- Play in the terminal against a computer opponent
- Choose your symbol (`X` or `O`) and whether you go first
- Minimax AI with **alpha-beta pruning**
- **Depth-aware scoring**: the AI prefers faster wins and delays losses
- Full **input validation** (bad input, out-of-range or occupied cells)
- **Play again** option after each game
- Standard library only, no dependencies

## Requirements

- Python 3.6 or higher

## How to Run

```bash
python tictactoe.py
```

## How to Play

1. Pick your symbol (`X` or `O`) and choose whether to move first.
2. On your turn, enter the row and column separated by a space (or comma). Indexing starts at **0**.

```
Enter your move (row and column, 0-2, e.g. '1 1'): 1 1
```

Board coordinates:

```
(0,0) | (0,1) | (0,2)
-----------------------
(1,0) | (1,1) | (1,2)
-----------------------
(2,0) | (2,1) | (2,2)
```

3. The game ends when someone gets three in a row or the board is full.

### Example Session

```
Welcome to Tic-Tac-Toe!
Choose your symbol (X/O): o
Do you want to go first? (y/n): y

   |   |
---+---+---
   |   |
---+---+---
   |   |

Enter your move (row and column, 0-2, e.g. '1 1'): 1 1

   |   |
---+---+---
   | O |
---+---+---
   |   |

AI is thinking...
AI plays at (0, 0)
```

## How It Works

### Minimax with Alpha-Beta Pruning

Minimax simulates all possible future moves and assumes both players play optimally. Alpha-beta pruning skips branches that cannot affect the final decision, so the same result is reached with far fewer positions evaluated.

- The **AI** is the *maximizing* player.
- The **human** is the *minimizing* player.

| Outcome  | Score            |
|----------|------------------|
| AI wins  | `10 - depth`     |
| Human wins | `depth - 10`   |
| Draw     | `0`              |

Subtracting depth means a quick win scores higher than a slow one, and a loss that happens later scores higher than one that happens sooner.

### Code Structure

| Function | Description |
|----------|-------------|
| `print_board(board)` | Prints the current board. |
| `check_winner(board, player)` | Returns `True` if the player has three in a row. |
| `check_draw(board)` | Returns `True` if the board is full. |
| `available_moves(board)` | Lists the empty cells. |
| `minimax(board, depth, alpha, beta, is_maximizing, ai, human)` | Recursively scores a position with pruning. |
| `best_move(board, ai, human)` | Returns the AI's best `(row, col)`. |
| `get_human_move(board)` | Reads and validates the player's move. |
| `ask_choice(prompt, options)` | Reusable validated prompt. |
| `play_game()` | Runs a single game. |
| `main()` | Replay loop and clean exit on Ctrl+C. |

## Notes

- The AI is **unbeatable**: the best result you can achieve is a draw.

## Possible Future Improvements

- Add a difficulty setting (e.g. occasional random moves)
- Add a GUI (Tkinter or Pygame)
- Track a win/loss/draw scoreboard across games

## License

This project is open for educational use. Add a license of your choice (e.g., MIT) if you plan to distribute it.

<div align="center">

Developed by Lakshya Kansal

</div>
