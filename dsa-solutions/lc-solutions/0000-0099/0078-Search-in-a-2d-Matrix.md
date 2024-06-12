---
id: Search-a-2d-matrix
title: Search a 2D Matrix (LeetCode)
sidebar_label: 0078-Search-a-2d-matrix
tags:
  - Array
  - Binary Search
  - Matrix
description: You are given an m x n integer matrix with Each row is sorted in non-decreasing order and the first integer of each row is greater than the last integer of the previous row.
---

## Problem Description

You are given an m x n integer matrix matrix with the following two properties:

- Each row is sorted in non-decreasing order.
- The first integer of each row is greater than the last integer of the previous row.
  Given an integer target, return true if target is in matrix or false otherwise. You must write a solution in O(log(m \* n)) time complexity.

### Examples

#### Example 1

```plaintext
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
Output: true
```

#### Example 2

```plaintext
Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
Output: false
```

### Constraints:

- $n == matrix[i].length$
- $1 <= m, n <= 100$
- $-104 <= matrix[i][j], target <= 104$

### Approach

### Solution Codes

#### Codes in Different Languages

<Tabs>
  <TabItem value="C++" label="C++" default>
  <SolutionAuthor name="@ayushchaware08"/>

```cpp
class Solution {
public:
    bool searchMatrix(vector<vector<int>>& matrix, int target) {

        int row = matrix.size();
        int col = matrix[0].size();

        int start =0;
        int end = row*col -1;

        int mid = start + (end-start)/2;

        while(start<=end){
            int element = matrix[mid/col][mid%col];
            if(element == target){
                return 1;
            }
            if(element <target){
                start = mid +1;
            }
            else{
                end = mid - 1;
            }
            mid = start + (end-start)/2;
        }
        return 0;
    }
};

```

  </TabItem>
  <TabItem value="Python" label="Python">
  <SolutionAuthor name="@ayushchaware08"/>

```py
  class Solution:
    def searchMatrix(self, matrix: List[List[int]], target: int) -> bool:
        if not matrix or not matrix[0]:
            return False

        rows = len(matrix)
        cols = len(matrix[0])

        start = 0
        end = rows * cols - 1

        while start <= end:
            mid = start + (end - start) // 2
            element = matrix[mid // cols][mid % cols]

            if element == target:
                return True
            elif element < target:
                start = mid + 1
            else:
                end = mid - 1

        return False
```

  </TabItem>
  <TabItem value="Java" label="Java"> 
  <SolutionAuthor name="@ayushchaware08"/>

```java
class Solution {
  public boolean searchMatrix(int[][] matrix, int target) {
      int rows = matrix.length;
      int cols = matrix[0].length;

      int start = 0;
      int end = rows * cols - 1;

      while (start <= end) {
          int mid = start + (end - start) / 2;
          int element = matrix[mid / cols][mid % cols];

          if (element == target) {
              return true;
          } else if (element < target) {
              start = mid + 1;
          } else {
              end = mid - 1;
          }
      }

      return false;
  }
}

```

  </TabItem>  
</Tabs>

### Conclusion
Given Solution help you to solve an m x n integer matrix by having
- Time Complexity: O(log(m×n))
- Space Complexity: O(1)


