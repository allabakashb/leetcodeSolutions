```java

//Recursive Solution
class Solution {
    public List<Integer> postorderTraversal(TreeNode root) {
        
        List<Integer> nodes = new LinkedList<>();
        
        postOrder(root, nodes);
        
        return nodes;
    }
    
    public void postOrder(TreeNode root, List<Integer> nodes) {
        
        if (root == null) return;
        
        postOrder(root.left, nodes);
        postOrder(root.right, nodes);
        nodes.add(root.val);
    }
}

Complexity - Time O(n) , Space O(n)

```
