# Pow(x, n) Notes

## Problem

Calculate:

```text
x^n
```

where:

* `x` = base value
* `n` = exponent
* Exponent can be positive or negative

---

## Algorithm Used

```text
Binary Exponentiation / Fast Power
```

---

## Main Idea

Instead of multiplying `x` repeatedly:

```text
2^10 = 2 × 2 × 2 × 2 × ...
```

Reduce the exponent using division by 2.

Rules:

If exponent is even:

```text
x^n = (x*x)^(n/2)
```

If exponent is odd:

```text
x^n = x * x^(n-1)
```

This reduces computations significantly.

---

## Handling Negative Powers

For negative exponent:

```text
x^-n = 1 / x^n
```

Example:

```text
2^-3

= 1 / 2^3

= 1 / 8

= 0.125
```

Use long type:

```java
long num = n;
```

Reason:

```text
Integer.MIN_VALUE

-2147483648
```

Negating directly may overflow.

---

## Recursive Logic

Base cases:

```java
if(n==0) return 1;

if(n==1) return x;
```

Even exponent:

```java
return power(x*x , n/2);
```

Odd exponent:

```java
return x * power(x , n-1);
```

---

## Dry Run

Example:

```text
x = 2
n = 3
```

Steps:

```text
power(2,3)

= 2 * power(2,2)

= 2 * power(4,1)

= 2 * 4

= 8
```

Answer:

```text
2^3 = 8
```

---

## Why Fast?

Normal method:

```text
2^1000

1000 multiplications
```

Binary Exponentiation:

```text
1000

↓

500

↓

250

↓

125

...
```

Exponent reduces quickly.

---

## Complexity

```text
Time Complexity  : O(log n)

Space Complexity : O(log n)
```

Space complexity comes from recursion stack.

---

## Pattern Used

```text
Binary Exponentiation

Divide and Conquer

Recursion
```

---

## Memory Trick

```text
Even exponent:

square base + halve exponent

Odd exponent:

multiply once + reduce exponent

Negative exponent:

take reciprocal
```
