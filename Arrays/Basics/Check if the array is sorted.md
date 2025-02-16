## Problem Statement

Given an array `nums`, determine if it was originally sorted in non-decreasing order and then rotated some number of positions (which could be zero). Return `true` if the array can be considered a rotated version of a sorted array, and `false` otherwise.

**Note:** The original array may contain duplicate elements.

---

## Key Insights:

- A **rotated array** is an array where elements are shifted cyclically.
  - Example: If the array is `[1, 2, 3, 4, 5]`, a rotation by 2 positions would result in `[3, 4, 5, 1, 2]`.

- The array should have **at most one "decrease"** in its sequence when traversed in order. This decrease represents the rotation point.

- If there are **multiple decreases**, it’s not a rotated sorted array.

---

## Approach:

1. **Traverse the array**:
   - Check if the array is sorted and look for where the order breaks (i.e., where an element is greater than the next one).
   
2. **Rotation Validity**:
   - The array should have no more than **one decrease** in its sequence for it to be valid.
   
3. **Handle Duplicates**:
   - The array may contain duplicates, so be sure to account for them when checking for decreases.

---

## Examples:

1. **Example 1:**
   - **Input**: `[4, 5, 6, 1, 2, 3]`
   - **Explanation**: The original array was `[1, 2, 3, 4, 5, 6]`, and it was rotated by 3 positions to become `[4, 5, 6, 1, 2, 3]`.
   - **Output**: `true`

2. **Example 2:**
   - **Input**: `[6, 5, 4, 3, 2, 1]`
   - **Explanation**: This array cannot be a rotated version of a sorted array because the numbers are strictly decreasing.
   - **Output**: `false`

3. **Example 3:**
   - **Input**: `[7, 8, 9, 10, 11]`
   - **Explanation**: The array is already sorted, and no rotation is required.
   - **Output**: `true`

``` java
class Solution {
    public boolean checks(int[] nums) {
            int n=nums.length;
            int c=0;
            for(int i=0;i<n-1;i++){
            if(nums[i]>nums[i+1]){
                c++;
            }   
        }
        if(c==0){
            return true;
        }
        if(c>1){
            return false;
        }
        if(nums[0]>=nums[n-1]){
            return true;
        }
        return false;
    }
}
```
