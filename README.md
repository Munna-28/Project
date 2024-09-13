# Sudoku Solver

## Overview
This is a C++ implementation of a **Sudoku Solver** that uses a **backtracking algorithm** to solve any valid 9x9 Sudoku puzzle. The program checks for an empty cell, tries placing a digit, validates the placement, and backtracks if necessary. 

## Features
- Solves a standard 9x9 Sudoku puzzle.
- Uses a backtracking algorithm to explore possible solutions efficiently.
- Follows Sudoku rules: each row, column, and 3x3 sub-grid must contain the digits 1 to 9 exactly once.

## Requirements
- C++11 or higher
- C++ Standard Template Library (STL)
  
## How the Algorithm Works
1. The solver checks each cell on the board.
2. When an empty cell is found, it tries placing digits 1 through 9.
3. If placing a digit violates any Sudoku rule, it backtracks and tries the next digit.
4. The algorithm continues until all cells are filled with valid digits.
5. If no solution is possible, the algorithm stops and returns `false`.

## Code Breakdown

### Main Functions
- **solveSudoku(board)**: Initializes the solution process by calling the recursive `solve()` function.
- **solve(board)**: Recursively attempts to place digits in the empty cells using the backtracking method.
- **isvalid(i, j, c, board)**: Checks whether placing a digit `c` at position `(i, j)` is valid, i.e., if it adheres to Sudoku rules.

### Key Components
- **Backtracking**: The core of the algorithm where each potential solution is explored recursively, and incorrect attempts are undone by "backtracking."
- **Validation**: Ensures that no digit is repeated in any row, column, or 3x3 sub-grid.

## Code Usage
1. Include the code in your C++ project.
2. You need to provide a 9x9 Sudoku board, where empty cells are represented by `'.'`.
3. Call the `solveSudoku(board)` function to solve the puzzle.

```cpp
vector<vector<char>> board = {
    {'5','3','.','.','7','.','.','.','.'},
    {'6','.','.','1','9','5','.','.','.'},
    {'.','9','8','.','.','.','.','6','.'},
    {'8','.','.','.','6','.','.','.','3'},
    {'4','.','.','8','.','3','.','.','1'},
    {'7','.','.','.','2','.','.','.','6'},
    {'.','6','.','.','.','.','2','8','.'},
    {'.','.','.','4','1','9','.','.','5'},
    {'.','.','.','.','8','.','.','7','9'}
};

Solution().solveSudoku(board);
