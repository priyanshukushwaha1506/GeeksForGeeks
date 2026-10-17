## 01. Maximum Average Subarray

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/maximum-average-subarray5859/1)

### Problem Description

**Task:** Given an array arr[] and a positive integer k, find the subarray of length k having the maximum average value.
Return the starting index of that subarray.
If multiple subarrays have the same maximum average, return the smallest starting index.

#### Examples

##### Example 1

- **Input:**
```text
k = 4, arr[] = [1, 12, -5, -6, 50, 3]
```
- **Output:**
```text
1
```
- **Explanation:** Maximum average is (12 - 5 - 6 + 50)/4 = 51/4. Therefore answer for this test case is 1.

##### Example 2

- **Input:**
```text
k = 3, arr[] = [3, -435, 335, 10, -50, 100, 20]
```
- **Output:**
```text
2
```
- **Explanation:** Maximum average is (335 + 10 - 50)/3 = 295/3. Therefore answer for this test case is 2.

#### Constraints

- **1.** `1 ≤ k ≤ arr.size() ≤ 10⁵-10³ ≤ arr[i] ≤ 10³`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (1)

#### Solution 1 (Java)

- **Submitted:** 2026-10-17 12:33:33
- **Status:** Correct
- **Marks:** 2

```java
class Solution {
    public int findMaxAverage(List<Integer> arr, int k) {
        // code here
       //sliding Window 
       //First Window
       if(k>arr.size()){
           return -1;
       }
       int sum=0;
       for(int i=0;i<k;i++){
           sum+=arr.get(i);
       }
       //Second Window
       int startIdx=0;
       int maxSum=sum;
       for(int j=k;j<arr.size();j++){
           sum=sum+arr.get(j)-arr.get(j-k);
           if(sum>maxSum){
               maxSum=sum;
               startIdx=j-k+1;
           }
       }
      return startIdx;  
    }
}
```

*Generated on: 10/17/2026, 12:34:09 PM*