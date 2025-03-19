## 2.1 : Analysis of Algorithms (Background)

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY3Mw%3D%3D

**Example Problem :** Sum of first n natural numbers. <br>
Input : 3 <br> 
Output : 6 <br>

Input : 5 <br>
Output : 15 <br>

```
int sumOfFirstNNaturalNumbers1(int N) {
    return N*(N+1)/2;
}

int sumOfFirstNNaturalNumbers2(int N) {
    int totalSum = 0;
    for (int i=1; i<=N, i++) {
        totalSum += i;
    }
    return totalSum;
}

int sumOfFirstNNaturalNumbers3(int N) {
    int totalSum = 0;
    for (int i=1; i<=N, i++) {
        for (int j=1; j<=i; j++){
            totalSum++;
        }
    }
    return totalSum;
}
```