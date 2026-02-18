## Title:

Cryptarithmetic Puzzle Solver using Backtracking and CSP Heuristics

## Executive Summary:

This project implements a Constraint Satisfaction Problem (CSP) solver to automatically solve cryptarithmetic puzzles such as SEND + MORE = MONEY.

In these puzzles, each letter represents a unique digit from 0–9, and the goal is to find a substitution that makes the arithmetic equation correct while ensuring no digit repeats and no number begins with zero.

The program applies a backtracking search algorithm enhanced with Minimum Remaining Values (MRV) and Degree heuristics to efficiently search the solution space. It reads letter equations from an input file and generates the corresponding numeric solution in an output file.

## Methodology:
### 1) Problem Representation
Each unique letter is treated as a variable.
- Domain: digits 0–9
- Constraint: each letter maps to a different digit
- Constraint: leading letters cannot be zero
- Constraint: column-wise addition must be correct
For example, a puzzle like SEND + MORE = MONEY is converted into a set of mathematical constraints between digits.

### 2) Constraint Satisfaction Model
The puzzle is modeled using:
- Variables → letters
- Domains → possible digits
- Constraints → arithmetic addition rules
Carry values between columns are treated as additional variables so the arithmetic validity is preserved.

### 3) Search Algorithm — Backtracking
The solver uses recursive backtracking:
- Choose an unassigned letter
- Assign a digit
- Check if constraints are satisfied
- Continue or backtrack if invalid
This ensures all possible assignments are explored, but invalid paths are discarded early.

### 4) Heuristics for Optimization
**Minimum Remaining Values (MRV):**
Chooses the letter with the fewest remaining valid digits first to reduce branching.

**Degree Heuristic:**
Prioritizes letters involved in the most constraints so conflicts are detected earlier.

**Domain Ordering:**
Digits are assigned in increasing numeric order.

### 5) Input / Output Handling
The input file contains three lines of uppercase letters representing the equation.
The output file contains the numeric substitution that satisfies the equation.

## Skills:
- **Artificial Intelligence:** Constraint Satisfaction Problems (CSP), Backtracking search, Heuristic optimization
- **Algorithms:** MRV heuristic, Degree heuristic, Recursive search, Constraint pruning
- **Programming:** Python, File parsing, Recursive algorithms, Mathematical modeling
- **Computer Science Concepts:** State space search, Combinatorial optimization, Constraint solving

## Results:
The solver successfully finds digit substitutions that satisfy cryptarithmetic equations.
It efficiently reduces search time using heuristics compared to brute force methods and correctly handles carry operations and multiple variables.
