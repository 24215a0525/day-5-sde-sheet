# Majority Element-I Notes

## Problem

Find the element that appears more than:

```text
n/2 times
```

The problem guarantees that a majority element exists.

---

## Algorithm Used

```text
Boyer-Moore Voting Algorithm
```

---

## Main Idea

Use cancellation logic.

```text
Same element       -> increase count

Different element  -> decrease count
```

Majority element survives because it appears more than all other elements combined.

---

## Steps

### Initialize

```java
int cnt = 0;
int el = 0;
```

### Traverse array

If count becomes 0:

```java
el = nums[i];
cnt = 1;
```

If same candidate:

```java
cnt++;
```

If different:

```java
cnt--;
```

---

## Why It Works?

Example:

```text
[2,2,1,1,1,2,2]
```

Cancellation:

```text
2 vs 1 -> cancel

Remaining element survives
```

Since majority frequency is greater than:

```text
n/2
```

it cannot be completely cancelled.

---

## Verification Step

Check candidate frequency:

```java
if(cnt1 > n/2)
    return el;
```

Needed only when majority element is NOT guaranteed.

For this problem:

```text
verification is optional
```

because majority always exists.

---

## Complexity

```text
Time Complexity  : O(n)

Space Complexity : O(1)
```

---

## Pattern

```text
Voting Algorithm
Cancellation Technique
Array Traversal
```

---

## Memory Trick

```text
count = 0  -> choose candidate

same       -> count++

different  -> count--

survivor candidate -> majority
```
