```java

class Solution {
    public String sortString(String s) {
        
        int[] chars = new int[26];
        
        for (int i = 0; i < s.length(); i++) {
            
            chars[s.charAt(i)-'a']++;
        }
        
        StringBuilder sb = new StringBuilder();
        
        boolean done = false;
        while(!done) {
            boolean found = false;
            for (int i = 0; i < chars.length; i++) {
                
                if (chars[i] > 0) {
                    
                    sb.append((char)(i+'a'));
                    --chars[i];
                    found = true;
                }
            }
            
            if (!found) break;
            
            for (int i = chars.length-1; i >= 0; i--) {
                
                if (chars[i] > 0) {
                    
                    sb.append((char)(i+'a'));
                    --chars[i];
                    found = true;
                }
            }
            
            if (!found) break;
        }
        
        return sb.toString();
    }
}

/*

Time Complexity - O(N)
Space Complexity - O(1)

*/

```
