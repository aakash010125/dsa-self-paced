## 2.1 : Analysis of Algorithms (Background)

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY3Mw%3D%3D

**Example Problem :** Sum of first N natural numbers. <br>
Input : 3 <br> 
Output : 6 <br>

Input : 5 <br>
Output : 15 <br>

```
Solution 1: Time Taken: C1

int sumOfFirstNNaturalNumbers1(int N) {
    return N*(N+1)/2;
}

Solution 2: Time Taken: C2(N) + C3

int sumOfFirstNNaturalNumbers2(int N) {
    int totalSum = 0;
    for (int i=1; i<=N; i++) {
        totalSum += i;
    }
    return totalSum;
}

Solution 3: Time Taken: C4(N^2) + C5(N) + C6

int sumOfFirstNNaturalNumbers3(int N) {
    int totalSum = 0;
    for (int i=1; i<=N; i++) {
        for (int j=1; j<=i; j++){
            totalSum++;
        }
    }
    return totalSum;
}
```

## 2.2 : Asymptotic Analysis

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/NjY3MA%3D%3D

1. The idea is to measure order of growth of function in terms of input size.
2. Doesn't depend upon the machine, programming language, testcases, etc.
3. No need to implement, we can analyze algorithms.

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/30197459-7d7a-4982-bd05-3b3d50625fbd" />
