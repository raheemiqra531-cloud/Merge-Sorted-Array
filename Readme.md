Merge Sorted Array

Problem Description:
You are given two integer arrays `nums1` and `nums2`, sorted in non-decreasing order, and two integers `m` and `n`, representing the number of elements in `nums1` and `nums2` respectively.  

`nums1` has a length of `m + n`, where the first `m` elements denote the elements to be merged, and the last `n` elements are set to 0 and should be ignored.  
The task is to merge `nums2` into `nums1` as one sorted array. The merge must be done in-place.

Examples:
Example 1:  
Input: nums1 = [1,2,3,0,0,0], m = 3  
       nums2 = [2,5,6], n = 3  
Output: [1,2,2,3,5,6]

Example 2:  
Input: nums1 = [1], m = 1  
       nums2 = [], n = 0  
Output: [1]

Example 3:  
Input: nums1 = [0], m = 0  
       nums2 = [1], n = 1  
Output: [1]

Approach:
We use a three-pointer method starting from the end:
1. Set `i = m - 1` (last valid element in nums1), `j = n - 1` (last element in nums2), and `k = m + n - 1` (last position in nums1).
2. Compare `nums1[i]` and `nums2[j]`:
   - Place the larger value at `nums1[k]`.
   - Move the corresponding pointer (`i` or `j`) one step left.
   - Move `k` one step left.
3. Continue until one array is exhausted.
4. If `nums2` still has elements left, copy them into `nums1`.
