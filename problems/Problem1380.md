```java

class Solution {
    public List<Integer> luckyNumbers (int[][] matrix) {
        
        List<Integer> list = new ArrayList<>();
        
        for (int i = 0; i < matrix.length; i++) {
            
            int smallest = Integer.MAX_VALUE, index = 0;
            
            for (int j = 0; j < matrix[0].length; j++) {
                
                if (smallest > matrix[i][j]) {
                    
                    smallest = matrix[i][j];
                    index = j;
                }
            }
            
            int biggest = 0;
            for (int k = 0; k < matrix.length; k++) {
                
                biggest = Math.max(matrix[k][index], biggest);
            }
            
            if (biggest == smallest) {
                
                list.add(biggest);
            }
        }
        
        return list;
    }
}


/*
Time Complexity - O(M*N)
Space Complexity - O(1) (not considering the output)
*/

```
