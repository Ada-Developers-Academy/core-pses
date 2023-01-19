# Implement Height of Binary Search Tree

## Problem

Given class `TreeNode` which represents a node in a binary search tree, implement a function, `height`, determining the height of the tree with the given `root` node. The height of the tree is the *maximum* depth from the root node to a leaf node.

The `height` function accepts one argument: `root`, which is the root of the tree of which we would like to calculate the height.

Calculate and return the *height* of the binary search tree.

**Example 1:**

```
Input: 

                10   <-- root
               /  \
              2    32
            /  \     
           1    5

Output: 3
Explanation: The maximum amount of nodes from the root to a leaf is 3 nodes (including the root).

The path from 10 -> 32 contains 2 nodes.
The path from 10 -> 2 -> 1 contains 3 nodes.
The path from 10 -> 2 -> 5 also contains 3 nodes.

The function should return 3 as that is the maximum amount of nodes from the root to any leaf in the tree.
```

**Example 2:**

```
Input:
             22  <--- root
           /    \
          /      \
         10       43
       /   \    /   \
      6    12  38     55
     / \      
    3   8    

Output: 4
Explanation: The maximum amount of nodes from the root to a leaf is 4 nodes (including the root).

The path from 22 -> 10 -> 6 -> 3 contains 4 nodes.
The path from 22 -> 10 -> 6 -> 8 contains 4 nodes.
The path from 22 -> 10 -> 12 contains 3 nodes.
The path from 22 -> 43 -> 38 contains 3 nodes.
The path from 22 -> 43 -> 55 contains 3 nodes.

The function should return 4 as that is the maximum amount of nodes from the root to any leaf in the tree.
```

**Example 3:**

```
Input: 
            12 <-- root
Output: 1
Explanation: The root is the only node in the tree, and therefore is itself a leaf. So the height of the tree would be 1.
```

Adapted from:  [GeeksForGeeks](https://www.geeksforgeeks.org/find-the-maximum-depth-or-height-of-a-tree/)

### !challenge

* type: code-snippet
* language: python3.6
* id: a292383f-196c-4e98-91ff-6ce22059bcb1
* title: BST Height Coding Challenge
* points: 3
* topics: python, bst, traversals

##### !question

Write a solution to the BST Height function below.

##### !end-question

##### !placeholder

```py
class TreeNode:
    def __init__(self, key, val = None):
        if val == None:
            val = key

        self.key = key
        self.value = val
        self.left = None
        self.right = None
    
def height(root):
    pass

```

##### !end-placeholder

##### !tests

```py
import unittest
from main import *

class Tree:
    def __init__(self):
        self.root = None

class TreeExtended(Tree):

    def add_helper(self, current_node, new_node):
        if new_node.key  < current_node.key:
            if not current_node.left:
                current_node.left = new_node
                return
            self.add_helper(current_node.left, new_node)
        else:
            if not current_node.right:
                current_node.right = new_node
                return
            self.add_helper(current_node.right, new_node)

    def add(self, key, value = None):
        if not self.root:
            self.root = TreeNode(key, value)
        else:
            new_node = TreeNode(key, value)
            self.add_helper(self.root, new_node)

class TestPython1(unittest.TestCase):
  def setUp(self) -> None:

    def tree_with_nodes() -> TreeExtended():
        t = TreeExtended()
        t.add(5, "Peter")
        t.add(3, "Paul")
        t.add(1, "Mary")
        t.add(10, "Karla")
        t.add(15, "Ada")
        t.add(25, "Kari")
        return t
    
    self.empty_tree = TreeExtended()
    self.tree_with_nodes = tree_with_nodes()
    
  def tearDown(self) -> None:
      self.empty_tree = TreeExtended()

  def test_height_of_empty_tree_is_zero(self):
    self.assertEqual(0, height(self.empty_tree))
  
  def test_height_of_one_node_tree_is_one(self):
    self.empty_tree.add(5, "Peter")

    self.assertEqual(1, height(self.empty_tree))

  def test_height_of_many_node_tree(self):
    self.assertEqual(4, height(self.tree_with_nodes))

    self.tree_with_nodes.add(2, "pasta")
    self.tree_with_nodes.add(2.5, "bread")
    self.assertEqual(5, height(self.tree_with_nodes))
```

##### !end-tests

##### !explanation

Our recursive solution:

```python
# recursive helper function that accepts the current node as an argument
def height_helper(current_node):
    # base case for our recursive function; checks if the current node is None
    if not current_node:
        # the function returns a height of 0 for a tree with 0 nodes
        return 0

    # our recursive calls
    # the first call recursively calculates the height for the left side of the tree
    # the second call recursively calculates the height of the right side of the tree
    # the max of these two calls is calculated by the max function
    # we then add 1 to whatever is returned from the max function, to account for our current node
    return max(height_helper(current_node.left), height_helper(current_node.right)) + 1
    
def height(root):
    return height_helper(root)
```

Our iterative solution:

```python
# this iterative solution uses a breadth first traversal
# of the tree, keeping track of how many levels of the tree
# which have been traversed.
def height(root):
    # import deque, which will be used to handle the queue
    from collections import deque

    # if the root is None, return a height of 0
    if root is None:
        return 0

    # initialize the queue
    q = deque()
    # append the root of the tree to the queue
    q.append(root)
    # counter for calculating the height
    height = 0

    # while the queue is not empty
    while q:
        # add one to the height 
        height += 1
        # keep count of the number of tree nodes on this level
        node_count = len(q)

        # loop through all of the nodes on this level, adding all of their children to the queue
        for _ in range(node_count):
            # pop off the next node in the queue
            current = q.popleft()
            # if it has a left child, add the left child to the queue
            if current.left:
                q.append(current.left)
            # if it has a right child, add the right child to the queue
            if current.right:
                q.append(current.right)
    
    # return the height of the tree
    return height
```

##### !end-explanation

### !end-challenge

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: paragraph
* id: ed25526f-88eb-4b45-aa4e-b340dba3d367
* title: What is the time complexity of your solution?
* points: 1
* topics: Big-O, python

##### !question

What is the time complexity of your solution? Explain. Define your variable(s).

*Note: The tree may be unbalanced.*

##### !end-question

##### !placeholder

Time Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

<!-- >>>>>>>>>>>>>>>>>>>>>> BEGIN CHALLENGE >>>>>>>>>>>>>>>>>>>>>> -->

### !challenge

* type: paragraph
* id: fda55052-b2c2-401d-b870-39d7080042dc
* title: What is the space complexity of your solution?
* points: 1
* topics: Big-O, python

##### !question

What is the space complexity of your answer? Explain. Define your variable(s).

*Note: The tree may be unbalanced*

##### !end-question

##### !placeholder

Space Complexity?

##### !end-placeholder

##### !answer

/.+/

##### !end-answer

### !end-challenge

<!-- ======================= END CHALLENGE ======================= -->

## Reminders

- Finish this assignment individually.
- If you'd like a full list of our tips, hints, and notes, please bring up the document "[About Problem Solving Exercises](../about-pses/about-pses.md )" in unit.
