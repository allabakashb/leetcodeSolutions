```java

class Solution {
    public boolean canMeasureWater(int x, int y, int z) {
        
        if (x < y) return canMeasureWater(y, x, z);

        if (z==0) return true;
                                
        if ((x + y) < z || (x % 2 == 0 && y % 2 == 0 && z % 2 != 0)) return false;
        
        if (x+y == z || x-y == z || z%x == 0 || z%y == 0) return true;
                     
        return z % gcd(x,y) == 0;
    }
    
    private int gcd(int a, int b) {
        
        if (b == 0) return a;
        
        return gcd(b, a%b);
    }
}

/*

Time Complexity = O(logN)
Space Complexity = O(1)

*/


```
