# Instructor: BST Height

Please note the tree is not guaranteed to be balanced; the space complexity for a solution may be affected.

## Recursive Solution - O(n) time, O(n) space

```py
def height_helper(current_node):
        if not current_node:
            return 0

        return max(height_helper(current_node.left), height_helper(current_node.right)) + 1
    
def height(root):
    return height_helper(root)
```

## Iterative Solution - O(n) time, O(w) space (where w is the # of nodes in the widest level in the tree)

```py
def height(root):
    from collections import deque
    if root is None:
        return 0

    q = deque()
    q.append(root)
    height = 0

    while q:
        height += 1
        node_count = len(q)

        for _ in range(node_count):
            current = q.popleft()
            if current.left:
                q.append(current.left)
            if current.right:
                q.append(current.right)
        
    return height
```