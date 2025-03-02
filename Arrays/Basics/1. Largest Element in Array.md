# Largest Element in Array

## Problem Statement

Given an array `arr[]`, the goal is to identify and return the largest element.

### Examples:
- **Input:** arr[] = [2, 6, 7, 65, 99]
- **Output:** 99
- **Explanation:** The maximum value in the array is 99.

* **Input:** arr[] = [7, 7, 7, 7]
* **Output:** 7
* **Explanation:** The largest value in the array is 7.

+ **Input:** arr[] = [10]
+ **Output:** 10
+ **Explanation:** There is only one element, so it is the largest.
``` java
class Solution {
    public static int largest(int[] arr) {
        int max=Integer.MIN_VALUE;
        for(int i=0;i<arr.length;i++){
            if(arr[i]>max){
                max=arr[i];
            }
        }
        return max;
    }
}
```
