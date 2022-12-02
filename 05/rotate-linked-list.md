# Rotate Linked List

## Problem

Imagine working on software that processes linked lists. Create a function named `rotate_list` that accepts a linked list and rotates it `k` places to the right. This function should take in the head of a linked list which has at least two nodes and a non-negative integer `k`. The function should return the head of the rotated list.

| List                  | k            | Output                            |
| --------------------- | ------------ | --------------------------------- |
| a -> b -> c -> d -> e | 1            | e -> a -> b -> c -> d
| a -> b -> c -> d -> e | 2            | d -> e -> a -> b -> c             |
| 1 -> 2                | 5            | 2 -> 1                            |

Sourced from: [Leetcode](https://leetcode.com/problems/rotate-list/)

## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 2346cae7-8f10-43ba-8f17-fbfa6009109a
* title: Ask Clarifying Questions
* points: 3
* topics: pse
##### !question

List three or more questions whose answers would clarify the problem statement.

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation

Here are some example clarifying questions:

- What should I return if `k` is zero?
- Can there be cycles in the input linked list?
- Can I modify the original list?

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
* id: b3b4910e-f4ed-4055-8135-de6fb7e3c1ef
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `rotate_list` for the nominal and edge cases you identified in the first step.

*Note: The `==` operator for the `Node` class has been defined such that comparing the head nodes of two linked lists using this operator will check that the two lists are equal.*

*Note: Click the **Run Tests** button to save your tests for instructor feedback. No real tests are actually run again your unit tests.*

##### !end-question
##### !placeholder

```py
# DO NOT MODIFY THE NODE CLASS
class Node:
    def __init__(self, value, next=None):
        self.value = value 
        # if next is None, this is the last element in the list
        self.next = next

    def __eq__(self, other):
        '''
        Understanding this function is NOT necessary for solving the problem;
        it is only used for the assertions.
        Feel free to explore your curiosity of how this works after the interview :)
        '''
        try:
            return (type(other) == Node and 
                    self.value == other.value and 
                    self.next == other.next)
        except RecursionError:
            raise Exception("Linked list has a cycle or is too large")

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

##### !hint

Unsure how to define a linked list?

We can define the linked list `a -> b -> c -> d -> e` as follows:

```py
# initialize nodes
a = Node('a')
b = Node('b')
c = Node('c')
d = Node('d')
e = Node('e')

# link the nodes together
a.next = b
b.next = c
c.next = d
d.next = e

# lst represents the head of the linked list, a
lst = a
```
We initialize a new instance of `Node` for each of our elements, passing in the appropriate values. We then set each node's `next` to the next node in the list.

Finally, instead of using a separate linked list class, we simply create a variable to represent our list `lst` and set it equal to our head node.  

We can represent the same list more concisely as follows:

```py
lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
```

The `lst` variable is set equal to a new `Node` instance with value `'a'`. For node `a`'s `next` parameter, we pass in a second `Node` instance with value `b` and so on. Notice that because node `e` is the tail of our list, we don't pass in an argument for the `next` parameter. Our `Node` constructor will by default set `e`'s `next` value to `None`. 

##### !end-hint

##### !explanation 

Example tests:

```python
def test_nominal_list():
    # nominal test case
    # Arrange
    lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
    expected = Node('d', Node('e', Node('a', Node('b', Node('c')))))

    # Act
    result = rotate_list(lst, 2)

    # Assert
    assert result == expected

def test_k_is_zero():
    # edge test case
    lst = Node('a', Node('b', Node('c', Node('d', Node('e')))))
    expected = Node('a', Node('b', Node('c', Node('d', Node('e')))))

    # Act
    result = rotate_list(lst, 0)

    # Assert
    assert result == expected


def test_k_longer_than_list_length():
    # alternative test case
    # Arrange
    lst = Node(55, Node(8, Node(2, Node(99))))
    expected = Node(2, Node(99, Node(55, Node(8))))

    # Act
    result = roate_list(lst, 6)

    # Assert
    assert result == expected

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->
<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 43573075-b3a5-40f2-adf0-418c4e930af6
* title: Create Logical Steps
* points: 3
* topics: pse
##### !question

Without writing code, describe how you would implement `rotate_list` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example steps for an O(nk) solution:

1. Determine the length of the list
   1. Set `length` to 1 and `current` to head of the list.
   2. Loop through list until the end
      1. Set `current` to next node in the list
      2. Increment length

2. If the requested rotation `k` is greater than length of list
   1. Truncate by finding remainder of length / k
3. If k is zero or multiple of length of list
   1. return `head`
4. Loop k times:
   1. Find tail of the list
      1. Set `current` to `head`
      2. Loop through list until find the second to last node
      3. Store `tail` as last node in the list
      4. Update second to last node's `next` to `None` to make it new tail
      5. Set `tail` as new `head` of list
5. Return `head`

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->

