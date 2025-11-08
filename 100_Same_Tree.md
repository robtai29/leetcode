#####  https://leetcode.com/problems/same-tree/
#####  11.27.24, 11.07.25 

<br>

 ```java
class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {
        if (p == null && q == null) {
            return true;
        }
        
        if (p == null || q== null){
            return false;
        }
        
        return p.val == q.val && isSameTree(p.left, q.left) && isSameTree(p.right, q.right);
    }
}
```

---

```java

class Solution {
    public boolean isSameTree(TreeNode p, TreeNode q) {

        Queue<TreeNode> queue = new LinkedList<>();
        queue.offer(p);
        queue.offer(q);
        while(!queue.isEmpty()){
            TreeNode a = queue.poll();
            TreeNode b = queue.poll();

            if (a == null && b == null){
                continue;
            }else if (a == null || b == null || a.val != b.val){
                return false;
            }

            queue.offer(a.left);
            queue.offer(b.left);
            queue.offer(a.right);
            queue.offer(b.right);
        }

        return true;
    }
}

```