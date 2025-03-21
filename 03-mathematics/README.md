# 3.1 : Count Digits

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTgzNQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/Njg4OA%3D%3D

**Problem Statement :** Given a number N, the task is to return the count of digits in this number (provided x > 0).

I/P: 9235 <br>
O/P: 4

I/P: 38 <br>
O/P: 2

I/P: 7 <br>
O/P: 1

```
int countDigits(int n) {
    int countOfDigits = 0;
    while (n > 0) {
        n /= 10;
        countOfDigits++;
    }
    return countOfDigits;
}

// Time Complexity :  theta(d) where d is the no. of digits in number n.
// Space Complexity:  theta(1)
```

