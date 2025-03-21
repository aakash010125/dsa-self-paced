# 3.1 : Count Digits

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTgzNQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/Njg4OA%3D%3D

```
Problem Statement: 

Given a number N, the task is to return the count of digits in this number (provided x > 0).

I/P: 9235
O/P: 4

I/P: 38
O/P: 2

I/P: 7
O/P: 1

Solution:

int countDigits(int n) {
    int countOfDigits = 0;
    while (n > 0) {
        countOfDigits++;
        n /= 10;
    }
    return countOfDigits;
}

// Time Complexity: O(log10(n)) or θ(d) where d is the no. of digits in n.
// Auxiliary Space: O(1) or constant
```

# 3.2 : Palindrome Numbers

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg1Mw%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/Njg5MA%3D%3D

```
Problem Statement: 

We are given an n-digit number. The task is to find if the number is palindrome or not, provided that, n>=0.
If the Reversed Number is equal to the original number, then the number is said to be a palindrome number, otherwise not.

I/P: 78987
O/P: true

I/P: 8668
O/P: true

I/P: 8
O/P: true

I/P: 21
O/P: false

I/P: 367
O/P: false

Solution:

bool isPalindrome(int n) {
    int reversedNumber = 0, temp = n;
    while (temp > 0) {
        reversedNumber = reversedNumber * 10 + (temp % 10);
        temp /= 10;
    }
    return (n == reversedNumber);
}

// Time Complexity : O(log(n)) or O(Number of digits in a given number)
// Auxiliary space : O(1) or constant
```

