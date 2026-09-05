# LeetCode 130 – Surrounded Regions

## Problem

Given an `m x n` matrix containing `'X'` and `'O'`, capture all regions that are surrounded by `'X'`.

A region is surrounded if it is completely enclosed by `'X'`.

Any `'O'` connected to the **border of the matrix** cannot be surrounded and must remain unchanged.

## Example

**Input:**

```text
[
  ["X","X","X","X"],
  ["X","O","O","X"],
  ["X","X","O","X"],
  ["X","O","X","X"]
]
```

**Output:**

```text
[
  ["X","X","X","X"],
  ["X","X","X","X"],
  ["X","X","X","X"],
  ["X","O","X","X"]
]
```

The `O` cells in the middle are completely surrounded by `X`, so they are changed to `X`.

The `O` on the border remains unchanged because it is connected to the boundary.

## Approach

Instead of searching for surrounded regions directly, we can identify the regions that **cannot be surrounded**.

Any `'O'` connected to a border `'O'` is safe and should remain unchanged.

The approach is:

1. Find every `'O'` on the boundary.
2. Perform DFS or BFS from each boundary `'O'`.
3. Mark all connected `'O'` cells as safe.
4. Traverse the entire matrix.
5. Convert every unmarked `'O'` into `'X'`.
6. Restore the safe cells back to `'O'`.

This works because an `O` region can only be surrounded if it has no connection to the boundary.

## Algorithm

1. Check all cells on the four borders.
2. Whenever a border cell contains `'O'`, start DFS/BFS.
3. Mark every connected `'O'` as safe.
4. Traverse the matrix again.
5. Change every remaining `'O'` to `'X'`.
6. Change the temporary safe markers back to `'O'`.

## Complexity

Let the matrix contain `m × n` cells.

* **Time Complexity:** `O(m × n)`
* **Space Complexity:** `O(m × n)` in the worst case for DFS/BFS traversal.

If an iterative traversal is used, the auxiliary space depends on the number of connected cells.

## Key Learning

The important idea is to work **from the boundary inward** rather than trying to detect surrounded regions directly.

This problem is a good example of:

* Matrix traversal
* DFS
* BFS
* Connected components
* Boundary-based searching

## LeetCode Details

* **Problem Number:** 130
* **Problem Name:** Surrounded Regions
* **Difficulty:** Medium
* **Language:** Python 3
* **File:** `solution.py`

## Topics

* Array
* Depth-First Search
* Breadth-First Search
* Union Find
* Matrix

## Author

T.Nandhini
