```java

class CustomStack {

    private int size = 0;
    private int[] stack;
    
    public CustomStack(int maxSize) {
        
        stack = new int[maxSize];
    }
    
    public void push(int x) {
        
        if (size < stack.length) {
            
            stack[size++] = x;
        }
    }
    
    public int pop() {
        
        if (size == 0) return -1;
        
        return stack[--size];
    }
    
    public void increment(int k, int val) {
        
        k = Math.min(k, size);
        for (int i = 0; i < k; i++) {
                
            stack[i] += val;
        }
    }
}

/*

Time Complexity

push - O(1)
pop - O(1)
increment - O(k)

*/
 
```
