# 🔍 LeetCode Problem - Search Insert Position (Python Solution)

This repository contains a Python solution for the LeetCode problem **"Search Insert Position"**.

## 📌 Problem Statement

> Given a **sorted array** of distinct integers and a `target` value, return the **index** if the target is found.  
> If not, return the index **where it would be** if it were inserted in order.

- The algorithm should run in **O(log n)** time.

🔗 [View Problem on LeetCode](https://leetcode.com/problems/search-insert-position/)

---

## 💡 Approach

This solution uses **binary search** to find the target index or the correct insertion position in a sorted array.

### Steps:
1. Initialize two pointers: `left = 0`, `right = len(nums) - 1`.
2. While `left <= right`:
   - Find the midpoint `mid`.
   - If `nums[mid] == target`, return `mid`.
   - If `nums[mid] > target`, search in the left half.
   - If `nums[mid] < target`, search in the right half.
3. If not found, return `left` as the insertion point.

---

## 🧪 Python Code

```python
class Solution(object):
    def searchInsert(self, nums, target):
        left = 0
        right = len(nums) - 1

        while left <= right:
            mid = (left + right) // 2
            if nums[mid] == target:
                return mid
            elif nums[mid] > target:
                right = mid - 1
            else:
                left = mid + 1

        return left
