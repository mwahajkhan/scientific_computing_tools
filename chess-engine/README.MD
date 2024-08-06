# Chess Game

## **Project Description**

This project is a simple chess game implemented in Python using Pygame. The game provides a graphical interface for playing chess, including features like move animation, AI opponent, and game state management.

## **Improvements and Use Case**

### Improvements
- **Enhanced AI**: Future updates could include more sophisticated AI algorithms for challenging gameplay.
- **User Interface**: Better graphics and user interface improvements for a more engaging experience.
- **Multiplayer Mode**: Adding network support for online multiplayer games.

### Use Case
This chess game is designed for users who want a straightforward chess-playing experience with both human and AI opponents. It's suitable for learning and casual play.

## **Project Setup**

To set up this project locally, follow these steps:

1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/chess-game.git
```
2. Create Virtual environment:

        > conda create --name chess_engine python=3.8

###Dependencies

pygame - For the graphical interface and game loop.
numpy - For array manipulations and optimizations.

You can install the required dependencies using:

```bash
pip install pygame numpy
```

###Demo 

To run the application:

1. Project Setup (dependencies & virtual env refer up)
2. Open terminal:
   ```bash
cd /path to project
python Chess-Main
```

This should launch the application.

![image_1]('images1.png')

![image_1]('images1.png')



##**Project Structure**
### 1. Chess-Main.py

**Description**: The main driver file for the chess game. Handles user input and displays the current game state.

**Functions:**

- **loadImages()**: Loads images for all chess pieces and stores them in the IMAGES dictionary.
- **drawGameState(screen, gs, validMoves, sqSelected)**: Draws the game state on the screen.
- **drawBoard(screen):** Draws the chessboard with alternating colors for squares.
- **drawPieces(screen, gs, validMoves, sqSelected):** Draws the chess pieces based on their positions.
- **highlightSquares(screen, gs, validMoves, sqSelected):** Highlights the selected square and possible moves.
- **animateMove(move, screen, board, clock, validMoves, sqSelected):** Animates moves from one square to another.
- *8drawText(screen, text):** Displays text on the screen, such as checkmate or stalemate messages.
- **main():** Initializes the game, handles events, and updates the game state.

### 2. chessEngine.py

**Description:** Manages the chess game's state, including the board, moves, and game logic.

Class: GameState

- **__init__(self):** Initializes the game state, setting up the board and move functions.
- **makeMove(self, move):** Executes a move and updates the game state.
- **undoMove(self):** Undoes the last move.
- **getValidMoves(self):** Returns all valid moves for the current game state.
- **getAllPossibleMoves(self):** Returns all possible moves without considering checks.
- **checkForPinsAndChecks(self):** Updates the game state to handle checks and pins.
- **getPawnMoves(self, row, col, moves), getRookMoves(self, r, c, moves)**, etc.: Methods for getting possible moves for each piece type.
- **squareUnderAttack(self, r, c):** Checks if a square is under attack.
- **getCastleMoves(self, r, c, moves):** Returns possible castling moves.

### 3. smartMoveFinder.py

**Description:** Implements the AI logic for determining the best move.

**Functions:**

- **scoreBoard(gs):** Evaluates the board position and assigns a score.
- **isEndgame(gs):** Checks if the game is in the endgame phase.
- **findBestMove(gs, validMoves, returnQueue):** Finds the best move using an AI algorithm.
- **findMoveNegaMaxAlphaBeta(gs, validMoves, depth, alpha, beta, turnMultiplier):** Implements the NegaMax algorithm with alpha-beta pruning.
- **findRandomMove(validMoves):** Selects a random move from the list of valid moves.
