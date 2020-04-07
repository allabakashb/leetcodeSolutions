```java

class Solution {
    public int rangeSumBST(TreeNode root, int L, int R) {
        
        if (root == null) return 0;
        
        int sum = 0;
        
        if (root.val >= L && root.val <= R) {
            
            sum = root.val;
        }
        
        if (L < root.val) {
            
           sum += rangeSumBST(root.left, L, R);
        }
        
        if (R > root.val) {
            
            sum += rangeSumBST(root.right, L, R);
        }
        
        return sum;
    }
}

/*

Time Complexity - O(N)
Space Complexity - O(H) - height of the tree

*/


```
