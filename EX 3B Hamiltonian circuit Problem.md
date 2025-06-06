# EX 3B Hamiltonian Circuit Problem
## DATE: 04-05-2025
## AIM:
To write a python program to check whether Hamiltonian path exits in the given graph.

## Algorithm
1. Start and input the number of vertices V and the adjacency matrix graph[][] of the given undirected graph.
2. Initialize a path array path[] of size V with all elements as -1.
3. Define a recursive function hamCycleUtil(path, pos):.
4. For each vertex v from 1 to V-1:.
5. If no vertex can be added at position pos, return False.
6. In the main function hamCycle(), call hamCycleUtil(path, 1):.

## Program:
```
/*
Program to implement to check whether Hamiltonian path exits in the given graph.
Developed by: Vishinu H
Register Number: 212223220124 
*/

class Graph():
    def __init__(self, vertices):
        self.graph = [[0 for column in range(vertices)]
                            for row in range(vertices)]
        self.V = vertices
    def isSafe(self, v, pos, path):
        if self.graph[ path[pos-1] ][v] == 0:
            return False
        for vertex in path:
            if vertex == v:
                return False
 
        return True
    def hamCycleUtil(self, path, pos):
        if pos == self.V:
            if self.graph[path[pos-1]][path[0]] == 1:
                return True
            else:
                return False
        for v in range(1,self.V):
            if self.isSafe(v,pos,path):
                path[pos]=v
                if self.hamCycleUtil(path,pos+1)==True:
                    return True
                path[pos]=-1
        return False
        
 
    def hamCycle(self):
        path = [-1] * self.V
        path[0] = 0
 
        if self.hamCycleUtil(path,1) == False:
            print ("Solution does not exist\n")
            return False
 
        self.printSolution(path)
        return True
 
    def printSolution(self, path):
        print ("Solution Exists: Following",
                 "is one Hamiltonian Cycle")
        for vertex in path:
            print (vertex, end = " ")
        print (path[0], "\n")
g1 = Graph(5)
g1.graph = [ [0, 1, 0, 1, 0], [1, 0, 1, 1, 1],
            [0, 1, 0, 0, 1,],[1, 1, 0, 0, 1],
            [0, 1, 1, 1, 0], ]
g1.hamCycle();
```

## Output:
![image](https://github.com/user-attachments/assets/e9d725b0-bc88-46de-b301-a23dc040cb47)



## Result:
The Hamiltonian path program executed successfully, and it determined whether a Hamiltonian path exists in the given graph.
