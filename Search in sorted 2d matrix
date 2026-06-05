# Search in 2D Matrix - Notes

## Idea

Treat the 2D matrix as a single sorted 1D array because:

* Each row is sorted
* First element of next row > last element of previous row

So apply Binary Search on total elements.

## Steps

1. Calculate rows and columns

```java
int m = mat.length;
int n = mat[0].length;
```

2. Binary Search range

```java
low = 0
high = m*n - 1
```

3. Convert 1D index to 2D index

```java
row = mid / n
col = mid % n
```

4. Compare matrix element with target

```java
if(mat[row][col] == target)
    return true;
else if(mat[row][col] < target)
    low = mid + 1;
else
    high = mid - 1;
```

## Why division and modulus?

```text
row = index / columns
col = index % columns
```

Used to convert imaginary 1D position into matrix coordinates.

## Complexity

Time Complexity: O(log(m*n))

Space Complexity: O(1)
