# Sudoku Solver - Naked Single Technique
![C++](https://img.shields.io/badge/C++-00599C?style=for-the-badge&logo=c%2B%2B&logoColor=white)

A C++ implementation of a Sudoku solver that uses the Naked Single technique to solve Sudoku puzzles as much as possible.

## Table of Contents

- [Description](#description)
- [Features](#features)
- [Tech Stack](#tech-stack)
- [How It Works](#how-it-works)
- [Installation](#installation)
- [Usage](#usage)
- [Screenshots](#screenshots)
- [Algorithm Explanation](#algorithm-explanation)
- [Author](#author)

## Description

This project implements a Sudoku puzzle solver using the **Naked Single** technique - one of the fundamental solving strategies in Sudoku. The program reads a 9x9 Sudoku board, applies the Naked Single technique iteratively, and displays the partially or fully solved board.

The Naked Single technique works by identifying cells that have only one possible value based on the constraints of Sudoku rules (no duplicates in rows, columns, or 3x3 boxes).

## Features

- ✅ Read Sudoku puzzles from user input
- ✅ Display formatted Sudoku boards with grid separators
- ✅ Solve puzzles using the Naked Single technique
- ✅ Handle partially solvable puzzles
- ✅ Clear visualization with 'x' for empty cells
- ✅ Iterative solving until no more naked singles are found

## Tech Stack

**Language:** C++  
**Paradigm:** Procedural Programming  
**Standard:** C++11 or higher

## How It Works

### Naked Single Technique

A **Naked Single** occurs when a cell has only one possible candidate number that can be placed in it, considering:

1. Numbers already present in the same **row**
2. Numbers already present in the same **column**
3. Numbers already present in the same **3x3 box**

The program:
1. Scans each empty cell (marked as 0)
2. Creates a candidate list [1-9]
3. Eliminates numbers found in the same row, column, and box
4. If only one candidate remains, fills that cell
5. Repeats until no more naked singles are found

## Installation

### Prerequisites

- C++ compiler (g++, clang++, or MSVC)
- Standard C++ library

### Compilation

```bash
g++ -o sudoku Sudoku.c++ -std=c++11
```

Or using clang:

```bash
clang++ -o sudoku Sudoku.c++ -std=c++11
```

## Usage

### Running the Program

```bash
./sudoku
```

### Input Format

Enter the Sudoku board row by row, using `0` for empty cells:

```
5 3 0 0 7 0 0 0 0
6 0 0 1 9 5 0 0 0
0 9 8 0 0 0 0 6 0
8 0 0 0 6 0 0 0 3
4 0 0 8 0 3 0 0 1
7 0 0 0 2 0 0 0 6
0 6 0 0 0 0 2 8 0
0 0 0 4 1 9 0 0 5
0 0 0 0 8 0 0 7 9
```

### Output

The program displays:
1. The input board
2. The solved/partially solved board

```
Input Sudoku board:
5 3 x | x 7 x | x x x
6 x x | 1 9 5 | x x x
x 9 8 | x x x | x 6 x
------+-------+-------
8 x x | x 6 x | x x 3
4 x x | 8 x 3 | x x 1
7 x x | x 2 x | x x 6
------+-------+-------
x 6 x | x x x | 2 8 x
x x x | 4 1 9 | x x 5
x x x | x 8 x | x 7 9

Final Sudoku board:
5 3 4 | 6 7 8 | 9 1 2
6 7 2 | 1 9 5 | 3 4 8
1 9 8 | 3 4 2 | 5 6 7
------+-------+-------
8 5 9 | 7 6 1 | 4 2 3
4 2 6 | 8 5 3 | 7 9 1
7 1 3 | 9 2 4 | 8 5 6
------+-------+-------
9 6 1 | 5 3 7 | 2 8 4
2 8 7 | 4 1 9 | 6 3 5
3 4 5 | 2 8 6 | 1 7 9
```

## Screenshots

### Input Board
<img width="492" alt="Input Sudoku Board" src="https://user-images.githubusercontent.com/99832552/210157801-9f2ba41c-ab3f-4dd8-a87f-59959ac9e657.png">

### Solving Process
<img width="503" alt="Solving Step 1" src="https://user-images.githubusercontent.com/99832552/210157803-3f58065b-6de4-4b82-8a7c-0e9eec87ccd0.png">

<img width="497" alt="Solving Step 2" src="https://user-images.githubusercontent.com/99832552/210157807-64a51f9b-bd12-4bfc-ba45-ead8f0703881.png">

<img width="491" alt="Solving Step 3" src="https://user-images.githubusercontent.com/99832552/210157809-2710e178-b3de-466a-a2ed-543768d489d6.png">

### Partial Solutions
<img width="495" alt="Partial Solution 1" src="https://user-images.githubusercontent.com/99832552/210157810-23674663-aa65-47ca-abbf-88ab81dfae79.png">

<img width="498" alt="Partial Solution 2" src="https://user-images.githubusercontent.com/99832552/210157812-59c3fad9-0303-4941-a7ed-edd1b7de7489.png">

### Final Solution
<img width="497" alt="Final Solution" src="https://user-images.githubusercontent.com/99832552/210157813-260fbff4-b1c7-4328-ad65-8eeca0bbfeed.png">

<img width="476" alt="Completed Board" src="https://user-images.githubusercontent.com/99832552/210157814-c294b91f-e668-4ee6-b5f4-5f404f9fd85d.png">

## Algorithm Explanation

### Core Functions

#### `ReadBoard(int b[][9])`
Reads 81 integers from standard input to populate the 9x9 board.

#### `PrintBoard(int b[][9])`
Displays the board with:
- Grid separators (`|` and `-`)
- 'x' for empty cells (value 0)
- Numbers for filled cells

#### `check_board(int row, int col, int b[][9])`
The heart of the naked single technique:
1. Creates a candidate array [1-9]
2. Eliminates numbers in the same row
3. Eliminates numbers in the same column
4. Eliminates numbers in the same 3x3 box
5. Returns `true` and fills the cell if exactly one candidate remains

#### `SolveBoard(int b[][9])`
Iteratively applies the naked single technique:
- Loops through all cells
- Applies `check_board()` to empty cells
- Continues until no more cells can be filled

### Time Complexity

- **Best Case:** O(n²) where n = 9 (one pass fills all cells)
- **Worst Case:** O(n⁴) for difficult puzzles requiring multiple iterations
- **Space Complexity:** O(1) - uses fixed-size arrays


### Sample Test Cases

**Easy Puzzle:**
```
5 3 0 0 7 0 0 0 0
6 0 0 1 9 5 0 0 0
0 9 8 0 0 0 0 6 0
8 0 0 0 6 0 0 0 3
4 0 0 8 0 3 0 0 1
7 0 0 0 2 0 0 0 6
0 6 0 0 0 0 2 8 0
0 0 0 4 1 9 0 0 5
0 0 0 0 8 0 0 7 9
```

## Author

**Muhammad Asad Naveed**  

