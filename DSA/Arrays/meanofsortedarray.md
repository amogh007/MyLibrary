# Question
<!-- Describe your first thoughts on how to solve this problem. -->
Given two sorted arrays nums1 and nums2 of size m and n respectively, return the median of the two sorted arrays.

The overall run time complexity should be O(log (m+n)).

 

Example 1:

Input: nums1 = [1,3], nums2 = [2]
Output: 2.00000
Explanation: merged array = [1,2,3] and median is 2.
Example 2:

Input: nums1 = [1,2], nums2 = [3,4]
Output: 2.50000
Explanation: merged array = [1,2,3,4] and median is (2 + 3) / 2 = 2.5.
 
```
Constraints:

nums1.length == m
nums2.length == n
0 <= m <= 1000
0 <= n <= 1000
1 <= m + n <= 2000
-106 <= nums1[i], nums2[i] <= 106
```

# Intuition
<!-- Describe your first thoughts on how to solve this problem. -->
easier problem solution i came up is good 

# Approach
<!-- Describe your approach to solving the problem. -->
just the median problem sort the array by its numeric value 

# Complexity
- Time complexity:0(m+n)
<!-- Add your time complexity here, e.g. $$O(n)$$ -->

- Space complexity:
<!-- Add your space complexity here, e.g. $$O(n)$$ -->

# Code
```
/**
 * @param {number[]} nums1
 * @param {number[]} nums2
 * @return {number}
 */
var findMedianSortedArrays = function(nums1, nums2) {
    let temp=[...nums1,...nums2].sort((a,b)=>a-b)
    if(temp.length%2===0){
        let middle=temp.length/2
        let median=temp[middle-1]+temp[middle]
        return median/2
    }else{
        let ind=Math.ceil(temp.length/2)
        return temp[ind-1]
    }
};
```