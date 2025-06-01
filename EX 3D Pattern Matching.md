# EX 3D Pattern Matching
## DATE: 04-05-2025
## AIM:
To write a python program to implement pattern matching on the given string using Brute Force algorithm.

## Algorithm
1. start with two strings s1 and s2.
2. Set index i = 0 to start matching from the beginning of the Text.
3. While i ≤ n - m and While j < m and Text[i + j] == Pattern[j]: ,if match return pattern else no match is found after the loop ends, return -1
4. End the program.

## Program:
```
/*
Program to implement the Pattern Matching.
Developed by: Vishinu H 
Register Number: 212223220124 
*/

def BF(s1,s2):
    i = j = 0
    while i<len(s1) and j < len(s2):
        if s1[i]==s2[j]:
            i+=1
            j+=1
        else:
            i = i - j + 1
            j = 0
    if j>=len(s2):
        return i - j
    else:
        retirn -1
if __name__ == "__main__":
    a1=input() 
    a2=input() 
    b=BF(a1,a2)
    print(b)

```

## Output:
![image](https://github.com/user-attachments/assets/1184be29-5563-41d6-a420-4565bf88c8cc)



## Result:
The brute force substring search program executed successfully and returned the starting index of the match or 0 if no match was found.
