```java

class Solution {
    public int findLUSlength(String[] strs) {
        
        boolean[] visited = new boolean[strs.length];        
        int maxLength  =  -1;
        for (int i = 0; i < strs.length; i++) {
                            
            if (!visited[i] && !isSubSeq(strs, i, visited)) {

                maxLength = Math.max(strs[i].length(), maxLength);
            }
        }

	     return maxLength;
    }
    
    public boolean isSubSeq(String[]strs, int index, boolean[] visited) {
        
        for (int i = 0; i < strs.length; i++) {
            
            if (i != index) {
                
                //length equal
                if (strs[i].length() == strs[index].length() 
                    && strs[i].equals(strs[index])) {
                    
                    visited[i] = true;
                    visited[index] = true;
                    return true;
                } else if (strs[i].length() > strs[index].length()) {
                    
                    int j = 0, k = 0;
                    
                    while (j < strs[i].length() && k < strs[index].length()) {
                        
                        if (strs[i].charAt(j) == strs[index].charAt(k)) {
                            
                            ++k;
                        }
                        ++j;
                    }
                    
                    if (k == strs[index].length()) return true;
                }
                
            }
        }
        
        return false;
    }
    
    
    /*
    
    Time Complexity = O(n ^ 2) * m
    Space Complexity = O(n)
    
    m - Max length of string in the Array
    
    */
}

```
