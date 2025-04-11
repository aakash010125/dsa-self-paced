# 5.1 : Recursion Introduction

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYxNw%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/MTAwODc%3D

### Recursion : A function calls itself directly or indirectly.

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/93eb5ce4-f4fd-4c93-8c04-18d0277d617b" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/ed4a254d-75c0-47e8-9398-f87f56d33992" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/cf23e270-8679-4e75-8928-b86c61024982" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/0478f96b-b299-4b80-97c4-44656a3a26e0" />

# 5.2 : Applications of Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYxNg%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/MTAwODc%3D

1. Many algorithmic techniques are based on recursion like Dynamic Programming (DP), Backtracking and Divide & Conquer (binary search, quick sort & merge sort).
2. Many problems which are inherently recursive like Tower of Hanoi, DFS based traversals (DFS of graph and Other Inorder, preorder & postorder traversals in tree).

# 5.3 : Recursion Output Practice - Part 1

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYyNQ%3D%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/4f0c8239-7b7a-4abb-9e4a-e5164ded1a1a" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/7e704dfb-287f-441e-a12e-fb6838252546" />

# 5.4 : Recursion Output Practice - Part 2

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYzNQ%3D%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/4f1073c4-ad3a-4f4d-bc2f-ba03b0a42d78" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/d8c020a1-d7a1-43ca-89dc-3e78c77d44b4" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/28e72480-0c13-4d19-b84b-92b31d12de73" />

# 5.5 : Print N to 1 Using Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYxOA%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/Njg5Mg%3D%3D

```
Problem Statement: 

Given a number N, the task is to print the numbers from N to 1.

I/P: N = 10 
O/P: 10 9 8 7 6 5 4 3 2 1

I/P: N = 7 
O/P: 7 6 5 4 3 2 1 

1. Recursive Solution:

void printNTo1(int N) {
    if (N <= 0) {
        return;
    }
    std::cout << N << " ";
    printNTo1(N-1);
}

// Time Complexity: O(N)
// Auxiliary Space: O(N)
```

# 5.6 : Print 1 to N Using Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYxOQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/Njg5Mw%3D%3D

```
Problem Statement: 

Given a number N, the task is to print the numbers from 1 to N.

I/P: N = 10 
O/P: 1 2 3 4 5 6 7 8 9 10

I/P: N = 7 
O/P: 1 2 3 4 5 6 7

1. Recursive Solution:

void print1ToN(int N) {
    if (N <= 0) {
        return;
    }
    print1ToN(N-1);
    std::cout << N << " ";
}

// Time Complexity: O(N)
// Auxiliary Space: O(N)
```

# 5.7 : Tail Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYyNA%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/NzUwNg%3D%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/9b8542cb-38ce-4cde-bb2d-a144dad60dcb" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/8a1b8a44-f452-4bd8-8582-806c4ed93f78" />

# 5.8 : Writing Base Cases in Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTM2OA%3D%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/98139258-4137-405b-96da-b1ee63ccdcc5" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/aac8113f-a4e8-4240-8cdf-13097d375424" />

# 5.9 : Natural Number Sum using Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYyNg%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/NzUwNw%3D%3D

```
Problem Statement: 

Given a number n, find sum of first n natural numbers.

I/P: 3
O/P: 6
Explanation : 1 + 2 + 3 = 6

I/P: 5
O/P: 15
Explanation : 1 + 2 + 3 + 4 + 5 = 15

1. Recursive Solution:

int sumOfNaturalNumbers(int n) {
    // base condition
    if (n == 1) return 1;
    return n + sumOfNaturalNumbers(n-1);
}

// Time Complexity: O(N)
// Auxiliary Space: O(N)
```

# 5.10 : Palindrome Check using Recursion

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/video/MTYyOQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Recursion/article/NzUwOA%3D%3D

```
Problem Statement: 

Given a string, write a recursive function that checks if the given string is a palindrome or not.

I/P: malayalam
O/P: Yes
Reverse of malayalam is also malayalam.

I/P: max
O/P: No
Reverse of max is not max. 

1. Recursive Solution:

#include<bits/stdc++.h>
using namespace std;

bool isPalindrome(string s, int start, int end) {
    // base condition
    if (start >= end) {
        return true;
    }
    return (s[start] == s[end]) && isPalindrome (s, start+1, end-1);
}

int main() {
    std::cout << isPalindrome("abba", 0, 3) << std::endl;
    std::cout << isPalindrome("geeks", 0, 4);
    return 0;
}

// Time Complexity: O(N)
// Auxiliary Space: O(N)
```

