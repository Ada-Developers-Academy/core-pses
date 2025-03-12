# Kth Missing Positive Number

## Problem Description

Given an array arr of positive integers sorted in a strictly increasing order, and an integer k.

Find the kth positive integer that is not present in the array.

**Example 1:**

```
Input: arr = [2,3,4,7,11], k = 5
Output: 9
Explanation: The missing positive integers are [1,5,6,8,9,10,12,13,...]. 
    The 5th missing positive integer is 9.
```

**Example 2:**

```
Input: arr = [1,2,3,4], k = 2
Output: 6
Explanation: The missing positive integers 
    are [5,6,7,...]. The 2nd missing
    positive integer is 6.
``` 

Sourced from:  [Leetcode](https://leetcode.com/problems/kth-missing-positive-number/)


## Prompts

<!-- Question 1 -->
<!-- prettier-ignore-start -->
### !challenge

* type: paragraph
* id: d0bbf25f-3aa8-4849-9d6e-fa5112ebe2cc
* title: Ask Clarifying Questions
* topics: pse

##### !question

List three or more questions whose answers would clarify the problem statement. For each question, provide an answer which includes the effect your decision would have on how you would approach the problem.

##### !end-question
##### !hint

Consider the following for inspiration:

- [About PSEs](../about-pses/about-pses.md)
- [Our example PSE with example answers](../about-pses/example-pse.md)
- Any past PSEs you may have

##### !end-hint
##### !explanation

Here are some example clarifying questions:

- How does the function handle empty lists?
- What if `k` is bigger than the length of the list?
- Can numbers in the input lists be zero?

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
* id: 1c95204d-d1c0-4e9a-b16a-5fdb3d91ba34
* title: Write Unit Tests
* topics: pse
##### !question

1. Use the comments provided to write at least two example input/outputs:
    * Consider at least one nominal and one edge case.
    * What is the expected output for the given input?
    * You can use the examples provided in the prompt, or other examples.
2. Write unit tests for `kth_missing_positive_number` for the nominal and edge cases you identified in the first step.

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
def test_nominal_list():
    # nominal test case
    # Arrange
    arr = [2,3,4,7,11]
    k = 5

    # Act
    result = kth_missing_positive_number(arr, k)

    # Assert
    assert result == 9

def test_empty_lists():
    # edge test case
    # Arrange
    arr = []
    k = 3

    # Act
    result = kth_missing_positive_number(arr, k)

    # Assert
    assert result == 3

```

##### !end-explanation
### !end-challenge
<!-- prettier-ignore-end -->

<!-- Question 3 -->
<!-- prettier-ignore-start -->
### !challenge
* type: paragraph
* id: 9deb4772-73ad-4f8f-ba65-ae645ed33a65
* title: Create Logical Steps
* topics: pse
##### !question

Without writing code, describe how you would implement `kth_missing_positive_number` in enough detail that someone else could write the code. 

* It may be helpful to break up the problem/algorithm into smaller subproblems/algorithms. For example, 1. Handle invalid input, 2. Given valid input, perform the computation/solve the problem/etc.
* Your logical steps could take the form of a numbered list, pseudo code, or anywhere in between. What's important at this stage is to think through and outline the implementation before writing code.

##### !end-question

##### !placeholder

Write the logical steps here.

##### !end-placeholder

### !explanation

Example Steps for an O(n) solution:

1. Check for valid input
2. If `k` is smaller than the first value in the input list `arr`, return `k`
3. Create a loop over the input `arr` that: 
   * starts at the first element of `arr` 
   * ends one element before the last element of `arr`
4. Inside the loop:
    1. Check if there are numbers missing between the current element and the next element in `arr`. Store the difference between the next element and the current element of `arr` in a new variable `missing_count`.
    2. if `k` is less than or equal to `missing_count`, return the value of `arr` at `index` plus `k` 
    3. Update the variable `k` by subtracting `missing_count`
5. If the loop ends, return the last element of the list plus the remaining value of `k`.

### !end-explanation

### !end-challenge
<!-- prettier-ignore-end -->
