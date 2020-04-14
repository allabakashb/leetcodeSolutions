```java

class Solution {
    public String shiftingLetters(String S, int[] shifts) {
        
        for (int i = shifts.length-2; i >= 0; i--) {
            
            shifts[i] += (shifts[i+1] % 26);
        }
                
        char[] array = S.toCharArray();
        
        for (int i = 0; i < array.length; i++) {
            
            int next = 'a' + (array[i] - 'a' + shifts[i]) % 26;

            array[i] = (char) next;
        }
        
        return new String(array);
    }
}

/*

Time Complexity - O(N)
Space Complexity - O(1)

*/

```
