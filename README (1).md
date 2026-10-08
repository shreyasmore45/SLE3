# Tic-Tac-Toe Game-Playing AI (Minimax)

## Project Overview

This project implements a **Tic-Tac-Toe Game-Playing AI** using the **Minimax algorithm**. The system allows a human player to play Tic-Tac-Toe against an AI agent on a 3×3 board.

The AI examines possible future moves and selects the move that gives it the best guaranteed outcome, while assuming that the opponent also plays optimally. Because the Tic-Tac-Toe game tree is small enough to search completely, the Minimax-based AI can play perfectly and cannot lose.

## Course Information

- **Course:** 02AML204 – Introduction to Artificial Intelligence
- **Student:** Shreyas More
- **PRN:** 25UAM071
- **Project:** Tic-Tac-Toe Game-Playing AI (Minimax)
- **Architecture:** Full C4 Model

## Features

- Human vs AI gameplay
- 3×3 Tic-Tac-Toe board
- Input validation
- Win and draw detection
- Minimax-based decision making
- Best-move selection
- Self-contained execution
- No network or external API dependency

## System Architecture

The project is organized into the following major components:

### 1. Input Module
Reads the player's selected cell (1–9) and checks whether the selected position is valid and empty.

### 2. Game Engine
Controls the game flow, turn order, move application, and win/draw checking.

### 3. Board State
Stores the current 3×3 board using a simple list of 9 cells.

### 4. AI Engine
Uses the Minimax algorithm to evaluate possible moves and select the best move for the AI.

### 5. Output Module
Displays the current board and announces the final result.

## Minimax AI

The AI engine contains the following logical components:

- **Move Generator:** Finds all currently available moves.
- **Terminal Test:** Checks whether the game has been won or has ended in a draw.
- **Evaluator:** Assigns scores:
  - `+1` → AI win
  - `0` → Draw
  - `-1` → Player win
- **Move Selector:** Maximizes the AI score while assuming the human player minimizes it.

## Main Functions

The implementation is structured around these functions:

```text
print_board(board)
check_winner(board)
is_full(board)
minimax(board, depth, is_maximizing)
best_move(board)
play_game()
```

### Function Responsibilities

| Function | Purpose |
|---|---|
| `print_board()` | Displays the current board |
| `check_winner()` | Checks all winning combinations |
| `is_full()` | Checks whether the board is full |
| `minimax()` | Recursively evaluates future game states |
| `best_move()` | Selects the AI's best available move |
| `play_game()` | Controls the complete game loop |

## Design Decisions

A simple list containing 9 cells is used to represent the board instead of a separate Board class or 2D structure. This keeps placing, undoing, and recursive search operations simple.

Minimax was selected because Tic-Tac-Toe has a small game tree that can be searched completely. This allows the AI to make optimal decisions.

The game rules and AI decision-making are kept separate. Functions such as `check_winner()` handle game rules, while `minimax()` and `best_move()` handle AI decisions. This makes the system easier to modify and extend.

## C4 Architecture

The project was documented using four levels of the C4 model:

1. **Context Level** – Shows the player interacting with the Tic-Tac-Toe AI system.
2. **Container Level** – Shows the Input Module, Game Engine, Board State, AI Engine, and Output Module.
3. **Component Level** – Breaks the AI Engine into Move Generator, Terminal Test, Evaluator, and Move Selector.
4. **Code Level** – Describes the main functions used to implement the system.

## How to Run

1. Make sure Python 3 is installed.
2. Clone this repository.
3. Open the project directory.
4. Run the Python game file.

Example:

```bash
python tic_tac_toe.py
```

Follow the instructions displayed in the terminal to select a board position.

## Example Game Flow

```text
Player selects a cell
        ↓
Input validation
        ↓
Board updated
        ↓
Check win/draw
        ↓
AI calculates best move using Minimax
        ↓
AI move applied
        ↓
Board displayed
        ↓
Game continues until win/draw
```

## AI Contribution

AI tools were used during development for code generation/refinement, C4 diagram creation, and document formatting. The project design, component breakdown, design decisions, and review of the generated material were completed by the student.

See **[AI_CONTRIBUTION_LOG.md](AI_CONTRIBUTION_LOG.md)** for the detailed AI contribution record.

## Limitations

- The project is designed specifically for Tic-Tac-Toe.
- The interface is command-line based.
- The current version does not include a graphical user interface.
- There is no online multiplayer or network functionality.

## Future Enhancements

Possible improvements include:

- Alpha-Beta pruning
- Graphical user interface
- Difficulty levels
- Player vs player mode
- Game statistics
- Move history
- Sound effects and animations
- Web-based version
- Larger board/game variants

## Conclusion

This project demonstrates how an adversarial search algorithm can be applied to a simple two-player zero-sum game. The Minimax algorithm provides a clear example of AI-based decision-making, while the C4 architecture shows how the same system can be represented from high-level system context down to individual implementation functions.
