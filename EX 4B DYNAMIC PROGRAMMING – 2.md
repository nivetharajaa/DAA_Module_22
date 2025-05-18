# EX 4B DYNAMIC PROGRAMMING – 2
## DATE:
## AIM:
To find the longest string (or strings) that is a substring (or are substrings) of two strings..

## Algorithm
1.  Initialize a 2D array lookup of size (m+1) x (n+1) with zeros.

2.  Set maxLength = 0 and endingIndex = m.

3.  Traverse both strings using nested loops.

4.  If characters match, update lookup[i][j] = lookup[i-1][j-1] + 1.

5.  If the updated value is greater than maxLength, update maxLength and endingIndex.

6.  After processing, extract substring from X[endingIndex - maxLength : endingIndex].

7.   Return the extracted substring.   

## Program:
```
Program to implement the longest common substring problem.

Developed by:Nivetha A 
Register Number: 212222230101 

```
```
def LCS(X, Y, m, n):
    maxLength = 0          
    endingIndex = m        
    lookup = [[0 for x in range(n + 1)] for y in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if X[i - 1] == Y[j - 1]:
                lookup[i][j] = lookup[i - 1][j - 1] + 1
                if lookup[i][j] > maxLength:
                    maxLength = lookup[i][j]
                    endingIndex = i
    return X[endingIndex - maxLength: endingIndex]
if __name__ == '__main__':
    X = input()
    Y = input()
    m = len(X)
    n = len(Y)
    print('The longest common substring is', LCS(X, Y, m, n))
```
## Output:
![439502406-7db63937-836c-4810-9833-0cab1825d3c5](https://github.com/user-attachments/assets/c8e43f16-3b23-427a-8cb5-d1bb36eb0dc5)

## Result:
Thus the program was executed successfully for finding the longest common substring .
