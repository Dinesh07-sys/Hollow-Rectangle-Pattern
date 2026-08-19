# Hollow Rectangle Pattern in Python

A Python implementation of a Hollow Rectangle Pattern using nested loops and boundary-based conditional logic.

Unlike a solid rectangle, this pattern prints stars only on the outer edges while keeping the interior empty.

## Pattern Preview

For `N = 5`:

```text
*****
*   *
*   *
*   *
*****
```

## How It Works

The program uses two nested loops to traverse every position in an `N × N` grid.

For each position, it checks whether it belongs to the boundary:

```python
if i == 0 or j == 0 or i == n - 1 or j == n - 1:
```

If the position is on the boundary, a star is printed:

```text
*
```

Otherwise, a space is printed:

```text
" "
```

This creates the hollow effect.

## Implementation

```python
class Solution:
    def pattern21(self, n):
        for i in range(n):
            for j in range(n):
                if i == 0 or j == 0 or i == n - 1 or j == n - 1:
                    print("*", end="")
                else:
                    print(" ", end="")
            print()


if __name__ == "__main__":
    sol = Solution()
    N = 5
    sol.pattern21(N)
```

## Boundary Logic

The four conditions represent the four sides of the rectangle:

```text
i == 0       → Top edge
i == n - 1   → Bottom edge
j == 0       → Left edge
j == n - 1   → Right edge
```

Any position satisfying at least one of these conditions receives a `*`.

## Example

For `N = 4`:

```text
****
*  *
*  *
****
```

## Complexity Analysis

| Metric | Complexity |
|---|---|
| Time Complexity | `O(N²)` |
| Auxiliary Space | `O(1)` |

The program visits every position in the `N × N` grid once, resulting in `O(N²)` time complexity.

No additional data structures are used, so the auxiliary space is `O(1)`.

## Concepts Practiced

- Nested loops
- Conditional statements
- Boundary detection
- Grid traversal
- Pattern printing
- Boolean logic
- Space management

## Key Takeaway

The important idea in this pattern is identifying whether a position belongs to the boundary.

```text
Boundary → Print *
Interior  → Print space
