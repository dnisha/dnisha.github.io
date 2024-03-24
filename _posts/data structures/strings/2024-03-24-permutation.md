---
title: "Permutations of given String"
date: 2024-03-24 00:00:00 +0800
categories: [dsa, string]
tags: [dsa, string]
---

[Ref link1](https://www.geeksforgeeks.org/write-a-c-program-to-print-all-permutations-of-a-given-string/)

[Ref link2](https://youtu.be/vKQ6oUH02gw)

## Sudo Code

```
1) Solve using recursion
2) Take index and swap it with each element in the array
```
![alt text](../assets/datastructure/permutation.png)
## Solution
```
def permutat(arr, l, r):

    if l == r:
        print("".join(arr))
        return
    
    for i in range(l,r,1):
        arr[l], arr[i] = arr[i], arr[l]
        permutat(arr, l+1, r)
        arr[l], arr[i] = arr[i], arr[l] 


string = "ABC"
n = len(string) 
a = list(string) 
  
# Function call 
permutat(a, 0, n) 
```
[Leetcode](https://leetcode.com/problems/permutations/)