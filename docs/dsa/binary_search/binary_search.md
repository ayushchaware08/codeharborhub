---
id: binary-search-DSA
title: Binary Search
sidebar_label: Binary Search
sidebar_position: 6
description: "In this blog post, we'll dive into the binary search algorithm, a fundamental technique in computer science for efficiently finding an element in a sorted array. You'll learn what binary search is, how it works, and its time complexity. We'll also cover practical applications, variations of binary search, and common problems you can solve using this algorithm. By the end, you'll have a thorough understanding of binary search and how to implement it in your programming projects."
tags: [dsa, algorithms, binary search]
---

Binary Search algorithm is essential for efficiently finding elements in sorted arrays, making it a staple in the toolkit of any adept programmer. Whether you're optimizing search operations or solving complex algorithmic challenges, understanding binary search is crucial. Let's delve into its mechanics, applications, and implementation.

## What is Binary Search?

Binary search is a highly efficient algorithm used to find an element in a sorted array. It works by repeatedly dividing the search interval in half. If the value of the search key is less than the item in the middle of the interval, the algorithm narrows the interval to the lower half. Otherwise, it narrows it to the upper half. The process continues until the search key is found or the interval is empty.

In pseudo-code, binary search is defined as follows:

```cpp
FUNCTION binarySearch(array, key):
low = 0
high = array.length - 1
WHILE low <= high:
mid = (low + high) / 2
IF array[mid] == key:
RETURN mid
ELSE IF array[mid] < key:
low = mid + 1
ELSE:
high = mid - 1
RETURN -1
```

In C++, this can be represented as:

```cpp
int binarySearch(int array[], int size, int key) {
int low = 0;
int high = size - 1;
while (low <= high) {
int mid = low + (high - low) / 2;
if (array[mid] == key) {
return mid;
} else if (array[mid] < key) {
low = mid + 1;
} else {
high = mid - 1;
}
}
return -1;
}
```

## How Binary Search Works

### Step-by-Step Explanation

1.  Initialize: Set two pointers, low at the beginning and high at the end of the array.
2.  Middle Element: Calculate the middle element's index.
3.  Comparison:
    If the middle element is the target, return its index.
    If the middle element is less than the target, discard the left half by setting low to mid + 1.
    If the middle element is greater than the target, discard the right half by setting high to mid - 1.
4.  Repeat: Repeat steps 2 and 3 until the target is found or the low pointer exceeds the high pointer.

### Time Complexity

The time complexity of binary search is $𝑂(log𝑛)$

where $n$ is the number of elements in the array. This logarithmic time complexity makes binary search significantly faster than linear search for large datasets.

## Practical Applications

Binary search is widely used in various real-world applications and algorithmic problems:

1. Searching in a Sorted Array
   The primary use of binary search is to find elements in a sorted array efficiently. It is the foundation for more complex search algorithms.

2. Dictionary Lookups
   Binary search is used in dictionaries (like the one you're reading now) to quickly find words and their definitions.

3. Binary Search Trees
   Binary search is the basis for searching in binary search trees (BSTs), a fundamental data structure in computer science.

4. Finding Boundaries
   Binary search can be adapted to find the first or last occurrence of a target element, making it useful in problems requiring boundary searches.

Variations of Binary Search
Binary search can be adapted in various ways to solve different types of problems. Here are a couple of common variations:

1. Lower Bound and Upper Bound
   These variations of binary search are used to find the first and last occurrence of a target element in a sorted array.

Lower Bound Pseudo-Code:

```cpp
FUNCTION lowerBound(array, key):
low = 0
high = array.length
WHILE low < high:
mid = (low + high) / 2
IF array[mid] < key:
low = mid + 1
ELSE:
high = mid
RETURN low
```

Upper Bound Pseudo-Code:

```cpp
FUNCTION upperBound(array, key):
low = 0
high = array.length
WHILE low < high:
mid = (low + high) / 2
IF array[mid] <= key:
low = mid + 1
ELSE:
high = mid
RETURN low
```

2. Rotated Sorted Array
   Binary search can be modified to handle rotated sorted arrays, where the array is sorted but then rotated at some pivot point.

:::Tip
Handle Edge Cases: Ensure your implementation correctly handles cases where the target element is not present or when the array is empty.
Prevent Overflow: When calculating the middle index, use $\text{mid} = \text{low} + \frac{\text{high} - \text{low}}{2}$ instead of $\text{mid} = \frac{\text{low} + \text{high}}{2}$ to prevent potential overflow.
Iterative vs. Recursive: Both iterative and recursive implementations are valid. Choose based on your preference and the problem constraints.
:::

## Conclusion
Binary search is a fundamental algorithm that every programmer should master. Its efficiency and versatility make it a powerful tool for solving a wide range of problems. By understanding how binary search works and how to implement its variations, you'll be well-equipped to tackle numerous challenges in your programming journey.
