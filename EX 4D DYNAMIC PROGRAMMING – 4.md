# EX 4D DYNAMIC PROGRAMMING – 4
## DATE:
## AIM:
To find the minimum number of operations to convert str1 to str2 using Naive recursive method.

## Algorithm
1.  If the first string s is empty, return the length of t.

2.  If the second string t is empty, return the length of s.

3.  If the last characters of s and t are equal, set cost = 0; otherwise, set cost = 1.

4.  Recursively compute:
    a. Deletion: LD(s[:-1], t) + 1

    b. Insertion: LD(s, t[:-1]) + 1

    c. Substitution: LD(s[:-1], t[:-1]) + cost

  5.  Return the minimum of the three values.   

## Program:
```
Program to implement to find the minimum number of operations to convert str1 to str2 using Naive recursive method.
Developed by:Nivetha A 
Register Number:212222230101  

```
```

def LD(s, t):
    if s == "":
        return len(t)
    if t == "":
        return len(s)
    if s[-1] == t[-1]:
        cost = 0
    else:
        cost = 1
    res = min([LD(s[:-1], t)+1, LD(s, t[:-1])+1, LD(s[:-1], t[:-1]) + cost])
    return res
    
str1=input()
str2=input()
print('Edit Distance',LD(str1,str2))
```
## Output:

![439503635-6edbc8e9-0dc9-4bd4-b153-0e61916433d3](https://github.com/user-attachments/assets/6d9efb2a-2aa5-40f8-9ccf-73f5288fd469)

## Result:
Thus the program was executed successfully for finding edit distance between two strings.
