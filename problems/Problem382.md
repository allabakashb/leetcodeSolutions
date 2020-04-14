```java

class Solution {

    List<Integer> list = new ArrayList<>();
    Random random = new Random();
    /** @param head The linked list's head.
        Note that the head is guaranteed to be not null, so it contains at least one node. */
    public Solution(ListNode head) {

        while (head != null) {
            
            list.add(head.val);
            head = head.next;
        }
    }
    
    /** Returns a random node's value. */
    public int getRandom() {
        
        return list.get(random.nextInt(list.size()));
    }
}

/*
 Time Complexity -
 Constructor - O(N)
 getRandom - O(1)*
 
 Space Complexity  - O(N)
 */
 

```
