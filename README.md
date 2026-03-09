# Ascendeum Technical Assessment - Round 1: Matrix Generation

This repository contains the Python implementation for the matrix pattern generation assessment.

##  Problem Addressed
The script generates an `n x n` 2D matrix (with `n=6`) filled with elements from `1` to `n^2` in a clockwise spiral order. 

##  Approach & Algorithmic Logic
To solve this efficiently in pure Python without using external libraries like NumPy, I implemented a **4-Pointer Boundary Traversal** approach.

1. **Initialization:** Created a pre-sized 2D list `res` filled with zeros to avoid dynamic memory reallocation overhead.
2. **Boundary Pointers:** Defined `top`, `bottom`, `left`, and `right` pointers to track the current shrinking boundaries of the spiral.
3. **Traversal:** Utilized a `while` loop to iteratively fill the perimeter in four distinct steps:
   - Traverse Left → Right (increment `top` boundary)
   - Traverse Top → Bottom (decrement `right` boundary)
   - Traverse Right → Left (decrement `bottom` boundary)
   - Traverse Bottom → Top (increment `left` boundary)
4. **Boundary Checks:** Added strict `if left <= right:` and `if top <= bottom:` checks before the reverse traversals to prevent out-of-bounds indexing and overlapping.

##  Complexity Analysis
- **Time Complexity:** `O(N^2)` 
  The algorithm iterates through exactly `n * n` elements. Each cell in the matrix is visited and assigned a value exactly once.
- **Space Complexity:** `O(N^2)`
  The space is strictly bounded by the `n x n` output matrix required to store the result. No auxiliary data structures are used.

