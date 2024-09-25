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


#### 1st Approach using by loop 
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

#### 2nd approach using Recursion 

```Python
class Solution(object):
    def isPowerOfTwo(self, n):
        """
        :type n: int
        :rtype: bool
        """
        if n <= 0:
            return False 
        if n == 1:
            return True
        if n % 2 != 0:
            return False
            
        return self.isPowerOfTwo

```


#### 3rd approach using integer 

````Python
class Solution(object):
    def isPowerOfTwo(self, n):
        """
        :type n: int
        :rtype: bool
        """
        if n <= 0:
            return False 
        if n == 1:
            return True
        power = 1
        while power < n:
            power *= 2
            
        return power == n 
````

### 258. Add Digits - Solved (Easy)

**LeetCode Question:** [ 258. Add Digits - Solved (Easy)](https://leetcode.com/problems/add-digits/)

### Example 1:
- **Input:** `num = 38`
- **Output:** `2`

### Example 2:
- **Input:** `num = 0`
- **Output:** `0`

## Solution:

**1st approach**
```python

class Solution(object):
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        # Base case: if the number is a single digit, return it
        if len(str(num)) == 1:
            return num 

        # Calculate the sum of the digits
        sum_value = 0
        for i in str(num):
            sum_value += int(i)
        
        # Update num with the sum of digits and make recursive call
        num = sum_value 
        return self.addDigits(num)

```

**2nd approach**
**LeetCode Question:** [ 258. Add Digits - Solved (Easy)](https://leetcode.com/problems/add-digits/)
```python
class Solution(object):
    def addDigits(self, num):
        """
        :type num: int
        :rtype: int
        """
        if num < 10:
            return num
            
        sum_value = 0
        for i in str(num):
            sum_value += int(i)

        return self.addDigits(sum_value)

```

## 326. Power of Three
**LeetCode Question:** [ 326. Power of Three (Easy)](https://leetcode.com/problems/power-of-three/)


### Example 1:

- **Input**: `n = 27`
- **Output**: `true`
- **Explanation**: \(27 = 3^3\)

### Example 2:

- **Input**: `n = 0`
- **Output**: `false`
- **Explanation**: There is no integer `x` such that \(3^x = 0\).

### Example 3:

- **Input**: `n = 9`
- **Output**: `true`
- **Explanation**: \(9 = 3^2\)


#### 1st approach with loop 
``` Python
class Solution(object):
    def isPowerOfThree(self, n):
        """     
        :type n: int
        :rtype: bool
        """
        if n <= 0:
            return False 
        
        if n == 1:
            return True 
        
        while n >1:
            if n % 3 != 0:
                return False 
            n = n//3
        return True 

```
#### 2nd approach by using recursion 

```python

class Solution(object):
    def isPowerOfThree(self, n):
        """     
        :type n: int
        :rtype: bool
        """
        if n <= 0:
            return False 
        if n == 1:
            return True  
        if n % 3 !=0:
            return False 
        return self.isPowerOfThree(n//3)
```

#### 3rd Using Integer Powers (Exponentiation)

```` Python
class Solution(object):
    def isPowerOfThree(self, n):
        """     
        :type n: int
        :rtype: bool
        """
        if n <= 0:
            return False 
        if n == 1:
            return True  
        power = 1  
        
        while power<n:
            power *= 3 
        
        return power == n 

````
---------------------------------------------------------------------------------------------------------------


# nums = [2,2,1,1,1,2,2]

# # for i in nums:
# #     print(i)

# l = []
# for i in range(len(nums)):
#     if nums[i] != nums[i-1]:
#         l.append(nums[i])

# print(l)

# # num_map = {}
# max_count = 0 
# for i in l: 
#     prev_count = 0 
#     for j in nums:
        
#         if i == j:
#             prev_count += 1 
        
#     if prev_count > max_count:
        
# def majorityElement(nums):
#     # Step 1: Create a hashmap (dictionary) to store counts of each element
#     counts = {}
    
#     # Step 2: Count the frequency of each element
#     for num in nums:
#         counts[num] = counts.get(num, 0) + 1
    
#     # Step 3: Find the element that appears more than n // 2 times
#     for num, count in counts.items():
#         if count > len(nums) // 2:
#             return num, counts

# nums = [2, 2, 1, 1, 1, 2, 2]
# print(majorityElement(nums))  # Output: 2
 
class Solution(object):
    def removeElement(self, nums, val):
        """
        :type nums: List[int]
        :type val: int
        :rtype: int
        """
        k = 0  # Pointer to track the position of the next valid element
        
        for i in range(len(nums)):
            if nums[i] != val:
                nums[k] = nums[i]  # Move valid element to position k
                k += 1  # Increment k for the next valid element
        
        return k  # Return the count of elements that are not equal to val

# Example usage:
nums = [3, 2, 2, 3]
val = 3
obj = Solution()
k = obj.removeElement(nums, val)
print(k)        # Output: 2
print(nums[:k]) # Output: [2, 2] (modified list in-place)






## 7. Reverse Integer

**LeetCode Question:** [7. Reverse Integer(medium](https://leetcode.com/problems/reverse-integer/description/)


```Python
class Solution(object):
    def reverse(self, x):
        """
        :type x: int
        :rtype: int
        """

        int_min = 2**31 
        int_max = -2**31 + 1

        is_negative = False
        if x < 0:
            is_negative = True
            x = -x

        reversed_sum = 0 
        while x > 0:
            r = x %10 
            reversed_sum = reversed_sum * 10  + r 
            x //= 10 

        if is_negative:
            reversed_sum = -reversed_sum

        if int_min < reversed_sum or int_max > reversed_sum:
            return 0
        return reversed_sum
```

        
## 9. Palindrome Number
**LeetCode Question:** [9. Palindrome Number(Easy)](https://leetcode.com/problems/palindrome-number/description/)

```Python
class Solution(object):
    def isPalindrome(self, x):
        """
        :type x: int
        :rtype: bool
        """
        original_value = x 
        if x < 0:
            return False

        reversed_sum = 0
        while x > 0:
            r = x %10 
            reversed_sum = reversed_sum * 10 + r 
            x = x//10 
        
        if original_value == reversed_sum:
            return True 

        return False 
        
```

