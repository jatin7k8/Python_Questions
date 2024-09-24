# Python Questions

## LeetCode Questions

### 1. Two Sum
**LeetCode Question:** [Two Sum](https://leetcode.com/problems/two-sum/description/)

**Problem Statement:**
Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`. You may assume that each input would have exactly one solution, and you may not use the same element twice. You can return the answer in any order.

**Example:**
```python
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        # The inner loop starts from i + 1 to avoid using the same element twice
        for i in range(len(nums)):
            for j in range(i + 1, len(nums)):
                if nums[i] + nums[j] == target:
                    return [i, j]

```
**2nd method**

```Python 
class Solution(object):
    def twoSum(self, nums, target):
        """
        :type nums: List[int]
        :type target: int
        :rtype: List[int]
        """
        num_map = {}
        for i , n in enumerate(nums):
            
            diff = target - n
            
            if diff in num_map:
                return [num_map[diff] , i]
                
            num_map[n]  = i 

```
