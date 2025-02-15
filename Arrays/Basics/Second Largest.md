# Second Largest
## Problem Statement

Given an array arr[] containing positive integers, find and return the second largest element. If there is no second largest element, return -1.

Note: The second largest element must be different from the largest element.

### Examples
* **Input:** arr[] = [3, 53, 4, 6, 34, 23]
* **Output:** 34
* **Explanation:** The largest element of the array is 53 and the second largest element is 34.
  
- **Input:** arr[] = [10, 5, 10]
- **Output:** 5
- **Explanation:** The largest element of the array is 10 and the second largest element is 5.
  
+ **Input:** arr[] = [10, 10, 10]
+ **Output:** -1
+ **Explanation:** The largest element of the array is 10 and the second largest element does not exist.

```java
class Solution {
    public int getSecondLargest(int[] arr) {
        int max = Integer.MIN_VALUE;
        int secmax = Integer.MIN_VALUE;
        for (int i = 0; i < arr.length; i++) {
            if (arr[i] > max) {
                secmax = max;
                max = arr[i];
            } else if (arr[i] > secmax && arr[i] != max) {
                secmax = arr[i];
            }
        }
        if (secmax == Integer.MIN_VALUE) {
            return -1;
        }
        return secmax;
    }
}
