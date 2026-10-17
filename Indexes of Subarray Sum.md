## 01. Indexes of Subarray Sum

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/subarray-with-given-sum-1587115621/1)

### Problem Description

**Task:** Given an array arr[] containing only non-negative integers, your task is to find a continuous subarray (a contiguous sequence of elements) whose sum equals a specified value target . You need to return the 1-based indices of the leftmost and rightmost elements of this subarray. You need to find the first subarray whose sum is equal to the target. If no such array is possible then, return [-1].Examples:Input: arr[] = [1, 2, 3, 7, 5], target = 12

#### Examples

##### Example 1

- **Output:**
```text
[1, 5]
```
- **Explanation:** The sum of elements from 1st to 5th position is 15.

##### Example 2

- **Input:**
```text
arr[] = [5, 3, 4], target = 2
```
- **Output:**
```text
[-1]
```
- **Explanation:** There is no subarray with sum 2.

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-10-12 16:57:02
- **Status:** Correct
- **Marks:** 4

```java
import java.util.ArrayList;
class Solution {
    static ArrayList<Integer> subarraySum(int[] arr, int target) {
        // code here
        ArrayList<Integer>ans=new ArrayList<>();
       int left=0;
       int currentSum=0;
       for(int right=0;right<arr.length;right++){
           currentSum+=arr[right];
           while(currentSum>target&&left<right){
               currentSum-=arr[left];
               left++;
           }
           if(currentSum==target){
              ans.add(left+1);
              ans.add(right+1);
              return ans;
           }
       }
       ans.add(-1);
       return ans;
       }
}
```

*Generated on: 10/17/2026, 12:35:13 PM*