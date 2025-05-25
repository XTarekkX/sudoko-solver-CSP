# Sudoku Solver Using CSP (Constraint Satisfaction Problem)

## 1. Game Description
Sudoku is a logic-based number-placement puzzle played on a **9x9 grid**. The objective is to fill the grid with digits from **1 to 9** so that:

- Each **row** contains all digits from 1 to 9 without repetition.
- Each **column** contains all digits from 1 to 9 without repetition.
- Each of the nine **3x3 subgrids** (regions or boxes) contains all digits from 1 to 9 without repetition.

---

## 2. Requirements

### 2.1 Game GUI
- **Mode 1:** A fully interactive game GUI that **shows the AI agent solving the Sudoku puzzle automatically**.
- **Mode 2:** A GUI that allows the user to **input a Sudoku board**, then the AI agent solves it visually.

### 2.2 Algorithms
- Implement **Backtracking** for:
  - Validating the input puzzle (checking solvability).
  - Generating random puzzles by filling random cells while ensuring the puzzle is solvable.
  
### 2.3 Arc Consistency for Solution
- **Sudoku as a CSP:**
  - **Variables:** Each cell in the 9x9 grid.
  - **Domains:** Possible values for each cell (1 to 9).
  - **Constraints:** No repeating number in any row, column, or 3x3 box.

- **Arcs Definition:**
  - Each arc represents a binary constraint between two connected variables.
  - Arcs are created between all pairs of cells in each row, each column, and each 3x3 subgrid.

- **Initial Domain Reduction:**
  - For pre-filled cells: domain is reduced to the given value only.
  - For empty cells: domain is initially [1, 2, 3, 4, 5, 6, 7, 8, 9].

- **Arc Consistency Algorithm (AC-3):**
  - Iteratively enforce arc consistency on all arcs.
  - Revise domains by removing values inconsistent with neighbors.
  - Repeat until no more reductions possible.

- **Grid Update:**
  - Cells with singleton domains (only one possible value) are assigned that value.
  - Continue enforcing arc consistency and updating until the board is solved or no further progress.

---

## Project Structure
- `GUI/` — Source code for the graphical user interface.
- `main_no_print.py` — Core logic without print statements for clean execution.
- `main_print.py` — Core logic with print statements for debugging/visualization.
- `Sudoku_report.docx` — Detailed report and documentation.
- `README.md` — This file.

---

## Notes
- The solver combines **backtracking** with **arc consistency** to efficiently prune the search space.
- The GUI provides a clear visualization of the solving process, enhancing understanding.
- The project demonstrates CSP techniques applied to a classical logic puzzle.
- This is a robust base that can be extended with heuristic improvements or advanced solving strategies.

---

Feel free to explore and modify the code for more features or improvements!
