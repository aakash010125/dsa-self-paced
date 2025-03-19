# 2.1 : Analysis of Algorithms (Background)

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY3Mw%3D%3D

**Example Problem :** Sum of first N natural numbers. <br>

Input : 3 <br> 
Output : 6 <br>

Input : 5 <br>
Output : 15 <br>

```
// Solution 1: Time Taken: C1

int sumOfFirstNNaturalNumbers1(int N) {
    return N*(N+1)/2;
}

// Solution 2: Time Taken: C2(N) + C3

int sumOfFirstNNaturalNumbers2(int N) {
    int totalSum = 0;
    for (int i=1; i<=N; i++) {
        totalSum += i;
    }
    return totalSum;
}

// Solution 3: Time Taken: C4(N^2) + C5(N) + C6

int sumOfFirstNNaturalNumbers3(int N) {
    int totalSum = 0;
    for (int i=1; i<=N; i++) {
        for (int j=1; j<=i; j++) {
            totalSum++;
        }
    }
    return totalSum;
}
```

# 2.2 : Asymptotic Analysis

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/NjY3MA%3D%3D

1. The idea is to measure order of growth of function in terms of input size.
2. Doesn't depend upon the machine, programming language, testcases, etc.
3. No need to implement, we can analyze algorithms.

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/30197459-7d7a-4982-bd05-3b3d50625fbd" />

# 2.3 : Order of Growth

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY3Ng%3D%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/e2ac419d-8c8b-4ee3-8745-08dfbba283a4" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/e08da53a-0eff-49f5-82b4-d0ecf5f9b8b4" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/5d80eb0b-8a12-4166-b39c-6a4be7a6836d" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/2d5b5bb7-5e90-4a48-a34a-df89520d8a31" />

# 2.4 : Best, Average and Worst cases

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY3OA%3D%3D

**Example 1:** Simple function with same Order of Growth for every Input

```
// Time Taken: C1(n) + C2
// Order of Growth: n (or Linear)

#include <iostream>

int getSum(int arr[], int n) {
    int totalSum = 0;
    for (int i=0; i<n; i++) {
        totalSum += arr[i];
    }
    return totalSum;
}

int main() {
    int arr[] = {1, 2, 3, 4, 5};
    std::cout << getSum(arr, 5);
    return 0;
}
```

**Example 2:** Multiple Orders of Growths

1. **Best Case :** Constant
2. **Average Case :** Linear (under the assumption that odd and even cases are equally likely)
3. **Worst Case :** Linear

```
#include <iostream>

int getSum(int arr[], int n) {
    if (n % 2 == 0) {
        return 0;
    }
    int totalSum = 0;
    for (int i=0; i<n; i++) {
        totalSum += arr[i];
    }
    return totalSum;
}

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6};
    std::cout << getSum(arr, 6);
    return 0;
}
```

# 2.5 : Asymptotic Notation

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY3Nw%3D%3D

```
Big O : Exact or Upper Bound
Theta : Exact
Omega : Exact or Lower Bound
```

```
// Time Complexity: O(n)

#include <iostream>

int linearSearch(int arr[], int n, int target) {
    for (int i=0; i<n; i++) {
        if (arr[i] == target) {
            return i;
        }
    }
    return -1;
}

int main() {
    int arr[] = {1, 2, 3, 4, 5, 6};
    std::cout << linearSearch(arr, 6, 5);
    return 0;
}
```

# 2.6 : Big O Notation

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY4MQ%3D%3D

**Direct way to Find Big O of any expression :**

1. Ignore lower order terms.
2. Ignore leading terms constant.

```
3N^2 + 5N + 6 --> O(N^2)

3N + 10NlogN + 3 --> O(NlogN)

10N^3 + 40N + 10 --> O(N^3)
```

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/111b3679-ee3a-49b7-97d9-74a5d7b4131c" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/15b385e3-d46c-4f55-844d-20f154f9102e" />

## Applications

Used when we have an upper bound.

```
// Time Complexity: O(sqrt(n))

#include <iostream>

bool isPrime(int n) {
    if (n == 1) return false;
    if (n == 2 || n == 3) return true;
    if (n % 2 == 0 || n % 3 == 0) return false;
    for (int i=5; i*i<=n; i+=6) {
        if (n % i == 0 || n % (i+2) == 0) {
            return false;
        }
    }
    return true;
}

int main() {
    int n1 = 45, n2 = 100, n3 = 17;
    std::cout << isPrime(n1) << " " << isPrime(n2) << " " << isPrime(n3);
    return 0;
}
```

# 2.7 : Omega Notation

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY4NQ%3D%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/ea9cac6c-d384-4f27-adbc-00dc5f6e0186" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/af454c69-4106-4666-8ae0-2ed29c7c7515" />

# 2.8 : Theta Notation

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MTU0MjU%3D

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/f819dc77-d5d6-438c-bb07-0dd7388bcb9b" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/5af002bb-a6e9-48b9-ade0-d8c56ca62e1f" />

<img width="900" alt="Image" src="https://github.com/user-attachments/assets/3f2fc4b5-257d-4da4-918a-ab4c8263e23b" />

# 2.9 : Analysis of Common loops

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MTY1MDg%3D

**Example 1:** n - User Input, c - Constant

```
for (int i=0; i<n; i+=c) {
    // some theta(1) work
}

// Loop runs ceil(n/c) times
// Time Complexity: theta(n)
```

**Example 2:** n - User Input, c - Constant

```
for (int i=n; i>0; i-=c) {
    // some theta(1) work
}

// Loop runs ceil(n/c) times
// Time Complexity: theta(n)
```

**Example 3:** n - User Input, c - Constant

```
for (int i=1; i<n; i*=c) {
    // some theta(1) work
}

// Loop runs ceil(logn with base c) times
// Time Complexity: theta(logn with base c)
```

<img width="325" alt="Image" src="https://github.com/user-attachments/assets/51a02fdc-10a4-4938-95ca-71595462da1b" />

**Example 4:** n - User Input, c - Constant

```
for (int i=n; i>1; i/=c) {
    // some theta(1) work
}

// Loop runs floor(logn with base c) times
// Time Complexity: theta(logn with base c)
```

<img width="325" alt="Image" src="https://github.com/user-attachments/assets/ba70bcfd-7e5d-477c-b5ac-f6c09ca99203" />

**Example 5:** n - User Input, c - Constant

```
for (int i=2; i<n; i=pow(i, c)) {
    // some theta(1) work
}

// Time Complexity: theta(loglogn)
```

<img width="325" alt="Image" src="https://github.com/user-attachments/assets/6600b733-a680-42c2-8254-bfe3828f6bcd" />

# 2.10 : Analysis of multiple loops

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjY4MA%3D%3D

**Example 1:** Subsequent Loops

```
void function(int n) {
    // TC1: theta(n)
    for (int i=0; i<n; i++) {
        Some theta(1) Constant Work
    }
    // TC2: theta(logn)
    for (int i=1; i<n; i=i*2) {
        Some theta(1) Constant Work
    }
    // TC3: theta(1)
    for (int i=1; i<100; i++) {
        Some theta(1) Constant Work
    }
}

Total Time Complexity = TC1 + TC2 + TC3 = theta(n) + theta(logn) + theta(1) = theta(n)
```

**Example 2:** Nested Loops

```
void function(int n) {
    // Outer Loop (TC1): theta(n)
    for (int i=0; i<n; i++) {
        // Inner Loop (TC2): theta(logn)
        for (int j=1; j<n; j=j*2) {
            // Some theta(1) Constant Work
        }
    }
}

Total Time Complexity = TC1 * TC2 = theta(n) * theta(logn) = theta(nlogn)
```

**Example 3:** Mixed Loops

```
void function(int n) {
    // TC1: theta(nlogn)
    for (int i=0; i<n; i++) {
        for (int j=1; j<n; j=j*2) {
            // Some theta(1) Constant Work
        }
    }
    // TC1: theta(n^2)
    for (int i=0; i<n; i++) {
        for (int j=1; j<n; j++) {
            // Some theta(1) Constant Work
        }
    }
}

Total Time Complexity = TC1 + TC2 = theta(nlogn) + theta(n^2) = theta(n^2)
```

**Example 4:** Mixed Loops with different Inputs

```
void function(int n) {
    // TC1: theta(nlogn)
    for (int i=0; i<n; i++) {
        for (int j=1; j<n; j=j*2) {
            // Some theta(1) Constant Work
        }
    }
    // TC1: theta(m^2)
    for (int i=0; i<m; i++) {
        for (int j=1; j<m; j++) {
            // Some theta(1) Constant Work
        }
    }
}

Total Time Complexity = TC1 + TC2 = theta(nlogn) + theta(m^2) = theta(nlogn + m^2)
```

# 2.10 : Analysis of Recursion (Introduction)

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Intro/video/MjYyNQ%3D%3D

**Example 1:** 

```
void function(int n) {
    if (n <= 0) return;
    print("GFG");
    function(n/2);
    function(n/2);
}

// Recurrence Relation:

For n > 0:
T(n) = T(n/2) + T(n/2) + theta(1)
T(n) = 2T(n/2) + theta(1)

For n <= 0 (i.e., base condition):
T(0) = theta(1)
```

**Example 2:**

```
void function(int n) {
    if (n <= 0) return;
    for (int i=0; i<n; i++) {
        print("GFG");
    }
    function(n/2);
    function(n/3);
}

// Recurrence Relation:

For n > 0:
T(n) = theta(n) + T(n/2) + T(n/3) + theta(1)

For n <= 0 (i.e., base condition):
T(0) = theta(1) when n = 0
```

**Example 3:**

```
void function(int n) {
    if (n <= 1) return;
    print("GFG");
    function(n-1);
}

// Recurrence Relation:

For n > 1:
T(n) = T(n-1) + theta(1)

For n <= 1 (i.e., base condition):
T(1) = theta(1) when n = 1
```

