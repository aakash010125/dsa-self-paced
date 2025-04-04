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

# 3.8 : Prime Factors

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg0OQ%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAyNA%3D%3D

```
Problem Statement: 

We are given a number n. The task is to print all prime factors of n (provided n > 1).
Prime Factors: They are prime numbers, which are factors of a given number.

I/P: 12
O/P: 2 2 3

I/P: 13
O/P: 13

I/P: 315
O/P: 3 3 5 7

1. Naive Method: 
// Iterate from 2 to  (n-1) and check if the number is prime. If the number is prime, 
// then divide the given number by this number, till it remains completely divisible.

#include <iostream>

// TC: sqrt(n)
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

void primeFactors(int n) {
    for (int i=2; i<n; i++) {
        if(isPrime(i)) {
            int num = i;
            while (n % num == 0) {
                std::cout << i << " ";
                num *= i;
            }
        }
    }
}

int main() {
    int n = 315;
    primeFactors(n);
    return 0;
}

// Time Complexity: O(n * sqrt(n) * log(n))
// Auxiliary Space: O(1)

2. Efficient Approach: 
// Iterate through all numbers from 2 to square root of n and for every number check 
// if it divides n [because if a number is expressed as n = xy and any of the x or y 
// is greater than the root of n, the other must be less than the root value]. 
// Repetitively divide n by the number till it remains completely divisible, and print the values.

void primeFactors(int n) {
    if(n <= 1) return;
    for (int i=2; i*i<=n; i++) {
        while(n % i == 0) {
            std::cout << i << " ";
            n /= i;
        }
    }
    if (n > 1) std::cout << n;
}

// Time Complexity: O(sqrt(n))
// Auxiliary Space: O(1)

3. More Efficient Approach: [for large value of n]

void primeFactors(int n) {
    if(n <= 1) return;
    while (n % 2 == 0) {
        std::cout << 2 << " ";
        n /= 2;
    }
    while (n % 3 == 0) {
        std::cout << 3 << " ";
        n /= 3;
    }
    for (int i=5; i*i<=n; i+=6) {
        while(n % i == 0) {
            std::cout << i << " ";
            n /= i;
        }
        while(n % (i+2) == 0) {
            std::cout << (i+2) << " ";
            n /= (i+2);
        }
    }
    if (n>3) std::cout << n;
}

// Time Complexity: O(sqrt(n)) - approx 3 times faster than Approach 2
// Auxiliary Space: O(1)
```

# 3.9 : All Divisors of a Number

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTkwMg%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAyNQ%3D%3D

```
Problem Statement: 

We are given a number n. The task is to print all the divisors of n. 
Divisor: A divisor is a number that completely divides a number.

I/P: 15
O/P: 1 3 5 15

I/P: 100
O/P: 1 2 4 5 10 20 25 50 100

I/P: 7
O/P: 1 7

1. Naive Method: 
// A Naive Solution would be to iterate all the numbers from 1 to n, checking if that number divides n and printing it. 

void printDivisors(int n) {
    for (int i=1; i<=n; i++) {
        if (n % i == 0) {
            std::cout << i << " ";
        }
    }
}

// Time Complexity: O(n)
// Auxiliary Space: O(1)

2. Efficient Approach: [Not in sorted Order]
// If we look carefully, all the divisors are present in pairs.
// For example if n = 100, then the various pairs of divisors are: (1,100), (2,50), (4,25), (5,20), (10,10)
// Using this fact we could speed up our program significantly. We, however, 
// have to be careful if there are two equal divisors as in the case of (10, 10). In such case, we’d print only one of them. 
// We iterate through all numbers from 1 to square root of n in this case.

void printDivisors(int n) {
    for (int i=1; i*i<=n; i++) {
        if (n % i == 0) {
            std::cout << i << " ";
            if (i != (n/i)) {
                std::cout << (n/i) << " ";
            }
        }
    }
}

// Time Complexity: O(sqrt(n))
// Auxiliary Space: O(1)

3. More Efficient Approach:
// We want to print the divisors in sorted order.
// The idea is to 1st print all divisors from 1 (inclusive) to square root n (exclusive)
// Then, print all divisors from square root n (inclusive) to n (inclusive)

void printDivisors(int n) {
    int i;
    // print all divisors from 1 (inclusive) to sqrt(n) (exclusive)
    for (i=1; i*i<=n; i++) {
        if (n % i == 0) {
            std::cout << i << " ";
        }
    }
    // print all divisors from sqrt(n) (inclusive) to n (inclusive)
    for (; i*i>=1; i--) {
        if (n % i == 0) {
            std::cout << (n/i) << " ";
        }
    }
}

// Time Complexity: O(sqrt(n))
// Auxiliary Space: O(1)
```

# 3.10 : Sieve of Eratosthenes

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg1MA%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAyNg%3D%3D

```
Problem Statement: 

Given a number n, print all primes smaller than or equal to n. It is also given that n is a small number.

I/P: n = 10
O/P: 2 3 5 7 

I/P: n = 20 
O/P: 2 3 5 7 11 13 17 19

1. Naive Method: 
// A Naive Solution would be to iterate all the numbers from 1 to n, checking if that number is prime or not, if it's prime print it. 

#include <iostream>

bool isPrime(int n) {
    if (n <= 1) return false;
    if (n == 2 || n == 3) return true;
    if (n % 2 == 0 || n % 3 == 0) return false;
    for (int i=5; i*i<=n; i+=6) {
        if ((n % i == 0) || (n % (i+2) == 0)) {
            return false;
        }
    }
    return true;
}

int main() {
    int n = 25;
    for (int i=1; i<=n; i++) {
        if (isPrime(i)) {
            std::cout << i << " ";
        }
    }
    return 0;
}

// Time Complexity: O(n * sqrt(n))
// Auxiliary Space: O(1)

2. Efficient Approach:

void SieveOfEratosthenes(int n) {
    vector<bool> isPrime(n+1, true);
    
    for (int i=2; i*i<=n; i++) {
        if (isPrime[i]) {
            for (int j=2*i; j<=n; j+=i) {
                isPrime[j] = false;
            }
        }
    }
    
    for (int i=2; i<=n; i++) {
        if(isPrime[i]) {
            std::cout << i << " ";
        }
    }
}

// Time Complexity: O(n * loglogn)
// Auxiliary Space: O(n)

3. Optimised Efficient Approach:

void SieveOfEratosthenes(int n) {
    vector<bool> isPrime(n+1, true);
    
    for (int i=2; i<=n; i++) {
        if (isPrime[i]) {
            std::cout << i << " ";
            for (int j=i*i; j<=n; j+=i) {
                isPrime[j] = false;
            }
        }
    }
}

// Time Complexity: O(n * loglogn)
// Auxiliary Space: O(n)
```

# 3.11 : Computing Power

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MTg0Ng%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAyNw%3D%3D

```
Problem Statement: 

We are given two numbers. The task is to compute Power(x,n)  which means x to the power y.

I/P: x = 2, n = 3
O/P: 8  // 2*2*2

I/P: x = 7, n = 2
O/P: 49 // 7*7

1. Naive Method: 
// A Naive Solution would be to iterate all the numbers from 1 to n, and multiply number x, n times. 

int power(int x, int n) {
    if (n == 0) return 1;
    int result = 1;
    for(int i=1; i<=n; i++) {
        result *= x;
    }
    return result;
}

// Time Complexity: O(n)
// Auxiliary Space: O(1)

2. Efficient Approach: Recursion
// The problem can be recursively defined by:
// power(x, n) = power(x, n / 2) * power(x, n / 2);        // if n is even
// power(x, n) = x * power(x, n / 2) * power(x, n / 2);    // if n is odd

int power(int x, int n) {
    if (n == 0) return 1;
    int temp = power(x, n/2);
    temp = temp * temp;
    if (n % 2 == 0) return temp;
    else return temp * x;
}

// Time Complexity: Theta(logn)
// Auxiliary Space: Theta(logn) // Since uses recursion and height of tree goes upto logn height
```

# 3.12 : Iterative Power

**Lecture Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/video/MjEzNw%3D%3D

**Article Link :** https://www.geeksforgeeks.org/batch/dsa-4/track/DSASP-Mathematics/article/NzAyOA%3D%3D

```
Problem Statement: 

We are given two numbers. The task is to compute Power(x,n)  which means x to the power y, using, Iterative Power (Binary Exponentiation)

I/P: x = 2, n = 3
O/P: 8  // 2 * 2 * 2

I/P: x = 7, n = 2
O/P: 49 // 7 * 7

1. Efficient Solution: 
// Some important concepts related to this approach:
// 1. Every number can be written as the sum of powers of 2
// 2. We can traverse through all the bits of a number from LSB to MSB in O(log n) time.

int power(int x, int n) {
    int result = 1;
    while(n > 0) {
        if (n % 2 != 0) {
            result *= x;
        }
        n /= 2;
        x *= x;
    }
    return result;
}

// Time Complexity: O(logn)
// Auxiliary Space: O(1)

2. Further Optimisation using bitwise operators:

int power(int x, int n) {
    int result = 1;
    while(n > 0) {
        if (n & 1) {
            result *= x;
        }
        n = n >> 1;
        x *= x;
    }
    return result;
}

// Time Complexity: O(logn)
// Auxiliary Space: O(1)
```
