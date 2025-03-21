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

1. Solution:

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

2. Solution:

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

# 3.3 : Factorial of a Number

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg1Mg%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAwMA%3D%3D

```
Problem Statement: 

We are given a number. The task is to find the factorial of the number.
The factorial (n!) of a number is the product of all the integers from 1 to that number, i.e, n! = 1*2*3*.....(n-1)*n

I/P: 4
O/P: 24

I/P: 6
O/P: 720

I/P: 0
O/P: 1

1. Iterative Solution:

int factorial(int n) {
    int result = 1;
    for (int i=2; i<=n; i++) {
        result *= i;
    }
    return result;
}

// Time Complexity : O(n)
// Auxiliary space : O(1) or constant

2. Recursive Solution:

int factorial(int n) {
    if (n == 0) return 1;
    return n * factorial(n-1);
}

// Time Complexity : O(n)
// Auxiliary space : O(n)
```

# 3.4 : Trailing Zeros in Factorial

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg0MQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAwMQ%3D%3D

```
Problem Statement: 

We are given a number. The task is to find the Number of Trailing Zeros in the factorial of the number.
The Trailing Zeros are the Zeros, which appear at the end of a number(factorial in that case)

I/P: 5
O/P: 1

I/P: 10
O/P: 2

I/P: 100
O/P: 24

1. Naive Method:
// Overflow issue with this solution

int countZeros(int n) {
    int factorial = 1, count = 0;
    for (int i=2; i<=n; i++) {
        factorial *= i;
    }
    
    while ((factorial % 10) == 0) {
        count++;
        factorial /= 10;
    }
    return count;
}

// Time Complexity: O(n)
// Auxiliary Space: O(1) or constant

2. Efficient Solution:
// Trailing zero count = floor(n/5) + floor(n/25) + floor(n/125) + ....

int countTrailingZeros(int n) {
    int count = 0;
    for (int i=5; i<=n; i*=5) {
        count += floor(n/i);
    }
    return count;
}

// Time Complexity: O(log(n))
// Auxiliary Space: O(1) or constant
```

# 3.5 : GCD or HCF of two Numbers

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTgzOQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAwMg%3D%3D

```
Problem Statement: 

We are given two numbers. The task is to find the GCD / HCF of the numbers.
GCD: Greatest Common Divisor
HCF: Highest Common Factor

I/P: a = 4, b = 2
O/P: 2

I/P: a = 100, b = 200
O/P: 100

I/P: a = 7, b = 3
O/P: 1

1. Naive Method:

int gcd(int a, int b) {
    int result = min(a,b);
    while (result > 0) {
        if ((a % result == 0) and (b % result == 0)) {
            break;
        }
        result--;
    }
    return result;
}

// Time Complexity: O(min(a,b))
// Auxiliary Space: O(1) or constant

2. Euclidean Approach:
// The idea of this algorithm is, the GCD of two numbers doesn’t change if the smaller number is subtracted from the bigger number. 
// This is the Euclidean algorithm by subtraction. It is a process of repeat subtraction, carrying the result forward each time until the result is equal to any one number being subtracted.

int gcd(int a, int b) {
    while (a != b) {
        if (a > b) {
            a = a - b;
        } else {
            a = b - a;
        }
    }
    return a;
}

// Time Complexity: O(min(a,b))
// Auxiliary Space: O(1) or constant

3. Optimised Euclidean Approach:
// In this approach, instead of repeatedly subtracting the numbers till both become equal, we can check if one number is a factor of the other.

int gcd(int a, int b) {
    if (b == 0)
        return a;
    else
        return gcd(b, a % b);
}

// Time Complexity: O(log(min(a,b))
// Auxiliary Space: O(1) or constant
```

# 3.6 : LCM of Two Numbers

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg0Nw%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAwMw%3D%3D

```
Problem Statement: 

We are given two numbers. The task is to find the LCM of the numbers.
LCM: Least Common Multiple

I/P: a = 4, b = 6
O/P: 12

I/P: a = 12, b = 15
O/P: 60

I/P: a = 2, b = 8
O/P: 8

I/P: a = 3, b = 7
O/P: 21

1. Naive Method:

int lcm(int a, int b) {
    int result = max(a,b);
    while (true) {
        if ((result % a == 0) and (result % b == 0)) {
            return result;
        }
        result++;
    }
    return result;
}

// Time Complexity: O(a*b - max(a,b))
// Auxiliary Space: O(1)

2. Efficient Approach:
// An efficient solution is based on the below formula for LCM of two numbers ‘a’ and ‘b’. 
// a x b = LCM(a, b) * GCD (a, b)
// LCM(a, b) = (a x b) / GCD(a, b)

int gcd(int a, int b) {
    if (b == 0)
        return a;
    else
        return gcd(b, a % b);
}

int lcm(int a, int b) {
    return (a * b) / gcd(a, b);
}

// Time Complexity: O(log(min(a,b))
// Auxiliary Space: O(1)
```

# 3.7 : Check for Prime

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg0NQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAyMw%3D%3D

```
Problem Statement: 

We are given a number. The task is to check if the number is prime or not.
Prime Number: A prime is a natural number greater than 1 that has no positive divisors other than 1 and itself.

I/P: 13
O/P: Yes

I/P: 14
O/P: No

I/P: 101
O/P: Yes

1. Naive Method: 
// Iterate from 2 to  (n-1) and check if any number in this range divides n. If the number divides n, then it is not a prime number.

bool isPrime(int n) {
    if (n == 1) return false;
    for (int i=2; i<n; i++) {
        if (n % i == 0) {
            return false;
        }
    }
    return true;
}

// Time Complexity: O(n)
// Auxiliary Space: O(1)

2. Efficient Approach: 
// Iterate through all numbers from 2 to square root of n and for every number check if it divides n [because if a number is expressed as n = xy and 
// any of the x or y is greater than the root of n, the other must be less than the root value]. If we find any number that divides, we return false.

bool isPrime(int n) {
    if (n == 1) return false;
    for (int i=2; i*i<=n; i++) {
        if (n % i == 0) {
            return false;
        }
    }
    return true;
}

// Time Complexity: O(sqrt(n))
// Auxiliary Space: O(1)

3. More Efficient Approach: [for large value of n]

bool isPrime(int n) {
    if (n == 1) return false;
    if (n == 2 || n == 3) return true;
    if ((n % 2 == 0) || (n % 3 == 0)) return false;
    for (int i=5; i*i<=n; i+=6) {
        if ((n % i == 0) and (n % (i+2) == 0)) {
            return false;
        }
    }
    return true;
}

// Time Complexity: O(sqrt(n)) - approx 3 times faster than Approach 2
// Auxiliary Space: O(1)
```

