# EX 3C Sudoku Solver
## DATE: 29-04-2025
## AIM:
To write a python program to find the solution of sudoku puzzle using Backtracking.


## Algorithm
1. Start with a 9×9 Sudoku board where empty cells are marked with 0.
2. Find the next empty cell (i.e., value 0) on the board.
3. For numbers from 1 to 9:.
4. Check if the number is safe:.
5. Check if placing the number doesn't lead to a solution:.
6. Check if all cells are filled and constraints are satisfied:
7. End the program when all possibilities are exhausted.

## Program:
```
/*
Program to implement to to find the solution of sudoku puzzle using Backtracking.
Developed by: Vishinu H
Register Number: 212223220124
*/

board = [
    [0, 0, 0, 8, 0, 0, 4, 0, 3],
    [2, 0, 0, 0, 0, 4, 8, 9, 0],
    [0, 9, 0, 0, 0, 0, 0, 0, 2],
    [0, 0, 0, 0, 2, 9, 0, 1, 0],
    [0, 0, 0, 0, 0, 0, 0, 0, 0],
    [0, 7, 0, 6, 5, 0, 0, 0, 0],
    [9, 0, 0, 0, 0, 0, 0, 8, 0],
    [0, 6, 2, 7, 0, 0, 0, 0, 1],
    [4, 0, 3, 0, 0, 6, 0, 0, 0]
]

def printBoard(board):
    for i in range(0, 9):
        for j in range(0, 9):
            print(board[i][j], end=" ")
        print()

def isPossible(board, row, col, val):
    for j in range(0, 9):
        if board[row][j] == val:
            return False

    for i in range(0, 9):
        if board[i][col] == val:
            return False

    startRow = (row // 3) * 3
    startCol = (col // 3) * 3
    for i in range(0, 3):
        for j in range(0, 3):
            if board[startRow+i][startCol+j] == val:
                return False
    return True

def solve():
    for i in range(0,9):
        for j in range(0,9):
            if board[i][j]==0:
                for val in range(0,10):
                    if isPossible(board,i,j,val)==True:
                        board[i][j]=val
                        solve()
                        board[i][j]=0
                return 
    printBoard(board)
solve()
```

## Output:
![image](https://github.com/user-attachments/assets/13dced1e-e400-413a-97d5-73786fbfa324)


## Result:
The Sudoku solver program executed successfully and found the solution for the given puzzle.
