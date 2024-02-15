# Chess-Game
Chess game is implemented from scratch using minimax algorithm and alpha-beta pruning techniques.

# Chess Game using Min-Max Algorithm with Alpha-Beta Pruning

## Author: Faziha Ikhlaq
## Language used: Python

### Explanation:

1. **piece_square_tables**: Dictionary of piece square tables for evaluation.
2. **getOppositeTable(table)**: Function that takes in a table and returns the inverted table by reversing and negating all the elements.
3. **getPieceVal(_piece)**: Function that gets the value of a piece.
4. **getPieceEvaluation(_piece)**: It gets the evaluations for a piece at a position according to our piece square tables.
5. **getBoardEvaluation(_board)**: It gets the total value of a board.
6. **parseInput(move)**: It takes in string input and returns appropriate indexes.
7. **parsePosition(pos)**: Using a tuple of integers, this function translates a chess position from a string format to an index format. The string representation comprises a letter indicating the column and a digit indicating the row.
8. **unparseInput(curr_row, curr_col, new_row, new_col)**: It takes indexes of current position and new position of a chess piece and returns a string representation of the move.
9. **getOppositeTeam(team)**: It takes in a team name and returns the opposite team name.

### Piece Class Explanation:

- It contains a constructor to initialize the Piece object, i.e., `__init__(self, name, symbol, team, row, col, points)`.
- Moreover, it also contains the following functions:
    - `updateIndexes(self, r, c)`: for updating indexes.
    - `getAllowedMoves(self, _board)`: for allowed moves.
    - `getCopy(self)`: for returning a deep copy of objects.

### Other Classes Used:

- class King(Piece)
- class Queen(Piece)
- class Rook(Piece)
- class Bishop(Piece)
- class Knight(Piece)
- class Pawn(Piece)

Each class has its own `__init__(self, symbol, team, row, col)` and moves.

### Chessboard Class Functions:

1. `placePieces(self)`: Puts initial pieces on the actual board.
2. `getCopy(self)`: Gets a copy of the board (all pieces and their attributes copied as well).
3. `updatePoints(self)`: Changes the points of a piece depending on its color.
4. `updateMoves(self)`: Depending on color, the moves have to be negated as the teams face opposite directions.
5. `disp(self)`: Display function for displaying 8x8 chessboard.
6. `inRange(self, row: int, col: int)`: Check if coordinates are on the board.
7. `isCellEmpty(self, row: int, col: int)`: Check if a particular cell is empty.
8. `teamAtDest()`
9. `enemyAtDest()`: Check if there is a member of the opposite team at the destination.
10. `get_all_allowed_moves()`: Gets the list of all allowed moves for this board.
11. `get_team_positions()`: Gets the list of (row, column) positions of every piece of the specified team.

Moreover, there are functions like `getPiece()`, `getTeam()`, `getPieceName()`, `emptyCell()`, `putPiece()`, `castle()`, `transform_pawn()`, `should_pawn_transform()`, `is_move_possible()`, `team_in_path()`, and `move_piece()`.

### AI Class:

- `__init__(self, team, depth)`
- `maxValue(self, _board, depth, team, alpha, beta)`
- `minValue(self, _board, depth, team, alpha, beta)`
- `minimax()`
- `move()`

### Game Function:

- Necessary function calls and print statements, user input is also taken over here.

### Main:

- Entry point of the program.

### Summary:

The code includes a dictionary named "piece_square_tables" that contains four lists of lists of floats that each represent the value of a certain chess piece (king, queen, rook, or bishop) that is situated on a given square of the chessboard. Chess engines use what are referred to as "piece-square values" to determine the strength of a specific position on the board. A strong position is indicated by positive values, whilst the opposite is true for negative numbers.

The chess pieces King, Queen, and Rook are subclasses of the base class "Piece," which is defined in the code. The list of moves available to the Piece class is expanded by the constructors and special moves that are specific to each piece subclass.

Two arguments are passed to the inCheck function: team, a string representing the team being checked, and _board, an instance of the chessBoard class.

The inChkmate function examines if the specified team is in checkmate using the same two arguments as inCheck. The same two inputs are required for the inStalemate function, which determines whether the specified team is deadlocked.

The 8x8 chessboard object is defined by the chessBoard class, which also has various more methods like placePieces(), getCopy(), updatePoints(), updateMoves(), and disp().

The class also has methods for a variety of board circumstances, including inRange(), isCellEmpty(), teamAtDest(), and enemyAtDest().

The class also has methods like get all allowed_moves(team), which produces a list of all the moves that a given team is permitted to make, and isCheckmate(team), which determines whether or not a team is in checkmate.

You would create an instance of the chessBoard class and use its methods as necessary to use this code.

Overall, the code implements a basic game of chess between a human player and an AI player using minimax and alpha-beta pruning techniques.


