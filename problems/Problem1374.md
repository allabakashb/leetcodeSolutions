```java


class Solution {
    public String generateTheString(int n) {
        
        StringBuilder sb = new StringBuilder();
        
        int i = 0;
        
        while (i < n-1) {
            
            sb.append('a');
            ++i;
        }
        
        if (n % 2 == 0) {
            
            sb.append('c');
        } else {
            
            sb.append('a');
        }
                
        return sb.toString();
    }
}


/*

Time Complexity = O(n)
Space Complexity = O(1)


*/

```
