```java

class Solution {
    public int longestCommonSubsequence(String text1, String text2) {
        
        int m = text1.length();
        int n = text2.length();
        
        int[][] dp = new int[m+1][n+1];
        
        char[] array1 = text1.toCharArray();
        char[] array2 = text2.toCharArray();
        
        int max = 0;
        for (int i = 1; i <= m; i++) {
            
            for (int j = 1; j <= n; j++) {
                
                if (array1[i-1] == array2[j-1]) {
                    
                   dp[i][j] = dp[i-1][j-1] + 1;
                    
                } else {
                    
                    dp[i][j] = Math.max(dp[i-1][j], dp[i][j-1]);
                }
                
                max = Math.max(max, dp[i][j]);
            }
        }
        
        return max;
    }
}

/*

Time Complexity = O(N^2)
Space Complexity = O(N^2)

*/

```
