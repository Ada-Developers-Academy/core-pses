# Calculate BST Height

## Given this problem prompt:

Given classes `Tree` and `TreeNode` which respectively represent a binary search tree and a node in a binary search tree, implement a function, `height`, determining the height of the tree. The height of the tree is the *maximum* depth from the root node to a leaf node.

The `height` function is a part of the `Tree` class and accepts one argument: `self`. This argument may be used to access the `root` of the binary search tree.

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

We want to return 3 here as that is the maximum amount of nodes from the root to any leaf in the tree.
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

We want to return 4 here as that is the maximum amount of nodes from the root to any leaf in the tree.
```

**Example 3:**

```
Input: 
            12 <-- root
Output: 1
Explanation: The root is the only node in the tree, and therefore is itself a leaf. So the height of the tree would be 1 in this nominal case.
```

Adapted from:  [GeeksForGeeks](https://www.geeksforgeeks.org/find-the-maximum-depth-or-height-of-a-tree/)


## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 5b8678ea-cbf2-45e3-824e-987dff657020
* title: Ask Clarifying Questions
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint

##### !explanation

Here are some example clarifying questions:

- What should I do if invalid input is passed in?
- What type of data will be stored in the values of the TreeNodes?
- Is the tree guaranteed to be balanced?

##### !end-explanation

##### !rubric

- The answer is wrong if there aren't at least 3 questions

##### !end-rubric

### !end-challenge
<!-- prettier-ignore-end -->


<!-- Question 2 -->
<!-- prettier-ignore-start -->

### !challenge
* type: code-snippet
* language: python3.6
* id: 20767bcf-d43f-46ec-a19d-4fa9b27a2f01
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `height` for the nominal and edge cases you identified in the first step.

*Note: Click the **Run Tests** button to save your tests for instructor feedback. No real tests are actually run again your unit tests.*

##### !end-question

##### !placeholder

```py
# example input 1:
# expected output 1:

# example input 2:
# expected output 2:

def test_nominal_case():
    # ^rename with meaningful test name
    # and complete test implementation below
    pass
    # arrange

    # act

    # assert

def test_edge_case():
    # ^rename with meaningful test name
    # and complete test implementation below
    pass
    
    # arrange
    
    # act
    
    # assert
```

##### !end-placeholder

##### !tests

```py
import unittest

class TestPython1(unittest.TestCase):
  def test_always_pass(self):
    self.assertEqual(1,1)
```

##### !end-tests

##### !explanation 

Example tests:

```python
def test_two_nominal_case():
    # nominal test case
    # Arrange
    root = TreeNode(12)
    root.left = TreeNode(5)
    root.right = TreeNode(17)

    # Act
    result = height(root)

    # Assert
    assert result == 2

def test_empty_tree():
    # edge test case
    # Arrange
    root = None

    # Act
    result = height(root)

    # Assert
    assert result == 0
```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 68012502-30a7-46fe-bf96-c9a346cb5632
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `height` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for a recursive, O(n) solution:

1. Create helper function (this will have one argument, which is the current node whose height we are calculating)
1. In helper function, deal with the edge case of a node that is None (height is 0)
1. In helper function, return `1 + max(helper(current_node.left), helper(current_node.right))`
1. In main height function, deal with edge case of root node being None
1. In main height function, call helper function with the root.

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
