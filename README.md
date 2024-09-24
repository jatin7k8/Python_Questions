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
### 2. left shift rotation:- 
```python 

def left_shifiting(n, left_shift):
    
    temp = n[:left_shift]
    for i in range(len(n)-left_shift):
        n[i] = n[i + left_shift]
    
    n[-left_shift:]  = temp 
    
    return f'After shifting by {left_shift} :- \nresult look like {n}'
        
a = [1,2,3,4,5,6,7]
l = 3
print("Before shifting :- ", a)
print(left_shifiting(a, l))

```

```
    
Before shifting :-  [1, 2, 3, 4, 5, 6, 7]
After shifting by 3 :- 
result look like [4, 5, 6, 7, 1, 2, 3]

```
    
    
### 231. Power of Two - Solved (Easy)
**LeetCode Question:** [Power of Two - Solved (Easy)](https://leetcode.com/problems/power-of-two/)
## Problem Statement:
Given an integer `n`, return `true` if it is a power of two. Otherwise, return `false`.

An integer `n` is a power of two if there exists an integer `x` such that \( n == 2^x \).

### Example 1:
- **Input:** `n = 1`
- **Output:** `true`
- **Explanation:** \( 2^0 = 1 \)

### Example 2:
- **Input:** `n = 16`
- **Output:** `true`
- **Explanation:** \( 2^4 = 16 \)

### Example 3:
- **Input:** `n = 3`
- **Output:** `false`

```python
class Solution(object):
    def isPowerOfTwo(self, n):
        """
        :type n: int
        :rtype: bool
        """
        if n <= 0:
            return False 
        
        while n > 1:
            if n % 2 != 0:
                return False
            n = n // 2
        return True
```



    
    
    
    
    
    
