## 01. Set Matrix Zeros

The problem can be found at the following link: [Question Link](https://www.geeksforgeeks.org/problems/set-matrix-zeroes/1)

### Problem Description

**Task:** Given a 2D matrix mat[][] of size n x m. Modify the matrix such that if mat[i][j] is 0, all the elements in the i-th row and j-th column are set to 0.

#### Examples

##### Example 1

- **Input:**
```text
mat[][] = [[1, -1, 1], [-1, 0, 1], [1, -1, 1]]
```
- **Output:**
```text
[[1, 0, 1], [0, 0, 0], [1, 0, 1]]
```
- **Explanation:** mat[1][1] = 0, so all elements in row 1 and column 1 are updated to zeroes.

##### Example 2

- **Input:**
```text
mat[][] = [[0, 1, 2, 0], [1, 2, 6, 2], [1, 3, 1, 8]] Output: [[0, 0, 0, 0], [0, 2, 6, 0], [0, 3, 1, 0]] Explanation: mat[0][0] and mat[0][3] are 0s, so all elements in row 0, column 0 and column 3 are updated to zeroes.
```

#### Constraints

- **1.** `1 ≤ n, m ≤ 500^- 2³¹ ≤ mat[i][j] ≤ 2³¹ - 1`

### Time and Auxiliary Space Complexity

- **Expected Time Complexity:** O(n * m)
- **Expected Auxiliary Space Complexity:** O(1)

### Accepted Solutions (2)

#### Solution 1 (Java)

- **Submitted:** 2026-10-16 11:31:55
- **Status:** Correct
- **Marks:** 0

```java
class Solution {
    public void setMatrixZeroes(int[][] mat) {
        // code here
        int row=mat.length;
        int col=mat[0].length;
        boolean firstColHasZero=false;
        //Step1:Mark indicators in first row and colmn
        for(int i=0;i<row;i++){
            if(mat[i][0]==0){
                firstColHasZero=true;
            }
            for(int j=1;j<col;j++){
                if(mat[i][j]==0){
                    mat[i][0]=0;
                    mat[0][j]=0;
                }
            }
        }
        //Step2:Handle inner matrix using indicators
        for(int i=1;i<row;i++){
            for(int j=1;j<col;j++){
                if(mat[i][0]==0||mat[0][j]==0){
                    mat[i][j]=0;
                }
            }
        }
        //Step3:Handle first row
        if(mat[0][0]==0){
            for(int j=0;j<col;j++){
                mat[0][j]=0;
            }
        }
        //Step4:Handle first column
        if(firstColHasZero){
            for(int i=0;i<row;i++){
                mat[i][0]=0;
            }
        }
    }
}
```

#### Solution 2 (Java)

- **Submitted:** 2026-10-16 11:31:29
- **Status:** Correct
- **Marks:** 4

```java
class Solution {
    public void setMatrixZeroes(int[][] mat) {
        // code here
        int row=mat.length;
        int col=mat[0].length;
        boolean firstColHasZero=false;
        //Step1:Mark indicators in first row and colmn
        for(int i=0;i<row;i++){
            if(mat[i][0]==0){
                firstColHasZero=true;
            }
            for(int j=1;j<col;j++){
                if(mat[i][j]==0){
                    mat[i][0]=0;
                    mat[0][j]=0;
                }
            }
        }
        //Step2:Handle inner matrix using indicators
        for(int i=1;i<row;i++){
            for(int j=1;j<col;j++){
                if(mat[i][0]==0||mat[0][j]==0){
                    mat[i][j]=0;
                }
            }
        }
        //Step3:Handle first row
        if(mat[0][0]==0){
            for(int j=0;j<col;j++){
                mat[0][j]=0;
            }
        }
        //Step4:Handle first column
        if(firstColHasZero){
            for(int i=0;i<row;i++){
                mat[i][0]=0;
            }
        }
    }
}
```

*Generated on: 10/16/2026, 12:16:37 PM*