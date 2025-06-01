# EX 3A Knight Tour & Count Path
## DATE: 04-05-2025
## AIM:
To write a python program to find minimum steps to reach to specific cell in minimum moves by knight


## Algorithm
1. Start the program. Input the size of the chessboard N, the starting position of the knight knightpos, and the target position targetpos.
2. Define a class cell to represent a square on the board with attributes.
3. Create a function isInside(x, y, N):.
4. Define the 8 possible moves of a knight using arrays dx[] and dy[].
5. Initialize a queue (using deque) for BFS and a visited 2D list to mark visited cells.
6. While the queue is not empty:
7. If no path exists, return -1.  
8. End the program.

## Program:
```
/*
Program to implement to find minimum steps to reach to specific cell in minimum moves by knight.
Developed by: Vishinu H
Register Number: 212223220124
*/

from collections import deque
class cell:
     
    def __init__(self, x = 0, y = 0, dist = 0):
        self.x = x
        self.y = y
        self.dist = dist

def isInside(x, y, N):
    if (x >= 1 and x <= N and
        y >= 1 and y <= N):
        return True
    return False
def minStepToReachTarget(knightpos,targetpos, N):
     
    # add your code here
    dx = [2,2,-2,-2,1,1,-1,-1]
    dy = [1,-1,1,-1,2,-2,2,-2]
    
    queue = deque()
    queue.append(cell(knightpos[0],knightpos[1],0))
    
    visited = [[False for i in range(N+1)]for i in range(N+1)]
    visited[knightpos[0]][knightpos[1]]=True
    
    while queue:
        t = queue.popleft()
        
        if t.x == targetpos[0] and t.y == targetpos[1]:
            return t.dist
        
        for i in range(8):
            x = t.x + dx[i]
            y = t.y + dy[i]
            
            if isInside(x,y,N) and not visited[x][y]:
                visited[x][y]=True
                queue.append(cell(x,y,t.dist+1))
    return -1
if __name__=='__main__':
    N = 30
    knightpos = [1, 1]
    targetpos = [30, 30]
    print(minStepToReachTarget(knightpos,
                             targetpos, N))
```

## Output:
![image](https://github.com/user-attachments/assets/97734ea2-7af7-4d74-baa0-2a32443fe840)



## Result:
The program executed successfully, and the minimum number of steps for the knight to reach the target was calculated.
