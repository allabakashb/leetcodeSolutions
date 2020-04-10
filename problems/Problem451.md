```java


class Solution {
    
    class Char {
        
        int index;
        int count = 0;
        
        Char(int index) {
            
            this.index = index;
        }
    }
    public String frequencySort(String s) {
        
        Char[] chars = new Char[128];
        
        for (int i = 0; i < 128; i++)  chars[i] = new Char(i);
        
        for (int i = 0; i < s.length(); i++) {
            
             ++chars[s.charAt(i)].count;
        }
        
        Arrays.sort(chars, (o1, o2)-> o2.count-o1.count);
        
        char[] result = new char[s.length()];
        int k = 0;
        for (int i = 0; i < 128; i++) {
            
            while (chars[i].count > 0) {
                
                result[k++] = (char) chars[i].index;
                
                --chars[i].count;
            }
        }
        
        return new String(result);
    }
}


/*

 Time Complexity - O(N)
 Space Complexity - O(N) - output size

*/

```
