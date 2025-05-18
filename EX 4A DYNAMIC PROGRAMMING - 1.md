# EX 4A DYNAMIC PROGRAMMING - 1
## DATE:
## AIM:
To find longest common subsequence using Dynamic Programming.

## Algorithm
1. Initialize a 2D array dp of size (len(s1)+1) x (len(s2)+1) with zeros.

2. Iterate through each character of s1 and s2.

3. If characters match, set dp[i][j] = dp[i-1][j-1] + 1.

4. If characters do not match, set dp[i][j] = max(dp[i-1][j], dp[i][j-1]).

5.  After filling the table, start from dp[m][n] and trace back to build the LCS.

6.  Move diagonally if characters match, otherwise move in the direction of the larger value.

7.  Reverse the collected characters to get the LCS string.

8.   Return the LCS.
 
 

## Program:
```

Program to implement the longest common subsequence using Dynamic Programming
Developed by: Nivetha A
Register Number:212222230101 
```
```

def longest_common_subsequence(s1, s2):
    m, n = len(s1), len(s2)
    dp = [[0] * (n + 1) for _ in range(m + 1)]
    for i in range(1, m + 1):
        for j in range(1, n + 1):
            if s1[i - 1] == s2[j - 1]:
                dp[i][j] = dp[i - 1][j - 1] + 1
            else:
                dp[i][j] = max(dp[i - 1][j], dp[i][j - 1])
    i, j = m, n
    lcs = []
    while i > 0 and j > 0:
        if s1[i - 1] == s2[j - 1]:
            lcs.append(s1[i - 1])
            i -= 1
            j -= 1
        elif dp[i - 1][j] > dp[i][j - 1]:
            i -= 1
        else:
            j -= 1
    lcs = ''.join(reversed(lcs))
    return lcs
s1 = input()
s2 = input()
lcs_str = longest_common_subsequence(s1, s2)
print(lcs_str)
```
## Output:
![439501472-7b23089e-7a17-42bd-9318-62c0224567a6](https://github.com/user-attachments/assets/638c4873-c2e5-4333-b5a7-f9076a05c55f)

## Result:
Thus the program was executed successfully for computing the length of longest common subsequence.
