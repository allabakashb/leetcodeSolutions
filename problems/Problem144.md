```
class Solution {
	
	//stack solution
    public List<Integer> preorderTraversal(TreeNode root) {
                
        List<Integer> preOrderList = new LinkedList<>();
        
        if (root == null) return preOrderList;
        
        Stack<TreeNode> stack = new Stack<>();

        stack.push(root);
        
        while (!stack.isEmpty()) {
            
            TreeNode node = stack.pop();
            preOrderList.add(node.val);
            
            if (node.right != null) {
                
                stack.push(node.right);
            }
            
            if (node.left != null) {
                
                stack.push(node.left);
            }
            
        }
        
        return preOrderList;
    }
}
```