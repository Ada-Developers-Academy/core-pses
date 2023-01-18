# Instructor: BST Height

## Recursive Solution - O(n)

```py
def height_helper(self, current_node):
        if not current_node:
            return 0

        return max(self.height_helper(current_node.left), self.height_helper(current_node.right)) + 1
    
def height(self):
    return self.height_helper(self.root)
```

## Iterative Solution - O(n)

```py
from collections import deque
def height(self):
    if self.root is None:
        return 0

    q = deque()
    q.append(self.root)
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