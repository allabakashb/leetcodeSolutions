```java


class Solution {
    public Node flatten(Node head) {
        
        Node refHead = head; 
        
        while (refHead != null) { 
            
            Node next = refHead.next; 
            
            Node child = flatten(refHead.child); 
            
            Node childRef = child;
            while (child != null && child.next != null) {
                
                child = child.next;
            }
            
            if (childRef != null) {
                refHead.child = null;
                refHead.next = childRef;
                childRef.prev = refHead;
                
                child.next = next;
                if (next != null) {
                
                    next.prev = child;
                }
            }
                        
            refHead = next;
        }
        
        return head;
    }
}

/*

TimeComplexity - O(N) - number of nodes
SpaceComplxity - O(N) - number of levels
*/
```
