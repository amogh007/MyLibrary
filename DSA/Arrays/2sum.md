Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 
```
Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Explanation: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
```

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
 

Follow-up: Can you come up with an algorithm that is less than O(n2) time complexity?



# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
Simple problem 

# Approach
<!-- Describe your approach to solving the problem. -->
my initial approach is 

```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    for(let i = 0; i < nums.length; i++){
        let compliment=target-nums[i]
        let j=nums.indexOf(compliment)
        if(j>-1&&j!=i){
            return [i,j]
        }
    }
    return []
};
```

# Complexity
- Time complexity:o(n^2)
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:o(constant)
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function(nums, target) {
    let compareValues = {};
    for (let i = 0; i < nums.length; i++) {
        if (compareValues[target - nums[i]] !== undefined) {
            return [ compareValues[target - nums[i]], i ]
        } else {
            compareValues[nums[i]] = i;
        }
    }
};
```
# Comment
<!-- Describe your first thoughts on how to solve this problem. -->
The above solution is better then my initial solution cause it does in o(n)
